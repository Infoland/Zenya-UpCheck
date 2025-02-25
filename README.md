# Zenya UpCheck
Description of the system with which can be checked if your Zenya instance is up and running.

# Explanation
A GET request can be sent a certain url of a customer Zenya which will return a 2xx if everything is okay and a 500 if something is wrong.

It checks the following things:
- Database access
- Storage access
- Search Api

# Curl
```curl
curl --location 'https://<customer>.zenya.work/upcheck'
```

# Response

## Everything is okay
Status code: 200 

Response body:
```html
<html><head></head><body>OK</body></html>
```

## Something is wrong
Status code: 500

If enabled on the server in the response body can contain the following:

Database issue:
```html
<html><head></head><body>1</body></html>
```

Storage issue:
```html
<html><head></head><body>2</body></html>
```

Search issue:
```html
<html><head></head><body>4</body></html>
```
