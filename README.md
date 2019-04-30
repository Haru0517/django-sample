# django-sample
This is a django sample.

## 使い方
`docker-compose up`でコンテナ起動．


## Tutorial 1
`django-admin startproject mysite`でプロジェクトの作成．

`python manage.py runserver 0:8000` でDjango起動．

`python manage.py startapp polls`でアプリケーション作成．

**polls/view.py**, **polls/urls.py**, **mysite/urls.py**を編集してビュー作成．

`python manage.py runserver 0:8000`して，http://0:8000/polls/にアクセス．


## Tutorial 2
### DB作成：
__polls/models.py__を編集．

`python manage.py makemigrations polls`でマイグレーション作成．

`python manage.py migrate`でマイグレーション適用．

### API
`python manage.py shell`で起動．


### Admin
`python manage.py createsuperuser`で管理者ユーザー作成．

`python manage.py runserver 0:8000`して，http://0:8000/admin/にアクセス．

