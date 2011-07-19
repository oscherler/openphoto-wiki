Open Photo API / Hello
=======================
#### OpenPhoto, a photo service for the masses

----------------------------------------

1. [Purpose][purpose]
1. [Endpoint][endpoint]
1. [Parameters][parameters]
1. [Examples][examples]
  * [Curl][example-curl]
  * [PHP][example-php]
1. [Response][response]
  * [Sample][sample]

----------------------------------------

<a name="purpose"></a>
### Purpose of the Get Photo API

Hello world.

----------------------------------------

<a name="endpoint"></a>
### Endpoint

_Authentication: optional_

    GET /hello.json

<a name="parameters"></a>
### Parameters

_None_

----------------------------------------

<a name="examples"></a>
### Examples

<a name="example-curl"></a>
#### Command line curl

    curl http://jmathai.openphoto.me/hello.json

<a name="example-php"></a>
#### PHP

    $ch = curl_init('http://jmathai.openphoto.me/hello.json');
    curl_exec($ch);

----------------------------------------

<a name="response"></a>
### Response

The response is in a standard [response envelope][Envelope].

* _message_, A string describing the result. Don't use this for anything but reading.
* _code_, _200_ on success
* _result_, A [Photo][Photo] object

<a name="sample"></a>
#### Sample

    {
      "message":"",
      "code":200,
      "result":"Hello, world!"
    }

[Envelope]: api/Envelope.markdown
[purpose]: #purpose
[endpoint]: #endpoint
[parameters]: #parameters
[examples]: #examples
[example-curl]: #example-curl
[example-php]: #example-php
[response]: #response
[sample]: #sample