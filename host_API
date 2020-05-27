# -*- coding: utf-8 -*-
#import 
import requests, json

#call Shodan.io
def call_shodan(ip,key):
  start = "https://api.shodan.io/shodan/host/"
  end = "&minfiy"
  call = start + ip + "?key=" + key + end
  r = requests.get(call)
  result = r.text
  return(r,result)

#parser JSON
def parser(data) :
  parsed_json = json.loads(data)
  region = parsed_json['region_code'] 
  ports = parsed_json['ports']
  org = parsed_json['org']
  return(region,ports,org)

#main
address = "11.22.33.44"
key  = "myAPIkeyHere"
cr, data = call_shodan(address,key)
region, ports, org = parser(data)
print("bilan appel : " + str(cr))
print("L'adresse IP " + address + " appartient à la région de " + str(region) + " et le(s) port(s) : " + str(ports) + " sont visibles")
print("L'opérateur suivant a été trouvé : " + str(org))
