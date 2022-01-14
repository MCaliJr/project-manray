# Propozycja projektu - SHT - SafeHypeTrade marketplace dla hypebeastów (coś a'la Vinted tylko skupione na bezpieczeństwie użytkowników):

**Node.js / Express**

- REST API
  - tworzenie bazy danych użytkownika
    - ogłoszenia
    - zdjęcia
    - informacje
    - dane na temat bezpieczeństwa (żeby uchronić przed scamem <-- główny feature apki!!!)
  - wyświetlanie elementów z bazy danych użytkownika jako aukcje / sprzedaż
- zakładanie konta użytkownika
- autoryzacja i autentykacja użytkownika, różne uprawnienia. Wykorzystanie Json Web Token.
- wykorzystanie bazy danych (NoSQL lub SQL)
  - może tutaj powinno być to co w REST API <-- wtedy z API inne dane musimy brać - np. informacje na temat ciuchów konkretnych marek, jakieś opinie czy coś w ten deseń - może fotki też. Do obczajenia
- integracja z jakimś zewnętrznym systemem (np. wysyłanie e-maili)
  - wysyłanie maili potwierdzających założenie oraz zarządzanie kontem
  - płatności za aukcje / ogłoszenia sprzedaży - może opcja krypto?
  - dream: integracja z jakimś Vinted czy coś i nakładanie layeru bezpieczeństwa na ogłoszenia stamtąd za mały % od transakcji
  - identyfikacja użytkowników na podstawie selfie z dowodem
- pisanie testów

**React**

- Komunikacja klient — serwer
  - wszelka funkcjonalność - przeglądanie ofert, sortowanie, dodawanie, usuwanie, licytowanie, potwierdzanie "legitności" innych użytkowników
    Cała reszta z dołu to wiadomo, ciężko bez tego stworzyć produkt:
- functional component
- React hooks
- tworzenie list komponentów
- JSX
- pisanie testów

Aplikacja musi korzystać z bazy danych (noSQL lub SQL) i zostać wykonana w architekturze Klient-Serwer (składać się co najmniej z 3 jednostek wdrożeniowych, tzn.: aplikacja webowa, backend i baza danych).

Back-end zależy zaimplementować za pomocą frameworka Express.js lub NestJS (uczą się go backendowcy w ostatnim rozdziale).

Front-end wykonajcie przy użyciu biblioteki React.

Sugerujemy w czasie działu 3 implementować część back-endową, a wczasie działu 2-go część front-endową.

Ale to Wy odpowiadacie za powodzenie projektu, więc podejmujcie decyzje, korzystajcie z porad bardziej doświadczonych
i zróbcie coś niesamowitego! W trakcie trwania projektu odbędą się dwie prezentacje (z częstotliwością jak dotychczas).

## Projekt końcowy — aplikacja webowa

Platforma, której celem jest poprawa procesu wtórnego handlu ubraniami.
Pozwala na realizację transakcji pomiędzy dwiema stronami w sposób **bezpieczny**. To znaczy, że to nie klienci muszą zastanawiać się, czy przypadkiem po drugiej stronie nie ma oszusta, a sam system jest w pewien sposób odporny na znaczną część podejrzanych działań.

Analizując feedback społeczny dotyczący mediów sprzedażowych takich jak grupy Facebookowe oraz Vinted można zauważyć znaczny poziom niezadowolenia szczególnie wśród osób zajmujących się handlem rzeczami o stosunkowo wysokiej wartości. Narażeni są oni bowiem na kontakt z osobami chcącymi oszukać / wyłudzić rzecz albo pieniądze. Dodatkowo po fakcie nieudanej transakcji obsługa klienta w wielu przypadkach jest w znacznym stopniu mało skuteczna, często też ostatecznie podejmowane są przez nich złe decyzje.

Chcąc podejść do tematu w sposób systemowy należałoby stworzyć możliwość przeprowadzenia bezpiecznej transakcji wyłączając oszustów z obiegu. Aby tego dokonać należałoby podjąć następujące kroki:

- Wymusić na użytkownikach obowiązkowy ID Check (wykonanie zdjęcia wraz z dowodem). Będzie to miało następujący wpływ – ludzie wiedząc, że ich dane są w systemie nie będą tak chętni do nieuczciwych zachowań, ponieważ będą mogli zostać pociągnięci do odpowiedzialności, oraz osoba, której konto zostało zablokowane nie będzie mogła w prosty sposób na platformę wrócić.

- Oprzeć proces na ludziach wiarygodnych (potwierdzonych swoją historią transakcji lub poleceniem od sprawdzonych użytkowników)
  Osoby wykonujące transakcje w sposób bezproblemowy będą zyskiwały pozytywne oceny, które potem będą znaczące pod względem dalszej funkcjonalności użytkownika w całym procesie.

- Zastąpić niekoniecznie kompetentne osoby pracujące w obsłudze klienta i również zajmujące się rozstrzyganiem sporów samymi użytkownikami.

## SafeHypeTrade — Założenia projektowe:

> **_Liczy się czas „time to market”, dlatego na samym początku, określcie główne funkcjonalności, które apka potrzebuje._**

Przykładowy proces transakcji (sprzedaż):

1. Osoba dowiaduje się o istnieniu platformy i postanawia ją wypróbować. Wchodzi na stronę i zakłada konto. Konto przed odblokowaniem jakiejkolwiek funkcjonalności musi zostać potwierdzone tzn. Osoba musi wysłać zdjęcie ze swoim dowodem, które zostanie potem sprawdzone przez firmę.
1. Po zatwierdzeniu konto, osoba może wystawić przedmiot na sprzedaż. Typowy serwis tego typu tj. zdjęcia plus opis. Oczywiście każdy będzie miał swoją stronę profilową, gdzie pokazane są ogólne informację o niej (oczywiście wszystkie istotne dane wrażliwe są ukryte), widoczne są oceny, czy wszystkie przedmioty które sprzedaje.
1. Po znalezieniu potencjalnego kupca strony zaczynają ze sobą rozmawiać. Ustalają wszystkie szczegóły, dogadują cenę. Może im się np. pojawiać dymek z checkpointami, które warto ustalić wcześniej. Potem, jeżeli ktoś ma takie życzenie może zaznaczyć w aplikacji, że chce, aby do tej rozmowy dolosowano trzecią stronę. Byłaby to osoba, która 1) Ma dużo pozytywnych opinii 2) W swojej historii transakcji np. zajmowała się już sprzedażą / kupnem rzeczy podobnej marki. Oczywiście wcześniej byłaby zbudowana baza osób, które zarówno chcą, jak i mają wystarczająco dobre recenzje, aby takie zadanie spełniać. Wówczas taka osoba miałaby dostęp do konwersacji, zostałaby do niej dołączona i mogłaby się wypowiedzieć w przypadku wątpliwości. Dodatkowo osoba ta sprawdzałaby, czy ogólne ustalenia wyglądają dobrze, ale też czy wrażenie, które robi każda ze stron wydaje się w porządku. W przypadku jakichkolwiek niejasności lub przypuszczeń, że jedna z osób przeprowadzających transakcję może próbować oszustwa, wówczas próbuje
   a) doradzić drugiej stronie, która jest w porządku na temat decyzji
   b) podjąć odpowiednie kroki np. oznaczając jako osobę podejrzaną.
   Paragraf poświęcony stronie doradczej:
   W zamian za wykonywanie funkcji na rzecz społeczności aplikacji, osoby miałyby dodatkowe benefity np. w postaci zbierania punktów, które można wykorzystać jako walutę do reklamowania swoich własnych aukcji lub obniżki cen poprzez wymianę punktów za złotówki w ramach jakiegoś przelicznika.
1. Transakcja może przebiegać ostatecznie według dwóch schematów:
   a) Przebiega bezproblemowo
   Jeżeli podczas przeprowadzenia kupna / sprzedaży nie wynikną żadne nieprawidłowości, wówczas obie strony są usatysfakcjonowane. Mogą wystawić sobie wzajemnie ocenę, mogą też wystawić ocenę osobie, która pomogła im podczas ustaleń.
   b) Jedna ze stron okazała się nie w porządku
   W przypadku, gdy jedna ze stron okazała się oszustem, czyli np. w przypadku kupującego byłyby to następujące zachowanie:
   - w jakiś sposób cofnęła wykonaną transakcję
   - po odebraniu paczki wysłała do obsługi klienta, że paczka się nie zgadza z opisem; produkt jest wadliwy; produkt jest nieoryginalny i w związku z tym rząda zwrotu pieniędzy, mimo że produkt zgadza się z opisem na aukcji
   - w ogóle nie wykonała transakcji (to akurat chciałbym rozwiązać systemowo w jakiś sposób)
   - Itd.
     W przypadku sprzedającego:
   - nie wysłanie produktu, mimo otrzymania pieniędzy
   - wysłanie produktu niezgodnego z opisem i zdjęciami na aukcji
   - wysłanie innego produktu
   - Itd.
     Wówczas otwierana jest sprawa sporna, w której obie strony próbują dowieźć swojej racji. Teraz sytuacja w przypadku pociągnięcia do odpowiedzialności jednej ze stron w przypadku dużej wartości przedmiotu nie będzie problemem, ponieważ platforma posiada dostęp do dokumentu identyfikującego każdego użytkownika.
     Sprawa sporna może być rozstrzygana w następujący sposób. Dobierane do danej sprawy byłyby osoby np. do liczby pięć. Osoby zajmujące się tą sprawą miałyby wgląd we wszystkie konwersacje oraz ustalenia sprawy, natomiast nie mogłyby zidentyfikować osób biorących w niej udział (aby zachować anonimowość oraz bezstronność osądzających). Po jakimś określonym czasie dochodziłoby do głosowania (dlatego nieparzysta liczba osób) zakończonego werdyktem.
     1.Przeprowadzając transakcję w taki sposób osiągamy kilka istotnych benefitów względem istniejących już rozwiązań tzn.:
     a) Posiadanie niezbędnych informacji na temat każdego użytkownika
     b) Włączenie do procesu rozstrzygania sporów sprawdzone osoby ze środowiska, które mają wiedzę na temat sposobów oszukiwania, czy udawadniania racji jednej ze stron w tym segmencie.
     c) Ogólne zaangażowanie społeczności platformy do oczyszczania bazy użytkowników z oszustów.
     d) Ograniczenie rozwijania w nieskończoność działu obsługi klienta

<!-- ## Wymagania

Klient wraz z analitykiem biznesowym spisali podstawowe wymagania co do projektu.
Jednakże nie krępujcie się przed ich doprecyzowaniem / zmianami, czy też ulepszeniami.
To Wy jesteście profesjonalistami w swoim fachu i Klient ufa, że zrobicie wszystko jak najlepiej.
Jeśli uważacie, że jakichś informacji Wam brakuje, najlepiej, jeśli Product Owner spróbuje uzupełnić luki w wymaganiach wraz z klientem.
Wymagania podzielono na dwie sekcje. Aplikację dla widza i panel administracyjny. -->

<!-- ### Prototyp interfejsu użytkownika

Niestety współpraca z grafikiem projektującym interfejs nie układała się najlepiej i jego praca nie została skończona.
Wasz zespół zobowiązał się do pokrycia wymaganych funkcjonalności, chociaż nie na wszystko znajdziecie projekty interfejsu.
Możecie sami wykonać projekty ekranów i/lub od razu implementować. Warto wzorować się na rozwiązaniach konkurencyjnych.
Projekt grafika znajdziecie tutaj: https://www.figma.com/file/cuKLOWensUxkq5dYB082yd/CodersCamp2020.Project.FullStack-Node-React.Cinema?node-id=4412%3A3065
 -->

### Wymagania funkcjonalne:

> **_Do modyfikacji / uzupełnienia!!!_**

1. Klient może zarejestrować się w systemie, podając imię, nazwisko, hasło i adres e-mail.
1. Klient może zalogować się w systemie, podając adres e-mail i hasło.
1. Klient może przeglądać filmy „nadchodzące". Czyli takie, które są dostępne dla kina, ale nie zaplanowano jeszcze dla nich żadnych seansów.
1. Klient wybiera film i seans, na jaki chce kupić bilet / zarezerwować miejsce.
1. Klient może przeczytać szczegóły o filmie takie jak: Tytuł, rok produkcji, opis fabuły, plakat, kategorie (może być kilka), czas trwania.
1. W przypadku rezerwacji miejsca płatność odbywa się w kasie. Jeśli klient kupuje bilet, płatności należy dokonać on-line.
1. Rezerwacji może dokonać jedynie zarejestrowany klient.
1. Zakupu można dokonać bez rejestracji — podając jedynie adres email.
1. Jeśli rezerwacja nie zostanie odebrana na 15 minut przed rozpoczęciem seans, miejsce zostaje zwolnione, a rezerwacja anulowana.
1. Jeden klient nie może zarezerwować więcej niż 20 miejsc na jeden seans.
1. Klient powinien zostać poinformowany o statusie swojej płatności w systemie.
1. Klient powinien otrzymać bilet na podany przy zakupie / rejestracji adres email.

### Panel Administracyjny (zarządzanie użytkownikami, planowanie widoku, podgląd revenue):

#### Wymagania funkcjonalne:

> **_Do modyfikacji / uzupełnienia!!!_**

1. Administrator wprowadza informację o placówkach w sieci kin. Sieć ma zamiar posiadać Kina w różnych miastach na całym świecie.
   Dlatego konieczne jest, aby prowadzić ewidencję Kin sieci. Kino musi mieć swój unikalny numer identyfikacyjny. Każda placówka ma określony adres i godziny otwarcia.
1. Administrator wprowadza informacje o filmie, który będzie dostępy dla wszystkich placówek w sieci.
1. Usunięcie filmu powinno skutkować odwołaniem wszystkich zaplanowanych projekcji, anulowaniem rezerwacji i wysłaniem do klientów, którzy zakupili bilety, wiadomości o zwrocie kosztów.
1. Administrator wprowadza informacje o seansach w danych kinie i przypisuje do seansu salę kinową i film oraz określa godzinę.
1. W danej sali kinowej nie mogą odbywać się 2 seanse jednocześnie. Dodatkowo między seansami należy zachować co najmniej 15 minutową przerwę na sprzątanie.
1. Seans musi się kończyć co najmniej 15 minut przed zamknięciem kina i zaczynać minimum 15 minut po otwarciu kina.
1. Każda sala kinowa ma określone, ile posiada kolumn i rzędów (zakładamy uproszczony model prostokąta).
1. Administrator zarządza listą cen za bilety. Wybiera jakie bilety są dostępne na które seanse. (np. na seans premierowy nie obowiązują zniżki, ale na resztę można zakupić bilet studencki).
1. Administrator otrzymuje raport w czasie rzeczywistym o liczbie sprzedanych i zarezerwowanych miejsc. Dzięki temu będzie mógł podejmować
   decyzje, które zwiększa przychód.
1. Administrator może konfigurować czy na dany seans można zostawiać (w czasie zakupu lub rezerwacji) puste miejsca na rogu rzędów.
   Tę zasadę może zmienić w każdym momencie.
1. Administrator może włączyć specjalny tryb pandemii, w którym muszą być przynajmniej 2 miejsca odstępu w jednym rzędzie, między miejscami
   z 2 różnych rezerwacji / zakupów.

## Możliwe usprawnienia i dodatkowe funkcjonalności:

> **_Jak macie pomysły na więcej niż tutaj to proszę bardzo 🔥_**

1. Integracja z zewnętrznym systemem płatności — np. PayU (wykorzystać Sandbox, który umożliwia testowanie płatności bez prawdziwych transakcji)
1. Sprawdzanie biletów — generowanie kodu QR z zakupionym biletem. Bilet jest „sprawdzony” po zeskanowaniu kodu QR telefonem.
1. Kreator do ustawiania miejsc na sali w bardziej skomplikowany sposób niż wspomniany prostokąt.

<!-- ## Dodatkowe zadania (wykraczające poza zakres kursu):

1. Wykonanie testów E2E, przy użyciu odpowiedniego narzędzia. Proponujemy np. Cypress.
1. Utworzenie Storybook dla zdefiniowanych komponentów.

Wszelkie inne dodane przez Was funkcjonalności czy usprawnienia infrastrukturalne należy przedstawić w README.md projektu :) -->
