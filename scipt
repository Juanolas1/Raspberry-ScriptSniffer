#!/bin/sh
if [ «$(ping -w 5 google.com)» == «$ping: unknown host google.com» ]; then
echo «>No hay salida a Internet»
tshark -nni eth0 -a filesize:2 -a files:1 -w /tmp/capturas/1234.pcap
echo » Capturas ejecutadas»
else
echo «>Hay salida a Internet»
tshark -nni eth0 -a filesize:200 -a files:1 -w /tmp/capturas/prueba.pcap
echo «Esperando 5 segundos» sleep 5;
tar -zcvf raspberry.tar.gz /tmp/capturas/
sleep 5s;
mpack -s «Capturas PCAP» /tmp/raspberry.tar.gz juanolas@gmail.com
echo «Correo enviado»
fi
