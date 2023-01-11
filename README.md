<p align="left" >
 <img width="150px" height="100px" alt="aws-logo" src="https://user-images.githubusercontent.com/38281651/211433086-9002c229-c939-4b24-982a-d6767b9b8320.png">
<img width="190px" height="100px" alt="google-platform-logo" src="https://user-images.githubusercontent.com/38281651/211888072-143f76ff-25bd-4e76-905c-c76b3934fbc1.png">
 <img width="170px" height="100px" alt="openwhisk-logo" src="https://user-images.githubusercontent.com/38281651/211433466-8cc30e59-2e37-4ec4-a0f6-09a7ce3bb6fd.png">	

</p>


# Reverse Engineering of Serverless Functions

In your handler function: 

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
## Example Output JSON:

The attributes collect can be customized by changing which functions are called. For more detailed descriptions of each variable and the functions that collect them, please read the full documentation.

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



# Metrics Collected

```
uuid:            A unique identifier assigned to a container if one does not already exist.
newcontainer:    Whether a container is new (no assigned uuid) or if it has been used before.
vmuptime:        The time when the system started in Unix time.
cpuUsrDelta:      Time spent normally executing in user mode.
cpuNiceDelta:     Time spent executing niced processes in user mode.
cpuKrnDelta:      Time spent executing processes in kernel mode.
cpuIdleDelta:     Time spent idle.
cpuIowaitDelta:   Time spent waiting for I/O to complete.
cpuIrqDelta:      Time spent servicing interrupts.
cpuSoftIrqDelta:  Time spent servicing software interrupts.
vmcpustealDelta:  Time spent waiting for real CPU while hypervisor is using another virtual CPU.
contextSwitchesDelta: Number of context switches.
```


## Sample Architecture and Results: [AWS] 

![image](https://user-images.githubusercontent.com/38281651/211887441-84392c61-6210-4237-8794-351339dcc351.png)

### Sample Results

![image](https://user-images.githubusercontent.com/38281651/211889032-c903b3ea-87a4-41b6-8356-091e362dc9cf.png)



## Author 

Ashutosh Neupane
<br> adhinneupane2020@gmail.com </br>


