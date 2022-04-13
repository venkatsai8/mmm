pipeline {
    agent {
        docker { image 'ubuntu:latest' 
                  args '-u root'
                }
    }
    stages {
        stage('Develop') {
            steps {
	     withCredentials([usernamePassword(credentials:'mor',
		passwordVariable:'password',usernameVariable:'username')]){
                sh '''

                apt-get update
		apt-get intall git -y
		git init
		git config --global user.name "venkatsai8"
		git config --global user.email "natrajsai7@gmail.com"
		echo "# sam" >> README.md
		git add README.md
		git commit -m "first commit"
		git branch -M master
		git remote set-url git@github.com:venkatsai8/mmm.git
		git push -u origin master
               '''
		}
            }
        }
     }
}
