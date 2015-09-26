Zadanie 2
=========

1. Instalacja produktu `cdv` jako paczka developerska
 1. Przejdź do podfolderu `src` i sklonuj repozytorium z paczką `cdv-demo`:
    
    ```
    cd src
    git clone https://github.com/radekj/cdv-demo.git
    ```
    
 1. W pliku `buildout.cfg` dodaj w sekcji `develop` wpis:
    
    ```
    develop =
        src/cdv-demo
    ```

 2. W sekcji `eggs` dodaj wpis:
    
    ```
    eggs = 
        ...
        cdv
    ```

2.  Stwórz nowy portal z zainstalowanym produktem `cdv`

3. W definicji typu treści `Dom` dodaj nowe (wymagane) pole tekstowe 'Adres'

4. W widoku dla typu treści `Dom` (`house_view`) dodaj wyświetlanie treści pola dodanego w poprzednim punkcie

5. Zarejestruj nowy widok dla strony głównej portalu, który będzie listował 4 najnowsze oferty domów wyświetlane wraz z miniaturkami.
 
Przydatne linki:
----------------
* Dokumentacja developerska Plone: http://docs.plone.org
* TAL: http://docs.plone.org/adapt-and-extend/theming/templates_css/template_basics.html



