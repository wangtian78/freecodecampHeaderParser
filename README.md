# API Project: Request Header Parser Microservice for freeCodeCamp

### stories:
1. I can get the IP address, preferred languages (from header `Accept-Language`) and system infos (from header `User-Agent`) for my device.

#### Example usage:
* [base_url]/api/whoami

#### Example output:
* `{"ipaddress":"159.20.14.100","language":"en-US,en;q=0.5","software":"Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:50.0) Gecko/20100101 Firefox/50.0"}`

Note: req.headers has this:

{"header":{"connection":"close","x-forwarded-for":"150.135.165.91,::ffff:10.10.11.180,::ffff:10.10.10.26","x-forwarded-proto":"https,http,http","x-forwarded-port":"443,80,80","host":"clever-drive.glitch.me","x-amzn-trace-id":"Root=1-5b350b55-6fe986e6de37b8382043c788","upgrade-insecure-requests":"1","user-agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.186 Safari/537.36","accept":"text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8","accept-encoding":"gzip, deflate, br","accept-language":"en-US,en;q=0.9","if-none-match":"W/\"2-vyGp6PvFo4RvsFtPoIWeCReyIC8\"","x-request-id":"b1da5625c92009fa","x-glitch-routing":"df231883-90cd-42bf-9455-120ba0b57590:1085","x-forwarded-host":"clever-drive.glitch.me"}}

so we can get ip by req.headers["x-forwarded-for"],
              language by req.headers["accept-language"],
              sys-info by req.headers["user-agent"]


Glitch link
https://glitch.com/edit/#!/clever-drive?path=server.js:1:0
