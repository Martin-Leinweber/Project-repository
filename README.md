# Stundenprotokoll

[Dienstag, 03. August 2021](#1)

[Mittwoch, 04. August 2021](#2)

[Dienstag, 10. August 2021](#3)

[Mittwoch, 11. August 2021](#4)

[Dienstag, 17. August 2021](#5)

[Mittwoch, 18. August 2021](#6)

[Dienstag, 24. August 2021](#7)

[Mittwoch, 25. August 2021](#8)

[Dienstag, 31. August 2021](#9)

[Mittwoch, 01. September 2021](#10)

[Dienstag, 07. September 2021](#11)

[Mittwoch, 08. September 2021](#12)

[Dienstag, 14. September 2021](#13)

[Mittwoch, 15. September 2021](#14)

[Dienstag, 21. September 2021](#15)

[Mittwoch, 22. September 2021](#16)

[Dienstag, 28. September 2021](#17)

[Mittwoch, 29. September 2021](#18)

[Dienstag, 19. Oktober 2021](#19)

[Mittwoch, 20. Oktober 2021](#20)

[Dienstag, 26. Oktober 2021](#21)

[Mittwoch, 27. Oktober 2021](#22)

[Dienstag, 02. November 2021](#23)

[Mittwoch, 03. November 2021](#24)

[Dienstag, 09. November 2021](#25)

[Mittwoch, 10. November 2021](#26)

[Dienstag, 16. November 2021](#27)

[Mittwoch, 17. November 2021](#28)

[Dienstag, 23. November 2021](#29)

[Mittwoch, 24. November 2021](#30)

[Dienstag, 30. November 2021](#31)

[Dienstag, 01. Dezember 2021](#32)


### <a name="1"></a>Dienstag, 03. August 2021
Heute, in der ersten Informatikstunde, wurden wir informiert was in Zukunft in diesem Fach auf uns zukommen wird, und wie das ganze Ablaufen wird.
Anschließend haben wir uns unsere GitHub Accounts eingerichtet und uns mit dieser Plattform etwas vertraut gemacht. Zwischendurch haben wir uns schon einige Projektideen ausgedacht und diese besprochen.

### <a name="2"></a>Mittwoch, 04. August 2021

Wir haben an der letzten Stunde angeknüpft, und uns weiter mit den Funktionen von Markdown auseinandergesetzt. Wir haben dieses Repository erstellt und mit den Blogeinträgen angefangen. Außerdem haben wir weiter über Projektideen gegrübelt.

### <a name="3"></a>Dienstag, 10. August 2021
Heute haben wir weiter über Projektideen nachgedacht und intensiv über deren Machbarkeit diskutiert.

### <a name="4"></a>Mittwoch, 11. August 2021
Heute haben wir uns auf eine Projektidee festgelegt. Unser Plan ist es einen Arcade-Spielekasten zu bauen, dessen Spielinhalt nicht auf einem Bildschirm, sondern mit echten Modellen dargestellt wird. Es soll in dem Spiel um einen Flugzeug Luftkampf, auf Englisch Dogfight genannt, gehen. Das verfolgende Flugzeug soll vom Spieler gesteuert werden und muss ein automatisch gesteuertes gegnerisches Flugzeug abschießen.

### <a name="5"></a>Dienstag, 17. August 2021
Heute haben wir uns überlegt, wie man überprüfen kann, ob der Spieler das andere Flugzeug wirklich getroffen hat. Eine Überlegung war es, die schienen auf denen sich die Flugzeuge bewegen mit Linearwidertänden auszustatten, und auf die weise die Positionen der Flugzeuge zu berechnen. Nach kurzer Recherche über die dafür benötigten Bauteile haben wir diese Idee wieder verworfen. Dann kamen wir auf die Idee, dass man an dem verfolgenden Flugzeug einen Laser befestigen könnte und am verfolgten Flugzeug einen Fotowiderstand. Wenn der Laser den Fotowiderstand trifft, kann der Arduino  dies Messen.

### <a name="6"></a>Mittwoch, 18. August 2021
Heute haben wir getestet, ob unsere Idee zur Treffererkennung des gegnerischen Flugzeuges mittels eines Fotowiderstandes und eines Laserpointers funktionieren könnte. Also haben wir mit dem Fotowiderstand und einem weiteren Widerstand einen Spannungsteiler aufgebaut und getestet ob bei direktem Beleuchten mit einem Laserpointer der Spannungsunterschied zum normalen Tageslicht groß genug ist, um ihn eindeutig auszulesen. Der Code sowie der Schaltkreis und ein Screenshot des Seriellen Monitors finden sich im Folgenden.

![Screenshot 2021-12-05 174717](https://user-images.githubusercontent.com/88385986/144761199-aa851cea-45b3-4096-9701-6276cc0a39f1.png)
```c

void setup() {

  Serial.begin(9600);
}


void loop() {
 
  int sensorValue = analogRead(A0);

  Serial.println(sensorValue);
  delay(1);        
}
```

### <a name="7"></a>Dienstag, 24. August 2021
Am heutigen Tage haben wir als erstes etwas mit dem Großen Logitech Joystick beschäftigt. D.h. die Analogsignale der beiden Achsenpotentiometer auslesen und auf bestimmten Pins ein entsprechende Analogsiganl ausgeben. Hierzu mussten wir zunächst mittels eines Multimeters und dessen Kontaktprüfungs Funktion ermitteln welche Pins des Sub-D Steckers zu welchen Kabeln im inneren gehören. Außerdem müssen wir eine zusätliche Leitung anbringen, da die zwei Achsenpotentiometer im Joystick nicht als Spannungsteiler, also mit allen 3 Kontakten, sondern nur mit 2 Kontakten als variablen Widerstand genutzt wurden. Das neue Kabel ist also der Ground für beide Potentiometer. Das neue Kabel wird mittels aufgekrimpter Flachstecker an die Potentiometer angeschlossen. Mit den genannten Arbeitsschritten sind wir in der heutigen Unterrichtseinheit leider nicht fertig geworden.



### <a name="8"></a>Mittwoch, 25. August 2021
Heute haben wir die am Vortag genannten Arbeitsschritte beendigt. Die Verkabelung des Joysticks ist nun wie auf dem Schaubild zu sehen. Der Joystick wird im Schaubild durch zwei Potentiometer dargestellt.

![Screenshot 2021-12-05 175220](https://user-images.githubusercontent.com/88385986/144758447-55c91426-aac9-4c53-9be6-37864bfed54b.png)

### <a name="9"></a>Dienstag, 31. August 2021
Da uns in der letzten Stunde bereits aufgefallen ist, dass der Abzug des Joysticks nicht mehr funktionstüchtig ist, haben wir uns heute mit der Reparatur des selbigen befasst. Hierzu wurde der Taster ausgebaut und die Kontaktflächen gereinigt. Außerdem musste das Kontaktfähnchen etwas nachgebogen werden. Danach hat der Taster wieder einwandfrei funktioniert. Weiterführend haben wir angefangen einen kurzen Testcode für den Arduino zu schreiben mit welchem wir den Laserpointer mittels Knopfdruck des Joysticks aktivieren können. Die Laserdiode haben wir bereits zu Hause ausgebaut, jedoch mussten noch zwei Kabel an diese gelötet werden, um diese mit dem Steckbrett verwenden zu können. 

```c
const int TriggerPin = 2;     // Der Digital Pin 2 des Arduinos bekommt den Namen "TriggerPin"
const int LaserPin =  13;     // Der Digital Pin 13 des Arduinos bekommt den Namen "LaserPin"


int buttonState = 0;          // Die Variabel welche für AN und AUS steht bekommt den Namen "buttonState"

void setup() {
  pinMode(LaserPin, OUTPUT);  // Der "LaserPin" wird als Output Pin definiert
 
  pinMode(TriggerPin, INPUT);   // Der "TriggerPin" wird als Input Pin definiert
}

void loop() {

  buttonState = digitalRead(TriggerPin); /* Es wird festgelegt, dass die Variable "buttonState" ab jetzt einem Wert gleichgesetzt ist, nämlich dem Input Wert. Dieser 
  kann entweder HIGH sein, dann liegen 5V an diesem an, oder LOW sein, dann liegne 0V an.*/


  if (buttonState == HIGH) {      // Es wird eine Bedingung aufgestellt, nur wenn diese Erfüllt ist wird der Inhalt ausgeführt.
    
    digitalWrite(LaserPin, HIGH); // Am Output Pin werden 5V angelegt
  }
  else {            
     digitalWrite(LaserPin, LOW); // Wenn die vorangegangene Bedingung nicht erfüllt ist, wird die Spannung am OutputPin auf 0V gesetzt
  }
}
```



### <a name="10"></a>Mittwoch, 01. September 2021
Nach dem nun der Abzug des Joysticks benutzbar ist haben wir uns damit auseinander gesetzt, wie man mit einem Arduino Sounddateien abspielen kann. Hierzu haben wir einen kleinen 0,5W Lautsprecher benutzt. Um MP3 Dateien ohne Erweiterungsmodul abspielen zu können, muss diese in dekodierter Form in den Arduino Code geschrieben werden. Das heißt, im Code steht in Zahlenwerten wie lange und wie stark Strom durch den Elektromagneten des Lautsprechers fließen soll. Somit wird ein Klang erzeugt. Um dies auszuführen haben wir eine Libary eines anderen Nutzers genutzt. Die Dekodierung der MP3 Datei haben wir mit einem kleinen JavaScript gemacht, welches wir auf GitHub gefunden haben. Unser Test Sound war ein kurzes Geräusch einer Laserkanone.


### <a name="11"></a>Dienstag, 07. September 2021
Heute haben wir am letzten Mittwoch angeknüpft und uns weiter mit der Libary zum Abspielen von Sounds befasst, bis wir das ganze zum Laufen gebracht haben. Im Folgenden findet sich der entsprechende Code.
```c
#include <PCM.h>
    const unsigned char sample[] PROGMEM = {
129, 128, 126, 129, 129, 125, 128, 130, 126, 126, 129, 128, 126, 128, 128, 127, 127, 128, 128, 127, 126, 128, 130, 125, 125, 132, 128, 122, 130, 133, 122, 124, 135, 127, 120, 131, 133, 121, 126, 133, 125, 124, 131, 128, 125, 129, 127, 127, 129, 127, 126, 128, 129, 127, 126, 129, 130, 123, 127, 135, 124, 120, 137, 131, 114, 132, 140, 114, 122, 144, 123, 115, 139, 132, 116, 130, 135, 123, 124, 131, 130, 125, 125, 131, 130, 121, 128, 135, 122, 124, 137, 124, 121, 136, 126, 120, 136, 126, 118, 137, 130, 115, 134, 135, 116, 127, 137, 123, 122, 133, 130, 125, 124, 130, 135, 120, 122, 143, 124, 110, 143, 136, 105, 135, 146, 108, 121, 149, 121, 113, 142, 131, 114, 132, 135, 123, 126, 129, 130, 128, 123, 131, 131, 121, 129, 131, 123, 131, 128, 119, 135, 134, 112, 131, 145, 110, 118, 154, 121, 105, 146, 135, 107, 133, 142, 117, 120, 137, 131, 121, 124, 132, 133, 122, 120, 139, 132, 110, 130, 144, 121, 115, 133, 141, 119, 109, 149, 143, 95, 125, 159, 114, 105, 153, 141, 97, 126, 153, 117, 119, 140, 120, 127, 133, 118, 139, 136, 109, 125, 140, 129, 119, 128, 141, 117, 117, 150, 126, 103, 138, 145, 112, 121, 161, 118, 77, 159, 168, 83, 120, 167, 114, 101, 144, 149, 108, 109, 148, 131, 123, 138, 115, 119, 133, 131, 137, 116, 130, 136, 102, 152, 142, 77, 151, 157, 89, 137, 144, 118, 132, 118, 129, 130, 117, 141, 132, 128, 124, 110, 145, 114, 109, 186, 116, 81, 166, 126, 105, 142, 108, 138, 166, 102, 103, 151, 128, 103, 152, 138, 81, 161, 162, 68, 154, 149, 47, 165, 195, 68, 111, 174, 116, 103, 148, 114, 93, 192, 147, 55, 176, 136, 39, 198, 155, 45, 197, 153, 31, 165, 194, 59, 85, 211, 139, 35, 180, 193, 26, 135, 215, 61, 80, 185, 162, 108, 99, 143, 122, 92, 174, 167, 67, 94, 183, 164, 79, 103, 167, 114, 101, 161, 154, 118, 80, 114, 194, 129, 67, 139, 172, 121, 81, 142, 188, 76, 68, 197, 169, 91, 98, 126, 145, 114, 137, 184, 97, 75, 145, 125, 133, 156, 126, 136, 115, 78, 134, 169, 141, 108, 105, 154, 152, 90, 99, 150, 156, 128, 108, 120, 126, 125, 149, 147, 110, 96, 126, 154, 126, 99, 158, 189, 95, 40, 124, 172, 147, 163, 132, 61, 120, 173, 108, 89, 135, 180, 181, 89, 46, 123, 179, 168, 100, 66, 163, 189, 96, 92, 137, 134, 129, 124, 131, 132, 116, 137, 147, 124, 113, 99, 122, 158, 134, 134, 143, 103, 111, 132, 118, 139, 139, 107, 139, 168, 114, 70, 127, 187, 115, 65, 172, 190, 68, 93, 180, 115, 89, 163, 148, 106, 122, 126, 127, 132, 130, 138, 120, 111, 142, 129, 112, 135, 134, 138, 133, 95, 120, 157, 129, 114, 122, 136, 144, 115, 107, 137, 149, 127, 95, 127, 163, 110, 118, 160, 103, 114, 158, 110, 126, 139, 102, 164, 146, 53, 142, 179, 90, 144, 163, 64, 111, 180, 112, 116, 167, 104, 95, 179, 130, 66, 149, 152, 101, 170, 141, 53, 150, 168, 70, 150, 174, 59, 128, 198, 96, 110, 160, 78, 111, 213, 114, 30, 172, 222, 72, 73, 174, 107, 103, 208, 118, 36, 165, 197, 96, 91, 132, 123, 120, 163, 174, 95, 69, 147, 156, 102, 121, 158, 128, 96, 135, 166, 124, 88, 103, 154, 190, 103, 43, 170, 194, 59, 110, 217, 108, 38, 158, 213, 111, 46, 115, 165, 129, 140, 169, 112, 78, 126, 155, 136, 114, 130, 155, 121, 78, 122, 172, 131, 84, 129, 175, 138, 94, 101, 135, 163, 142, 117, 135, 102, 73, 165, 195, 92, 77, 145, 150, 117, 100, 137, 197, 150, 52, 78, 159, 168, 151, 136, 93, 89, 137, 132, 86, 117, 188, 196, 140, 63, 54, 145, 194, 130, 87, 136, 180, 141, 74, 82, 134, 127, 100, 130, 175, 185, 164, 122, 90, 81, 72, 89, 170, 234, 179, 80, 58, 99, 138, 141, 110, 120, 186, 185, 104, 70, 110, 161, 170, 116, 78, 114, 138, 108, 106, 149, 177, 166, 132, 100, 100, 116, 113, 98, 116, 172, 199, 160, 113, 99, 86, 67, 91, 152, 182, 168, 145, 128, 124, 135, 120, 69, 59, 129, 206, 212, 155, 85, 51, 82, 139, 149, 120, 115, 151, 193, 192, 128, 68, 60, 83, 113, 142, 160, 173, 174, 146, 105, 82, 91, 121, 137, 122, 108, 125, 161, 184, 169, 123, 90, 99, 121, 117, 99, 98, 115, 139, 163, 185, 188, 155, 100, 71, 79, 91, 99, 122, 155, 178, 178, 164, 141, 112, 87, 78, 90, 122, 154, 155, 119, 91, 118, 178, 201, 162, 113, 96, 100, 105, 115, 122, 101, 72, 87, 152, 215, 229, 195, 136, 83, 62, 76, 96, 101, 109, 135, 158, 155, 142, 142, 150, 149, 136, 117, 99, 92, 108, 134, 147, 144, 139, 125, 94, 68, 86, 143, 198, 215, 193, 148, 99, 65, 58, 75, 103, 129, 146, 150, 149, 153, 159, 157, 142, 122, 104, 93, 91, 98, 115, 141, 169, 177, 151, 111, 90, 99, 121, 134, 134, 126, 118, 125, 147, 171, 176, 156, 115, 68, 37, 48, 102, 166, 203, 204, 181, 146, 113, 93, 86, 88, 104, 132, 151, 142, 115, 100, 112, 143, 179, 203, 189, 127, 51, 14, 35, 91, 154, 207, 233, 218, 164, 99, 55, 52, 85, 127, 149, 145, 130, 117, 108, 110, 131, 160, 177, 174, 160, 143, 119, 93, 72, 62, 63, 81, 122, 179, 225, 231, 190, 122, 59, 33, 52, 104, 165, 210, 215, 176, 110, 52, 30, 54, 107, 164, 199, 201, 172, 127, 90, 81, 101, 134, 156, 153, 128, 96, 81, 97, 139, 181, 198, 178, 129, 75, 45, 56, 103, 165, 209, 213, 175, 111, 53, 26, 41, 92, 160, 217, 238, 213, 155, 90, 47, 46, 87, 148, 193, 197, 156, 91, 35, 20, 56, 131, 212, 255, 255, 207, 124, 46, 1, 3, 45, 111, 175, 214, 218, 188, 139, 92, 69, 77, 112, 160, 198, 207, 181, 128, 68, 22, 7, 30, 86, 155, 217, 250, 244, 200, 134, 69, 31, 35, 78, 142, 199, 224, 207, 155, 90, 37, 14, 29, 72, 129, 182, 218, 231, 219, 186, 141, 95, 59, 43, 50, 78, 118, 158, 187, 196, 181, 145, 99, 59, 39, 51, 94, 156, 217, 254, 252, 209, 141, 71, 19, 3, 23, 68, 121, 165, 189, 191, 175, 150, 127, 112, 106, 106, 112, 117, 123, 134, 152, 174, 194, 200, 183, 139, 79, 22, 0, 0, 27, 96, 172, 233, 255, 253, 215, 163, 115, 84, 74, 77, 90, 108, 116, 120, 125, 129, 138, 152, 159, 163, 155, 131, 101, 71, 51, 50, 70, 112, 162, 210, 239, 237, 214, 170, 110, 64, 43, 41, 62, 98, 134, 157, 164, 152, 132, 118, 106, 102, 121, 140, 147, 150, 143, 124, 103, 91, 104, 122, 150, 197, 213, 205, 196, 152, 87, 45, 21, 12, 27, 76, 133, 170, 201, 213, 190, 162, 128, 96, 93, 101, 114, 141, 159, 155, 140, 118, 90, 81, 89, 102, 145, 191, 203, 214, 204, 154, 113, 64, 24, 28, 30, 57, 111, 145, 183, 198, 191, 194, 152, 121, 122, 88, 96, 123, 118, 156, 166, 143, 160, 128, 95, 104, 80, 92, 119, 120, 167, 182, 162, 178, 151, 108, 92, 58, 54, 63, 68, 115, 153, 176, 204, 200, 194, 172, 118, 100, 95, 72, 85, 116, 134, 154, 165, 155, 153, 142, 104, 94, 101, 84, 94, 116, 122, 152, 168, 153, 159, 162, 132, 91, 92, 104, 63, 73, 139, 135, 140, 197, 198, 184, 185, 158, 121, 93, 81, 63, 53, 79, 99, 123, 157, 164, 179, 176, 140, 136, 127, 103, 96, 101, 130, 128, 112, 146, 142, 129, 145, 122, 127, 140, 114, 125, 130, 128, 141, 117, 126, 137, 111, 131, 123, 119, 164, 112, 84, 158, 140, 87, 128, 177, 128, 80, 152, 161, 89, 120, 142, 132, 150, 111, 106, 139, 122, 128, 127, 127, 137, 109, 141, 156, 117, 133, 108, 123, 174, 96, 111, 150, 80, 138, 145, 83, 164, 140, 95, 165, 138, 125, 130, 106, 165, 136, 89, 132, 105, 115, 129, 109, 182, 134, 79, 174, 127, 102, 170, 95, 111, 184, 105, 101, 151, 118, 116, 144, 115, 86, 149, 161, 84, 141, 169, 80, 155, 205, 88, 97, 146, 90, 112, 163, 93, 75, 190, 167, 83, 164, 139, 69, 189, 155, 53, 157, 130, 48, 172, 197, 66, 84, 208, 152, 36, 141, 187, 66, 130, 199, 91, 99, 171, 143, 101, 102, 145, 122, 89, 168, 161, 65, 106, 178, 151, 115, 132, 150, 106, 90, 141, 146, 110, 94, 130, 191, 150, 73, 115, 167, 116, 85, 156, 174, 78, 78, 184, 173, 90, 96, 146, 143, 123, 147, 136, 75, 90, 149, 154, 144, 139, 133, 125, 114, 113, 112, 129, 150, 120, 112, 160, 138, 84, 120, 180, 155, 88, 91, 128, 122, 134, 162, 137, 106, 113, 144, 154, 104, 90, 160, 183, 116, 53, 72, 153, 194, 172, 129, 87, 99, 139, 134, 110, 115, 160, 179, 100, 45, 119, 187, 158, 105, 110, 155, 160, 128, 94, 70, 100, 156, 159, 141, 145, 155, 143, 101, 82, 85, 84, 140, 226, 218, 123, 47, 58, 113, 137, 141, 146, 167, 192, 137, 48, 51, 121, 179, 179, 123, 93, 118, 134, 112, 106, 161, 197, 150, 103, 91, 87, 97, 105, 122, 162, 185, 179, 155, 119, 87, 64, 71, 118, 167, 192, 165, 104, 88, 123, 153, 144, 99, 87, 137, 180, 168, 113, 66, 78, 128, 160, 149, 124, 137, 173, 178, 133, 69, 54, 93, 104, 98, 142, 199, 219, 198, 149, 90, 51, 62, 95, 108, 111, 118, 147, 205, 226, 178, 116, 73, 59, 81, 109, 116, 120, 151, 180, 165, 141, 145, 142, 113, 75, 60, 84, 124, 160, 183, 179, 162, 143, 115, 88, 74, 82, 117, 158, 177, 147, 92, 83, 134, 189, 192, 137, 81, 75, 110, 158, 173, 127, 61, 40, 82, 150, 204, 232, 217, 164, 107, 63, 38, 46, 82, 128, 159, 166, 165, 169, 169, 150, 118, 98, 91, 91, 105, 128, 147, 157, 158, 144, 113, 81, 71, 91, 136, 186, 214, 201, 148, 81, 40, 43, 79, 127, 164, 179, 177, 166, 152, 135, 119, 107, 97, 87, 82, 90, 117, 158, 192, 197, 165, 115, 77, 70, 94, 133, 158, 152, 126, 111, 128, 164, 188, 172, 121, 68, 44, 55, 86, 124, 166, 203, 219, 195, 136, 76, 48, 61, 98, 134, 155, 160, 154, 140, 123, 120, 141, 174, 188, 158, 91, 23, 0, 25, 101, 187, 247, 255, 218, 148, 80, 44, 50, 86, 131, 165, 175, 159, 126, 93, 81, 101, 140, 172, 179, 161, 135, 114, 95, 76, 61, 66, 102, 159, 209, 228, 210, 165, 108, 56, 29, 43, 101, 178, 231, 226, 166, 87, 34, 30, 67, 120, 164, 186, 183, 162, 133, 111, 106, 120, 141, 150, 139, 111, 86, 81, 106, 149, 188, 197, 168, 113, 59, 36, 56, 112, 177, 219, 217, 170, 99, 40, 23, 58, 130, 205, 249, 241, 184, 104, 38, 15, 42, 102, 163, 197, 192, 152, 97, 52, 42, 76, 143, 213, 252, 242, 186, 110, 43, 10, 21, 69, 134, 191, 216, 200, 155, 101, 64, 57, 82, 129, 181, 216, 220, 188, 129, 62, 13, 0, 28, 91, 168, 233, 255, 244, 187, 113, 49, 20, 36, 89, 156, 209, 225, 198, 140, 72, 23, 10, 39, 98, 167, 221, 246, 234, 194, 138, 86, 51, 41, 56, 88, 125, 156, 174, 176, 163, 139, 113, 91, 81, 85, 104, 135, 170, 200, 215, 206, 172, 121, 65, 23, 9, 27, 72, 128, 178, 207, 208, 188, 158, 129, 110, 102, 100, 102, 105, 112, 127, 153, 182, 203, 204, 175, 122, 57, 3, 0, 0, 55, 131, 203, 250, 255, 239, 191, 137, 92, 65, 60, 73, 96, 121, 142, 157, 161, 159, 152, 141, 128, 113, 97, 82, 68, 61, 67, 88, 123, 166, 209, 241, 249, 232, 192, 137, 81, 41, 23, 28, 54, 93, 130, 156, 167, 164, 149, 132, 123, 121, 126, 136, 142, 137, 125, 110, 97, 94, 110, 141, 177, 209, 225, 213, 176, 124, 65, 17, 0, 5, 40, 95, 153, 196, 214, 209, 182, 144, 113, 94, 92, 108, 132, 155, 164, 155, 140, 120, 93, 79, 87, 113, 145, 172, 193, 201, 180, 144, 108, 65, 31, 30, 46, 68, 106, 157, 193, 208, 213, 197, 156, 121, 99, 77, 76, 97, 122, 144, 165, 177, 161, 131, 116, 95, 75, 95, 116, 125, 171, 201, 176, 158, 141, 93, 51, 39, 48, 55, 69, 131, 193, 205, 216, 225, 202, 170, 129, 87, 62, 44, 62, 97, 110, 147, 195, 193, 190, 185, 129, 77, 60, 52, 54, 78, 119, 155, 181, 205, 198, 165, 137, 93, 68, 83, 76, 78, 123, 153, 184, 193, 157, 168, 177, 118, 110, 122, 70, 58, 92, 104, 119, 129, 140, 177, 184, 168, 159, 126, 104, 104, 75, 58, 89, 118, 130, 155, 188, 173, 137, 148, 145, 103, 110, 124, 97, 112, 145, 145, 143, 134, 123, 124, 120, 129, 124, 94, 128, 171, 124, 83, 117, 147, 125, 98, 136, 158, 95, 115, 190, 131, 95, 160, 132, 95, 153, 150, 110, 138, 148, 120, 108, 108, 118, 121, 118, 136, 139, 116, 119, 146, 145, 125, 126, 126, 106, 116, 135, 127, 139, 135, 106, 151, 173, 100, 93, 146, 143, 122, 101, 110, 155, 147, 135, 148, 108, 108, 144, 103, 112, 146, 86, 111, 175, 112, 126, 195, 113, 92, 173, 116, 74, 160, 135, 81, 176, 174, 46, 97, 179, 110, 131, 170, 82, 131, 204, 89, 101, 178, 71, 98, 211, 91, 61, 191, 125, 66, 187, 155, 41, 156, 241, 87, 47, 175, 128, 65, 190, 175, 44, 124, 199, 103, 77, 129, 134, 144, 148, 129, 129, 125, 117, 136, 139, 105, 109, 151, 121, 81, 156, 195, 97, 65, 144, 178, 130, 85, 138, 184, 77, 45, 202, 202, 50, 98, 215, 141, 55, 110, 145, 97, 114, 193, 169, 82, 89, 149, 163, 132, 110, 141, 150, 80, 64, 139, 165, 133, 125, 136, 141, 131, 121, 131, 137, 121, 112, 123, 131, 114, 105, 141, 161, 125, 110, 136, 138, 120, 133, 163, 139, 66, 57, 139, 192, 163, 125, 121, 118, 107, 127, 134, 98, 133, 216, 159, 34, 38, 124, 183, 180, 124, 117, 172, 164, 100, 76, 89, 111, 129, 135, 144, 154, 155, 151, 127, 85, 64, 87, 156, 225, 201, 107, 66, 90, 101, 105, 121, 132, 184, 234, 144, 17, 54, 162, 186, 152, 100, 79, 133, 153, 96, 92, 160, 194, 171, 122, 80, 81, 99, 105, 137, 179, 176, 162, 158, 116, 63, 53, 58, 101, 198, 230, 159, 120, 142, 135, 97, 71, 64, 104, 188, 231, 174, 79, 46, 93, 147, 144, 107, 97, 135, 197, 228, 175, 76, 30, 61, 107, 128, 139, 164, 191, 180, 128, 85, 84, 105, 118, 120, 121, 134, 156, 171, 166, 140, 97, 73, 96, 127, 124, 114, 134, 160, 165, 157, 145, 116, 88, 95, 117, 108, 91, 115, 165, 188, 181, 165, 141, 107, 76, 63, 82, 119, 145, 154, 149, 125, 111, 145, 190, 178, 118, 78, 83, 112, 143, 154, 123, 75, 70, 118, 170, 193, 191, 169, 134, 98, 73, 66, 81, 106, 133, 164, 184, 173, 144, 121, 114, 120, 126, 119, 110, 108, 113, 130, 153, 152, 122, 89, 72, 86, 140, 200, 229, 212, 158, 101, 72, 55, 41, 58, 102, 141, 172, 189, 173, 147, 149, 156, 140, 119, 104, 88, 81, 93, 120, 157, 178, 161, 122, 93, 86, 102, 128, 143, 147, 150, 149, 147, 153, 156, 140, 105, 67, 47, 60, 103, 154, 191, 201, 182, 151, 129, 114, 98, 87, 95, 118, 141, 139, 111, 86, 95, 139, 193, 222, 203, 144, 73, 23, 18, 61, 133, 196, 229, 220, 175, 119, 76, 57, 65, 98, 138, 163, 161, 135, 107, 98, 114, 139, 156, 157, 153, 152, 151, 136, 101, 64, 49, 71, 121, 174, 208, 211, 180, 124, 64, 30, 43, 98, 167, 215, 222, 190, 136, 81, 45, 41, 73, 128, 180, 201, 182, 142, 108, 99, 115, 136, 145, 135, 110, 82, 69, 88, 137, 196, 226, 205, 140, 69, 29, 38, 86, 147, 198, 221, 207, 156, 87, 32, 21, 60, 131, 197, 229, 218, 170, 106, 52, 33, 60, 121, 182, 210, 189, 132, 71, 39, 50, 99, 168, 231, 255, 238, 165, 72, 0, 0, 3, 75, 157, 223, 250, 230, 173, 106, 59, 53, 86, 136, 178, 196, 184, 148, 101, 56, 31, 39, 78, 135, 189, 220, 221, 193, 148, 100, 65, 58, 81, 123, 166, 190, 183, 148, 99, 52, 27, 33, 71, 129, 189, 232, 249, 238, 202, 150, 97, 53, 30, 35, 63, 101, 139, 167, 177, 171, 152, 121, 90, 72, 72, 95, 138, 184, 218, 231, 215, 172, 117, 63, 24, 14, 35, 76, 127, 173, 195, 195, 179, 151, 124, 108, 101, 101, 109, 120, 132, 149, 168, 180, 184, 173, 141, 96, 50, 12, 0, 21, 68, 133, 199, 243, 255, 239, 198, 146, 105, 80, 74, 87, 108, 123, 133, 137, 132, 128, 128, 125, 122, 117, 104, 87, 74, 68, 74, 102, 141, 183, 223, 246, 244, 221, 180, 127, 81, 50, 36, 43, 67, 92, 115, 131, 134, 129, 128, 127, 131, 145, 156, 158, 155, 141, 117, 101, 96, 100, 124, 161, 191, 212, 218, 196, 153, 107, 58, 17, 6, 15, 38, 83, 132, 166, 193, 204, 191, 171, 154, 133, 122, 130, 136, 140, 147, 138, 114, 97, 80, 69, 86, 117, 149, 188, 213, 206, 182, 145, 90, 44, 26, 20, 
};
const int triggerPin = A2;
const int SoundPin = 2;



int triggerState = 0;


void setup() {

  pinMode(triggerPin, INPUT);
  pinMode(SoundPin, OUTPUT);
}

void loop() {
  triggerState = digitalRead(triggerPin);
 
  if (triggerState == HIGH) {
    
    startPlayback(sample, sizeof(sample));
    delay(700);
    stopPlayback();
    
  } 
 
  else {
    digitalWrite(SoundPin, LOW);
  }
  delay(1);
  }
```
  
### <a name="12"></a>Mittwoch, 08. September 2021
Da das Abspielen von Sounds nun funktionierte, haben wir uns heute das erste mal genauer mit Ideen über die Hardware unseres Projektes auseinander gesetzt.
  
  
### <a name="13"></a>Dienstag, 14. September 2021
  Entfall
### <a name="14"></a>Mittwoch, 15. September 2021
  Entfall
  
### <a name="15"></a>Dienstag, 21. September 2021
Heute haben wir nach einiger Recherche nach Bauteilen aus Kostengründen beschlossen, die Bewegungsbahnen des Flugzeuges mittels Schubladen schienen zu realisieren. Linearkugellager wären natürlich die bessere Option, aber dafür auch die  teurere. Das Flugzeug wird sich also auf zwei senkrecht zueinanderstehenden Schienen auf einem Schlitten bewegt. Eine weitere Frage die offen blieb war, ob wir normale Gleichstrommotoren für die Achsenbewegung verwenden, oder Schrittmotoren. Mit Schrittmotoren wäre es möglich, dass der Arduino zu jedem Zeitpunkt genau weiß, wo, in einem vorher definierten Koordinatensystem, sich das Flugzeug befindet. Den Gleichen Effekt könnte man jedoch auch mit normalen Motoren erlangen, wenn man parallel zu den Achsenschienen einen Linearwiderstand anbringen würde. Der sogenannte Schleifer würde dann an den Schlitten auf der Schiene montiert werden. Diese Frage haben wir zunächst offengelassen.
Entschieden haben wir uns aber in der Frage nach der Kraftübertragung vom Motor an den Schlitten. Wir haben uns auch hier für die günstigste Variante entschieden. An dem Motor wird ein Zahnrad montiert, welches in eine Zahnstange parallel zur Schien greift. Ander Möglichkeiten wären noch die Kraftübertragung per Riemen oder Gewindestange, wie es bei 3D-Druckern üblich ist. 
 
### <a name="16"></a>Mittwoch, 22. September 2021 
Heute haben wir uns auf einen Motortyp festgelegt. Wir haben uns gegen die Schrittmotoren entschieden, da wir es nicht für nötig halten, dass die Position des Flugzeuges zu jedem Zeitpunkt genau bestimmbar ist. Wir werden normale Motoren verwenden und dann an das Ende jeder Schiene einen Taster montieren, so dass der Schlitten nicht aus der Schiene herausfahren kann. 
  
### <a name="17"></a>Dienstag, 28. September 2021
Heute haben wir uns damit befasst, wie man einen Motor nicht mechanisch, sondern elektronisch umpolen kann. Dies wird mit vier elektrischen Halbleitern, also Transistoren oder MOSFET´S realisier. Mit diesen wird eine sogenannte H-Bridge Schaltung aufgebaut (Siehe Bild). Bei dieser werden zwei der Transistoren durchgeschaltet (S1 und S4) um so einen Stromfluss durch den Motor zu ermöglichen. Wenn die anderen zwei Transistoren (S2 und S3) durchgeschaltet werden, fließt der Strom in die andere Richtung, ergo der Motor dreht sich in die andere Richtung. So ist die Bewegung nach links und rechts und ober und unten möglich. Eine solche Schaltung haben wir heute begonnen aufzubauen.

![310px-H_bridge svg](https://user-images.githubusercontent.com/88385986/144763248-f9dd9373-5276-48ae-a490-cbb7d415482a.png)


### <a name="18"></a>Mittwoch, 29. September 2021
  Entfall
  
### <a name="19"></a>Dienstag, 19. Oktober 2021
Heute ist uns bei weiterer Teilerecherche aufgefallen, dass es bereits fertige Motorentreiber-Platinen für einen schmalen Taler zu kaufen gibt. Diese funtionierne ebenfalls auf dem Prinzip einer H-Bridge Schaltung haben aber einige Vorteile, z.B. in der Einfachheit und in ihrem Volumen.
 
  
### <a name="20"></a>Mittwoch, 20. Oktober 2021
Da wir nun ale Wesentlichen Hardwarefragen geklärt hatten haben wir begonnen Code zu entwickeln.

### <a name="21"></a>Dienstag, 26. Oktober 2021
Nach der Heutigen Stunde war unser Code auf diesem Stand und bereits in der Lage mit einem Joystick zwei Motoren ind jeweils beide Richtungen zu drehen.
```c
//Input Pin für die Achsen des Joysticks
const int analogInPinX = A1;
const int analogInPinY = A0;

//Pwm Pins für den Motor-Controller
const int analogOutPin9 = 9; 
const int analogOutPin11 = 11;
const int OutPinX10 = 10;
const int OutPinX6 = 6; 

//Variablen für zwischenspeicher
int sensorValueY = 0;
int sensorValueX = 0;  
int outputValueY = 0;   
int outputValueX = 0; 


void setup() {
  Serial.begin(9600);
}

void loop() {
  //X
    sensorValueX = analogRead(analogInPinX);


 if (sensorValueX > 540) {
  outputValueX = map(sensorValueX, 540, 955, 0, 255);
  analogWrite(OutPinX10, outputValueX);
 }

else if (sensorValueX < 500) {
  outputValueX = map(sensorValueX, 500, 210, 0, 255);
  analogWrite(OutPinX6, outputValueX);
 }
else  if (sensorValueX > 510 || sensorValueX < 522){
  outputValueX = 0;
  analogWrite(OutPinX10, outputValueX);
  analogWrite(OutPinX6, outputValueX);
}

// Y
  sensorValueY = analogRead(analogInPinY);
 
 if (sensorValueY > 540) {
  outputValueY = map(sensorValueY, 540, 890, 0, 200);
  analogWrite(analogOutPin9, outputValueY);
 }

else if (sensorValueY < 500) {
  outputValueY = map(sensorValueY, 500, 155, 0, 100);
  analogWrite(analogOutPin11, outputValueY);
 }
else if (sensorValueY > 510 && sensorValueY < 535){
  outputValueY = 0;
  analogWrite(analogOutPin11, outputValueY);
  analogWrite(analogOutPin9, outputValueY);
}

 
 
  Serial.print("sensor = ");
  Serial.print(sensorValueY);
  Serial.print("\t output = ");
  Serial.println(outputValueY);


  delay(1);
}
```
  
### <a name="22"></a>Mittwoch, 27. Oktober 2021
  
### <a name="23"></a>Dienstag, 02. November 2021
Auch wenn das Abspielen des Sounds funktioniert hat mussten wir feststellen, dass wir eine andere Lösung für das Abspieln von Geräuschen brauchten. 1. Problem war, dass der Befehl "sizeof" alle gespeicherten Werte für Variablen zurück setzt. Dieser Befehl ist für die Ausführung der Libary  welche wir nutzen unerlässlich. In Kombination mit dem Code, welcher für die Steuerung der Achsen zuständig ist kann die Steuerung nicht mehr funktionieren. Das 2. Problem war, dass dieser Kurze Sound bereits einen erheblichen Teil des Programmspeichers ein nimmt. Also haben wir uns nach Altenativen umgesehen. Und in der Tat sind wir online auf mehrere Erweiteungs-Shields gestoßen, welche Sounddateien von eine SD-Karte abspieln können. Hiermit soll in Zukunft also beim Betätigen des Abzuges des Joysticks ein Schussgeräusch zu höhren sein und während des Gesamten Spielen ein Motorengeräusch der Flugzeuge.
  
### <a name="24"></a>Mittwoch, 03. November 2021
Heute haben wir uns weiter über die Hardware gedanken gemacht und einige Zeichnungen angefertigt. Auf Grundlage dieser haben wir außerhalb der Schule begonnen in der CAD-Software "Fusion 360" die Hardware im Deteil zu entwickeln. An diesem Modell wurde zu Hause immer wieder zwischendurch weiter gearbeitet. Das fertige Modell befindet sich auf unserer Projektseite. Das Modell Zeigt jedoch nicht den ganzen Spieleautomaten, sondern nur die mechanische Steuerung des Spielerflugzeuges. Außerdem fehlen in dem Modell Teile wie Schrauben und auch Klebeverbindungen sind nicht extra markiert.
  
### <a name="25"></a>Dienstag, 09. November 2021
Entfall
  
### <a name="26"></a>Mittwoch, 10. November 2021
Heute haben wir die [Projektseite](https://github.com/Bnlng/Mechanical-Dogfight) für unser Projekt angelegt und uns einen vernünftigen Aufbau für diese überlegt.

### <a name="27"></a>Dienstag, 16. November 2021
Heute haben wir an der Projektseite weitergearbeitet. Wir haben den Code umgeschrieben, damit er übersichtlicher und leichter nachvollziehbar ist. Zusätzlich haben wir einen den Code dubliziert und mit weitgehenden erklärungen versehen. Beide Versionen des Codes sind auf der Projektseite zu finden.

### <a name="28"></a>Mittwoch, 17. November 2021

### <a name="29"></a>Dienstag, 23. November 2021

### <a name="30"></a>Mittwoch, 24. November 2021

### <a name="31"></a>Dienstag, 30. November 2021
Heute haben wir die mechanische Steuerung des flugzeuges getestet und dabei aufgetretene Fehler behoben. Zudem haben wir uns Gedanken über die Taster an den Rändern des Spiels gemacht. Eine Überlegung war es, (Diodenlösung). Stattdessen halten wir eine Softwarelösung für deutlich besser und simpler.

![image](https://user-images.githubusercontent.com/88386307/144904068-8c332e9d-e88f-467a-8d05-1efd01582796.png)


### <a name="32"></a>Mittwoch, 01. Dezember 2021
Heute haben wir den Code so verändert, dass das Flugzeug, wenn es einen Taster betätigt nicht mehr weiter in die Richtung des Tasters bewegen kann. Genaueres Zum Code kann auf der Projektseite nachgelesen werden.
