# HttpRequestRestAPI
IIB REST API that takes two inputs at the time of deploying a bar file and can also be changed at runtime.
This bar file can be used to call the ZOSConnect API. Created using IBM Integration Bus 10.0.0.3 

### Implemeneted API 
REST API: http://localhost:7800/apiJson

Method: as defined by your variable

Request body: JSON

### User defined variables 
REST_URL (Set to the Z/OS connect REST API URL)

HTTP_METHOD (Set to GET or POST)

### Steps to set these User Defined Variables at run time


**Using command line**
```
mqsiapplybaroverride -b ZOSRestAPIproject.generated.bar 
-m ZOSRest01#REST_URL=http://api-springboot.mybluemix.net/operate/add/5/7,ZOSRest01#HTTP_METHOD=GET -r

mqsiapplybaroverride -b ZOSRestAPIproject.generated.bar 
-m ZOSRest01#REST_URL=http://api-springboot.mybluemix.net/operate/addJSON,ZOSRest01#HTTP_METHOD=POST -r

mqsideploy TESTNODE_root -e default -a ZOSRestAPIproject.generated.bar
```


**Using from IBM Integration explorer**
![90404922d08747a](https://cloud.githubusercontent.com/assets/14492591/14194960/a05fb1d8-f7ff-11e5-80d8-34344b930d8a.jpg)


###How to execute the API


**GET Method**
In case variables are set to REST_URL=http://api-springboot.mybluemix.net/operate/add/5/7, HTTP_METHOD=GET

GET  http://localhost:7800/apiJson



**POST Mehtod**
In case variables are set to REST_URL=http://api-springboot.mybluemix.net/operate/addJSON, HTTP_METHOD=POST

POST  http://localhost:7800/apiJson

Request Header: **Content-Type: application/json**

Request Body: JSON Input of the API such as  {  "left": 5,  "right": 6 }


![21603bfe7d199f47-1](https://cloud.githubusercontent.com/assets/14492591/14194959/a000b03e-f7ff-11e5-8758-6ab483dc3f1b.jpg)

