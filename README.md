# CRUD

## 프로젝트 구조 작성

1. 프로젝트 폴더 생성
2. 프로젝트 폴더를 vscode로 열기
    - `.gitignore`, `README.md` 만들기
3. django 프로젝트 생성
```
django-admin startproject <pjt-name> . 
```

4. 가상환경 설정
```
python -m venv venv
```

5. 가상환경 활성화
```
source venv/Scripts/activate
```

6. 가상환경에 django 설치
```
pip install django
```

7. 서버 실행 확인
```
python manage.py runserver
```

8. 앱 생성
```
django-admin startapp <app-name>
```

9. 앱 등록 => 프로젝트 폴더의 `settings.py`열기, <app_name>추가하기
```python
INSTALLED_APPS = [
    ...
    '<app_name>',
]
```

10. `urls.py` => `views.py` => `templates/*.html` 순서로 코드 작성 
<app_name>폴더 안에 templates 폴더 생성, 그 안에 '.html'파일 

## Model

1. 모델 정의(`models.py`)
    - 모델의 이름은 기본적으로 단수 형태
```
class Post(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField()
``` 
2. 번역본 생성
```
python manage.py makemigrations
```

3. DB에 반영
```
python manage.py migrate
```

4. 생성한 모델을 admin에 등록(`admin.py`)
```python
from django.contrib import admin
from .models import Post
# Register your models here.

admin.site.register(Post)
```

5. 관리자 계정 생성
```
python manage.py createsuperuser
```

## CRUD
- Create, Read, Update, Delete

1. Read
- 전체 게시물 출력
```python
def index(request):
    posts = Post.objects.all()

    context = {
        'posts': posts,
    }

    return render(request, 'index.html', context)
```
- 하나의 게시물 출력
```python
def detail(request, id):
    post = Post.objects.get(id=id)

    context = {
        'post': post,
    }

    return render(request, 'detail.html', context)
```