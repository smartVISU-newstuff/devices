Die erste Test-Version eines KWL-Widgets. Aktuell ist es möglich die wichtigsten Dinge anzuzeigen:

- Lüftergeschwindigkeit
- Filter
- VOC-Sensor
- RH-Sensor
- Bypass
- Sommermodus

Die Idee war ein multifunktionelles Widget zu schaffen, welches mit den meisten Lüftungsgeräten funktioniert. Erstellt und getestet wurde es mit einer Pluggit AP310 und dem SmartHomeNG plugin der pluggit, welches ihr auch auf meinem Account findet.

Die entsprechenden Parameter sind in der kwl.html zu finden. Die Dateien müssen einfach ins smartVISU-Verzeichnis. Eine Einbindung kann dann so aussehen:

    {% import "kwl.html" as kwl %}
    <div class="block">
        <div class="set-1" data-role="collapsible-set" data-theme="c" data-content-theme="a" data-mini="true">
            <div data-role="collapsible" data-collapsed="false">
                <h3>Lüftungsanlage</h3>
				{{ kwl.kwl('', 'Zentral.pluggit.OutdoorTemperature', 'Zentral.pluggit.SupplyTemperature', 'Zentral.pluggit.ExtractTemperature', 'Zentral.pluggit.ExhaustTemperature', 'Zentral.pluggit.FanSpeedLevel', 0, 4, 'Zentral.pluggit.FilterRemainingLifetime', 'Zentral.pluggit.FilterDefaultTime', 'Zentral.pluggit.CurrentUnitMode.SummerMode', 'Zentral.pluggit.Bypass.Open', 'Zentral.pluggit.VOC_Sensor.SensorValue') }}
			</div>
        </div>
    </div>
