# Web Services — Odoo 17.0 documentazione

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](company.html "Multi-company Guidelines") |
  * [precedente](website_themes/going_live.html "Going live") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Web Services



# Web Services¶

The web-service module offers a common interface for all web services:

  * XML-RPC

  * JSON-RPC




Business objects can also be accessed via the distributed object mechanism. They can all be modified via the client interface with contextual views.

Odoo is accessible through XML-RPC/JSON-RPC interfaces, for which libraries exist in many languages.

## XML-RPC Library¶

The following example is a Python 3 program that interacts with an Odoo server with the library `xmlrpc.client`:
    
    
    import xmlrpc.client
    
    root = 'http://%s:%d/xmlrpc/' % (HOST, PORT)
    
    uid = xmlrpc.client.ServerProxy(root + 'common').login(DB, USER, PASS)
    print("Logged in as %s (uid: %d)" % (USER, uid))
    
    # Create a new note
    sock = xmlrpc.client.ServerProxy(root + 'object')
    args = {
        'color' : 8,
        'memo' : 'This is a note',
        'create_uid': uid,
    }
    note_id = sock.execute(DB, uid, PASS, 'note.note', 'create', args)
    

Exercise

Add a new service to the client

Write a Python program able to send XML-RPC requests to a PC running Odoo (yours, or your instructor’s). This program should display all the sessions, and their corresponding number of seats. It should also create a new session for one of the courses.

Vedi anche

  * [External API](../reference/external_api.html): The in-depth tutorial on XML-RPC, with examples spanning multiple programming languages.




## JSON-RPC Library¶

The following example is a Python 3 program that interacts with an Odoo server with the standard Python libraries `urllib.request` and `json`. This example assumes the **Productivity** app (`note`) is installed:
    
    
    import json
    import random
    import urllib.request
    
    HOST = 'localhost'
    PORT = 8069
    DB = 'openacademy'
    USER = 'admin'
    PASS = 'admin'
    
    def json_rpc(url, method, params):
        data = {
            "jsonrpc": "2.0",
            "method": method,
            "params": params,
            "id": random.randint(0, 1000000000),
        }
        req = urllib.request.Request(url=url, data=json.dumps(data).encode(), headers={
            "Content-Type":"application/json",
        })
        reply = json.loads(urllib.request.urlopen(req).read().decode('UTF-8'))
        if reply.get("error"):
            raise Exception(reply["error"])
        return reply["result"]
    
    def call(url, service, method, *args):
        return json_rpc(url, "call", {"service": service, "method": method, "args": args})
    
    # log in the given database
    url = "http://%s:%s/jsonrpc" % (HOST, PORT)
    uid = call(url, "common", "login", DB, USER, PASS)
    
    # create a new note
    args = {
        'color': 8,
        'memo': 'This is another note',
        'create_uid': uid,
    }
    note_id = call(url, "object", "execute", DB, uid, PASS, 'note.note', 'create', args)
    

Examples can be easily adapted from XML-RPC to JSON-RPC.

Nota

There are a number of high-level APIs in various languages to access Odoo systems without _explicitly_ going through XML-RPC or JSON-RPC, such as:

  * <https://github.com/akretion/ooor>

  * <https://github.com/OCA/odoorpc>

  * <https://github.com/nicolas-van/openerp-client-lib>

  * <http://pythonhosted.org/OdooRPC>

  * <https://github.com/abhishek-jaiswal/php-openerp-lib>




[ __Edit on GitHub](https://github.com/odoo/documentation/edit/17.0/content/developer/howtos/web_services.rst)

### Navigazione

  * [indice](../../genindex.html "Indice generale")
  * [moduli](../../py-modindex.html "Indice del modulo Python") |
  * [successivo](company.html "Multi-company Guidelines") |
  * [precedente](website_themes/going_live.html "Going live") |
  * [Odoo 17.0 documentazione](../../index-2.html) »
  * [Developer](../../developer.html) »
  * [How-to guides](../howtos.html) »
  * Web Services


  *[ORM]: Object-Relational Mapping
  *[SQL]: Structured Query Language
  *[PR]: Pull Request
  *[CI]: Continuous integration