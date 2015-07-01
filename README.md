# Anypoint Template: API Gateway External OAuth2 Provider

+ [License Agreement](#licenseagreement)
+ [Use Case](#usecase)
+ [Considerations](#considerations)
+ [Run it!](#runit)
	* [Running on premise](#runonopremise)
	* [Running on Studio](#runonstudio)
	* [Running on API Gateway stand alone](#runonmuleesbstandalone)
	* [Running on CloudHub](#runoncloudhub)
	* [Deploying your Anypoint Template on CloudHub](#deployingyouranypointtemplateoncloudhub)
	* [Properties to be configured (With examples)](#propertiestobeconfigured)
+ [Customize It!](#customizeit)
	* [config.xml](#configxml)
	* [businessLogic.xml](#businesslogicxml)
	* [endpoints.xml](#endpointsxml)
	* [errorHandling.xml](#errorhandlingxml)


# License Agreement <a name="licenseagreement"/>
Note that using this template is subject to the conditions of this [License Agreement](AnypointTemplateLicense.pdf).
Please review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with API Gateway, CloudHub, or as a trial in Anypoint Studio.

# Use Case <a name="usecase"/>
This new OAuth 2.0 Token Validation Policy allows you to use HTTPS communication and to configure a single OAuth provider for multiple APIs.

# Considerations <a name="considerations"/>
It is assumed that you are familiar with the [policy documentation](https://developer.mulesoft.com/docs/display/current/OAuth+2.0+Provider+and+AES+OAuth+2.0+Token+Enforcement+Policies).

# Run it! <a name="runit"/>
Simple steps to get API Gateway External OAuth2 Provider running.

## Running on premise <a name="runonopremise"/>
In this section we detail the way you should run your Anypoint Template on your computer.

### Where to Download Mule Studio and API Gateway
First thing to know if you are a newcomer to API Gateway is where to get the tools.

+ You can download Mule Studio from this [Location](http://www.mulesoft.com/platform/mule-studio)
+ You can download API Gateway from this [Location](https://www.mulesoft.com/ty/dl/api-gateway)

### Importing an Anypoint Template into Studio
Mule Studio offers several ways to import a project into the workspace, for instance: 

+ Anypoint Studio generated Deployable Archive (.zip)
+ Anypoint Studio Project from External Location
+ Maven-based Mule Project from pom.xml
+ API Gateway Configuration XML from External Location

You can find a detailed description on how to do so in this [Documentation Page](http://www.mulesoft.org/documentation/display/current/Importing+and+Exporting+in+Studio).

### Running on Studio <a name="runonstudio"/>
Once you have imported your Anypoint Template into Anypoint Studio you need to follow these steps to run it:

+ Locate the properties file `mule.dev.properties`, in src/main/resources
+ Complete all the properties required as per the examples in the section [Properties to be configured](#propertiestobeconfigured)
+ Once that is done, right click on you Anypoint Template project folder 
+ Hover you mouse over `"Run as"`
+ Click on  `"Mule Application"`

Note: It is assumed that the runtime defined on your project is API Gateway 2.0.0 or greater.

### Running on API Gateway stand alone <a name="runonmuleesbstandalone"/>
Complete all properties in one of the property files, for example in [mule.prod.properties](../master/src/main/resources/mule.prod.properties) and run your app with the corresponding environment variables to use it (additional details can be found [here](https://developer.mulesoft.com/docs/display/current/Configuring+an+API+Gateway)). To follow the example, this will be `mule.env=prod`. 

## Running on CloudHub <a name="runoncloudhub"/>
While [creating your application on CloudHub](http://www.mulesoft.org/documentation/display/current/Hello+World+on+CloudHub) (Or you can do it later as a next step), you need to go to Deployment > Advanced to set all environment variables detailed in **Properties to be configured** as well as the **mule.env**.

### Deploying your Anypoint Template on CloudHub <a name="deployingyouranypointtemplateoncloudhub"/>
Mule Studio provides you with really easy way to deploy your Template directly to CloudHub, for the specific steps to do so please check this [link](http://www.mulesoft.org/documentation/display/current/Deploying+Mule+Applications#DeployingMuleApplications-DeploytoCloudHub)

## Properties to be configured (With examples) <a name="propertiestobeconfigured"/>
In order to use this Mule Anypoint Template you need to configure properties (Credentials, configurations, etc.) either in properties file or in CloudHub as Environment Variables. Detail list with examples:
### Application configuration
#### Application configuration
+ https.port `eg 8082`

#### Environment related properties
Follow the instructions that can be found [here] (https://developer.mulesoft.com/docs/display/current/Walkthrough+Deploy+to+Gateway)

##### Keystore

+ key.store.password `eg mule1234`
+ key.store.key.password `eg mule1234`
+ key.store.path `eg keystore.jks`

##### Simple Validation

+ admin.name `eg admin`
+ admin.password `eg pass`

##### Endpoints

+ validate.endpoint.path `eg aes/external/validate`
+ authorization.endpoint.path `eg aes/external/authorize`
+ access.token.endpoint.path `eg aes/external/access-token`

##### Scopes

+ scopes `eg READ WRITE`

##### Supported Grant Types

+ supported.grant.types `eg AUTHORIZATION_CODE RESOURCE_OWNER_PASSWORD_CREDENTIALS CLIENT_CREDENTIALS IMPLICIT`
