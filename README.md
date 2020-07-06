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
OnClose is called when the widget closes. This should hold what happens when the widget closes e.g switch to another page.

for **android** this is the handler:
     `Android.onClose(JSON.stringify(json))`
     
for **IOS** this the handler:
`window.webkit.messageHandlers.jsMessageHandler.postMessage(JSON.stringify(json))`


## Option

|Name                     | Type           | Required            | Default Value       | Description         |
|-----------------------  |----------------|---------------------|---------------------|---------------------|
|  `isWebview`             |`boolean`        | true              | false               | tells okras widget if this is from a webview
|    `source`            | `string`          | true              |  `''`                | used to determine which platform and and how the widget responds `android` or `ios`
|  `callback_url `        | `string`       | true                |  undefined          | 
|  `redirect_url `        | `string`       | true                |  undefined          | 
|  `key `                 | `String`       | true                |  undefined          | Your public key from Okra.
|  `token `               | `String`       | true                |  undefined          | Your token from your Okra Dashboard.
|  `products`             | `Array`.       | true                |  `['auth']`          | The Okra products you want to use with the widget. `['auth', 'balance', 'identity', 'transaction']`
|  `env`                  | `String`       | true                | `production`           |  `production` or `production-sandbox`
|  `clientName`          | `String`       | false               |  `This client`       | Name on the widget
|  `logo `                | `String(URL)`  | false               | Okra's Logo         | 
|  `color`                | `HEX   `       | false               | #3AB795             | Theme on the widget 
|  `limit`                | `Number`       | false               | 24                  | Statement length
|  `filter`               | `Object`       | false               |                     | Filter for widget
|  `corporate`            | `Boolen`       | false               | `false`             | Corporate or Individual account
|  `connectMessage`      | `String`       | false               |                     | Instruction to connnect account
|  `guarantors`            | `Object`       | false              |                     | 
|  `widget_success`       | `String`       | false               |                     | Widget Success Message
|  `widget_failed`        | `String`       | false               |                     | Widget Failed Message
|  `success_title`       | `String`       | false               |                     | Widget Success Message
|  `success_message`        | `String`       | false               |                     | Widget Failed Message
|  `currency`             | `String`       | false               | NGN                 | Wallet to bill
|  `exp`                  | `Date`         | false               | Won't expire        | Expirary date of widget



