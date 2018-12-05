# Visual van de aardbevingen in Groningen
Deze kaart toont de aardbevingen in en rond Groningen wegens de gaswinning. De voor mensen niet voelbare bevingen zijn in groen weergegeven. Door deze opzet zijn vooral recentere en sterkere bevingen prominenter op de kaart aanwezig; hiermee wordt een beeld van het verloop van bevingen door de tijd gegeven. Journalistiek is mijn aannaame dat recente bevingen ook meer impact hebben op de bevolking dan die welke langer geleden zijn. Een verdere uitwerking kan zin of het aantal en de sterkte van de bevingen de laatste jaren toeneemt. Persoonlijke voorlopige aanname: het ligt vooral aan het beeld dat geschapen is, dat de Groningers in de steek gelaten zijn door de politiek, wat veel boosheid met zich meebrengt. <br>

Een uitwerking kan nog zijn meer lagen toe te voegen: 

* bevolkingsdichtheid. Je ziet dat vooral in dunbevolkte gebieden veel bevingen zijn. Het aantal mensen dat het betreft is absoluut gezien niet heel groot. Dit zal mede de oorzaak er van zijn dat aan de problematiek zo lang niets gedaan is

* gasvelden. Op de website van de NAM zijn in de interactieve bevingskaart ook de gasvelden zelf te zien. Vinden de bevingen meer plaats in de buurt van boorputten of onder het hele oppervlak van de velden? (uitzoeken: zijn deze polygonen beschikbaar?)

Metingen zijn beschikbaar sinds 1986 tot nu getoond (begin december 2018). recentere aardbevingen zijn feller rood, langer geleden steeds doorzichtiger. Zwaardere aardbevingen zijn weergegeven als grotere bollen.
Via de knop rechts bovenin kunnen de lagen met voelbare en niet-voelbare bevingen aan- en uitgezet worden.

**TOELICHTING**
*	onderlegger is Stamen Toner Light. Hierdoor minder afleiding dan standaard topkaarten; vooral voor kleine schermen is dit belangrijk
* bevingen kleiner dan magnitude 1.2 zijn in de Groningse situatie niet voelbaar https://nl.wikipedia.org/wiki/Schaal_van_Richter). Deze hebben kleur groen en zijn in afzonderlijke laag gestopt die gebruiker kan uitzetten. Rode bevingen zijn (in principe) voelbaar. De zwaarste bevingen (magnitude 3+) zijn van een donkerder rood voorzien en zijn relatief nog wat groter gemaakt.
* de visual is zodanig opgezet dat de kaart aan alle schermgroottes aanpast zodat ook op kleine schermen de volledige functionaliteit behouden blijft. Zo werkt ook op een telefoon het werken met de lagen voor grotere en kleinere magnitude. Ik weet dat het ontwerp nu niet letterlijk mobile-first, maar gezien "de visual hoeft niet 100% af te zijn"  heb ik het gezien de tijd hierbij gehouden
* dat de opdracht "mobile-first" dient te zijn is wel even nieuw voor mij. Ik heb zoveel mogelijk met kleine schermen rekening gehouden, maar moet (en kan) mezelf hier nog in verbeteren.

**TODO**
* **[1] altijd tonen alle aardbevingen.** Nu zijn alle bevingen pas zichtbaar bij hoogste zoomlevel. Zou een simpele oplossing voor moeten zijn, OpenLayers kan prima al deze symbolen tegelijk tonen. Helaas realiseerde ik mij dit pas op het eind, leek het bijna opgelost, maar het onderzoek hiernaar loopt uit de tijd, dus nog niet gefixt...
* **[2] kaart mag niet gedraaid kunnen worden via touch**
* [gerelateerd aan vorige punt] bolgrootte bevingen afhankelijk van zoomlevel?
* voor de zwaarste aardbevingen (zie https://www.nu.nl/groningen/5078771/top-5-zwaarste-aardbevingen-in-groningen.html) in de popups informatie geven met Wikipedia- en NOS-links en bv een foto.
* opwaarderen voor grotere schermen: uitleg naast de kaart. meer mogelijkheden bv slider voor jaartallen
* opstartmelding via cookie eenmalig tonen
* beving "3+": tekst staat verkeerd uitgelijnd. In OpenLayers code duiken om dit op te lossen
* support voor selectie van bevingen in afzonderlijke jaren of via een slider
* opschonen laatst toegevoegde code

**TECHNISCH**

De basis is gemaakt in QGIS (v 3.2) met plugin qgis2web (v 3.4.0). Een uitgebreide nabwerking vindt handmatig plaats. Uitleg daarvan in <a href="nabewerking.md">nabewerking.md</a>

Ik heb een eenvoudig buildscript in Travis gemaakt. Dit test puur het kopiëren van de release versie naar een productiemap. In theorie zou alles vanuit source opgebouwd kunnen worden maar dan moet qgis via de commandline aangestuurd, moet de gebruikte plugin daarbij meewerken en dienen de handmatige wijzigingen achteraf ook ingescript te worden. Dit is best te doen maar erg tijdrovend, dus ik heb hier van afgezien.

