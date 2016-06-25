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

### [GAE api.go](http://github.com/golang/appengine/blob/master/internal/api.go)

##### Incoming

- X-AppEngine-API-Ticket
- X-Google-DapperTraceInfo
- X-Cloud-Trace-Context
- X-AppEngine-Current-Namespace
- X-AppEngine-User-IP
- X-AppEngine-Remote-Addr

##### Outgoing

- X-Google-RPC-Service-Endpoint
- X-Google-RPC-Service-Method
- X-Google-RPC-Service-Deadline
- X-AppEngine-Log-Flush-Count
 
### GO Client IP

`http.Request.RemoteAddr` ex: `r.RemoteAddr`

### [How Requests are handled](http://cloud.google.com/appengine/docs/flexible/nodejs/how-requests-are-handled)

##### Incoming

- X-AppEngine-Cron
- X-Appengine-City
- X-Appengine-Citylatlong
- X-Appengine-Country
- X-Appengine-Region
- X-AppEngine-Estimated-CPM-US-Dollars
- X-AppEngine-Resource-Usage


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

### Other non-gae headers of interest

#### [CloudFront](https://aws.amazon.com/blogs/aws/enhanced-cloudfront-customization/)

Generated headers which can be used for routing

- CloudFront-Viewer-Country
- CloudFront-Is-Mobile-Viewer
- CloudFront-Is-Desktop-Viewer
- CloudFront-Is-Tablet-Viewer
- CloudFront-Forwarded-Proto
- Host
- Origin

#### [CloudFlare]()

[Request headers](https://support.cloudflare.com/hc/en-us/articles/200170986-How-does-CloudFlare-handle-HTTP-Request-headers-):

- X-Forwarded-For 
- X-Forwarded-Proto
- CF-Connecting-IP 
- Cf-Visitor - `{ "scheme":"https" }`
- Cf-Ipcountry
- CF-Ray - request hash with datacenter `230b030023ae2822-SJC`

Response headers

- Cf-Railgun
- CF-Ray
- __cfuid
- 
