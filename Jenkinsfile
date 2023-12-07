pipeline {
agent {
    label {
        label "slave-2"
        customWorkspace "/mnt/workspace"
         }
}
stages {
    stage ("httpd-install") {
        steps {
            sh "sudo yum install httpd -y"
            sh "sudo service httpd start"
        }
    }

    stage ("clone-repo") {
        steps {
            git branch: '2023q2', changelog: false, credentialsId: 'ssh-key', poll: false, url: 'https://github.com/Aprerana/aws.git'
    }
}

stage ("deploy index.html") {
    steps {
        sh " sudo chmod -R /var/www/html/"
        sh "cp index.html /var/www/html"
    }
}
}
}
