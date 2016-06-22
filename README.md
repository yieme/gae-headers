# gae-headers

List of Google App Engine Headers

### Live hosting environment

##### Incoming

- X-Appengine-City
- X-Appengine-Citylatlong
- X-Appengine-Country
- X-Appengine-Region
- X-Cloud-Trace-Context

### Local hosting environment

##### Incoming

- X-Appengine-Default-Version-Hostname
- X-Appengine-User-Organization
- X-Appengine-User-Id
- X-Appengine-Server-Software
- X-Appengine-User-Email
- X-Appengine-Backend-Id
- X-Appengine-Server-Name
- X-Appengine-Request-Id-Hash
- X-Appengine-User-Is-Admin
- X-Appengine-Server-Protocol
- X-Appengine-User-Nickname
- X-Appengine-Country
- X-Appengine-Remote-Addr
- X-Appengine-Request-Log-Id
- X-Appengine-Server-Port

### github.com/golang/appengine/blob/master/internal/api.go

##### Incoming

- X-AppEngine-API-Ticket
- X-Google-DapperTraceInfo
- X-Cloud-Trace-Context
- X-AppEngine-Current-Namespace
- X-AppEngine-User-IP
- X-AppEngine-Remote-Addr
- 
##### Outgoing

- X-Google-RPC-Service-Endpoint
- X-Google-RPC-Service-Method
- X-Google-RPC-Service-Deadline
- X-AppEngine-Log-Flush-Count
 
### GO Client IP

`http.Request.RemoteAddr` ex: `r.RemoteAddr`

### cloud.google.com/appengine/docs/flexible/nodejs/how-requests-are-handled

##### Incoming

- X-AppEngine-Cron
- X-Appengine-City
- X-Appengine-Citylatlong
- X-Appengine-Country
- X-Appengine-Region

### GO list headers

```go
func listHeadersHandler(w http.ResponseWriter, r *http.Request) {
  w.Header().Set("Content-Type", "application/javascript; charset=utf-8")
  fmt.Fprint(w, "{ \"now\": \"", time.Now().Format("2006-01-02 15:04:05"))
  for k, v := range r.Header {
      fmt.Fprint(w, "\", \""+ k + "\": \"", v)
  }
  fmt.Fprint(w, "\" }")
}
```
