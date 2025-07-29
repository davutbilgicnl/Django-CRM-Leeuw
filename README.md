# Django-CRM

============

Django CRM is opensource CRM developed on django framework. It has all
the basic features of CRM to start with. We welcome code contributions
and feature requests via github.

This is divided into three parts
1. Backend API [Django CRM](https://github.com/MicroPyramid/Django-CRM)
2. Frontend UI [React CRM](https://github.com/MicroPyramid/react-crm "React CRM")
3. Mobile app [Flutter CRM]("https://github.com/MicroPyramid/flutter-crm")

## Runcode 

 Runcode is online developer workspace. It is cloud based simple, secure and ready to code workspaces, assuring high performance & fully configurable coding environment. With runcode you can run django-crm(API) with one-click.


- Open below link to create django-crm workspace on [RunCode](https://runcode.io/ "RunCode"). It will cretae django-crm API

    [![RunCode](https://runcode-app-public.s3.amazonaws.com/images/dark_btn.png)](https://runcode.io)

- After running API, Go to Frontend UI [React CRM](https://github.com/MicroPyramid/react-crm "React CRM") project to cretae new workpsace with runcode.

## Docs

Please [Click Here](http://django-crm.readthedocs.io "Click Here") for latest documentation.

## Project Modules
This project contains the following modules:
- Contacts
- Companies
- Leads
- Accounts
- Invoices (todo)
- Cases (todo)
- Opportunity (todo)

## Try for free [here](https://bottlecrm.io/)

## Installation Guide

We recommend ubuntu 20.04. These instructions are verified for ubuntu 20.04.

#### To install system requirments

```
sudo apt update && sudo apt upgrade -y

sudo apt install python-is-python3 xvfb libfontconfig wkhtmltopdf python3-dev python3-pip build-essential libssl-dev libffi-dev python3-venv redis-server redis-tools virtualenv -y
```

#### Install dependencies

##### Optional (based on personal choice)

```
sudo apt update && sudo apt upgrade -y && sudo apt install zsh python3-virtualenv

sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

pip install virtualenvwrapper

echo "source /home/ubuntu/.local/bin/virtualenvwrapper.sh" >> ~/.zshrc
```

If you want to install postgres, follow https://www.postgresql.org/download/
#### To modify postgresql root password

```
sudo -u postgres psql
ALTER USER postgres WITH PASSWORD 'root';
```

#### Create and activate a virtual environment.
if you installed and configured virtualenv wrapper then use the following
``` 
mkvirtualenv <env_name>
workon <env_name>
```
or else
```
virtualenv venv
source venv/bin/activate
```
Install the project's dependency after activating env

```
pip install -r requirements.txt
```

### Env variables

* Then refer to `env.md` for environment variables and keep those in the `.env` file in the current folder as your project is in.


### Docker / docker-compose
in order to use docker, please run the next commands after cloning repo:
```
docker build -t djcrm:1 -f docker/Dockerfile .
docker-compose -f docker/docker-compose.yml up
```

**Note**: you must have docker/docker-compose installed on your host. 
### next steps


```
python manage.py migrate
python manage.py runserver
```
- Then open http://localhost:8000/swagger/ in your borwser to explore API.

- After running API, Go to Frontend UI [React CRM](https://github.com/MicroPyramid/react-crm "React CRM") project to configure Fronted UI to interact with API.


## Start celery worker in another terminal window

celery -A crm worker --loglevel=INFO

### Useful tools and packages

```
pipdeptree # to see pip dependancy tree
black # to format code to meet python coding standards
pip-check -H  # to see upgradable packages
isort # to sort imports in python
```

### Community

Get help or stay up to date.

-   [Issues](<https://github.com/MicroPyramid/Django-CRM/issues>)
-   Follow [@micropyramid](<https://twitter.com/micropyramid>) on Twitter
-   Ask questions on [Stack Overflow](<https://stackoverflow.com/questions/tagged/django-crm>)
-   Chat with community [Gitter](<https://gitter.im/MicroPyramid/Django-CRM>)
-   For customisations, email to <django-crm@micropyramid.com>

## Credits

### Contributors

This project exists thanks to all the people who contribute!

![image](https://opencollective.com/django-crm/contributors.svg?width=890&button=false)

### Feature requests and bug reports

We welcome your feedback and support, raise github issue if you want to
report a bug or request new feature. we are glad to help.

For commercial support [Contact us](https://micropyramid.com/contact-us/)

# Trigger deploy

# Update Readme door Back-end Team
Back-end opstellen:
### 1- install Docker desktop en zorg voor dat de versie van python is: 3.11.0 
-----------------------------------------------------------------------------------
### 2- install PostgreSQL
-----------------------------------------------------------------------------------
### 3- maak een nieuwe bestaand .env in de project route, met de inhoud:
###### Django Ayarları
SECRET_KEY=mco934$@)NHUYTC%6789
ENV_TYPE=dev
DOMAIN_NAME=localhost
 
###### Veritabanı Ayarları (PostgreSQL örneği)
DBNAME=bottlecrm
DBUSER=postgres
DBPASSWORD=root
DBHOST=db
DBPORT=5432
 
###### Celery / Redis
CELERY_BROKER_URL=redis://redis:6379/0
CELERY_RESULT_BACKEND=redis://redis:6379/0
 
###### Swagger
SWAGGER_ROOT_URL=http://localhost:8000/
 
###### Cache
MEMCACHELOCATION=memcached:11211
 
###### AWS (prod için boş)
AWS_BUCKET_NAME=mybucket
AWS_ACCESS_KEY_ID=your-access-key-id
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_SES_REGION_NAME=eu-west-1
AWS_SES_REGION_ENDPOINT=email.eu-west-1.amazonaws.com
 
###### Sentry
SENTRY_DSN=
 
###### Email
DEFAULT_FROM_EMAIL=no-reply@localhost
ADMIN_EMAIL=admin@localhost
APP_NAME=DjangoCRM
-------------------------------------------------------------------------------------
 
### 4- update requirements.txt met deze inhoud: 
aiofiles==24.1.0
amqp==5.3.1
annotated-types==0.7.0
anyascii==0.3.3
anyio==4.5.0
arrow==1.3.0
asgiref==3.9.1
attrs==25.3.0
bcrypt==4.3.0
beautifulsoup4==4.13.4
billiard==4.2.1
boto3==1.39.4
botocore==1.39.4
celery==5.5.3
certifi==2025.7.9
cffi==1.17.1
charset-normalizer==3.4.2
click==8.2.1
click-didyoumean==0.3.1
click-plugins==1.1.1.2
click-repl==0.3.0
colorama==0.4.6
cryptography==45.0.5
defusedxml==0.7.1
Django==5.2.4
django-cors-headers==4.7.0
django-crum==0.7.9
django-extensions==4.1
django-filter==25.1
django-modelcluster==6.4
django-permissionedforms==0.1
django-phonenumber-field==8.1.0
django-ses==4.4.0
django-stubs-ext==5.2.1
django-taggit==6.1.0
django-tasks==0.7.0
django-treebeard==4.7.1
djangorestframework==3.16.0
djangorestframework_simplejwt==5.5.0
draftjs_exporter==5.1.0
drf-rw-serializers==1.4.0
drf-spectacular==0.28.0
ecdsa==0.19.1
et_xmlfile==2.0.0
fastapi==0.116.0
filetype==1.2.0
greenlet==3.2.3
h11==0.16.0
httpcore==1.0.9
httpx==0.28.1
idna==3.10
inflection==0.5.1
iniconfig==2.1.0
jmespath==1.0.1
jsonschema==4.24.0
jsonschema-specifications==2025.4.1
kombu==5.5.4
laces==0.1.2
openpyxl==3.1.5
packaging==25.0
passlib==1.7.4
phonenumbers==9.0.9
pillow==11.3.0
pillow_heif==0.21.0
pluggy==1.6.0
prompt_toolkit==3.0.51
psycopg2-binary==2.9.10
pyasn1==0.6.1
pycparser==2.22
pydantic==2.11.7
pydantic_core==2.33.2
Pygments==2.19.2
PyJWT==2.9.0
pytest==8.4.1
python-dateutil==2.9.0.post0
python-dotenv==1.1.1
python-jose==3.5.0
python-multipart==0.0.20
pytz==2025.2
PyYAML==6.0.2
referencing==0.36.2
requests==2.32.4
rpds-py==0.26.0
rsa==4.9.1
s3transfer==0.13.0
sentry-sdk==2.32.0
setuptools==80.9.0
six==1.17.0
sniffio==1.3.1
soupsieve==2.7
SQLAlchemy==2.0.41
sqlparse==0.5.3
starlette==0.46.2
telepath==0.3.1
types-python-dateutil==2.9.0.20250708
typing-inspection==0.4.1
typing_extensions==4.14.1
tzdata==2025.2
uritemplate==4.2.0
urllib3==2.5.0
uvicorn==0.35.0
vine==5.1.0
wagtail==7.0.1
wcwidth==0.2.13
websockets==15.0.1
whitenoise==6.6.0
Willow==1.10.0
-------------------------------------------------------------------------------------

### 5 -update Dockerfile :
 
FROM python:3.11-slim-buster
 
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        libpq-dev \
        default-libmysqlclient-dev \
        libjpeg62-turbo-dev \
        zlib1g-dev \
        libwebp-dev \
        curl \
        vim \
        net-tools && \
    apt-get clean && rm -rf /var/lib/apt/lists/*
 
WORKDIR /app
 
COPY . /app
 
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN pip install gunicorn
 
ENV PATH="/app/scripts:${PATH}"
 
EXPOSE 8000
 
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "crm.wsgi:application"]
-------------------------------------------------------------------------------------

### 6- Update docker-compose.yml
 
 
services:
  db:
    image: postgres:15
    env_file:
      - .env
    volumes:
      - pgdata:/var/lib/postgresql/data
    ports:
      - "5432:5432"
    environment:
      POSTGRES_DB: ${DBNAME}
      POSTGRES_USER: ${DBUSER}
      POSTGRES_PASSWORD: ${DBPASSWORD}
 
  web:
    build:
      context: .
      args:
        APP_NAME: django-crm
    env_file:
      - .env
    ports:
      - "8000:8000"
    depends_on:
      - db
    volumes:
      - .:/app
 
volumes:
  pgdata:
-------------------------------------------------------------------------------------

### 7- run op terminal de volgende commands:
pyhton -m pip install -r requirements.txt
docker-compose down
docker-compose build --no-cache
docker-compose up
 
 
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
-------------------------------------------------------------------------------------

### 8- op de broweser probeer deze url te gebruiken 
http://localhost:8000/
http://localhost:8000/admin/
http://127.0.0.1:8000/swagger-ui/

