# Sensor Data Analysis Tool

Een Python-programma dat sensormetingen simuleert (of uit een CSV-bestand
laadt), analyseert met NumPy, weergeeft met Matplotlib en opslaat met de
`csv`-module.

## Installatie

```bash
pip install -r requirements.txt
```

## Gebruik

```bash
python sensor_monitor.py
```

Kies een van twee opties:

1. **Nieuwe metingen genereren**: voer sensortype, aantal metingen,
   minimum, maximum en drempelwaarde in. De metingen zijn reproduceerbaar
   (`random.seed(42)`) en worden opgeslagen in `sensor_readings.csv`.
2. **Laden uit CSV**: laad een bestaand bestand met een kolom `reading`,
   en voer daarna sensortype en drempelwaarde in.

## Uitvoer

- Statistieken in de terminal: aantal, gemiddelde, minimum, maximum,
  standaarddeviatie, aantal metingen boven de drempel en welke dat zijn.
- `sensor_readings.csv` (kolommen: `sample_number`, `reading`)
- `line_plot.png`: metingen per sample met de drempellijn
- `histogram.png`: verdeling van de metingen

## Foutafhandeling

Ongeldige invoer (tekst i.p.v. getal, 0 of negatief aantal metingen,
minimum groter dan of gelijk aan maximum), ontbrekende of foute
CSV-bestanden en problemen bij het opslaan geven een duidelijke
foutmelding in plaats van een crash.

## Structuur

`sensor_monitor.py` gebruikt alleen functies: `get_user_input()`,
`generate_readings()`, `calculate_statistics()`, `find_outliers()`,
`save_readings()`, `load_readings()`, `plot_readings()`,
`plot_histogram()` en `main()`.