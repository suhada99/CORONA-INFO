# VIRUS CORONA UPDATE INDONESIA

### CO.VID19.ID

Version BASH 
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
