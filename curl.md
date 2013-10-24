# curl

POST something:

    curl -X POST --data "param=value&param2=value" url

POST some JSON from file:

    curl -X POST -d @filename.txt url --header "Content-Type:application/json"

PUT a resource:

    curl -X PUT url

Download a file:

    curl -O url

### Useful options

- `i` - show response headers
- `k` - skip validation of SSL certificate
