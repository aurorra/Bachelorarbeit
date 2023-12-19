# Bachelorarbeit

In diesem Verzeichnis befinden sich alle Dateien für den schriftlichen Teil der Bachelorarbeit **Flesh Simulation with Application to Character Animation**. Als PDF-Datei ist die Arbeit gespeichert unter `ba_thesis_masanti/main.pdf` oder in diesem Verzeichnis in der Datei `ba_thesis_masanti.pdf`. Diese Bachelorarbeit entstand in Zusammenarbeit mit der Computer Graphics Group der Universität Bern. Weitere Informationen zur Gruppe und ihren vielfältigen Projekten sind unter [Computer Graphics Group - Universität Bern](http://cgg.unibe.ch/) ersichtlich.


## Abstract

This thesis explores the process of simulating the fleshy appearances of virtual characters. The focus lies on the formulation of the deformation energy. In order to accurately simulate a fleshy look, nonlinear hyperelastic energies have proven to be the best choice. But simulating volume-preserving biological tissues such as flesh yields more than a few mathematical and physical challenges. Achieving rest stability while working with a high Poisson’s ratio can be named as an example. Inspired by the complexity of this field, this thesis serves as an entry-level document. Relevant mathematical and physical aspects are presented and explained in an introductory manner. In addition, this thesis includes some more detailed calculations to bridge the gap between an expert in the field and a beginner. At the end of this thesis, I am presenting a few results visually to conclude the studies.

# Template

Das Template für dieses Dokument kann unter diesem Link gefunden werden: https://github.com/a-czyrny/LaTeX-Master-Vorlage. Die folgenden Anweisungen zur Benutzung wurden ebenfalls diesem Link entnommen.

# Benutzung

Um diese Vorlage nutzen zu können muss die benötigte Software installiert werden. Sobald dies der Fall ist, kann die Vorlage heruntergeladen und angepasst werden.

## Empfohlene Umgebung
Diese Dateien wurden unter der [TEX Live](http://tug.org/texlive/) Umgebung mit folgenden Programmen kompiliert.

- **Compiler**: lualatex
- **Bibliographie**: biber
- **Index**: makeindex (Ergänzungen unter Anmerkungen beachten)
- **Glossar**: makeglossaries

## Installieren der benötigten Software
### Windows
**Benötigte Software:**

* MikTex
* TexStudio

**Optionale Software:**

* ```git``` (zum Clonen und Contributen)
* ```perl``` (für ```latexmk```)
* ```latexmk``` (über MikTex)

### Linux (getestet mit Debian Jessie)
**Benötigte Software:**

* wget (```apt-get -y install wget```)
* texlive (```apt-get -y install texlive```)
* texlive Pakete:
        wget http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz &&\
        tar -xzvf install-tl-unx.tar.gz &&\
        rm install-tl-unx.tar.gz
        echo I | install-tl*/install-tl
* Pakete zu Path hinzufügen
        PATH=/usr/local/texlive/2015/bin/x86_64-linux:$PATH    
* Noch mehr settings:
        tlmgr conf texmf TEXMFHOME "/usr/local/texlive/2015/bin/x86_64-linux"

**Optionale Software:**

* ```git``` (zum Clonen und Contributen)
* ```perl``` (für ```latexmk```)
* ```latexmk``` (über MikTex)

## Herunterladen der LaTeX Dateien
Die Vorlage kann entweder mit ```git clone https://github.com/a-czyrny/LaTeX-Master-Vorlage.git``` (siehe optionale Software) oder mit über die GitHub Seite als *.zip Datei runtergeladen werden.


## Bearbeiten und Compilieren der LaTeX Dateien
### Windows
Unter **Windows** ist [TexStudio](http://www.texstudio.org/) als Editor empfohlen.

Wenn die Standardeinstellungen von TexStudio genutzt werden, müssen noch zwei manuelle Schritte durchgeführt werden:
1. Die Referenzen für das Glossar und das Abkürzungsverzeichnis müssen erstellt werden. In der Kommandozeile in dem Ordner der Vorlage:

    makeindex -s main.ist -t main.alg -o main.acr main.acn
    makeindex -s main.ist -t main.glg -o main.gls main.glo

2. Das LaTeX Dokument muss zwei mal compiliert werden (```F5```) damit alle Referenzen aufgelöst werden.

**Alternative**

Wenn ```latexmk``` installiert wurde (siehe optionale Software) kann im TexStudio unter "Optionen / TexStudio konfigurieren / Erzeugen" auch ```latexmk```als Standardkompiler angegeben werden.
```latexmk```funktioniert dann auch von der Kommandozeile aus

### Linux
Unter **Linux** kann die Vorlage mit dem Texteditor der Wahl editiert werden. Zum compilieren kann ```lualatex``` genutzt werden:

    lualatex -synctex=1 -interaction=nonstopmode main
    biber main
    makeindex main
    makeindex -s main.ist -t main.alg -o main.acr main.acn
    makeindex -s main.ist -t main.glg -o main.gls main.glo
    lualatex -synctex=1 -interaction=nonstopmode main
    lualatex -synctex=1 -interaction=nonstopmode main

**Alternative**
Wenn ```latexmk``` installiert wurde (siehe optionale Software) kann in dem Verzeichnis auch ```latexmk```angegeben werden. Dies führt die oben genannten Schritte aus.


# Anmerkungen
## Stichwortverzeichnis
Zum Erzeugen des Glossar und Abkürzungsverzeichnis muss "makeinxed" wie folgt aufgerufen werden:

*makeindex -s main.ist -t main.glg -o main.gls main.glo*

*makeindex -s main.ist -t main.alg -o main.acr main.acn*

Der Titel im Header der Seite muss zusätzlich in der Style-Datei "[indexstyle.ist](indexstyle.ist)" angepasst werden:

siehe: preamble "\\\markboth{**STICHWORTVERZEICHNIS**}{}\n\n\\begin{theindex}\n"
