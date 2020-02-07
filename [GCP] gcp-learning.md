web.yaml

```
runtime: go112

service: web
```

You can stream logs from the command line by running:
>  $ gcloud app logs tail -s web

To view your application in the web browser run:
>  $ gcloud app browse -s web