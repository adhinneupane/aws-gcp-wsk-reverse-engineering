# Using Inspector in Serverless Functions

```
from Inspector import *

def myFunction(request):
  
  # Initialize the Inspector and collect data.
  inspector = Inspector()
  inspector.inspectAll()

  # Add a "Hello World!" message.
  inspector.addAttribute("message", "Hello " + request['name'] + "!")

  # Return attributes collected.
  return inspector.finish()

``` 
Example Output JSON:

The attributes collect can be customized by changing which functions are called. For more detailed descriptions of each variable and the functions that collect them, please see the framework documentation for each language.

```
{
	"version": 0.2,
	"lang": "python",
	"cpuType": "Intel(R) Xeon(R) Processor @ 2.50GHz",
	"cpuModel": 63,
	"vmuptime": 1551727835,
	"uuid": "d241c618-78d8-48e2-9736-997dc1a931d4",
	"vmID": "tiUCnA",
	"platform": "AWS Lambda",
	"newcontainer": 1,
	"cpuUsrDelta": "904",
	"cpuNiceDelta": "0",
	"cpuKrnDelta": "585",
	"cpuIdleDelta": "82428",
	"cpuIowaitDelta": "226",
	"cpuIrqDelta": "0",
	"cpuSoftIrqDelta": "7",
	"vmcpustealDelta": "1594",
	"frameworkRuntime": 35.72,
	"message": "Hello John Doe!",
	"runtime": 38.94
}
```


