Instalacja w Cloud9
===================

1. Pobierz instalator plone:
  ```
  wget wget https://launchpad.net/plone/4.3/4.3.6/+download/Plone-4.3.6r1-UnifiedInstaller. 
  ```
 
2. Rozpakuj pobrane archiwum: 
  ```
  tar xzf ./Plone-4.3.6r1-UnifiedInstaller.tgz
  ```

3. Przejdź do rozpakowanego archiwum: 
  ```
  cd ./Plone-4.3.6r1-UnifiedInstaller/
  ```

4. Uruchom skrypt instalacyjny (bez sudo!) podając ścieżkę docelową w katalogu domowym: 
  ```
  ./install.sh standalone --target="${HOME}/workspace/plone" --instance=Plone --static-lxml 
  ```

5. Przejdź do lokalizacji, w której zainstalował się Plone:
  ```
  cd /home/ubuntu/plone/workspace/Plone 
  ```

6. Dodaj użytkownika inicjalnego o podanej nazwie (plone) i haśle (123123, można zmienić): 
  ```
  ./bin/instance adduser plone 123123 
  ```
  (poczekaj chwilę, aż zostanie wypisany komunikat: "Created user: plone") 
 
7. Uruchom aplikację: 
  ```
  ./bin/instance fg 
  ```

8. Otwórz stronę w przeglądarce i zaloguj się na użytkownika, którego stwożyłeś. 
(adres: `https://${nazwa_twojego_projektu}­c9­${nazwa_użytkownika}.c9.io/` 
lub button 'Preview' ­> 'Preview with Web Server') 
 
9. Instalacja dodatkowych produktów:

  1. Zatrzymaj instancję 
  
  2. Dodanie zależności do instalowanego produktu: 
    W pliku `~/plone/Plone/buildout.cfg` w opcji 'eggs' dodaj nazwę produktu, np:
    ```
    eggs = 
        Plone 
        Pillow 
        Products.Ploneboard
    ```

  3. Przebuduj instancję: 
    ```
    ./bin/buildout -Nv -t 3
    ```

  4. W panelu zarządzania portalem (link `Ustawiania witryny`) przejdź do panelu zarządania 
  dodatkowymi produktami (`Add-ons`), zaznacz checkbox przy wybranym produkcie i kliknij 
  przycisk `Aktywuj`. 
