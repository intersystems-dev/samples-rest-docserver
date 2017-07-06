# samples-rest-docserver
Provide a REST interface to the document server service This UrlMap maps http requests to the classmethod to which it should be dispatched Example usages. In these examples please replace the host name and port with appropriate values for your situation.

Get the text of the class Samples/Sample.Person 

curl http://localhost:57772/csp/samples/docserver/class/samples/Sample.Person

Get a list of namespaces on the target server (plain/text) 

curl http://localhost:57772/csp/samples/docserver/namespaces 

Get a list of namespaces on the target server (jason format) 

curl -H "Accept:application/json" http://localhost:57772/csp/samples/docserver/namespaces 

Display the contents of the http request ( shows how to manage cookies) Set the UseSession Parameter to 1 to enable CSP SESSIONS 

curl -v -b cookie.txt -c cookie.txt http://localhost:57772/csp/samples/docserver/request 

Echo the contents of a file sent to the server 

curl -v -X POST --data-binary @class.txt --header "Content-Type:text/plain" http://localhost:57772/csp/samples/docserver/echo 

Send the contents of a file representing the text of a class definition. Return a JSON encoded set of descriptors which define how the text should be syntax colored. 

curl -v -X POST --data-binary @class.txt --header "Content-Type:text/plain" -H "Accept:application/json" http://localhost:57772/csp/samples/docserver/colorclass 

Get a list of embedded languages for syntax coloring: 

curl -H "Accept:application/json" http://localhost:57772/csp/samples/docserver/languages 
