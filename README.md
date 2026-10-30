# Cel de nit

Planificador d’astrofotografia pensat per a les sessions amb el **Dwarf Mini**. És una sola pàgina web (`index.html`), sense instal·lació ni dependències: s’obre al navegador, també des del mòbil.

## Què fa

- **Gràfic de la nit**: altura del Sol, la Lluna i l’objecte triat, amb les franges de crepuscle i foscor total.
- **Previsió de núvols** hora a hora, pintada sobre el gràfic (dades d’[Open-Meteo](https://open-meteo.com/)).
- **Lluna**: fase, percentatge il·luminat, sortida i posta, i hores de cel fosc sense Lluna.
- **Foscor**: posta de Sol, crepuscles civil i nàutic, inici i final de la foscor total, sortida del Sol.
- **Què fotografiar**: 15 objectes de cel profund ordenats segons les hores de cel clar i fosc amb l’objecte per sobre de 30°, penalitzant la Lluna brillant i propera.
- **Camp de visió**: calcula els graus a partir de la focal i el sensor, i diu si cada objecte hi cap.
- **Ubicació**: GPS del dispositiu, coordenades a mà, o cerca a OpenStreetMap i enganxa’n les coordenades o l’enllaç.
- **Registre de sessions** (es desa al navegador, amb `localStorage`).
- **Mode nit en vermell** per conservar l’adaptació de la vista al camp.

## Ús

Obre `index.html` al navegador, o la pàgina publicada. Indica la ubicació i la data, i la pàgina fa la resta. La previsió de núvols necessita connexió a internet; sense ella, hi ha un camp per introduir els percentatges a mà.

> **Important:** el camp de visió porta valors de partida orientatius (focal 100 mm, sensor 5,57 × 3,13 mm), que no són els del Dwarf Mini. Substitueix-los pels de les especificacions oficials del Mini.

## Publicar-la a GitHub Pages

1. Crea un repositori nou a GitHub (per exemple `cel-de-nit`), públic.
2. Puja-hi els fitxers d’aquesta carpeta: **Add file → Upload files**, arrossega’ls i fes **Commit changes**. Amb git:
   ```bash
   git init
   git add .
   git commit -m "Primera versió"
   git branch -M main
   git remote add origin https://github.com/EL_TEU_USUARI/cel-de-nit.git
   git push -u origin main
   ```
3. Al repositori, ves a **Settings → Pages**. A **Build and deployment**, tria **Deploy from a branch**, la branca `main` i la carpeta `/ (root)`, i desa.
4. Al cap d’un parell de minuts, la pàgina és a `https://EL_TEU_USUARI.github.io/cel-de-nit/`.

GitHub Pages serveix la pàgina per HTTPS, que és el que cal perquè el botó **Usa la meva ubicació** funcioni.

## Dades i atribució

La previsió de núvols ve de l’API d’[Open-Meteo.com](https://open-meteo.com/), que publica les dades sota llicència CC BY 4.0 i demana atribució (ja és al peu de la pàgina). L’ús gratuït és per a projectes no comercials; consulta’n les condicions d’ús si tens previst fer-ne un altre ús.

## Limitacions

- Els càlculs astronòmics són aproximacions de baixa precisió (errors d’uns pocs minuts en les hores). Contrasta’ls amb Stellarium abans d’una sessió important.
- No hi ha planetes, mapa de contaminació lluminosa ni realitat augmentada.
- El catàleg d’objectes és curt i editable a la constant `OBJ` de l’script.

## Llicència

Autor: Albert Saragossa Alòs
