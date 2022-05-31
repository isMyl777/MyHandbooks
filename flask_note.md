```python
from flask import  Flask
from flask import  request,redirect

app = Flask(__name__)
@app.route('/sb')
def hello_world():
    return 'hello world'

@app.route('/hi/<username>')
def hi_user(username):
    return "hi %s" % username


@app.route('/number/<int:number>')
def is_number(number):
    return "number is %s" % number

@app.route('/baidu')
def new_page():
    return redirect("http://www.baidu.com")

def get_profile(user_id):
    user = User.query.get(user_id)
    resp_dict = dict(re_code =200, msg = 'ok', data = user.to_dict())

app.run()
```
