<img alt="kwl" src="https://user-images.githubusercontent.com/47775739/158055191-ee90635b-360a-4afb-a6d3-38637e70a566.png">

Die Idee war ein multifunktionelles Widget zu schaffen, welches mit den meisten Lüftungsgeräten funktioniert, aber auch von der Größe nicht größer als herkömmliche Widgets ist. Erstellt und getestet wurde es mit einer Pluggit AP310 und dem SmartHomeNG plugin der pluggit, welches ihr auch auf meinem Account unter https://github.com/CannonRS/smarthomeng_pluggit findet.

Aktuell ist es möglich die wichtigsten Dinge anzuzeigen:

- Lüftergeschwindigkeit
- Filter
- VOC-Sensor
- RH-Sensor
- Bypass
- Sommermodus

Die entsprechenden Parameter sind in der kwl.html zu finden. Alle Dateien im Ordner "widget_kwl" müssen komplett ins smartVISU-Verzeichnis "dropins" kopiert werden. Eine Einbindung könnte dann so aussehen:

    {% import "kwl.html" as kwl %}
    <div class="block">
        <div class="set-1" data-role="collapsible-set" data-theme="c" data-content-theme="a" data-mini="true">
            <div data-role="collapsible" data-collapsed="false">
                <h3>Lüftungsanlage</h3>
               {{ kwl.kwl('', 'Zentral.pluggit.OutdoorTemperature', 'Zentral.pluggit.SupplyTemperature', 'Zentral.pluggit.ExtractTemperature', 'Zentral.pluggit.ExhaustTemperature', 'Zentral.pluggit.FanSpeedLevel', 0, 4, 'Zentral.pluggit.FilterRemainingLifetime', 'Zentral.pluggit.FilterDefaultTime', 'Zentral.pluggit.CurrentUnitMode.SummerMode', 'Zentral.pluggit.Bypass.Open', 'Zentral.pluggit.VOC_Sensor.SensorValue') }}
           </div>
        </div>
    </div>

Die nächsten Schritte wären noch weitere Möglichkeiten einzubauen. So fehlen aktuell noch:

- Vorheizregister
- CO2 Außenluftsensor
- Innenraumsensor
- Frostschutzmodus

Da ich diese Sensoren aber selbst nicht ahbe und den Frostschutzmodus noch nie gesehen habe, kann ich das aktuell nicht einbauen und testen. Wenn Bedarf besteht, bitte gern melden.

In späteren Versionen ist auch geplant die Anlage damit zu konfigurieren.

Änderungen:

16.03.2022:
- Änderungen der Pfade der Bilder und des Widgets
