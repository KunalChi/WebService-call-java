how to call a SOAP (JAX-WS) web service from Java and get its returning object. In that case, you have two possible approaches:


Create a SOAP client that:
Serializes the service's parameters to XML;
Calls the web method through HTTP manipulation; and
Parse the returning XML response back into an object.


A) Make the call:
Use the SAAJ (SOAP with Attachments API for Java) framework (see below, it's shipped with Java SE 1.6 or above) 
to make the calls; or You can also do it through java.net.HttpUrlconnection (and some java.io handling).

B) Turn the objects into and back from XML:
Use an OXM (Object to XML Mapping) framework such as JAXB to serialize/deserialize the XML from/into objects
Or, if you must, manually create/parse the XML (this can be the best solution if the received object is only a 
little bit differente from the sent one). Creating a SOAP client using classic java.net.HttpUrlConnection is not 
that hard (but not that simple either), 
and you can find in this link a very good starting code.
