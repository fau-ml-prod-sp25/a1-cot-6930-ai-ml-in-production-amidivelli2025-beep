# Albumy

*Capture and share every wonderful moment.*

> Example application for *[Python Web Development with Flask](https://helloflask.com/en/book/1)* (《[Flask Web 开发实战](https://helloflask.com/book/1)》).

Demo: http://albumy.helloflask.com

![Screenshot](https://helloflask.com/screenshots/albumy.png)

## Installation

clone:
```
$ git clone https://github.com/greyli/albumy.gitc
$ cd albumy
```
create & activate virtual env then install dependency:

with venv/virtualenv + pip:
```
$ python -m venv env  # use `virtualenv env` for Python2, use `python3 ...` for Python3 on Linux & macOS
$ source env/bin/activate  # use `env\Scripts\activate` on Windows
$ pip install -r requirements.txt
```
database setup
```
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```
environment variables
```
FLASK_APP=albumy
FLASK_ENV=development
SECRET_KEY=your_secret_key_here
DATABASE_URL=sqlite:///data.db
MAIL_SERVER=smtp.example.com
MAIL_PORT=587
MAIL_USE_TLS=1
MAIL_USERNAME=your_email@example.com
MAIL_PASSWORD=your_email_password
```
important
```
Never commit your real secrets or API keys to GitHub.

If you’re using YOLOv8 with custom models, place your .pt weights in the project root and update main.py or utility.py:

yolo_model = YOLO("your_custom_model.pt")
```
run the falsk app
```
flask run
By default, the app runs at:
http://127.0.0.1:5000
```
Test account:
* email: `admin@helloflask.com`
* password: `helloflask`

## License

This project is licensed under the MIT License (see the
[LICENSE](LICENSE) file for details).
```
example usage
```
Register and log in.
Upload an image from the Upload page.
The app will:
Save the image
Run YOLOv8 detection
Store detected objects in the database
Show them in the photo description
```
dependencies
```
See requirements.txt
 for all dependencies.
Key additions:
Ultralytics
 (YOLOv8)
OpenCV (cv2)
Pillow (image processing)
```
notes
```
Works with Python 3.8+.
Default YOLO model: yolov8n.pt.
For better accuracy, replace with yolov8s.pt or a custom trained model.
---
## Updated `requirements.txt`

Since your current one does not include YOLO and OpenCV, add them:

```txt
blinker==1.4
bootstrap-flask==1.2.0
click==7.1.1
flask-avatars==0.2.2
flask-dropzone==1.5.4
flask-login==0.5.0
flask-mail==0.9.1
flask-moment==0.9.0
flask-sqlalchemy==2.4.1
flask-whooshee==0.7.0
flask-wtf==0.14.3
flask==1.1.2
itsdangerous==1.1.0
jinja2==2.11.1
markupsafe==1.1.1
pillow==7.1.1
python-dotenv==0.12.0
sqlalchemy==1.3.15
werkzeug==1.0.1
whoosh==2.7.4
wtforms==2.2.1

# Dev
faker==4.0.2
pathtools==0.1.2
python-dateutil==2.8.1
six==1.14.0
text-unidecode==1.3
watchdog==0.10.2

# Added for YOLO
ultralytics==8.0.196
opencv-python==4.10.0.84