# 웹 관련 토픽

# 파이썬 Production mode 배포 관련

## flask 
- 내부적으로 blocking 작업이 있을 경우
  - A가 해당 API 작업에 요청을 보내고, B가 동일 API에 요청을 해도, A가 다 처리 될 때까지 기다림
  - 따라서 flask 앱 내부에서 IO작업(request, file i/o)를 할 때 주의해야함
- flask 앱은 기본적으로 *Synchronous*하다.
  - **gunicorn**을 통해서 여러 요청의 동시 처리를 가능케할 수 있다.
  ```
  gunicorn flask_app:app -w $NUM_WORKER --threads $NUM_THREADS -k $WORKER_CLASS
  ```


## 참고
- gunicorn으로 flask 동시 요청 처리 https://winterj.me/flask-concurrency-test/
