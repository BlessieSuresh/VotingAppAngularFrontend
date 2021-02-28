#!/usr/bin/env groovy

node {
    environment { 
        CI = 'true'
    }

    stage('checkout') {
        checkout scm
    }

    stage('install tools') {
        if (isUnix()) {
            sh "npm install"
        } else {
            bat(/npm install/)
        }
    }

    stage('build') {
        if (isUnix()) {
            sh "npm run build"
        } else {
            bat(/npm run build/)
        }
    }

    //https://github.com/facebook/jest/issues/7441
    stage('Testing') {
        if (isUnix()) {
            sh "npm run test"
        } else {
            bat(/npm run test/)
        }
    }


}
