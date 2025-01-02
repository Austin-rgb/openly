# openly
Have you ever met a very good python package 
that would very good if you use it in your Web application. 
Mostly the best option available for you is to write API endpoints on your server code
maybe in FastAPI or Flask or any other server side Web Development framework, 
then you have to write javascript consumer services on the frontend to consume the server endpoints.
This can be very tedious especially when you need to write many API endpoints. 
This is where openly comes to your aid.
Openly provides a simpler way to bind backend API to the front without writing a lot.
All you need is:
- import the APIs you want to expose
- add the APIs to backend openly environment
- import them in javascript frontend
- use as you wish

```python
from package1 import Class1, Class2
from openly.interpeter import Interpreter
from openly.service import Service

environment = []
environment ["Class1"]=Class1
environment ["Class2"]=Class2

interpreter=Interpreter(environment)

service = (interpreter,__name__)
service.run()
```

```javascript
import {bindAll} from "openly"
let Class1, Class2

bindAll().then(data=>{
({Class1, Class2})=data
let variable1 = new Class1();
let variable2 = new Class2();
})

