# Studio 1 Anleitung

Studio 1 verfügt über ein äußerst leistungsfähiges, wenn auch etwas komplexes Setup, insbesondere wenn außergewöhnliche Projekte realisiert werden sollen. Die Hauptausrichtung liegt auf der Produktion und dem Mischen von Mehrkanal-Produktionen mit eigenen Rechnern, basierend auf der DANTE Audio-over-IP-Netzwerktechnologie. Allerdings eignet sich das Studio auch hervorragend für Aufnahmen oder Stereoproduktionen.

Zu den Ausstattungsmerkmalen gehören hochwertige Lautsprecher, ein erstklassiger AD/DA-DANTE-Wandler, und ein Flaggschiff-8-Kanal-Mikrofonvorverstärker und (Dante-) Wandler. Darüber hinaus steht eine hochqualitative analoge 16-Kanal-Mikrofonvorverstärkeranlage zur Verfügung.

Für entspanntere Stereo- oder Quad-Setups besteht die Möglichkeit, das FIREFACE UC (oder Miniklinke/DI) und das Mackie-Pult zu verwenden, ohne auf das DANTE-Netz zurückgreifen zu müssen, ähnlich wie in der Vergangenheit. Dabei ersetzt das Mackie-Pult das frühere Abhörsystem.


# Drivers und Links

### RME - DIGIFACE DANTE
- https://rme-audio.de/driverkit-vs-kernel-extension.html (INFO)
- https://rme-audio.de/downloads.html

RME bietet verschiedene Treiberarten für Apple-Rechner an. Weitere Informationen finden Sie im oben stehenden Link. In den nächsten Jahren wird sich dies voraussichtlich ändern.

Zusätzlich gibt es optionale Treiber, um das Digiface auch als Netzwerkswitch zu verwenden, anstatt einen zusätzlichen Netzwerkanschluss für die Steuerung des Dante-Netzwerks zu benötigen (RME Network Interface für Digiface AVB und Digiface Dante).

Ältere USB-Treiber von RME könnten möglicherweise mit dem Digiface funktionieren. Es wird jedoch empfohlen, ein Update auf die neueste Version durchzuführen.

### AUDINATE DANTE
- https://my.audinate.com/support/downloads/dante-controller (benötigt eine kostenlose Konto bei Audinate)

### FOCUSRITE REDNET MP8R
- https://downloads.focusrite.com/focusrite-pro/rednet/rednet-mp8r


# Geräte/Verbindungen Arbeitsplatz

- RTW TC5 Monitor Controller - Verbunden mit dem DANTE Netzwerk (mit Strom über PoE)
- RME Digiface DANTE - USB Anschlusskabel 
- ElGato TB2 Dock - MacPro Serverraum
- Kensington TB3/USB-C Dock - Eigene TB3 Apple Rechner (Strom, Maus, Tastatur, Video und DANTE-Netzwerk)
- KVM Switch (Keyboard, Video, Mouse) - Bild, Maus und Tastatur Auswahl zwischen:
	- PC1: MacPro Serverraum
	- PC2: Kensington TB3/USB-C Dock (Apple Rechner)
	- PC3: Einzelne USB und HDMI Anschlüsse (WIN Rechner)
- Netzwerk Switch ins DANTE-Netzwerk (Nicht mit ICEM Netzwerk oder Internet verbunden)
- Netzwerkkabel ins DANTE-Netzwerk für WIN Rechner.
- Maus/Tastatur angeschlossen an den KVM Switch
- Bildschirm angeschlossen an den KVM Switch

# Setup

(KOMPONENTENDIAGRAM)

## ANALOG
Alle analogen Leitungen verlaufen über die Neutrik TT-Steckfelder im Rack und sind für die häufigsten Anwendungsfälle ohne zusätzliches Verkabeln vorbereitet, dank der Normalisierung der Steckfelder. Normalisierung bedeutet in diesem Kontext, dass Signale weitergeleitet werden, als ob ein Kabel eingesteckt wäre. Spezifisch sind die Steckfelder halb-normalisiert nach unten, d. h., von der oberen Buchse zur unteren Buchse. Alle Buchsen mit Beschriftung auf weißem Hintergrund sind halb-normalisiert. Die Verbindung wird unterbrochen, wenn ein Kabel in die untere Buchse eingesteckt wird. Im Gegensatz dazu unterbricht das Einstecken oben die Verbindung nicht, sondern wirkt wie ein Splitter: Das Signal setzt seinen Weg nach unten fort und fließt gleichzeitig durch das eingesteckte Kabel.

![Visualisierung Normalisierung](normalisierung.png)

Die Verbindungen zu den Lautsprechern L und R an der Wand sowie zu den Lautsprechern 1-4 erfolgen über das Mackie 1642 VLZ4 Mischpult am Fenster. Die Lautsprecher LR sind an den MAIN OUT des Pultes angeschlossen, während die Lautsprecher 1-4 an die BUSSE 1-4 angeschlossen sind. Alles ist über die Neutrik-Steckfelder normalisiert (siehe oben).
Die Inputs des Mackie-Pults sind wie folgt belegt:

- Kanäle 1-4: DANTE Kanäle 1-4 von ANDIAMO Out 1-4
- Kanäle 5-8: RME Fireface UC Out 1-4
- Kanäle 9-10 (Stereo): RME Fireface UC Out 5-6
- Kanäle 11-12 (Stereo): DI-Box
- Kanäle 13-14 (Stereo): CD Player
- Kanäle 15-16 (Stereo): Apollo Mon Out

Das Routing wird über das Pult mittels Knöpfe und Panorama-Einstellungen gesteuert. Um die 4 großen Genelec1038 Lautsprecher (QUAD) gleich laut zu haben wie die restliche kleine Genelec 8040 Lautsprecher (DOME), müssen die erste 4 Kanäle (DANTE) im Mackie Pult wie folgt eingestellt werden:

- Input Gain: ganz nach links (-20dB bzw U)
- PAN: 1 L, 2 R, 3 L, 4 R
- Level: auf Maximum (+10dB)
- Routing: Kanal 1 und 2 auf Bus 1-2
- Routing: Kanal 3 und 4 auf Bus 3-4

Alle Mikrofoneingänge der REDNET MP8R und des AUDIO216-Vorverstärkermoduls ('PREAMPS') stehen über die Neutrik-Steckfelder zur Verfügung, Mikrofone werden über die 3 XLR ‘Breakout’-Panels angeschlossen. Diese Anschlüsse sind NICHT normalisiert und müssen manuell gepatcht werden. 

Ein Beispiel: Ein Mikrofon (XLR-Kabel) wird in XLR Breakout 1, Buchse 1 gesteckt. Im Steckfeld wird dann XLR 1,1 auf REDNET In 1 gepatcht.

Die LINE-Ausgänge (verstärkte Mikrofonsignale) der AUDIO216 PREAMPS sind über die Steckfelder mit den Inputs 1-16 des ANDIAMO verbunden und normalisiert. 

Beispiel: Ein Mikrofon (XLR-Kabel) wird in XLR Breakout 1, Buchse 1 gesteckt. Im Steckfeld wird dann XLR 1,1 auf PREAMPS In 1 gepatcht. Die Vorverstärker werden eingestellt, und das Signal geht über die Normalisierung direkt auf Input 1 des ANDIAMO.

Andere LINE-Analogsignale können direkt über das XLR-Breakout und die Steckfelder (oder mittels TT-Adapterkabel) direkt auf das ANDIAMO geschickt werden, um dort digitalisiert und ins DANTE-Netzwerk übertragen zu werden.


## DIGITAL/DANTE
Studio 1 ist für verschiedene Abhör-Szenarien konzipiert:

- Mono bis 20.1 Mehrkanal (DANTE) über Digiface mit eigenem Rechner oder MacPro
- Mono bis 20.1 Mehrkanal (DANTE) über Dante Virtual Soundcard mit eigenem Rechner, MacPro (Serverraum) oder AstroSpatial Rechner (Serverraum), oder ein anderes externes Gerät (z. B. LINUX Rechner über das Soundcraft Pult).
- Arbeiten mit eigenen Rechnern am großen Tisch am Fenster (RME FIREFACE UC oder Miniklinke).

*WICHTIG:* Die Dante Virtual Soundcard (DVS) und das Digiface Dante von RME erfüllen dieselbe Funktion. Die Verwendung des Digiface anstelle von DVS bietet zahlreiche Vorteile und entlastet den Computer erheblich. Es sollte entweder das eine oder das andere verwendet werden und nicht beide gleichzeitig. Anders ausgedrückt: Wenn das Digiface genutzt werden soll, ist das Starten von DVS nicht erforderlich (oder empfohlen).

### Mono bis 20.1 Mehrkanal (DANTE) über Digiface mit eigenem Rechner oder MacPro

Benötigte Software/Treiber: Die erforderliche Software und Treiber umfassen RME Treiber und Software, REDNET Steuerungssoftware sowie den Dante Controller.

Die Lautstärke, das Monitoring und das Bassmanagement für alle Lautsprecher im DOME (20.1) werden über das RTW TouchControl 5 (TC5) gesteuert. Für Lautsprecher 1-4 müssen am MACKIE PULT (am Fenster) die Fader für Kanäle 1-4 UND für die Busse 1-4 ganz oben stehen, bis zum Anschlag, um die richtige Lautstärke der 4 Lautsprecher im Zusammenhang mit allen anderen zu erreichen. Weitere Informationen zum TC5 finden Sie [hier](LINK AUF TC5) und zum Lautsprecher-Setup [hier](LINK AUF LS SETUP).

An den eigenen Rechner muss folgendes angeschlossen werden: 

**Für Apple Rechner mit Thunderbolt 3 oder neuer:**
- DigifaceDANTE (USB-C Kabel mit weißer Beschriftung)
- TB3 Dock (Thunderbolt/USB-C Kabel mit Rote Beschriftung) für Strom, Dante Netzwerk, und KVM Switch. **KVM Switch auf PC2 setzten**

**Windows Rechner oder ältere Apple Rechner:**
- DigifaceDANTE (USB-C/USB-A Kabel mit weißer Beschriftung)
- USB, HDMI (Alle Kabel mit Grüne Beschriftung) die mit den KVM Switch verbunden sind. **KVM Switch auf PC3 setzen.**
- Netzwerk (Adapter auf USB-C liegt dabei, Kabel mit Grüne Beschriftung)
- Strom, wenn gewünscht.

**MacStudio (Serverraum)**
- DigifaceDANTE (USB-C Kabel mit weißer Beschriftung) and den passenden Dock anschliessen
- KVM Switch auf PC1 setzen

Zentral für dieses Setup ist das RME DigifaceDANTE USB Interface am Tisch, das über USB3 angeschlossen wird (ein Kabel mit USB-A und USB-C Anschlüssen liegt am Tisch). Es fungiert als Schnittstelle zwischen den eigenen Rechnern und dem DANTE Netzwerk. Weitere Informationen finden Sie [hier](LINK AUF DIGIFACE).

Die Wandlung zwischen dem DANTE Netzwerk und der analogen Welt erfolgt über das ANDIAMO von Direct Out und/oder das RedNet MP8R von Focusrite. Beide Geräte befinden sich im Rack und sind bereits in das DANTE Netzwerk integriert.
- Das ANDIAMO ist ein 32-Kanal-Line-AD/DA-Wandler (Analog-zu-Digital/Digital-zu-Analog). Weitere Informationen finden Sie [hier](LINK AUF ANDIAMO).
- Das REDNET MP8R ist ein 8-Kanal-Mikrofonvorverstärker und AD-Wandler. Weitere Informationen finden Sie [hier](LINK AUF REDNET).

Die digitalen Signale aus beiden Geräten werden mittels Dante Controller auf das DigifaceDANTE geroutet. Das Preset für den Dante Controller kann [hier](LINK AUF DOWNLOADS) heruntergeladen werden. Das Laden des Presets im Dante Controller setzt alles zurück auf das Standard-Setup, falls etwas verstellt wurde.

**Das Routing im Dante Controller ist Standardmäßig wie folgt:** 

ANDIAMO TRANSMITTER (OUT) 1 - 32 —> DIGIFACE RECEIVER (IN) 1 - 32
REDNET MP8R TRANSMITTER (OUT) 1 - 8 —> DIGIFACE RECEIVER (IN) 33 - 40

ANDIAMO TRANSMITTER (OUT) 1 - 32 —> MACPRO (DVS) RECEIVER (IN) 1 - 24
REDNET MP8R TRANSMITTER (OUT) 1 - 8 —> MACPRO (DVS) RECEIVER (IN) 25 - 32

MACPRO (DVS) TRANSMITTER (OUT) 1 -24 —> DIGIFACE RECEIVER (IN) 41 - 64

DIGIFACE TRANSMITTER (OUT) 1 - 24 —> RTW TC5 RECEIVER (IN) 1 - 24
DIGIFACE TRANSMITTER (OUT) 25 - 33 —> ANDIAMO RECEIVER (IN) 25 - 33

RTW TC5 TRANSMITTER (OUT) 1 - 24 —> ANDIAMO RECEIVER (IN) 1 - 24

(BILD DANTE CONTROLLER)

Das Routing im DIGIFACE wird durch die Software TotalMix gesteuert. Das Standard-Preset, oder WORKSPACE benannt kann [hier](LINK AUF DOWNLOADS) gefunden werden, und weitere Informationen zu TotalMix sind [hier](LINK ZU TOTALMIX) verfügbar. https://rme-audio.de/de_totalmix-fx.html 

**Das Routing im TotalMix ist standardmäßig wie folgt:**

Ins PHONES BUS gehen alle SOFTWARE PLAYBACK Kanäle. 
Andernfalls werden die Software Playback-Kanäle einzeln in die entsprechenden Büsse geleitet:
SOFTWARE PLAYBACK 1—> HARDWARE OUTPUT 1
SOFTWARE PLAYBACK 2 —> HARDWARE OUTPUT 2
SOFTWARE PLAYBACK 3 —> HARDWARE OUTPUT 4
Usw.

Zusätzlich werden die Eingänge 41 bis 64 in die Ausgänge 1 bis 24 geleitet, um externe Geräte (wie das Soundcraft Pult für LINUX Nutzer) oder DVS-Rechner (wie den MacPro oder Astrospatial im Serverraum) anzuschließen.

HARDWARE INPUT 41 —> HARDWARE OUTPUT 1
HARDWARE INPUT 42 —> HARDWARE OUTPUT 2

Die Inputs 1 bis 40 gehen standardmäßig NICHT in die PHONES oder andere OUTPUT BUSSE, um die Gefahr von Rückkopplungen zu vermeiden.
Das Workspace Datei enthält ausserdem verschiedene SNAPSHOTS:
S1 Reset: stellt alles wie oben beschrieben
S1 Reset St: Wie S1 Reset aber mit Stereo Kanäle
S1 no Ext: Wie S1 Reset ohne die sends von Inputs 41 bis 64 in die Outputs 1 bis 24.
S1 Backup: Ein Backup von S1 Reset falls man es aus Versehen überschreibt.

(BILD TOTALMIX)


### Mono bis 20.1 Mehrkanal (DANTE) über Dante Virtual Soundcard (DVS) mit eigenem Rechner, MacPro (Serverraum) oder AstroSpatial Rechner (Serverraum), oder ein anderes externes Gerät (z. B. LINUX Rechner über das Soundcraft Pult).

WICHTIG: Obwohl das Digiface nicht als Schnittstelle zwischen dem Rechner und dem Dante Netzwerk fungiert, werden die Signale über das Digiface  trotzdem geleitet. Es agiert wie eine Matrix, die die Signale aus DVS oder dem externen Gerät in den Monitor Controller TC5 und Andiamo weiterleitet. Dies ist zwar nicht zwingend notwendig, vereinfacht jedoch deutlich das Routing im Dante-System.


# Routings für typische Anwendungsfälle

## Eigener Rechner

### Eigener Rechner -> Stereo Abhöre

*Mit Dante* TODO

- Laptop anschließen (siehe [diesen Abschnitt](#mono-bis-201-mehrkanal-dante-über-digiface-mit-eigenem-rechner-oder-macpro))
- RME Digiface verbinden (dafür muss der RME treiber installiert sein)
- Audio auf 1-2 schicken
- Am Mischpult Lautstärke einstellen

![Diagramm Laptop -> Stereo](/graph/laptop-stereo.png)

*Ohne Dante* TODO

- Über USB Kabel am FIREFACE am Tisch anschließen (dafür muss der RME treiber installiert sein)
- am Steckfeld Fireface Outs 1-2 auf ... stecken...

![Diagramm Laptop -> Stereo](/graph/laptop-stereo-no-dante.png)

### Eigener Rechner -> Stereo Tafel

### Eigener Rechner -> Quadro Abhöre

### Eigener Rechner -> DOME

### Aufnahme mit dem eigenen Rechner

## Studio PC

### Studio PC -> Stereo Abhöre

### Studio PC -> Quadro Abhöre

### Studio PC -> DOME

### Aufnehmen mit dem Studio PC


# Lautsprecher Setup

Die Lautsprecherkonstellation bleibt erstmal nach der inoffizielle ICEM-Norm: Lautsprecher werden nach Ringen oder Ebenen im Uhrzeigersinn anfangend vorne links. 
Lautsprecher 1-4: Quadrofonischen Setup, große Genelecs 1038.
Lautsprecher 5-8: Genelec 8040 zwischen Positionen 1-4. 5 ist Center vorne
Lautsprecher 9-12: Genelec 8040 Top Ebene. Vorne links ist 9 
Lautsprecher 13-20: Genelec 8040 untere Ring, vorne links ist 13
Lautsprecher 21: Genelec 1092 Subwoofer


# Troubleshooting

## Ich habe keinen Ton - woran kann es liegen?
## mehr
## mehr



