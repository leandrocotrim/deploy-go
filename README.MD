## Sample GO server

#### Code
```go
package main

import "net/http"

func main() {
	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		w.Write([]byte("<h1>Go is works!</h1>"))
	})

	http.ListenAndServe(":8080", nil)
}
```

```bash
> go run main.go
```

```bash
> curl localhost:8080
# <h1>Go is works!</h1>
```

--------

```bash
gcloud init
gcloud auth login
gcloud auth configure-docker us-central1-docker.pkg.dev

docker build -t us-central1-docker.pkg.dev/teste-421902/docker-mages/deploy-go:latest .
docker push us-central1-docker.pkg.dev/teste-421902/docker-mages/deploy-go:latest
```
