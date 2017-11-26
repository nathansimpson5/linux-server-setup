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
  - create 'grader' user and give sudo privilege
  - update and upgrade all packages using apt-get
  - change ssh port to 2200
    - update Lightsail AND ufw rules
  - change timezone to UTC
  - give grader ssh key access
  - disable root ssh login
  - clone catalog app from github
  - create .wsgi file
  - update client_secrets.json and paths in python files
  - create catalog user in postgresql
  - make sure catalog is live and functioning on 18.217.78.14
  
Third-party resources:
  - Udacity forums
  - stackoverflow
  - various software documentation
  - digital ocean tutorials
