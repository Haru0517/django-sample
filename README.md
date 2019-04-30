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