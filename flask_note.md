# 路由
```python
from flask import  Flask,redirect

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
# flask 查看所有路由的方式
```text
命令行方式： flask routes
代码内部方式： print(app.url_map)
```
```python
@app.route('/route_rule')
def route_rule():
    '''
    route_rule 返回所有视图网址
    '''
    rules_iter = app.url_map.iter_rules()
    return json.dumps({rule.endpoint: rule.rule for rule in rules_iter})
```
# flask 请求方式
```text
GET
OPTIONS ---简化版的get请求，用于询问服务器接口信息
HEAD    ---简化版的get请求
只返回GET请求处理时的响应头，不返回响应体
自定 POST PUT DELETE PATCH
利用methods参数可以自己指定一个接口的请求方式
```
```PYTHON
@app.route('/baidu',methods = ['POST'])
def new_page():
    return redirect("http://www.baidu.com")
```
# 蓝图
```text
在flask中，使用蓝图来分模块组织管理
蓝图可以理解为是一个存储一组视图方法的容器对象
在一个应用初始化时，就应该要注册需要使用的Blueprint
```
```python
# 蓝图创建
user_bp = Blueprint('user',__name__)

@user_bp.route('/profile')
def get_profile():
    return 'user_profile'
# 注册蓝图
app.register_blueprint(user_bp)
from goods import  good_bp
app.register_blueprint(good_bp)
```
# 视图













