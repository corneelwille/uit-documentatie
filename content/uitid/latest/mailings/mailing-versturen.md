---
---

# Mailing versturen

```{server}/mailing/v2/{ID}/send```

waarbij {ID} de ID van de mailing is

* Methode: POST
* Authenticatie: UserAccessToken van de gebruiker die admin permissie op de Service Consumer heeft

## Response

**Response**  

_Bij succes_  

HTTP 200 OK met een response body in XML formaat  

* code: Status code string

### Fout

HTTP status code, eventueel aangevuld met een XML body met extra informatie.

* HTTP 403 Forbidden: er werd geen of geen geldig UserAccessToken meegestuurd.
* HTTP 401 Unauthorized: de gebruiker heeft geen rechten om de huidige actie uit te voeren. (bv. is geen admin van de Service Consumer)

## Voorbeeld

Request

```
GET {server}/mailing/3/send
```

Response

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<response>  
<code>MailingScheduled</code>  
</response> {%endhighlight %}
