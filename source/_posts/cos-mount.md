---
title: cos-mount
tags: []
categories:
  - 指南
date: 2020-01-04 17:21:09
---

s3fs mytest123 /mnt/kp-nc -o url=<https://s3.us-south.cloud-object-
storage.appdomain.cloud> -o passwd_file=/mnt/key

s3fs mytest123 /mnt/kp-c -o url=<https://s3.us-south.cloud-object-
storage.appdomain.cloud> -o passwd_file=/mnt/key
-o,umask=0007,use_path_request_style,use_sse=kmsid,dbglevel=info -f

s3fs sallytest /mnt/kp-nc -o url=<https://s3.ap.cloud-object-
storage.appdomain.cloud> -o passwd_file=/mnt/key
-o,umask=0007,use_path_request_style,use_sse=kmsid,dbglevel=info -f

s3fs mytest123 /mnt/kp-c -o url=<https://s3.us-south.cloud-object-
storage.appdomain.cloud> -o passwd_file=/mnt/key
-o,umask=0007,use_path_request_style,use_sse=custom,dbglevel=info -f

s3fs mytest123 /mnt/kp-c -o url=<https://s3.us-south.cloud-object-
storage.appdomain.cloud> -o passwd_file=/mnt/key -o use_sse=kmsid -o
dbglevel=info -f

curl -X POST \  
“[https://iam.bluemix.net/identity/token"](https://iam.bluemix.net/identity/token")
\  
-H “Content-Type: application/x-www-form-urlencoded” \  
-H “Accept: application/json” \  
-d “grant_type=urn%3Aibm%3Aparams%3Aoauth%3Agrant-type%3Aapikey&apikey=1QpV61aKwJIrUlti_2R7d5WzdzppAZjQN48vPFVNLoX7”

curl -X POST \  
<https://iam.bluemix.net/identity/token> \  
-H “Content-Type: application/x-www-form-urlencoded” \  
-H “Accept: application/json” \  
-d “grant_type=urn%3Aibm%3Aparams%3Aoauth%3Agrant-type%3Aapikey&apikey=1QpV61aKwJIrUlti_2R7d5WzdzppAZjQN48vPFVNLoX7”

crn:v1:bluemix:public:cloud-object-
storage:global:a/290f8f438c15a26b2b129419c1e9861f:f1f11fc4-939f-4896-9b53-f66a1661e14a::
f1f11fc4-939f-4896-9b53-f66a1661e14a

curl -X GET <https://keyprotect.us-
south.bluemix.net/api/v2/keys/da742336-a8ac-47cc-a1ee-3a1253344cb2> -H
‘authorization: Bearer $TOKEN’ -H ‘bluemix-instance:
f1f11fc4-939f-4896-9b53-f66a1661e14a’ -H ‘accept:
application/vnd.ibm.kms.key+json’

curl -X GET <https://keyprotect.us-
south.bluemix.net/api/v2/keys/da742336-a8ac-47cc-a1ee-3a1253344cb2> -H
‘authorization: Bearer
eyJraWQiOiIyMDE3MTAzMC0wMDowMDowMCIsImFsZyI6IlJTMjU2In0.eyJpYW1faWQiOiJpYW0tU2VydmljZUlkLWJmOTJmOWVhLWUwNDktNGI4MS1iOWY0LWU3NjliNGExNjRiYyIsImlkIjoiaWFtLVNlcnZpY2VJZC1iZjkyZjllYS1lMDQ5LTRiODEtYjlmNC1lNzY5YjRhMTY0YmMiLCJyZWFsbWlkIjoiaWFtIiwiaWRlbnRpZmllciI6IlNlcnZpY2VJZC1iZjkyZjllYS1lMDQ5LTRiODEtYjlmNC1lNzY5YjRhMTY0YmMiLCJzdWIiOiJTZXJ2aWNlSWQtYmY5MmY5ZWEtZTA0OS00YjgxLWI5ZjQtZTc2OWI0YTE2NGJjIiwic3ViX3R5cGUiOiJTZXJ2aWNlSWQiLCJhY2NvdW50Ijp7InZhbGlkIjp0cnVlLCJic3MiOiIyOTBmOGY0MzhjMTVhMjZiMmIxMjk0MTljMWU5ODYxZiJ9LCJpYXQiOjE1NDcxODgyNTksImV4cCI6MTU0NzE5MTg1OSwiaXNzIjoiaHR0cHM6Ly9pYW0uYmx1ZW1peC5uZXQvaWRlbnRpdHkiLCJncmFudF90eXBlIjoidXJuOmlibTpwYXJhbXM6b2F1dGg6Z3JhbnQtdHlwZTphcGlrZXkiLCJzY29wZSI6ImlibSBvcGVuaWQiLCJjbGllbnRfaWQiOiJkZWZhdWx0IiwiYWNyIjoxLCJhbXIiOlsicHdkIl19.GXfZHETWeNyghiyYC0jwTOTqRQ0plSLGZylkOUkl6MLzOH3Oy5VyZmreUV0k0M6xkbg6KBNQcru9h2nq7k3rEx1B7vNUVJN271T17_yxdUFF_aWU4jxC4JMNUkAsmEun_pip1VFhhQC5yH6HUsPQuW1SIqPH9Nn-
avsP7JO7JZDu_n5RPKUZjhFNxDgn-
kA2NlKSctinId_11bIVZjDumRzPLUMzTcY7pKBzPWMFr6fLyk3FPiv0SMEbbrSny27WhwMmDYk27zk0g3YiQM81R1M2mX1_NKwscp_k1G9lUO9FmAzVbIsMYx2aWl7-FygO5lBd-
MRPHtLhKpZRT_-Elg’ -H ‘bluemix-instance:25f403ed-3645-433d-b24c-40309c826856’
-H ‘accept: application/vnd.ibm.kms.key+json’

curl -X PUT <https://s3.us-south.objectstorage.softlayer.net>

curl -X “POST”
“[https://iam.bluemix.net/oidc/token"](https://iam.bluemix.net/oidc/token") \  
-H ‘Accept: application/json’ \  
-H ‘Content-Type: application/x-www-form-urlencoded’ \  
–data-urlencode “apikey=9BWoHWYnVP4GH2rtG1ZAoBuQy4tDVdYGLIGwABUY-p5U” \  
–data-urlencode “response_type=cloud_iam” \  
–data-urlencode “grant_type=urn:ibm:params:oauth:grant-type:apikey”

create bucket enable kp

curl -X “PUT” “[https://s3.us-
south.objectstorage.softlayer.net/simpletest"](https://s3.us-
south.objectstorage.softlayer.net/simpletest") -H “Authorization: Bearer
eyJraWQiOiIyMDE3MTAzMC0wMDowMDowMCIsImFsZyI6IlJTMjU2In0.eyJpYW1faWQiOiJpYW0tU2VydmljZUlkLTBhYWFiMzExLTQzOWEtNDdhYy05NmYxLTAyMWE3YmNkY2UxMyIsImlkIjoiaWFtLVNlcnZpY2VJZC0wYWFhYjMxMS00MzlhLTQ3YWMtOTZmMS0wMjFhN2JjZGNlMTMiLCJyZWFsbWlkIjoiaWFtIiwiaWRlbnRpZmllciI6IlNlcnZpY2VJZC0wYWFhYjMxMS00MzlhLTQ3YWMtOTZmMS0wMjFhN2JjZGNlMTMiLCJzdWIiOiJTZXJ2aWNlSWQtMGFhYWIzMTEtNDM5YS00N2FjLTk2ZjEtMDIxYTdiY2RjZTEzIiwic3ViX3R5cGUiOiJTZXJ2aWNlSWQiLCJhY2NvdW50Ijp7InZhbGlkIjp0cnVlLCJic3MiOiIyOTBmOGY0MzhjMTVhMjZiMmIxMjk0MTljMWU5ODYxZiJ9LCJpYXQiOjE1NDcxOTIzNjEsImV4cCI6MTU0NzE5NTk2MSwiaXNzIjoiaHR0cHM6Ly9pYW0ubmcuYmx1ZW1peC5uZXQvb2lkYy90b2tlbiIsImdyYW50X3R5cGUiOiJ1cm46aWJtOnBhcmFtczpvYXV0aDpncmFudC10eXBlOmFwaWtleSIsInNjb3BlIjoiaWJtIG9wZW5pZCIsImNsaWVudF9pZCI6ImRlZmF1bHQiLCJhY3IiOjEsImFtciI6WyJwd2QiXX0.IhYBWB6WJRR9Pi_S8hmEqXlqF9jrKdqCUF1O1-JXnjEli-O1EZNzfqevLFkgVuPLZ3FQpe0kaPRlDm9rmQsJ-93cbMrGEbLnOQMTrL3HpTqPQZJnmIJiJh6QSLYUFb6fBbEII_ydP56q3dLohXAfIyViW5S6p-PqEeuSCT5BW6kWiJdSTW4d1VUrxJ15HL2hOnxxL46izc9rIIV_nPqlMPQDKinK8vEvvD1xFag4wLEMmqYWiqrE8QFWYyR9rcCYPG7vLIFsQZf23fdx2qhjfFXXjqueVyeHjwzP9ED_i5vMpsjWOMFdgkFcacdcQcSRS3cqXoQUm5wyqOCsz6EKUQ”
-H “ibm-service-instance-id: f1f11fc4-939f-4896-9b53-f66a1661e14a” -H “ibm-
sse-kp-encryption-algorithm : AES256” -H “ibm-sse-kp-customer-root-key-crn :
crn:v1:bluemix:public:kms:us-
south:a/290f8f438c15a26b2b129419c1e9861f:25f403ed-3645-433d-b24c-40309c826856:key:da742336-a8ac-47cc-a1ee-3a1253344cb2”