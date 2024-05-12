**EducateMe web app**

Front-end:
1) _React (Redux)_
2) _react-router_
3) _axios_

Back-end:
1) _Django (REST)_

Docker

clone repository:
create folder and open terminal.
```
git init
git remote add origin "link of your repo fork (or use https://github.com/Sinkler521/educateme.git as origin)"
git pull origin master

since backend and frontend folders should be submodules we have to init and update both:

git submodule update --init --recursive
```

**Launch:**
1) create .env files in frontend and backend folders.

frontend .env should contain:
```
REACT_APP_BACKEND_PORT=8000
REACT_APP_BACKEND_DOMAIN=http://127.0.0.1:

REACT_APP_BACKEND_HOST=${REACT_APP_BACKEND_DOMAIN}${REACT_APP_BACKEND_PORT}/

REACT_APP_BACKEND_AUTH=${REACT_APP_BACKEND_HOST}auth
REACT_APP_BACKEND_API=${REACT_APP_BACKEND_HOST}api

# THESE ONES can be changed using recaptcha v2
# https://www.google.com/recaptcha/about/
REACT_APP_CAPTCHA_KEY=6LdsIJwpAAAAAJWPQM3kba8OFydXDXMryCQIOK8i
REACT_APP_CAPTCHA_SECRET=6LdsIJwpAAAAALgAChivSeoREG74wVXq__V6V2vh

# another one api key but for youtube
# https://developers.google.com/youtube/v3/getting-started?hl=ru
REACT_APP_YOUTUBE_API_KEY=AIzaSyBiiAS9i56Zy6FNQlSR2GXeLX_B94qcNZA
```
backend .env (replace SMTP server data according to which one you'd like to use)
```
This example contains free service
https://www.mailersend.com/
EMAIL_HOST=smtp.mailersend.net
EMAIL_HOST_USER=MS_Aj00FX@trial-7dnvo4d35e3g5r86.mlsender.net
EMAIL_HOST_PASSWORD=rXIq1dpYxIAfuXYW
EMAIL_PORT=587
ADMIN_EMAIL=Sinkler521@gmail.com
```

2) Run project:
Open terminal from the root folder.

Docker:

_If you use Windows make sure you have Docker Desktop installed and launched_
```
# Linux: use sudo to run these commands as superuser
docker-compose build --no-cache
docker-compose up
```
command using terminal or command line from root folder

Without Docker:

open terminal in frontend folder.
```
npm install
npm run start
```
then open terminal in backend folder
```
# set up virtual environment 
python -m venv venv
venv\Scripts\activate

# install all the libraries required for backend
pip install --no-cache-dir -r requirements.txt

# use such django commands
python manage.py collectstatic --no-input
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser (to create admin account)

python manage.py runserver
```

in dev mode you can access webapp using http://localhost:3000 (or a port you use for frontend)
backend (django admin panel) can be used with http://localhost:8000/admin/ (or another port you defined instead of 8000). You can log in as superuser (you have created one using "python manage.py createsuperuser")