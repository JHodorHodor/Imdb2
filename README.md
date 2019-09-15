------------------------imdb2--------------------------

If you want to open source code in IntelliJ, probably you should choose: Run -> Edit Configuration -> VM Options and type:
"--module-path /usr/lib/jvm/java-11-openjdk-amd64/javafx-sdk-11.0.2/lib/ --add-modules=javafx.controls,javafx.fxml,javafx.graphics,javafx.base --add-exports=javafx.base/com.sun.javafx.event=ALL-UNNAMED"


INSTALLATION:

0. Preferowana wersja javy 11, może działać na wcześniejszych, ale nie musi.

1. Pobierz javafx 11.0.2 z: 
https://gluonhq.com/products/javafx/ 
(T na pewno działa, używanie skutkuje możliwością niedziałania.

2. Otwórz dołączony plik start.sh i podmień: [JAVAFX_PATH] na ścieżkę do folderu z pobraną javafx/lib
czyli na przykład, jeśli umieściłeś/aś pobrany folder w domyślnej lokalizacji javy (zalecane) to prawdobodobnie będzie to:
 /usr/lib/jvm/java-11-openjdk-am64/javafx-sdk-11.0.2/lib/

3. Nadaj odpowiednie uprawnienia wykonywania skryptowi.

4. W pliku config.properties wpisz odpowiednie dane. (database_name, user_name, password)

5. Załaduj naszą baze danych ze skryptu create.sql.

6. Odpal skrypt.

--------------------------------------------------------------------

Można utworzyć swojego użytkownika, ale nie będzie on miał wszystkich uprawnień i nie będzie sie dało przetestować dokładnie aplikacji, tak więc jest już utworzony urzytkownik admin (hasło: admin). Sugerujemy więc zalogowanie sie nia niego.

--------------------OPIS FUNKCJONALNOŚCI----------------------------

Aplikacja symuluje uproszczoną wersję serwisów typu filmweb, czy IMDb. Udostępnia następujące funkcjonalności:

1. Rejestracja nowych użytkowników.

2. Wyszukiwanie filmów lub "osób kina" (dalej będę do nich referował jako po prostu do osób).

3. Wyszukiwanie z pewnymi constrainami, aby to zrobić należy wybrać z lewej strony ekranu głównego odpowiednie, a następnie zaakceptować odpowiednim przełącznikiem. Dalej możemy już próbować wpisywać odpowienie imię lub nazwę i będą to tylko takie spełniające constraint.

4. Ranking (klikalny) filmów i osób, po śrenich ocenach użytkowników.

5. Wyświetlanie informacji o filmach/osobach na osobnym ekranie (po kliknięciu lub wyszukaniu).

6. Również na tym ekranie można ocenić film/osobę, dodać do ulubionych, lub (dla filmu) do watchlisty.

7. Ranking jest liczony i update'owany na bierząco. (potrzeba 5 głosów, aby ocena zostałą policzona)

8. Dla filmów tabelka z "similar movies", a dla osób z filmmami gdzie występowali jest klikanla(display movie).

9. Dla filmów istnieje możliwość dodania/usunięcia recenzji.

10. Wracając do ekranu głównego w prawym dolnym rogu są trzy przyciski dosyć sugestywnie podpisane. Na odpowiadających ekranach można usuwać/wyświetlać filmy/osoby z watchlisty/ulubionych.

----FUNKCJONALNOŚCI DODATKOWE NA KONCIE admin----

1. Dodawanie nowych filmów i osób (ekran główny)

2. Usuwanie filmów i osób (ekran filmu/osoby)

3. Edytowanie filmów i osób (ekran filmu/osoby)

Add 3. Niektóre pola są zablokowane do edycji, gdyż są kluczami głównymi, więc dla zachowania tożsamości obiektów edycja jest wyłączona. Nie pozwala to również adminom na oszustwa związane z ocenami.

--------------------------PODZIAŁ ZADAŃ------------------------------


-----Dominik Wielgórski:

- wyszukiwanie

- rankingi na głównym ekranie

- ekran watchlist / ulubionych

- usuwanie filmów / osób


-----Jędrzej Hodor:

- ekran logowania

- ekran filmów / osób (wyświetlanie informacji)

- przyznawanie ocen, dodawanie do ulubionych / watchlisty, recenzje

- wstawianie nowych filmów / osób

- edytowanie informacji o filmach / osobach


Pozostałe rzeczy takie jak wstępne podłączenie do bazy danych, czy szata graficzna były wykonane wspólnie.
Lekkim zmianom (w większości technicznym) uległ schemat bazy danych.
