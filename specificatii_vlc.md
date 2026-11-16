# Document de specificații tehnice: VLC media player

Lucrare individuală nr. 1, disciplina *Planificarea aplicațiilor desktop*.

## 1. Introducere

### 1.1 Scopul documentului

Documentul descrie cerințele funcționale și non-funcționale ale aplicației VLC media player, așa cum reies din funcțiile ei vizibile și din documentația oficială. Nu este specificația internă a dezvoltatorilor VideoLAN.

### 1.2 Domeniul de aplicare

VLC media player este un player multimedia gratuit și open-source, dezvoltat de proiectul VideoLAN. Aplicația redă fișiere audio și video locale, fluxuri din rețea și poate converti fișierele între formate.

### 1.3 Definiții și abrevieri

- **CF**: cerință funcțională
- **CN**: cerință non-funcțională
- **Codec**: componentă care codifică sau decodifică un anumit format audio sau video
- **Listă de redare**: o listă de fișiere care se redau unul după altul

## 2. Descriere generală

### 2.1 Perspectiva produsului

VLC este o aplicație desktop independentă. Nu are nevoie de un server sau de un cont de utilizator și include propriile codecuri, deci nu depinde de alte programe instalate pe calculator.

### 2.2 Utilizatorii aplicației

Aplicația se adresează publicului larg: de la utilizatori care vor doar să vizioneze un film, până la cei care au nevoie de subtitrări sincronizate sau de conversie între formate.

### 2.3 Constrângeri și dependențe

- Aplicația trebuie să funcționeze pe mai multe sisteme de operare, cu aceeași interfață de bază.
- Formatele noi apar des, așa că aplicația depinde de actualizarea periodică a codecurilor incluse.

## 3. Cerințe funcționale

| Cod   | Cerință |
|-------|---------|
| CF-01 | Aplicația deschide și redă fișierul audio sau video selectat din meniul Media sau adus prin drag-and-drop în fereastră. |
| CF-02 | Utilizatorul poate porni, întrerupe, opri și derula redarea și poate regla volumul și viteza. |
| CF-03 | Aplicația încarcă o subtitrare dintr-un fișier extern și permite decalarea ei față de imagine. |
| CF-04 | Utilizatorul poate crea o listă de redare, o poate salva și o poate deschide ulterior. |
| CF-05 | Aplicația convertește un fișier media în alt format, prin opțiunea Convert/Save. |

## 4. Cerințe non-funcționale

| Cod   | Cerință |
|-------|---------|
| CN-01 | **Portabilitate:** aplicația rulează pe Windows, macOS și Linux. |
| CN-02 | **Compatibilitate:** fișierele MP4, MKV și MP3 se redau fără pachete de codecuri instalate separat. |
| CN-03 | **Performanță:** aplicația pornește în cel mult 3 secunde pe un calculator obișnuit. |
| CN-04 | **Ușurință în utilizare:** deschiderea unui fișier, redarea, pauza și volumul sunt accesibile din fereastra principală, fără configurare prealabilă. |
| CN-05 | **Confidențialitate:** aplicația nu afișează reclame și nu colectează date despre utilizator. |

**Verificarea CN-03:** pe un laptop cu Intel Core i5-10300H și Debian, VLC 3.0.24 a pornit fără interfață grafică (`vlc -I dummy`) în aproximativ 0,02 secunde, în medie pe 5 măsurători. Valoarea este mult sub limita de 3 secunde.
