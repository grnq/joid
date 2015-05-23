JOID is an OpenID 1.x/2.0 Java library that lets you implement
providers as well as relying parties. JOID compiles under JDK 1.4 or later.
## Flows ##

UsageFlows describes the common usage flows.

## Usage ##
The over-riding design goal of JOID is simplicity of use. The javadocs will
tell you more, but the main use case is:

```
// Get a store implementation (used to handle associations).
Store store = ...

// Get an OpenID implementation
OpenId openId = new OpenId(store);

// Process the request into a response
String response = openid.handleRequest(query);
```

JOID processes messages by using a factory to parse the request, and then
use this request to generate a response.

If you wish, you can also drop down
to a slightly lower level, for example, should you need to specify which type of crypto
implementation to use, or if you need to inspect incoming requests or outgoing
responses.

It's still a very simple API:

```
// Parse the incoming message
Request req = RequestFactory.parse(string);

// Get a store implementation (used to handle associations) and a 
// crypto implementation (to handle the OpenID protocol crypto)
Store store = ...
Crypto crypto = ...

// Use the request and process with the store and crypto to
// produce a response
Response resp = req.processUsing(store, crypto);
```


## JOID Enabling Your Application ##

[OpenIDConsumer](OpenIDConsumer.md)

## Setting Up A JOID Server ##

ServerInstallation

## Mailing lists ##
JOID has two mailing lists, both public to join:

| **Type** | **URL** |
|:---------|:--------|
| General  | http://groups.google.com/group/joid-general |
| Developer | http://groups.google.com/group/joid-dev |