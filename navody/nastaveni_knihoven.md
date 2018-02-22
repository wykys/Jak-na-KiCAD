# Nastavení knihoven v [KiCAD](http://kicad-pcb.org/)u
Jestli jste zvládli instalaci a máte i stažené knihovny (pokud používáte linux knihovny se stáhnou přímo z repozitářů), tak nastal ten správný čas, abychom si ukázali, jak říci KiCADu, kde je hledat.

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
