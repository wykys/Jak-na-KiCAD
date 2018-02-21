# Instalace KiCADu

Školení předpokládá, že máte nainstalováno __aktuální noční sestavení__ a stažené knihovny.

## GNU/Linux

Uživatelé Linuxu mají život jednodušší, stačí si přidat `ppa` repozitář a nainstalovat potřebné balíčky. Pro jistotu jsi doporučuji ověřit adresu řepozitáře a názvy potřebných balíčků na stránkách [KiCADu](http://kicad-pcb.org/download/ubuntu/), protože se mohou od napsání návodu změnit. Uvedený postup je platný pro distribuce založené na Ubuntu.
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
