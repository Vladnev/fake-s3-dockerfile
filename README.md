# fake-s3-dockerfile

Docerized fake AWS S3 server for local development.
See: [fake-s3](https://github.com/jubos/fake-s3).(version 0.2.5)

Usage (in docker-compose.yml):

```
s3:
  image: vladnev/fake-s3
  ports:
    - "9000:9000"
  volumes:
    - s3:/storage
  command: -r /storage -p 9000 -H s3

some other services ...

volumes:
    s3:
```

Run as standalone:   
`docker run --name s3 -p 9000:9000 -v "$(pwd)"/volume:/storage -d vladnev/fake-s3`

Aws default connection config:
```
region: us-east-1
scheme: http
key: 123
secret: asdf
version: latest
```
