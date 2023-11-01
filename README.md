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
```

8.

9. 앱 등록 => 프로젝트 폴더의 `settings.py`열기, <app_name>추가하기
```python
INSTALLED_APPS = [
    ...
    '<app_name>'
]
```

10. <app_name>폴더 안에 templates 폴더 생성, 그 안에 '.html'파일 생성