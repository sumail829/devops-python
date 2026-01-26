pipeline{
	agent any
	
	stages{
		stage("Install")
			steps{
				echo "installing"
				sh '''
				sudo apt install python3-full python3-venv -y
				python3 -m venv venv
				source venv/bin/activate
				pip install -r fastapi uvicorn httpx pytest

				'''
			}
		}
		stage("build"){
			steps{
				echo "building"
				sh "uvicorn app:app --reload"
			}
		}
		stage("test"){
			steps{
				echo "testing"
				sh "pytest"
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
