# LF7_CPS
Sketches und Python Code für Lernfeld 7<br>
Hier werden Python Programme und Arduino-Sketches für das Lernfeld 7 abgelegt.<br>
Derzeit werden Python Programme für den Raspi, den Laptop und den PC hier gehalten.<br>
Die Programme erhalten über die dedizierte Schnittstelle /dev/ttyACMX oder COMY<br>
mit X für 0 oder 1 und Y für die Nummer, die der Windows Gerätemanager vergibt,<br>
Daten von Sensoren am Arduino (Raspi ein DHT22 auf Mega; PC/LT je einen DHT 11 und DHT22.<br>
Es handelt sich dabei um eine Zeichenkette der Form:<br>
"Raum: <Wert>; Temperatur: <WERT>; Feuchte: <Wert>" oder <br>
"Raum: <Wert>; Fehler beim Lesen der Sensorwerte!"<br>
die alle 10 Minuten vom UNO bzw MEGA ausgegeben wird.<br>
Als Raum dienen die Nummern der Sensoren mit einer laufenden Nummer<br>
z.B. 111 für den ersten DHT11 oder 222 für den zweiten DHT22<br>
Am UNO wird derzeit nur ein Sensor betrieben und die Zeichenkette vom<br>
Programm DHT11_Werte_raspi ausgewertet.<br>
Das Ergebnis der Auswertung der Zeichenkette wird in eine Datenbank (XAMP)<br>
eines lokalen oder alternativ per VPN angebundenen Servers geschrieben.<br>
Aktoren sind derzeit nicht berücksichtigt.<br>
Stand 06.Jan 2025<br><br>

In Vorbereitung ist ein Programm und ein entsprechender Sketch, dass/der<br>
die Abfrage der Sensoren vom Host (PC/LT/Raspi) initiiert (Polling).<br>

Das ist nun soweit fertig. <hos>_triggers_myC.py<br>
Dafür gibt es auch einen entpechenden Sketch. sketch_host_triggers_sensors<br>
Dabei geht es darum, dass der Host den Arduino nach werten befragt, woraufhin<br>
der Arduino antwortet. Das ist z.B erforderlich, wenn man vom Host etwas auf dem<br>
Arduino auslösen möchte. Im Rahmen eines CPS wäre es aufgrund von abgefragten<br>
SensorwertenBerechnungen entsprechende Aktoren zu steuern<br>
