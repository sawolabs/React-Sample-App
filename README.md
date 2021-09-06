# SAWO React 
React is a free and open-source front-end JavaScript library for building user interfaces or UI components. It is maintained by Facebook. Several useful applications can be built through this library.
# Requirements
Node [Version 12.x+ ] , Node Package Manager (NPM) [Version 6.x+]

### Steps
1.The first step to getting started with SAWO API integration into your React web page is to install the sawo package as given below:
```
npm i sawo

```
2.After installation is done, you have to import the Sawo class from the installed sawo package to the top of the file:
```
import Sawo from "sawo"

```
3.To use SAWO Login you would need an API key which can be obtained by creating a project in the 
[sawo dashboard](https://dev.sawolabs.com/)
4.Once you create your project, you would need to set your project name and hostname.
  1. For development in a local machine, the hostname should be set to 'localhost'.
  2. For production, the hostname should be set to your domain. 
5.Copy the API key from the project and keep it safe and secure.
6.Initialize SAWO and render the form according to the following steps:
  1. As part of this step, a container has to be created for the SAWO component. This has to be done on your project’s source file.
```
<div id="sawo-container" style="height: 300px; width: 400px;"></div>

```
  2. Some configurations have to be checked as given below. The code given below should help in the same.
```
 var config = {
        // should be same as the id of the container created on 3rd step
        containerID: "<container-ID>",
        // can be one of 'email' or 'phone_number_sms'
        identifierType: "phone_number_sms",
        // Add the API key copied from 2nd step
        apiKey: "",
        // Add a callback here to handle the payload sent by sdk
        onSuccess: (payload) => {},
    };

```
  3. Then a SAWO instance has to be created using the code given below:
```
let sawo = new Sawo(config)

```
  4. The showForm method should be called thereafter as the showForm method is responsible for rendering the form in the given container.
```
sawo.showForm()

```
7. Below code-block can be used as a reference after you have completed setting up your project:
```
import React, { useEffect } from 'react'
import Sawo from 'sawo'

const LoginPage = () => {
    useEffect(() => {
        var config = {
            // should be same as the id of the container created on 3rd step
            containerID: '<container-ID>',
            // can be one of 'email' or 'phone_number_sms'
            identifierType: 'phone_number_sms',
            // Add the API key copied from 5th step
            apiKey: '',
            // Add a callback here to handle the payload sent by sdk
            onSuccess: payload => {
                // you can use this payload for your purpose
            },
        }
        let sawo = new Sawo(config)
        sawo.showForm()
    }, [])

    return (
        <div>
            <div id="sawo-container" style="height: 300px; width: 300px;"></div>
        </div>
    )
}

export default LoginPage

```
8. Once the SAWO SDK is successfully set up, a login form will be rendered in the provided container 


