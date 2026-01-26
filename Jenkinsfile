pipeline{
	agent any
	
	stages{
		stage("Install"){
			steps{
				echo "installing"
				sh '''
				python3 --version
				python3 -m venv venv
				./venv/bin/pip install --upgrade pip	
				./venv/bin/pip install fastapi uvicorn httpx pytest

				'''
			}
		}
		stage("build"){
			steps{
				echo "building"
				sh '''
					./venv/bin/python -c "from app import app; print('Build Ok')"  
				'''
			}
		}
		stage("test"){
			steps{
				echo "testing"
				sh "./venv/bin/pytest"
			}
		}
		stage("linting"){
			steps{
				echo "linting"
			}
		}
		stage("artifcat"){
			steps{
				echo "artifacting"

			scripts{
				def version=""

				if(env.TAG_NAME){
					version="${env.TAG_NAME}"
				}
				else {
					version="${env.BUILD_NUMBER}"
				}
				archiveArtifacts artifacts="**/*.py-${version}", fingerprint:true
			}
		}
		stage("deploy"){
			steps{
				echo "deploying now"
			}
		}
		stage("Pushing"){
			steps{
				echo "pushing now"
			}
		}
	}
}
