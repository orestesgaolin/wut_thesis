# wut_thesis
LaTeX **unofficial** template for diploma thesis on Warsaw University of Technology (2016)

## Opis [PL]
Witaj, to szablon pracy dyplomowej częściowo przystosowany do nowych wymagań edycyjnych PW. Zapoznaj się z kodem źródłowym przed przystąpieniem do pracy. Na początek wymienię kilka ważnych uwag:

* ustawienia dokumentu znajdują się w pliku config.tex,
* niestety ze względu na użycie płatnych fontów w stronie tytułowej aktualna wersja używa plików .png (Jeśli uda się dostać nagłówek i rodzaj pracy w krzywych, to zostaną one podmienione),
* bibliografia używa stylu zbliżonego do stylu harwardzkiego, a cytowania są w większości zgodne z zaleceniami BG PW; można to zmienić w pliku konfiguracyjnym na cytowania numeryczne,
* do kompilacji polecam TeXstudio 2.10.8 + MiKTeX w sekwencji pdflatex + biber + pdflatex + pdflatex (By dodać w TeXstudio przejdź do Opcje > Build > User commands i dodaj: `txs:///pdflatex | txs:///biber | txs:///pdflatex | txs:///pdflatex`) (czasem warto powtórzyć 2-3 razy, by zaktualizowała się bibliografia); do podglądu zaś [Sumatra PDF](https://www.sumatrapdfreader.org/). Działa też z Visual Studio Code (zob. niżej).
* do zarządzania bibliografią polecam oprogramowanie [Zotero](https://www.zotero.org/) i opcja Better BibTeX.

## Porównanie
![Comparison with official word template](https://github.com/orestesgaolin/wut_thesis/raw/master/img/comparison.png "Comparison")

## Wsparcie
BTC 1P6ofZnewRSWDfFHAKeDeh3Xw8Y5TjCk6y
DOGE DKjAgwqaM8sJPKGozcJheudVxhGBFQnxZE
MONERO 42oGFKK3BRHbZxLzVpE4sd4gMkjdxJdZv8ywBbC1PkMNWXuzD3ngcZv7wa9j3Fqqkb1N5rsfb4aLkP1YcNH9mK4pVeD895V

## Konfiguracja dla VS Code + LaTeX Workshop
settings.json:
```json
{
    "[latex]": {
        "editor.wordWrap": "on"
    },
    "latex-workshop.latex.toolchain": [{
        "command": "pdflatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    }, {
        "command": "biber",
        "args": [
            "%DOCFILE%"
        ]
    }, {
        "command": "pdflatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    }, {
        "command": "pdflatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    }]
}
```

## Rozwiązywanie błędów
W przypadku błędu: `FATAL miktex-makepk - PK font t1-zi4r-0 could not be created.` można posłużyć się radą [stąd](https://tex.stackexchange.com/a/129523/100921).
