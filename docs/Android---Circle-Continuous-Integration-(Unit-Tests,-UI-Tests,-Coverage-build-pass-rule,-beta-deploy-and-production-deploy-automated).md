
# Sumário 

[1. Introdução](#1-introdução)

[2. Circle CI](#2-circle-ci) 

[3. Script para checar se atingiu cobertura ](#3-Script-para-checar-se-atingiu-cobertura) 

[4. Gradle](#4-gradle) 

[5. Fastlane](#5-fastlane) 


***

# 1. Introdução

<p align="justify">Este documento descreve o plano de gerenciamento de configuração de mudanças e tem como objetivo deixar todos os integrantes do projeto por dentro de como ocorrerão as configurações de ambiente, as rotinas e padrões de nomenclatura realizadas durante as mudanças do mesmo.</p>

# 2. Circle CI
<p align="justify"><i>CircleCI</i> foi a ferramenta de integração contínua decidida por ser utilizada. Sua configuração é feita através de um arquivo <i>.yml</i> na pasta raiz do projeto.
As builds geradas pela ferramenta podem ser acessadas neste <a href="https://circleci.com/gh/fga-gpp-mds/2016.2-CidadeDemocratica/tree/master"><i>link</i></a>.</p>

```yml
#Install android build tools, platforms
#Supported versions here https://circleci.com/docs/android
machine:
  ruby:
    version: 2.3.0

dependencies:
  pre:
    - echo y | android update sdk --no-ui --all --filter tools,platform-tools,build-tools-23.0.3,android-23,extra-android-m2repository,extra-android-support,extra-google-google_play_services,extra-google-m2repository
    - gem install fastlane --verbose

  override:
    - ANDROID_HOME=/usr/local/android-sdk-linux ./gradlew dependencies

test:
  pre:
        # start the emulator
      - emulator -avd circleci-android22 -no-audio -no-window:
          background: true
          parallel: true
        # wait for it to have booted
      - circle-android wait-for-boot

  override:
    #run unit tests
    - ./gradlew test
    #run code coverage
    - ./gradlew jacocoTestReport
    # run tests  against the emulator.
    # - ./gradlew connectedCheck
    # copy the build outputs to artifacts
    - cp -r ./app/build/outputs $CIRCLE_ARTIFACTS/
    # copy the test results to the test results directory.
    - cp -r ./app/build/reports/* $CIRCLE_TEST_REPORTS/

    - sudo apt-get install dc

    - chmod +x ./CheckCoverageGoal.sh

    - ./CheckCoverageGoal.sh

  post:
    - bash <(curl -s https://codecov.io/bash)


deployment:
  production: 
    branch: production
    commands:
      - fastlane release

  beta:
    branch: beta
    commands:
      - fastlane beta
```
# 3. Script para checar se atingiu cobertura 
```shell
#!/bin/bash

coverageExpected="30.0"

# Get the coverage value from the coverage report
coverageResult=$(grep -oE '[0-9.]+%' ./app/build/reports/jacoco/jacocoTestFreeDebugUnitTestReport/html/index.html | head -n1)
coverageResult="${coverageResult//%}"

echo "Coverage expected $coverageExpected. Coverage Result $coverageResult "

# If the coverage requirements was satisfied
if ! echo "$coverageResult $coverageExpected -p" | dc | grep > /dev/null ^-; then
    echo "Coverage goal was satisfied"
		exit 0
	else
    echo "Error: Coverage goal was not satisfied"
		exit 1
fi

```

# 4. Gradle

 <p align="justify"><i>Task gradle</i> para configurar o identificador da versão do <i>apk</i> que será enviado e os certificados de cosntrucao do <i>.apk</i>. A versão está sendo identificada de acordo com a data atual para que sempre automaticamente ao criar um <i>apk</i> a versão atual seja maior que a antiga.</p>

```groovy 
apply plugin: 'com.android.application'
apply plugin: 'jacoco-android'

android {
    compileSdkVersion 23
    buildToolsVersion "23.0.3"

    //SETUP THE CERTIFICATE TO GENERATE A SIGNED .apk
    signingConfigs {
           release {
               storeFile file("release.jks")
               storePassword "123456"
               keyAlias "CidadeDemocratica"
               keyPassword "123456"
           }
    }

    //SETUP THE VERSION NAME WITH THE CURRENT DATE TIMESTAMP
    defaultConfig {
        applicationId "com.cidadedemocratica.android"
        minSdkVersion 16
        targetSdkVersion 23
        versionName "${getVersionNameTimestamp()}"
        versionCode getVersionCodeTimestamp()
        testApplicationId "com.cidadedemocratica.android.test"
        testInstrumentationRunner "com.cidadedemocratica.android.JUnitJacocoTestRunner"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
            signingConfig signingConfigs.release
        }
        debug {
            testCoverageEnabled true
        }
    }

    testOptions {
        unitTests.returnDefaultValues = true
    }

    productFlavors {
        free {}
    }

    jacocoAndroidUnitTestReport {
        excludes += ['**/External**/','**/ReportController**', '**/controller/**', '**/view/**']
    }
    configurations.all {
        resolutionStrategy.force 'com.android.support:support-annotations:23.1.0'
    }

}

dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])

    testCompile 'org.json:json:20140107'
    androidTestCompile 'junit:junit:4.12'
    androidTestCompile 'com.android.support.test.espresso:espresso-core:2.2.1'
    androidTestCompile ('com.android.support.test.espresso:espresso-contrib:2.2'){
        exclude module: 'support-annotations'
        exclude module: 'support-v4'
        exclude module: 'support-v13'
        exclude module: 'recyclerview-v7'
    }
    androidTestCompile 'com.android.support.test:runner:0.4.1'
    androidTestCompile 'com.android.support.test:rules:0.4.1'

    testCompile 'junit:junit:4.12'

    compile 'com.android.support:appcompat-v7:23.4.0'
    compile 'com.loopj.android:android-async-http:1.4.9'
    compile 'com.android.support:support-v4:23.4.0'
    compile 'com.google.firebase:firebase-messaging:9.8.0'
}

    //GET VERSION TIME STAMP
def getVersionNameTimestamp() {
    return new Date().format('yy.MM.ddHHmm')
}

def getVersionCodeTimestamp() {
    def date = new Date()
    def formattedDate = date.format('yyMMddHHmm')
    def code = formattedDate.toInteger()
    println sprintf("VersionCode: %d", code)
    return code
}

apply plugin: 'com.google.gms.google-services'

```

Antes de configurar a task, voce deve adiquirir o serviceAccountEmail e o jsonFile como descrito no 
[Tutorial de Deploy Automatico na Google Play PDF](https://github.com/GPP-MDS-2016/ImagensDaWiki/raw/master/tutorial_deploy_automático_google_play.pdf).

# 5. Fastlane

 <i>Fastfile</i> com a configuração do fastlane ferramenta para organizar <i>scripts</i> de automação em simples comandos:  
```ruby 
# Update this, if you use features of a newer version
fastlane_version "1.105.3"

default_platform :android

platform :android do
  before_all do
    # ENV["SLACK_URL"] = "https://hooks.slack.com/services/..."
  end

  desc "Runs all the tests"
  lane :test do
    gradle(task: "test")
  end

  desc "Submit a new Beta Build"
  lane :beta do
   gradle(task: 'clean')
   gradle(task: "assembleRelease")
   supply(track: "beta", apk: "app/build/outputs/apk/app-free-release.apk", json_key: "app/play-release.json", package_name: "com.cidadedemocratica.android")
   slack(message: 'Successfully distributed a new beta build', slack_url:"https://hooks.slack.com/services/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")
end

  desc "Deploy a new version to the Google Play"
  lane :deploy do
    gradle(task: 'clean')
    gradle(task: "assembleRelease")
    supply(apk: "app/build/outputs/apk/app-free-release.apk", json_key: "app/play-release.json", package_name: "com.cidadedemocratica.android")
    slack(slack_url: "https://hooks.slack.com/services/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", message: 'Successfully distributed a new build in Play Store')

  end
end
```


<p align="justify">Basicamente, o <i>CircleCI</i> gera a <i>build</i> do produto, executando os testes unitários e de aceitação, checa se atingiu o limite aceitável de cobertura de testes, comunica a ferramenta de cobertura de teste enviando a cobertura atual do <i>software</i>.</p>

<p align="justify">No caso das <i>branchs production</i> e <i>beta</i>, ao criar uma <i>branch</i> com o nome <i><b>production</b></i> ou com nome <i><b>beta</b></i>, ele também envia para <i>deploy</i> no respectivo contexto.</p>