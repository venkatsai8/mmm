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
		#git remote add origin git@github.com:venkatsai8/sam.git
		#git remote set-url origin git@github.com:venkatsai8/mmm.git
		git remote set-url https://mor:${password}@github.com:venkatsai8/mmm.git
		git push -u origin master
               '''
		}
            }
        }
     }
}
