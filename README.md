# Using Inspector in Serverless Functions

from Inspector import *

def myFunction(request):
  
  # Initialize the Inspector and collect data.
  inspector = Inspector()
  inspector.inspectAll()

  # Add a "Hello World!" message.
  inspector.addAttribute("message", "Hello " + request['name'] + "!")

  # Return attributes collected.
  return inspector.finish()
  