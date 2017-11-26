# linux-server-setup

ip address: 18.217.78.14

SSH port: 2200

url: http://18.217.78.14/sport/


software installed:
  - Ubuntu
  - Postgresql
  - python-pip
    - certifi (2017.11.5)
    - chardet (3.0.4)
    - click (6.7)
    - Flask (0.12.2)
    - httplib2 (0.10.3)
    - idna (2.6)
    - itsdangerous (0.24)
    - Jinja2 (2.10)
    - MarkupSafe (1.0)
    - oauth2client (4.1.2)
    - pip (9.0.1)
    - psycopg2 (2.7.3.2)
    - pyasn1 (0.4.2)
    - pyasn1-modules (0.2.1)
    - requests (2.18.4)
    - rsa (3.4.2)
    - setuptools (20.7.0)
    - six (1.11.0)
    - SQLAlchemy (1.1.15)
    - SQLAlchemy-Utils (0.32.21)
    - urllib3 (1.22)
    - virtualenv (15.1.0)
    - Werkzeug (0.12.2)
    - wheel (0.29.0)
  - Git
  - Apache
  - mod-wsgi
  
Process:
  1. create 'grader' user and give sudo privilege
    - sudo adduser grader
    - sudo nano /etc/sudoers.d/grader -> grader ALL=(ALL:ALL) ALL -> save -> exit
  2. update and upgrade all packages
    - sudo apt-get update
    - sudo apt-get upgrade
    - sudo apt-get dist-upgrade
  3. change ssh port to 2200 and configure ufw
    - sudo nano /etc/ssh/sshd_config -> change port number -> save -> exit
    - sudo ufw allow 2200/tcp
    - sudo ufw allow 80/tcp
    - sudo ufw allow 123/udp
    - sudo ufw enable
  4. change timezone to UTC
    - sudo dpkg-reconfigure tzdata
  5. give grader ssh key access
    - use ssh-keygen on local machine (not aws)
    - change to grader user on aws machine (su - grader)
    - mkdir .ssh
    - nano .ssh/authorized_keys
    - paste in the public key from your local machine -> save -> exit
    - chmod 700 .ssh
    - chmod 644 .ssh/authorized_keys
  6. disable root ssh login
    - sudo nano /etc/ssh/sshd_config
    - Change 'PermitRootLogin without-password' to 'PermitRootLogin no'
  7. clone catalog app from github
    - cd /var/www/
    - sudo mkdir catalog
    - sudo chown -R grader:grader catalog
    - cd catalog
    - git clone https://github.com/nathansimpson5/itemCatalog.git
    - mv application.py __init__.py
    - cd .. (current path should be /var/www/catalog)
  8. create .wsgi file
    - sudo nano catalog.wsgi -> follow flask instructions -> save -> exit
  9. update client_secrets.json and paths in python files
  10. create catalog user in postgresql
  11. make sure catalog is live and functioning on 18.217.78.14
  
Third-party resources:
  - Udacity forums
  - stackoverflow
  - various software documentation
  - digital ocean tutorials
