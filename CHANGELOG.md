# What’s New

## 1.1.2 (2014-08-21)
- improved error response messages, especially for EDAMUserException, EDAMSystemException and EDAMNotFoundException.
```json
{
   "timestamp":1408681609240,
   "status":400,
   "error":"Bad Request",
   "exception":"org.springframework.social.evernote.api.EvernoteException",
   "message":"com.evernote.edam.error.EDAMUserException, ErrorCode [PERMISSION_DENIED(3)], Parameter [authenticationToken]"
}
```
- spring-boot has been updated to 1.1.5.RELEASE


## 1.1.1 (2014-07-22)
- support `supportLinkedSandbox` parameter in oauth
  - see API change detail: [App Notebooks feature](https://dev.evernote.com/doc/articles/app_notebook.php)

*sample:*

```shell
$ curl -X POST -d "supportLinkedSandbox=true" -d "callbackUrl=http://myapp/oauth-callback" http://localhost:8080/oauth/auth
{
  "authorizeUrl":".../OAuth.action?oauth_token=...&supportLinkedSandbox=true", ...
}
```


## 1.1 (2014-07-15)

- spring-boot has been updated to 1.1.4.RELEASE
- added metrics for evernote api calls (store client operations)
  - number of success and failure calls to evernote endpoints
  - response time for evernote api call

*sample:*

```
# metrics endpoint:
#    http://localhost:8080/management/metrics
...
"counter.evernote.api.noteStore.listTags.succeeded": 3,   # num of successful evernote api calls
"gauge.evernote.api.noteStore.listTags.response": 42,     # evernote api call response time (ms)
...
```
