# Python-Crash-Course-Projects

## Alien_Game

总结：

1. 根据书本知识简单制作了一个射击外星人的游戏，主要学会了`pygame`库简单的使用，如添加图片，响应键盘和鼠标事件，检测元素间的碰撞等。
2. 学会把一些配置写在`settings.py`里面。
3. 学会重构，避免函数太长。
4. 学会宁愿向每个函数传递一个类（如生成一个Settings类）来获取其中的变量，也不要定义全局变量让多个函数去共享使用。

## Learning_log

总结：基于django来完成一个能记录文字的简单网页。

1. 创建虚拟环境
2. 编写Html时，可以创建一个父模板。
3. 使用`pip freeze > requirements.txt`获取项目依赖的包。
4. `在.gitignore`中忽略Python产生的文件，pyhon2是`*.pyc`，python3是`_pycache_`
## 本地部署流程
步骤1：创建一个新项目

(1) 命令：`(ll_env)learning_log$ django-admin.py startproject learning_log .`
这个命令末尾的句点让新项目使用合适的目录结构，这样开发完成后可轻松地将应用程序部署到服务器。

(2) 查看项目是否正确创建命令：`(ll_env)learning_log$ python manage.py runserver`

步骤2：创建数据库
(1) 命令：`learning_log$ python manage.py migrate`

步骤3：创建应用程序

(1) 命令：`(ll_env)learning_log$ python manage.py startapp learning_logs`

(2) 在`settings.py`激活应用程序。

(3) 修改`models.py`创建自己的模型。模型告诉Django如何处理应用程序中存储的数据。每次修改完`models.py`后执行`(ll_env)learning_log$ python manage.py makemigrations learning_logs`关联数据库。

(4) 添加模型后，修改`admin.py`注册模型。

步骤4：使用Django shell:`(ll_env)learning_log$ python manage.py shell`进行交互式查看数据。

步骤5：创建网页

(1) 在`urls.py`上映射url到对应跳转的页面（一般映射到视图上）。

(2) 在`view.py`上编写对应视图函数，一般返回一个html。

步骤5：让用户能输入数据

(1) 创建一个名为forms.py的文件，将其存储到models.py所在的目录在`forms.py`上添加表单。

步骤6：创建用户账户

(1) 使用命令创建一个users的应用程序,`(ll_env)learning_log$ python manage.py startapp users`

(2) 同样在`settings.py`上添加users程序。与创建上一个程序一样修改url和html。

(3) 在`view.py`里的视图函数中添加@login_required 限制用户的访问。

步骤7：将数据关联用于，在`models.py`里添加`owner = models.ForeignKey(User)`。然后执行迁移数据库命令。

步骤8：可以使用django-bootstrap3来美化页面。



## Heroku部署

步骤1：生成requierments.txt和runtime.txt（执行Python运行版本）

步骤2：为部署到Herohu而修改settings.py

步骤3：创建启动进程的Procfile

步骤4：为部署到Herohu而修改wsgi.py

步骤5：创建用于存储静态文件的目录

步骤6：使用git跟踪项目并push到heroku上。

步骤7：可以在heroku上创建超级用户；可以在Heroku上创建对用户友好的URL

步骤8：确保项目的安全，修改`settings.py`只允许托管某个host。







`