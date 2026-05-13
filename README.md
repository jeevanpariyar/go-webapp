go-webapp-sample
license report workflow release

Preface
This repository is the sample of web application using golang. This sample uses Echo as web application framework, Gorm as OR mapper and Zap logger as logger. This sample application provides only several functions as Web APIs. Please refer to the 'Service' section about the detail of those functions.

Also, this application contains the static contents such as html file, css file and javascript file which built vuejs-webapp-sample project to easily check the behavior of those functions. So, you can check this application without starting a web server for front end. Please refer to the 'Starting Server' section about checking the behavior of this application.

If you would like to develop a web application using golang, please feel free to use this sample.

Install
Perform the following steps:

Download and install MinGW(gcc).
Download and install Visual Studio Code(VS Code).
Download and install Golang.
Get the source code of this repository by the following command.
go get -u github.com/ybkuroki/go-webapp-sample
Starting Server
There are 2 methods for starting server.

Without Web Server
Starting this web application by the following command.
go run main.go
When startup is complete, the console shows the following message:
http server started on [::]:8080
Access http://localhost:8080 in your browser.
Login with the following username and password.
username : test
password : test
With Web Server
Starting Application Server
Starting this web application by the following command.
go run main.go
When startup is complete, the console shows the following message:
http server started on [::]:8080
Access http://localhost:8080/api/health in your browser and confirm that this application has started.
healthy
Starting Web Server
Clone vuejs-webapp-sample project and install some tools.
Start by the following command.
npm run serve
When startup is complete, the console shows the following message:
DONE Compiled successfully in *****ms

App running at:
- Local:   http://localhost:3000/
- Network: http://192.168.***.***:3000/

Note that the development build is not optimized.
To create a production build, run npm run build.
Access http://localhost:3000 in your browser.
Login with the following username and password.
username : test
password : test
Using Swagger
In this sample, Swagger is enabled only when executed this application on the development environment. Swagger isn't enabled on the another environments in default.

Accessing to Swagger
Start this application according to the 'Starting Application Server' section.
Access http://localhost:8080/swagger/index.html in your browser.
Updating the existing Swagger document
Update some comments of some controllers.
Download Swag library. (Only first time)
go get github.com/swaggo/swag/cmd/swag
Update docs/docs.go.
swag init
Build executable file
Build this source code by the following command.

go build main.go
Project Map
The follwing figure is the map of this sample project.

- go-webapp-sample
  + config                  … Define configurations of this system.
  + logger                  … Provide loggers.
  + middleware              … Define custom middleware.
  + migration               … Provide database migration service for development.
  + router                  … Define routing.
  + controller              … Define controllers.
  + model                   … Define models.
  + repository              … Provide a service of database access.
  + service                 … Provide a service of book management.
  + session                 … Provide session management.
  + test                    … for unit test
  - main.go                 … Entry Point.
Services
This sample provides 3 services: book management, account management, and master management. Regarding the detail of the API specification, please refer to the 'Using Swagger' section.

Book Management
There are the following services in the book management.

Service Name	HTTP Method	URL	Parameter	Summary
Get Service	GET	/api/books/[BOOK_ID]	Book ID	Get a book data.
List/Search Service	GET	/api/books?query=[KEYWORD]&page=[PAGE_NUMBER]&size=[PAGE_SIZE]	Page, Keyword(Optional)	Get a list of books.
Regist Service	POST	/api/books	Book	Regist a book data.
Edit Service	PUT	/api/books	Book	Edit a book data.
Delete Service	DELETE	/api/books	Book	Delete a book data.
Account Management
There are the following services in the Account management.

Service Name	HTTP Method	URL	Parameter	Summary
Login Service	POST	/api/auth/login	Session ID, User Name, Password	Session authentication with username and password.
Logout Service	POST	/api/auth/logout	Session ID	Logout a user.
Login Status Check Service	GET	/api/auth/loginStatus	Session ID	Check if the user is logged in.
Login Username Service	GET	/api/auth/loginAccount	Session ID	Get the login user's username.
Master Management
There are the following services in the Master management.

Service Name	HTTP Method	URL	Parameter	Summary
Category List Service	GET	/api/categories	Nothing	Get a list of categories.
Format List Service	GET	/api/formats	Nothing	Get a list of formats.
Libraries
This sample uses the following libraries.

Library Name	Version
echo	4.6.1
gorm	1.22.3
go-playground/validator.v9	9.31.0
zap	1.19.1
Contribution
Please read CONTRIBUTING.md for proposing new functions, reporting bugs and submitting pull requests before contributing to this repository.

License
The License of this sample is MIT License.
