**EducateMe web app**

Front-end:
1) _React (Redux)_
2) _react-router_
3) _axios_

Back-end:
1) _Django (REST)_

clone repository:
create folder and open terminal.
```
git init
git remote add origin "link of your repo fork (or use https://github.com/Sinkler521/educateme.git)"
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
```
backend .env (replace SMTP data according to your needs)
```
EMAIL_HOST=smtp.mailersend.net
EMAIL_HOST_USER=MS_Aj00FX@trial-7dnvo4d35e3g5r86.mlsender.net
EMAIL_HOST_PASSWORD=rXIq1dpYxIAfuXYW
EMAIL_PORT=587
ADMIN_EMAIL=Sinkler521@gmail.com
```

2) Run project: 

Docker: run ```docker-compose up```
command using terminal or command line from root folder

Without Docker:

open terminal in frontend folder.
```
npm install
npm run start
```
then open terminal in backend folder
```
pip install --no-cache-dir -r requirements.txt

python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser (to create admin account)

python manage.py runserver
```

in dev mode you can access webapp using http://localhost:3000 (or a port you use for frontend)
