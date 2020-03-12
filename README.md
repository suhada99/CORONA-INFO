# VIRUS CORONA UPDATE INDONESIA

### CO.VID19.ID

API : https://co.vid19.id/api/dashboard

#### BASH
```
#!/bin/bash
# @author : Rafshanzani Suhada
# Corona update indonesian!

API="https://co.vid19.id/api/dashboard" # By co.vid19.id
MengirimData(){
 echo "HARI INI  : $1" 
 echo "POSITIF   : $2"
 echo "SEMBUH    : $3"
 echo "MENINGGAL : $4"
}

MengambilData(){
 Hari_ini=$(curl -s "${API}" | jq .today_case)
 Positif=$(curl -s "${API}" | jq .total_case)
 Sembuh=$(curl -s "${API}" | jq .total_recovered)
 Meninggal=$(curl -s "${API}" | jq .total_death)
 MengirimData $Hari_ini $Positif $Sembuh $Meninggal
}
clear
echo " ====== CORONA UPDATE ======"
echo " @author : Rafsanzani Suhada"
echo " ==========================="
while true
do
 MengambilData $asal
 sleep 480s
 clear
done
```
#### PYTHON
```
#!/usr/bin/python
# @author : Rafshanzani Suhada
# Corona update indonesian!

import requests, time, json
API="https://co.vid19.id/api/dashboard" # By co.vid19.id

def MengirimData(Hari_Ini, Positif, Sembuh, Meninggal):
 print "HARI INI  : {}".format(Hari_Ini)
 print "POSITIF   : {}".format(Positif)
 print "SEMBUH    : {}".format(Sembuh)
 print "MENINGGAL : {}".format(Meninggal)

def MengambilData():
 try:
  R = requests.get('{}'.format(API))
  PD = json.loads(R.text)
  Hari_Ini = PD['today_case']
  Positif = PD['total_case']
  Sembuh = PD['total_recovered']
  Meninggal = PD['total_death']
  MengirimData(Hari_Ini, Positif, Sembuh, Meninggal)
 except Exception as e:
  raise
print " ====== CORONA UPDATE ======"
print " @author : Rafsanzani Suhada"
print " ==========================="
while True:
 MengambilData()
 time.sleep( 5 )
```
