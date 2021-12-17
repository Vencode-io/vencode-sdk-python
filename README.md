# Vencode Python SDK

Vencode provides an extensive and simple API and SDK for transcoding video in the cloud - you can find out more here https://vencode.io.

---

## View our documentation
For better and clearer documentation, please visit **https://docs.vencode.io**

### Before you start, you'll need
- Python 3.X
- Your API Key and User ID from https://app.vencode.io/access

---

### Basic Setup
- `pip install vencode-sdk`
- Import in your project and create a new instance of the Client

```py
from vencode_sdk import Client, Options, Access, Credentials

client = Client(options=Options(
  access=Access(
    key="******",
    id="usr_******"
  ),
  credentials=Credentials(
    clientId="***",
    clientSecret="***",
    type="s3",
    bucket="cdn.vencode.io"
  )
))
```
- You're ready to go!

---

### Create Job
```py
from vencode_sdk.options import CreateEncodeJobOptions, Encode, Input, Output

outputs = []
outputs.append(Output(
    key="path/to/video.mp4",
    encode=Encode(
        format="mp4"
    ),
))

job = client.encode(encode=CreateEncodeJobOptions(
    input=Input(path="https://url-to-video/video.mp4"),
    outputs=outputs
))

print(job)
```
