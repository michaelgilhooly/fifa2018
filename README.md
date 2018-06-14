import urllib.request
import json

endpoints = ['worldcup.json',
             'worldcup.groups.json',
             'worldcup.stadiums.json',
             'worldcup.standings.json',
             'worldcup.teams.json']

for endpoint in endpoints:
    print ("Endpoint:", endpoint)
    contents = urllib.request.urlopen("https://raw.githubusercontent.com/openfootball/world-cup.json/master/2018/" + endpoint).read()
    response = json.loads(contents.decode())
    print (json.dumps(response, indent=4, sort_keys=True))