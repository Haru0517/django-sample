# django-sample
This is a django sample.

## 使い方
`docker-compose up`でコンテナ起動．


## Tutorial 1
`django-admin startproject mysite`でプロジェクトの作成．

`python manage.py runserver 0:8000` でDjango起動．

`python manage.py startapp polls`でアプリケーション作成．

**polls/view.py**, **polls/urls.py**, **mysite/urls.py**を編集してビュー作成．

`python manage.py runserver 0:8000`して，http://0:8000/polls/ にアクセス．


## Tutorial 2
### DB作成：
__polls/models.py__を編集．

`python manage.py makemigrations polls`でマイグレーション作成．

`python manage.py migrate`でマイグレーション適用．

### API
`python manage.py shell`でシェル起動．


### Admin
`python manage.py createsuperuser`で管理者ユーザー作成．

`python manage.py runserver 0:8000`して，http://0:8000/admin/ にアクセス．



## Tutorial 3
**polls/urls.py**： pollsの各ページのpathを設定．
- `path('<int:question_id>/', views.detail, name='detail')`

**polls/views.py**：各ページの処理．
- render(): `render(request, 'polls/index.html', context)`
- get_object_or_404(): `question = get_object_or_404(Question, pk=question_id)`

**polls/templates/polls/xxx.html**：views.pyで読み込むテンプレート．
- `<a href="{% url 'detail' question.id %}">`でURL変更に柔軟に．
- `app_name`を設定すれば，名前空間を定義できる．



## Tutorial 4
フォームの作成
- **--/polls/detail.html**：フォーム作成．
- **polls/views.py: vote()**：入力を受け取って結果を保存してresultを表示．
- **polls/views.py: result()**：指定されたidのQuestionを取得してresult.htmlを表示．
- **--/polls/result.html**：投票数表示．
- http://0:8000/polls/1/ にアクセス．

汎用ビューを使う
- **polls/urls.py**：汎用ビューの書き方に変更．
- **polls/views.py**：IndexView, DetailView, ResultsViewを作成．
