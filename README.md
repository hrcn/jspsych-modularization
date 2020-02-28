## CORS configuration in AWS S3
```
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
<CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedMethod>POST</AllowedMethod>
    <AllowedHeader>*</AllowedHeader>
</CORSRule>
</CORSConfiguration>
```

## Local testing
To get rid of the CORS block in some browsers, you have to setup a static server.

Run `npm i -g serve`

Under to the project directory, run `serve ./`

Go to `http://localhost:5000/` and open `experiment.html`
