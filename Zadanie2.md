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

3. W definicji schemy dla typu treści `Dom` dodaj nowe (wymagane) pole tekstowe 'Adres'

   (ref. dot. pól i widgetów w Archetypes:
    * https://plone.org/products/archetypes/documentation/old/arch_field_quickref_1_3_1
    * https://plone.org/products/archetypes/documentation/old/arch_widget_quickref_1_3_1
   )

4. W widoku dla typu treści `Dom` (`house_view`) dodaj wyświetlanie treści pola dodanego w poprzednim punkcie

  (ref. dot. szablonów TAL: http://docs.plone.org/adapt-and-extend/theming/templates_css/template_basics.html)

5. Zarejestruj nowy widok dla strony głównej portalu, który będzie listował 4 najnowsze oferty domów wyświetlane wraz z miniaturkami:
  1. W module `browser` stwórz moduł `home_page_view.py` z definicją klasy widoku
  2. Stwórz szablon `home_page_view.pt` wypełniający slot `content-core` w makrze `main_template/macros/master` 
  3. Zarejestruj widok w pliku `browser/configure.zcml` pod nazwą `home_page_view`
  4. Ustaw zarejestrowany widok, żeby był możliwy do wybrania jako widok na obiekcie typu PloneSite
     (w pliku `profiles/defrault/types/Plone_Site.xml`). Pamiętaj o koniecznośći przeinstalowania produktu w panelu        zarządzania dodatkami (`Add-ons`) po dokonaniu zmian w pliku xml.
  
  
Przydatne linki:
----------------
* Dokumentacja developerska Plone: http://docs.plone.org
* TAL: http://docs.plone.org/adapt-and-extend/theming/templates_css/template_basics.html
* Rejestracja nowego widoku: http://docs.plone.org/develop/addons/helloworld/extend/view.html
* link do slajdów prezentowanych na zajęciach: http://goo.gl/m5QjX8


