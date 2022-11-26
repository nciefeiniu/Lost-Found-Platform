# Django失物招领系统
> Django 3.2 

可以使用Mysql 或者 Sqlite

## 怎么启动

1. 安装依赖

```shell
pip install -r requirements.txt
```

2. 同步数据库

如果你不适用Mysql，那么很简单

```shell
python manager.py migrate
```

如果你使用MySQL，那么首先，你去创建一个数据库

然后修改 `losthub/settings.py` 这个文件，把 `DATABASE` 修改为自己的数据库

```python
# 如果你想用sqlite，就不用改，如果你想用mysql
# DATABASES = {
#     'default': {
#         'ENGINE': 'django.db.backends.sqlite3',
#         'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
#     }
# }

# 这是 Mysql的配置
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'competition',  # 数据库名
        'HOST': '127.0.0.1',  # 数据库地址
        'PASSWORD': '123456',  # 数据库密码
        'PORT': 3306,  # 数据库端口
        'USER': 'root',  # 数据库用户
    }
}
```

然后
```shell
python manager.py makemigrations
python manager.py migrate
```

3. 启动服务

```shell
python manager.py runserver
```