# mobile.okra.ng
Okra HTML page for webview

This page enable you to connect your applications to Okra as it fully supports webview for all mobile platform/frameworks.
It follows a 2 step process:

1. Sending data
2. Getting response 


### Sending Data
sending data is done by calling the `openOkraWidget(Option option)` javascript function of the page, the functionn takes an option paramater.
**note :** this call should be fired when the page has fully loaded (onPageLoad).

### Getting response
There are 3 response that are available by the `mobile.okra.ng`, they are:

1. OnSuccess
2. OnError
3. OnClose

#### OnSuccess 
OnSuccess sends back the response of the okra process, this include the `auth` `identity` `balance` and `transaction`.

for **android** this is the handler:
     `Android.onSuccess(JSON.stringify(json))`
     
for **IOS** this the handler:
`window.webkit.messageHandlers.jsMessageHandler.postMessage(JSON.stringify(json))`

#### OnError 
OnError sends back the error response of the okra process.

for **android** this is the handler:
     `Android.onError(JSON.stringify(json))`
     
for **IOS** this the handler:
` window.webkit.messageHandlers.jsErrorMessageHandler.postMessage(JSON.stringify(json))`

#### OnClose
OnClose is closed when the widget closes. This should hold what happens when the widget closes e.g switch to another page.

for **android** this is the handler:
     `Android.onClose(JSON.stringify(json))`
     
for **IOS** this the handler:
`window.webkit.messageHandlers.jsMessageHandler.postMessage(JSON.stringify(json))`

