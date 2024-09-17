# HackTheBox-BountyHunter-XXE-automation

This is a simple python script that automates the XXE portion of the retired HTB box "bountyhunter"
Since this box is retired, putting this script online won't be a problem.

USAGE: python exploit.py <IP_ADDRESS> <FILE>

The web application uses javascript to convert 3 given values into xml, base64 encode it and then send it over to the server.
Using a web application proxy like burpsuite we could cut the javascript part and send over an encoded xml ourselves, Since
we have the ability to skip over javascript by directly sending a POST request with a web app proxy, we can send our own 
base64 converted xml, This is exactly what the script does. It creates an xml text, puts an external entity pointing to
any file of our choice, base64 and url encodes it and send it over to the server.
