Week 7  
1. Launch EC2 Instance (using ubuntu here)  
2. Security Roles > Open Anywhere IP4 & 6  
3. Open 2x Connections  
4. Start Running commands  
sudo apt-get update  
sudo apt install golang-go  
vi intro.go  
5. Paste below, followed by :wq  
  
package main  
  
import (  
	"fmt"  
	"net/http"  
)  
  
func main() {  
	http.HandleFunc("/", func(w http.ResponseWriter,r *http.Request) {  
		fmt.Fprintf(w, "Path: %s!", r.URL.Path[1:])  
	})  
  
	http.ListenAndServe(":8080", nil)  
  
}  
  
6. Run the intro with the following:  
go run intro.go  
7. Back to console; grab the public dns  
8. In the other control panel run the following:  
curl -X GET HTTP://ec2-3-148-252-35.us-east-2.compute.amazonaws.com:8080  
curl -X GET HTTP://ec2-3-148-252-35.us-east-2.compute.amazonaws.com:8080/TEST  
  
DEMO FOR BASIC WEBSERVER COMPLETE  
  
9. Cancel basic Webserver  
10. run:  
sudo apt install golang-github-gorilla-mux-dev  
go mod init gorilla/mux  
cat go.mod  
go mod tidy  
go get github.com/gorilla/mux  
vi intro_two.go  
11. Paste below, followed by :wq  
  
package main  
  
import (  
	"fmt"  
	"log"  
	"net/http"  
	"time"  
  
	"github.com/gorilla/mux"  
)  
  
func main() {  
	router := mux.NewRouter()  
	router.HandleFunc("/resources", func(w http.ResponseWriter, r *http.Request) {  
		fmt.Fprintf(w, "/resources")  
	})  
	router.HandleFunc("/resources/{id:[0-9]+}/values", func(w http.ResponseWriter, r *http.Request) {  
		fmt.Fprintf(w, "/resources/{id:[0-9]+}/values: %s", mux.Vars(r)["id"])  
	})  
  
	srv := &http.Server{  
		Handler:	router,  
		Addr:		":8080",  
		WriteTimeout:	15 * time.Second,  
		ReadTimeout:	15 * time.Second,  
	}  
  
	log.Fatal(srv.ListenAndServe())  
}  
  
12. Run the second intro with the following:  
go run intro_two.go  
13. Run the curl client with the public DNS again, this time with an extension into resources   
curl HTTP://ec2-3-148-252-35.us-east-2.compute.amazonaws.com:8080/resources/123  
curl http://ec2-3-148-252-35.us-east-2.compute.amazonaws.com:8080/resources/456/values  
  
DEMO FOR WEBSERVER 2 COMPLETE  
  
