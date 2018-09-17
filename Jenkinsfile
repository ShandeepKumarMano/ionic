pipeline {

	agent any

	environment {
		PATH = 'C:\Program Files\nodejs\node.exe'
	}

	stages {

		stage('NPM Setup') {
			steps {
				bat 'npm install'
			}
		}

		stage('IOS Build') {
			steps {
				bat 'ionic cordova build ios --release'

			}
		}

		stage('Android Build') {
			steps {
				bat 'ionic cordova build android --release'

			}
		}

		stage('APK Sign') {
			steps {
				// sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
				echo "Android"
			}
		}

		stage('Stage Web Build') {
			steps {
				bat 'npm run build --prod'
			}
		}

		stage('Publish Firebase Web') {
			steps {
				//sh 'firebase deploy --token "YourTokenKey"'
				echo 'Firebase Deploy'
			}
		}

		stage('Publish iOS') {
			steps {
				echo "Publish iOS"
			}
		}

		stage('Publish Android') {
			steps {
				echo "Publish Android"
			}
		}

	}
}