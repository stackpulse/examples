# Example Data



## What is it

This is example data you can use in a [StackPulse](https://stackpulse.com) playbook that is simple and reasonably structured.  It is often used in Knowledge Base articles or to validate a step inside of StackPulse.  Often it is easier to work with as simple data payload that is well understood when working through the logic of a step or passing information between steps.


## How do I use this example data with StackPulse?

The simplest way to access this data from within your [StackPulse](https://app.stackpulse.com) tenant is to curl the raw data from Github, that step might look something like this:

```
steps:
  - name: curlimages/curl
    id: curl-request
    args:
      - -s
      - https://raw.githubusercontent.com/stackpulse/examples/example-data/master/flat-example.json
    output_parser:
      name: us-docker.pkg.dev/stackpulse/public/json-parser 
```

From there you can access the data by simply specifying the step and json path of the data you want.

For more information visit the [StackPulse Knowledge Base](https://support.stackpulse.io/hc/en-us) or [StackPulse Docs](https://docs.stackpulse.io).

