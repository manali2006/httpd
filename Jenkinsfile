pipeline {
agent {
label {
label "built-in"
customWorkspace "/mnt/wsp-2/"
}
}
stages {
stage ("delete") {
steps {
sh "rm -rf /mnt/wsp-2/httpd"
}
}
stage ("git-clone") {
steps {
sh "git clone https://github.com/manali2006/httpd.git"
}
}
stage ("httpd") {
steps {
sh "yum install httpd -y"
sh "service httpd start"
}
}
stage ("deploy") {
steps {
sh "cp -r /mnt/wsp-2/httpd/index.html /var/www/html"
sh "chmod -R 777 /var/www/html/index.html"
}
}
}
}

