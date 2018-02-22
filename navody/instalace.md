# Instalace [KiCAD](http://kicad-pcb.org/)u
Školení předpokládá, že máte nainstalováno __aktuální noční sestavení__ a stažené knihovny.

## GNU/Linux
Uživatelé Linuxu mají život jednodušší, stačí si přidat `ppa` repozitář a nainstalovat potřebné balíčky. Pro jistotu jsi doporučuji ověřit adresu řepozitáře a názvy potřebných balíčků na stránkách [KiCAD](http://kicad-pcb.org/download/ubuntu/)u, protože se mohou od napsání návodu změnit. Uvedený postup je platný pro distribuce založené na Ubuntu.
```bash
# přidání repozitáře
sudo add-apt-repository --yes ppa:js-reynaud/ppa-kicad
# aktualizace zdrojů sw
sudo apt update
# instalace KiCADu
sudo apt install kicad
```

Pokud byste rádi používali KiCAD v češtině, tak si můžete ještě nainstalovat lokalizační balíček.
```bash
# instalace českých překladů
sudo apt install kicad-locale-cs
```

Nakonec je vhodné nainstalovat oficiální KiCAD knihovny.
```bash
# instalace knihovny schématických značek
sudo apt install kicad-library-symbols
# instalace knihovny footprintů
sudo apt install kicad-library-footprints
# instalace knihovny 3D modelů
sudo apt install kicad-library-packages3d
# instalace knihovny šablon (pinouty: arduino, rpi, ...)
sudo apt install kicad-library-templates
```

## MS Windows
Uživatelé windows si musí ručně [stáhnout](http://downloads.kicad-pcb.org/windows/nightly/) instalační soubor a instalaci provést obvyklým způsobem. Upozorňuji, že je vhodné mít __aktuální verzi__. Bohužel ve Windows není pro KiCAD žádný aktualizační systém, z toho důvodu je třeba při každém vydání nové verze (což je u nočních buildů každý den) starou instalaci odstranit a nahradit novou.

Po instalaci je vhodné stáhnout oficiální [knihovny](http://kicad-pcb.org/libraries/download/) pro aktuální verzi, v našem případě __v5__. I zde uživatelé Windows zapláčou, jelikož knihovny jsou jednou týdně sestavovány a aktuální změny se musí opět provést ručně. Na stránkách knihoven se dá proklikat až k odkazům ke stažení `zip` archivům: [symbolů](https://github.com/KiCad/kicad-symbols/archive/master.zip), [footprintů](https://github.com/KiCad/kicad-footprints/archive/master.zip) a [3D modelů](https://github.com/kicad/kicad-packages3d/archive/master.zip). Stažené soubory je vhodné rozbalit v rootu disku například do vhodně pojmenované složky.
```bash
kicad              # hlavní složka pro knihovny například v C:
├── library        # sem rozbalit schématické značky
├── modules        # zde rozbalit footprinty
│   └── packages3d # Kicad zvyklost je mít v modulech složku pro 3D modely
└── template       # sem přijsou šablony
```

Uživatelé [gitu](https://git-scm.com/) nezoufejte, vy si můžete knihovny naklonovat a jen __pullovat__ změny.

## Ostatní OS
Uživatelům ostatních operačních systémů mohu předat [odkaz](http://kicad-pcb.org/) na oficiální stránky a popřát jim hodně štěstí s instalací ;)

## Pro uživatele [gitu](https://git-scm.com/)
KiCAD od v5 přechází na __nový systém knihoven__. Dílčí části byli rozděleny do samostatných repozitářů:
- [ ] [kicad-symbols](https://github.com/KiCad/kicad-symbols)
- [ ] [kicad-footprints](https://github.com/KiCad/kicad-footprints)
- [ ] [kicad-packages3D](https://github.com/KiCad/kicad-packages3D)
