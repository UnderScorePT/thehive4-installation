# thehive4-installation
Installation step-by-step for TheHive4

STEP1 - sudo apt update -y && sudo apt upgrade -y

STEP2 - curl -fsSL https://www.apache.org/dist/cassandra/KEYS | sudo apt-key add -

STEP3 - echo "deb http://archive.apache.org/dist/cassandra/debian 311x main" | sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list

STEP4 - curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

STEP5 - echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list

STEP6 - curl https://raw.githubusercontent.com/TheHive-Project/TheHive/master/PGP-PUBLIC-KEY | sudo apt-key add -

STEP7 - echo 'deb https://deb.thehive-project.org release main' | sudo tee -a /etc/apt/sources.list.d/thehive-project.list

STEP8 - sudo apt update -y && sudo apt upgrade -y

STEP9 - sudo apt-get install -y openjdk-8-jre-headless -y

STEP10 - echo JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64" | sudo tee -a /etc/environment

STEP11 - export JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"

STEP12 - sudo apt install cassandra -y

STEP13 - cqlsh localhost 9042

STEP14 - UPDATE system.local SET cluster_name = 'thp' where key='local';

STEP15 - exit;

STEP16 - nodetool flush

STEP17 - sudo nano /etc/cassandra/cassandra.yaml

STEP18 - line 11 - cluster_name: 'thp'
