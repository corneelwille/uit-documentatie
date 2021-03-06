---
---

# Test mailing versturen

```{server}/mailing/v2/{ID}/test```

waarbij {ID} de ID van de mailing is

* Method: POST
* Authenticatie:  UserAccessToken van de gebruiker die admin permissie op de Service Consumer heeft

## Parameters

| Parameter | Beschrijving
| userId | UiD van de UiTiD user waarnaar de testmail gestuurd moet worden (verplicht)

## Response

### Succes  

HTTP 200 OK met een response body in XML formaat

* code: Status code string

### Fout

HTTP status code, eventueel aangevuld met een XML body met extra informatie.

* HTTP 403 Forbidden: er werd geen of geen geldig UserAccessToken meegestuurd.
* HTTP 401 Unauthorized: de gebruiker heeft geen rechten om de huidige actie uit te voeren. (bv. is geen admin van de Service Consumer)

## Voorbeeld

Request

```
POST {server}/mailing/3/test
```

Response

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<response>  
<code>MailingTestSent</code>  
</response> {%endhighlight %}
