```
$ vim Dockerfile
$ cat Dockerfile
...
LABEL org.dockerlings.author="nno0obb@kakao.com"
ENV PORT=8000
EXPOSE $PORT
CMD ["python3", "app.py"]
...
```
