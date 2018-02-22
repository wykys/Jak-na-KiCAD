# Nastavení knihoven v [KiCAD](http://kicad-pcb.org/)u
Jestli jste zvládli instalaci a máte i stažené knihovny (pokud používáte Linux knihovny se stáhnou přímo z repozitářů), tak nastal ten správný čas, abychom si ukázali, jak říci KiCADu, kde je hledat.

## Nastavení proměnných prostředí
Nastal čas poprvé spustit KiCAD. V navigační liště: `Nastavení > Configure Paths...`, čím se dostaneme k formuláři určenému k nastavené proměnných prostředí.

Zajímají nás proměnné:
- [ ] `KICAD_PTEMPLATES` - šablony
- [ ] `KICAD_SYMBOL_DIR` - schématické značky
- [ ] `KISYS3DMOD` - 3D modely
- [ ] `KISYSMOD` - footprinty

| Název              | Cesta                                 |
| :------------------|:--------------------------------------|
| `KICAD_PTEMPLATES` | `/usr/share/kicad/template`           |
| `KICAD_SYMBOL_DIR` | `/usr/share/kicad/library`            |
| `KISYS3DMOD`       | `/usr/share/kicad/modules/packages3d` |
| `KISYSMOD`         | `/usr/share/kicad/modules`            |

Pokud používáme Linux a knihovny máme nainstalované pomocí balíčkovacího systému, tak se budou nacházet ma místech odpovídající tabulce výše.

Jestli používáme Windows a nebo máme knihovny uložené v jiných složkách, tak si cesty upravíme tak, aby odpovídali naší konstelaci.

Poté je dobré KiCAD restartovat.

## Nastavení knihoven schématických symbolů
Abychom mohli nastavit knihovny je třeba založit nový projekt: `soubor > New > Project` případně `Ctrl+N`. Tím se nám vytvoří 3 soubory:
- [ ] `*.pro` - soubor projektu
- [ ] `*.sch` - schématický soubor
- [ ] `*.kicad_pcb` - soubor plošného spoje
Dvojlklikem na schématický soubor, nebo kliknutím na ikonku schématu, či klávesovou zkratkou `Ctrl+E` spustíme program __eeschema__.

Je možné, že při prvním spuštění na nás vyskočí "nějaké dialogové okno", pokud tato situace nastane, tak jej zavřeme a pokračujeme.

KiCADu 5 se pokouší sjednotit správu knihoven pro schématické značky a footprinty pomocí tabulek knihoven. Na Linuxu jsou umístěny `$HOME/.config/kicad`. Při prvním spuštění je třeba tyto tabulky vytvořit. Pomosí těchto tabulek KiCAD knihovny hledá.

Poznámka stranou: kromě globálních tabulek které právě vytváříme se dají vytvářet i projektové tabulky pro jednotlivé projekty, které často využívají proměnné `KIPRJMOD`, která ukazuje na umístění aktuálního projektu.

Ve schématickém editoru: `Preferences > Manage Symbol Library Tables...`. Ujistíme se, že se nacházíme v kartě __Global Libraries__. Označíme všechny knihovny, které jsou ve formuláři a stiskneme `Remove Library`.

Poté stiskneme `Browse Libraries...` půjdeme do složky kde jsou uložené schématické značky a přidáme všechny `*.lib`. Pokud jsme postupovali správně, tak Můžeme pozorovat, že v cestách přidaných knihoven se použili proměnné prostředí. Poté stiskneme `Budiž`. Nakonec si můžeme ověřit, že vše funguje klávesovou zkratkou `A`, ta nám otevře formulář pro vkládání symbolů. Editor schémat zavřeme.

## Nastavení knihoven footprintů
Otevřeme si editor plošných spojů, tedy program __pcbnew__ (dvojklik na `*.pcb_new`, nebo `Ctrl+P`). Postup bude obdobný jako u schématických knihoven. Tedy: `Preferences > Footprint Library Tables...`. A od teď postupuje jako u knihovny symbolů, jen s tím rozdílem, že přidáváme místo souborů `*.lib` složky `*.pretty`, které se nacházení ve složce `modules`. Po dokončení opět potvrdíme. Přidané knihovny si můžeme prohlédnout pomocí nástroje __Open footptint viewer__ na horní liště nástrojů.
