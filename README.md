# Introductory Workshop:

##### NOTE : Install Google Chrome Extension - JSONView

## 1. Request And Response Pattern:

### What Are Requests? Responses? Request/Response Pattern?
#### - Request:
Client (Maybe a Browser or a Mobile App...etc) Says Hi to the Server.
##### - - Api Request:
A Peice of Code (The Client) Says Hi to the Server.
#### - Response:
The Server Says Hi Client, in Response to the (Hi) Sent by the Client.
#### - Request/Response Pattern:
Is the whole Communication Process between the Client and the Server.

#### Example:
- On the Browser Console:
```javascript
const xhr = new XMLHttpRequest();
xhr;
```
- - Things to Conside: ```responseText``` || ```__proto__``` : look to ```open()``` and ```send()```

-----------

## 2. HTTP:

### 1. What is HTTP?
HyperText Transfer Protocol: A Mechanism/Protocol Used to Fire Requests to Fetch Some Data!

### 2. Other Transfer Protocols: FTP, SMTP, IMAP, FTPS, HTTPS
### 3. Request Methods : GET , POST , PUT , DELETE:

#### - GET:
Used to Fetch Data, the URL Contains the Parameters That Specifies which Data to Fetch. EX: Search Requests.

#### - POST:
Sends Data to Server, Data is Sent in The Request Body, It's Used to Insert Data in a Specific Place, EX: Form Submit

#### - PUT:
Also Sends Data to Server, But Unlike Post, it's Used to Replace an Existing Set of Data with New Data.

### 3. Status Codes:
#### - 100 :
Server Informs the Client that The Request Is Allowed to Send The Request Body.
#### - 200 :
Request is OK.
#### - 300 :
Redirect.
#### - 400 :
Client Side Errors.
#### - 500 :
Internal Server Errors.

-----------

## 3. XMLHttpRequest:

### 1.Definition:
- XHR is Just a JavaScript Object, that Containes Specific Data and Methods that Fire Requests from Client Side To a Server.

### 2. Creation:
```javascript
const xhr = new XMLHttpRequest();
```
### 3. Methods:
#### - Open("Method", "URL", ASYNC):
- - Initializes the Request.
- - First Two Parameters are used to Set Request Method and Request URL, the Third is a Boolean Value to Indicate Whether the XHR Request be Asynchronus or Not, Default Value is True, which is Preferable.

#### - Send(body):
- - Sends the Request to the Server.
- - It has Optional Parameter ```body``` which is Used to Hold the Data we Want to Send with a Request.

### 4. Properties:
#### - onreadystatechange:
- - It  Contains the Request Event Handler That is Used when ``` readystatechange ``` Event is Fired, It's Used to Listen to Changes on the XHR ``` readyState ``` Property that Indicates the State of a Request.

#### - readyState:
- - It has 5 Values (0 ---> 4), it Starts with 0 (Request is Not Initialized), and End with 4 (Request Is Finised, and the Response has Arrived).

#### - status:
- - It Holds the Status Code that Returns with a Response (1xx, 2xx, 3xx, 4xx, 5xx).

#### - responseText:
- - It Holds the Response Body as a String.

-----------

## 4. Asynchronicity:

### 1. Synchronous:
- - Means that It's Only Possible to Perform One Task at Time.

### 2. Asynchronous:
- - Well, I can do More, I Actually can Sneak Beyond Runtime.

### 3. Asynchronous Event Loop:
- - Event Loop: is the Processing of Code Lines, One after Another in the CALL STACK and the TASK QUEUE.
- - Tasks: A Peice of Code.
- - How it Works?
- - - it Pushes Asynchronous Tasks into the TASK QUEUE.
- - - Processes the Remaining Tasks in the CALL STACK.
- - - Once the CALL STACK is Completely Clear, the Event Loop Checks the TASK QUEUE, and Pushes Tasks from it into the CALL STACK One by One, until the TASK QUEUE is Completely Clear!
