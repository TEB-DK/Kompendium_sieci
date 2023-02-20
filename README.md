<h1 align="center">🌐 Podstawy sieci komputerowych 🌐</h1>
  
  Zanim jednak zostaną zgłębione tajniki sieci oraz protokołów, to należy najpierw poznać podstawowe pojęcia użytkowane w domenie sieciowej.


## 📚 Podstawowe pojęcia

  ### Sieć komputerowa
  > jest to zbiór urządzeń komputerowych, takich jak komputery, drukarki, telefony czy telewizory, połączonych ze sobą w celu wymiany danych. Do podłączenia urządzeń stosuje się media transmisyjne, a dane przekazywane są za pomocą protokołów komunikacyjnych.

  ### Adres IPv4
  > to adres zapisany na ``32 bitach``, gdzie każde 8 bitów to ``oktet``, np. pierwsze 3 oktety odpowiadają za sieć, a ostatni za hosta. Jest to numer identyfikacyjny hosta, który służy do prawidłowej komunikacji między urządzeniami. Zapisywana dla ułatwienia w postaci ``dziesiętnej`` (np. 192.168.34.200).

  ### Adres IPv6
  > rozszerzenie adresacji ``IPv4``, które zostało powołane do życia z powodu szybko kończących się adresów swojego poprzednika. Podstawowymi zadaniami nowej wersji protokołu jest zwiększenie przestrzeni dostępnych adresów poprzez zwiększenie długości adresu z 32 bitów do ``128 bitów``. Zapis ``IPv6`` jest reprezentowany w postaci ``heksadecymalnej``.

  ### Adres MAC
  > adres fizyczny, ``48-bitowa`` liczba zapisana ``heksadecymalnie``, gdzie pierwsze 24 bity oznaczają producenta karty sieciowej, a kolejne 24 to unikatowy identyfikator danego egzemplarza.

  ### Host
  > jest to urządzenie posiadające adres ``IP``, które jest źródłem, albo adresatem danych przesyłanych przez sieć. Pojęcie hosta stosowane jest czasem zamiennie z terminem urządzenia końcowego, ponieważ odnosi się najczęściej do komputera lub też urządzenia komputerowego czyli urządzenia, z którymi użytkownik sieci ma bezpośredni kontakt.

  ### Klient
  > to urządzenie, a dokładniej jego oprogramowanie, korzystające z usług udostępnianych przez serwery. Najbardziej popularnymi i powszechnymi klientami są przeglądarki internetowe, które pozwala na przeglądanie zawartości stron ``WWW`` udostępnianych właśnie przez serwery stron ``WWW``. Przykładem klienta może być również program FileZilla, pozwalający na wymianę plików przez Internet za pomocą protokołu ``FTP``. 

  ### Serwer
  > komputer z zainstalowanym dedykowanym, specjalistycznym oprogramowaniem, a także nawet i systemem operacyjnym oferujący usługi innym komputerom. Oferowane usługi przez serwer to: hosting stron ``WWW``, poczta elektroniczna czy zasoby plikowe za pomocą protokołu ``FTP``. Serwerem może być każdy komputer, pod warunkiem, że zostanie na nim zainstalowane i skonfigurowane takie oprogramowanie, czyli np. ``APACHE`` do utrzymywania i udostępniania stron internetowych. Serwery najczęściej są dedykowanymi komputerami, z dużą mocą obliczeniową, będące w stanie obsłużyć wiele połączeń i zapytań jednocześnie.

  ### Protokół komunikacyjny
  > to sposób lub też język komunikacji i wymiany danych między urządzeniami, określający reguły i zasady tej komunikacji. Protokoły te mogą zostać wdrożone w sposób sprzętowy lub oprogramowania.
  

  ### Internet
  > to zbiór połączonych ze sobą sieci rozległych, stanowiących globalną sieć komputerową. W dokładnej definicji informatyczej ``Internet`` to przestrzeń adresów ``IP`` przypisanych do hostów i serwerów połączonych za pomocą ``mediów transmisyjnych``. Komunikacja odbywa się za pomocą protokołu internetowego w infrastrukturze telekomunikacyjnej.

  ### Intranet
  > to prywatna, wewnętrzna sieć, wykorzystująca w komunikacji protokoły dokładnie takie same jak w przypadku sieci Internet, jednak z dostępem tylko dla upoważnionych użytkowników, np. pracowników danej firmy. 

  ### Extranet
  > to rozszerzona odmiana zamkniętej sieci Intranet umożliwiająca dostęp do jej zasobów, nie tylko pracownikom danej firmy, ale również innym użytkownikom takim jak partnerzy biznesowi. Oparta jest na protokołach internetowych przeznaczonych do wymiany informacji. W świetle ustawy o dostępności cyfrowej strony internetowych i aplikacji mobilnych podmiotów publicznych jest to ``niepubliczna`` sieć telekomunikacyjna.

  
## 📐 Jednostki danych w sieciach

  Podstawową i zarazem najmniejszą jednostką służącą w informatyce do zapisu danych jest ``1 bit [b]``. W sieciach komputerowych natomiast, do określania przepustowości sieci stosuję się jednostkę ``bit na sekundę``, zapisywaną ``[b/s]`` lub też ``bps`` (ang. bit per second).

  > Oczywiście ``1 [b/s]`` to bardzo mało, dlatego też stosuje się wielokrotności tej jednostki, podobnie jak dla określania wielkości plików, pojemności dysków czy pamięci operacyjnych, z tym, że w odniesieniu do bitów, a nie do bajtów, wielokrotnościami tymi są:

    1 Kilobit [kb] = 1 000 bitów [b]
    1 Megabit [mb] = 1 000 000 bitów [b]
    1 Gigabit [gb] = 1 000 000 000 bitów [b]
    1 Terabit [tb] = 1 000 000 000 000 bitów [b]

  W związku z tym, ze w sieciach komputerowych jako jednostkę stosuje się bity, inaczej niż w przypadku wielkości plików czy pojemności dysków, gdzie zamiast ``bitów [b]`` stosuję się ``bajty [B]``.
  
  ### ✖️ Bajty na bity

  Główną kwestią w tym przypadku okazuje się konwersja, czyli zamiana bitów na bajty. Należy wtedy zastosować ``mnożenie``.

  > 1 bajt [B] to 8 bitów [b] dlatego też, jeśli chcemy wielkość pliku wyrażoną w bajtach zapisać w bitach musimy ilość bajtów pomnożyć przez 8. Przykładowo, jeśli chcemy obliczyć ile megabitów zawiera plik o wielości ``2 155 [MB]``, pomnożymy jego wielkość przez 8. Uzyskany wówczas wynik to ``16 920 [mb]``.
  
    2 115 bajtów [B] * 8 = 16 920 bitów [b]
  
  ### ➗ Bity na bajty
  
  W przypadku zamiany odwrotnej czyli z bitów na bajty, musimy wykonać operację odwrotną do mnożenia, czyli ``dzielenie``.
  
  >Wówczas przykładowo: plik o wielkości ``420 [mb]`` po konwersji przyjmie wartość  ``52,5 [MB]``.

    420 megabitów [mb] ÷ 8 = 52,5 megabajtów [MB]

  Pytanie – dlaczego ``1024``, a nie ``1000``? Skąd taka liczba? Najprostsze wyjaśnienie to takie, że ``1024`` to liczba 2 podniesiona do dziesiątej potęgi ( 2<sup>10</sup> ).

    1 bajt [B] = 8 bitów [b]
    1 kilobajt [KB] = 1024 bajtów [B]
    1 megabajt [MB] = 1024 kilobajty [KB]
    1 gigabajt [GB] = 1024 megabajty [MB]
    1 terabajt [TB] = 1024 gigabajty [GB]

  W przypadku kilobajtów przedrostek „kilo-” nie oznacza 10 do trzeciej potęgi. Dla rozróżnienia wielokrotności ``1024`` oznacza się dużą literą ``K``, natomiast małą literą ``k`` opisuje się wielokrotność ``1000``.

  ### 🌟 Zadania do wykonania
  
  1. Oblicz, w jakim czasie pobrany zostanie plik w wielkości ``21,37 [GB]`` przy stałej przepustowości łącza która wynosi ``6,9 [Mb/s]``.
    
     Obliczenia:

     > 1.1 Zamieniamy jednostkę przesyłu danych z megabitów na megabajty na sekundę:

         6,9 [Mb/s] ÷ 8 = 0,8625 [MB/s]

     > 1.2 Zamieniamy jednostkę zapisu pliku z gigabajta na megabajty:
         
         21,37 [GB] => 21,37 * 1024 => 21 882,88 [MB]

     > 1.3 Dzielimy wielkość pliku przez przepustowość łącza:

         21 882,88 [MB] ÷ 0,8625 [MB/s] = 25 371,455 sekund ~ 422 minut 51 sekund

     Odpowiedź:

     > Plik o wielkości ``21,37 [GB]``, przez łącze o przepustowości ``6,9 [Mb/s]`` pobierzemy w około ``422 minut 51 sekund``.

  2. Oblicz ile danych uda się przesłać przez łącze o przepustowości ``37 [Mb/s]`` w czasie ``210 minut``.

     Obliczenia:


  3. Oblicz jaka jest przepustowość łącza ``(w Mb/s)`` jeśli w ciągu ``12 godzin`` jesteśmy wstanie pobrać ``120 [GB]`` danych.
     
     Obliczenia:


## 🕸️ Podział sieci komputerowych
  Sieci komputerowe podzielić można w różny sposób, uwzględniając różne kryteria. Podstawowym kryterium podziału sieci jest podział ze względu na obszar, w którym sieć funkcjonuje, i tak w ze względu obszar (zasięg) sieci dzielimy następująco:

  ### LAN (ang. Local Area Network)
  > sieć zajmująca najmniejszy obszar, np. w pracowni, szkole, czy w kilku budynkach szkoły. Sieć LAN występuje również w Waszych domach, jeśli korzystacie z więcej lub jednego komputera.

  ### MAN (ang. Metropolitan Area Network)
  > sieć zajmująca większy obszar niż pomieszczenie czy budynek. Sieci typu MAN zlokalizowane są na obszarze całego miasta lub aglomeracji. 

  ### WAN (ang. Wide Area Network)
  > rozległa sieć połączonych ze sobą sieci LAN i MAN.


  ### 🏗️ Architektura sieci
  Poza kryterium obszaru, sieci możemy jeszcze podzielić ze względu na architekturę. Wyróżniamy wówczas sieci o architekturze klient-serwer oraz architekturze równorzędnej.
    
  - #### 🤵 Klient - Serwer 🖥️
  
    W architekturze klient - serwer występuje jeden lub kilka komputerów udostępniających usługi użytkownikom sieci (są to serwery) oraz wiele komputerów korzystających z usług serwera (są to klienci). Przeglądając strony WWW, wysyłając pocztę elektroniczną czy korzystając z baz danych korzystamy z architektury klient - serwer.
    
    ![Architektura klient serwer](https://user-images.githubusercontent.com/125214141/218608637-2f247014-c399-4fc0-b69a-22b42bd6235c.png)

  - #### 💠 Peer2Peer 💠
    Inaczej jest w przypadku architektury równorzędnej, zwanej również Peer2Peer (P2P). Nie występuje tutaj jeden lub więcej komputerów udostepniających usługi, lecz wiele komputerów na tych samych prawach. Każdy komputer w tej sieci może jednocześnie korzystać z zasobów oraz je udostępniać. Korzystając z usług wymiany plików, np. ``BitTorrent`` korzystamy z architektury równorzędnej.

    ![Architektura peer to peer](https://user-images.githubusercontent.com/125214141/218608779-6a983db7-75d9-4c68-943d-1025dfcefa6c.png)


## 🪙 Topologie sieci
  Topologia sieci to model według którego urządzenia w sieci komputerowej są połączone względem siebie. Topologie sieci dzielimy na ``fizyczną`` oraz ``logiczną``. Każda, nawet najmniejsza sieć komputerowa posiada topologię fizyczną oraz logiczną.

  ### 💪 Topologia sieci ``fizyczna``
  > określa, w jaki sposób urządzenia w sieci są ze sobą połączone.
  
  Do topologii fizycznych możemy zaliczyć:
  - ``Magistrali (ang. Bus)``
    
    ![Topologia magistrali](https://user-images.githubusercontent.com/125214141/218601460-7352bcda-a64b-4407-92c6-b9b3d6ad31fa.png)

    - charakteryzuje się tym, że wszystkie urządzenia podłącza się do wspólnego medium transmisyjnego. Powszechnie stosowanym w tej topologii medium transmisyjnym był ``przewód koncentryczny``. Jedną z wad tej topologii, była niewielką przepustowość ``(maksymalnie do 10 [Mb/s])``. Kolejną natomiast była podatność na awarię sieci. Jedyną zaletą był niewielki koszt utworzenia tej struktury sieciowej.

  - ``Pierścienia (ang. Ring)``
    
    ![Topologia pierscienia](https://user-images.githubusercontent.com/125214141/218600541-4607ae1d-21a5-47d0-8e34-fe8be523147f.png)

    - każde urządzenie podłączone jest z dwoma sąsiadami, tworząc zamknięty krąg. Podobnie jak w przypadku topologii magistrali, przy budowie nie stosuję się dużej ilości okablowania oraz dodatkowych urządzeń. Ogromną wadą tej topologii jest podatność na awarie, przerwanie medium lub awaria jednego z komputerów skutkuję awarią całej sieci.

  - ``Gwiazdy (ang. Star)``

    ![Topologia gwiazdy](https://user-images.githubusercontent.com/125214141/218600746-d8f8f7b9-65e7-4a9b-a9be-513133ae0400.png)

    -  urządzenia podłączone są do centralnego punktu, stanowiącego punkt dostępu do sieci. Dawniej punkt ten stanowiły ``koncentratory (ang. hub)``, obecnie natomiast stosuje się ``przełączniki (ang. switch)``. W lokalnych sieciach jest to najczęściej spotykana topologia, ponieważ jest prosta w zaprojektowaniu, budowie oraz rozbudowie, odporna na awarie i łatwo zarządzalna. Wadą zdecydowanie jest koszt budowy takiej struktury sieciowej.
  

  ### 🧠 Topologia sieci ``logiczna`` 
  > opisuje, w jaki sposób przesyłane są dane pomiędzy urządzeniami w topologii sieci ``fizycznej``.
  
  
  Do topologii logicznych możemy zaliczyć:
  - ``Punkt-punkt (ang. Point to point)``
    
    ![Topologia punkt-punkt](https://user-images.githubusercontent.com/125214141/218603101-f000a864-4c9e-4da5-a021-b414f07d7016.png)

    - dane przesyłane są tylko od jednego urządzenia do drugiego. Urządzenia te mogą być podłączone ze sobą bezpośrednio, np. komputer z przełącznikiem, jak również pośrednio, na duże odległości, z wykorzystaniem urządzeń pośredniczących, czego przykładem może być połączenie ze sobą dwóch ruterów oddalonych od siebie o wiele kilometrów.

  - ``Przekazania żetonu (ang. Token passing)``
    
    ![Topologia przekazania zetonu](https://user-images.githubusercontent.com/125214141/218606971-fc3d372b-706a-47c9-8821-5f99f8785057.png)


    - dane przekazywane są kolejno do urządzeń połączonych w sieć. Urządzenie, które otrzyma porcję danych, analizuje czy są one kierowane do niego czy też nie. Jeśli dane nie są do niego adresowane, przekazuje je dalej, do sąsiedniego urządzenia. W taki sposób, dane przesyłane są przez wszystkie urządzenia występujące pomiędzy urządzeniem źródłowym, a docelowym.

  - ``Wielodostępowa (ang. Multi-access)``

    ![Topologia wielodostępowa](https://user-images.githubusercontent.com/125214141/218601460-7352bcda-a64b-4407-92c6-b9b3d6ad31fa.png)

    -  umożliwia komunikację urządzeń w sieci poprzez jedno fizyczne medium transmisyjne. Każde urządzenie w tej topologii widzi dane przesyłane przez sieć ponieważ są one przesyłane do wszystkich urządzeń, ale tylko konkretne urządzenie, do którego dane są adresowane je interpretuje.  Najczęściej stosowana była wspólnie z fizyczną topologią ``magistrali`` oraz ``gwiazdy`` na wczesnym etapie jej rozwoju, kiedy to stosowano jeszcze koncentratory jako punkty dostępowe do sieci. 
  

## 🔌 Media transmisyjne
> Ważnym dla komunikacji w sieci są media transmisyjne oraz w jaki sposób są wykonane. Wiele jest ku temu powodów jednak najważniejsze z nich to fakt, że dobór odpowiedniego medium stanowi podstawę i gwarancję właściwego oraz wydajnego działania sieci komputerowej.

  ### Medium transmisyjne
  > Innymi słowy jest to jakiś nośnik, element sieci, poprzez który urządzenia mogą komunikować się między sobą i wymieniać dane. Takim medium może być przewód miedziany, światłowodowy jak i również fale radiowe (Wi-Fi).

  <div align="center">

  |Rodzaj przewodu | Typ                  |
  |:---:           |:---:                 |
  | Miedziany      | Przewód koncentryczny|
  | Miedziany      | Przewód typu skrętka |
  | Światłowodowy  | Jednomodowy          |
  | Światłowodowy  | Wielomodowy          |

  </div>

  ### Przewody miedziane

   - ``Przewód koncentryczny``
      
      - #### Budowa

        - Koszulka zewnętrzna 
        - Miedziany ekran
        - Plastikowa izolacja
        - Miedziany rdzeń

      - #### Rodzaje
      > Z głównych rodzajów przewodu koncentrycznego wyróżniamy takie jak: cienki oraz gruby. Różnice ich zależą właśnie od średnicy przekroju, ponieważ im grubszy (co za tym idzie droższy) tym większa długość zasięgu. Przewód koncentryczny jednak jest już anarchicznym elementem sieci, w jego miejsce stosuje się bardziej efektywne rozwiązania na przykład światłowód, czy skrętke.


      |Rodzaj przewodu | Grubość                  | Maksymalna długość | Standard sieci | Maksymalna przepustowość                |  
      |:---:           |:---:                 |:---:                 |:---:     |:---:                 |
      | Cienki     | 5 mm| 185 m                 | 10Base-2     | 10 [Mb/s]                |
      | Gruby      | 10 mm |    500 m             | 10Base-5    | 10 [Mb/s]                |


   - ``Przewód typu skrętka``
      
      - #### Budowa

        - Koszulka zewnętrzna
        - Ewentualny separator po środku
        - 8 miedzianych żył splecionych w 4 pary

      - #### Rodzaje
      > W rodzajach skrętech występują różne kombinację poza podanymi podstawowymi - np. ``U/UTP`` - oznacza również niekranowaną, lub ``S/FTP`` - skrętka z każdą parą foliowaną i dodatkowo całość w ekranie siatki

        - ``UTP - U/UTP`` - Skrętka ``nieekranowana`` 

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220196503-33b62973-2c7e-421d-bc5d-9f553e4b05d0.png" />

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220197864-23aaa688-3aef-4849-b459-3b63306ade51.png" />

        - ``FTP - F/UTP`` - Skrętka ekranowana ``folią``

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220196334-cc52c982-5e4e-4cf8-a6d7-06baf13dc524.png" />
        
        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220198041-bceacbbe-4e0d-48ee-b2c4-427b069baa17.png" />

        - ``STP - SF/UTP`` - Skrętka ekranowana ``siatką``

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220196668-73226bea-7202-4ef9-9516-5c67ae259d7e.png" />


        - ``S/FTP`` - skrętka z każdą parą foliowaną, dodatkowo całość w ekranie z siatki

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220199942-bb6e1908-bdf3-49ba-a004-b00b36c7ebb5.png" />

        <img width="300px" src="https://user-images.githubusercontent.com/125214141/220199062-40f2ca81-9ab4-40b3-b9c0-ad3a873dfc07.png" />


      - #### Kategorie


        |Kategoria | Standard sieci                  |
        |:---:           |:---:                 |
        | 3      | Ethernet 10Base-T|
        | 5/5e      | FastEthernet 100Base-TX GigabitEthernet 1000Base-T |
        | 6  | GigabitEthernet 1000Base-T          |
        | 6a  | 10-GigabitEthernet 10GBase-T          |
        | 7  | 10-GigabitEthernet 10GBase-T          |



  ### Przewody światłowodowe
  > Najnowszym i zupełnie innym medium transmisyjnym jest przewód światłowodowy, innym ze względu na budowę rdzenia. Włókno szklane jest wykorzystywane jako rdzeń w przewodach światłowodowych, co za tym idzie sygnał przesyłowy to nie prąd elektryczny, a promień świetlny (wiązka światła). Dzielą się również tylko na dwa typy ogólne ``jednomodowy`` oraz ``wielomodowy``

   #### Budowa
   - Płaszcz zewnętrzny
   - Powłoka wzmacniająca chroniąca rdzeń podczas instalacji
   - Powłowka lakierowana chroniąca płaszcz
   - Płaszcz
   - Rdzeń

   ![obraz-removebg-preview(30)](https://user-images.githubusercontent.com/125214141/220202760-7b73cb67-d2ad-4b85-bdc5-15de22fe4810.png)

   Do tego dochodzą różne typy złącz: 

   ![obraz-removebg-preview(31)](https://user-images.githubusercontent.com/125214141/220203222-a2906fb6-f543-4354-bd7d-d51f15dec285.png)

  - ``Światłowód jednomodowy``
  > W przypadku światłowodu jednomodowego przez szklany rdzeń przysłana jest tylko jedna wiązka światła, dzięki temu ograniczone zostało zjawisko tzw. rozmycia sygnału, czyli jego osłabienia.

  ![Wiązka jednomodowa](https://user-images.githubusercontent.com/125214141/220204169-1e825f44-21d6-42e8-a472-05f350cf60b8.png)

  Wykorzystanie takiego rodzaju światłowodu pozwala na transmisje sygnału na bardzo ``duże odległości`` bez konieczności stosowania urządzeń wzmacniający sygnał.

  - ``Światłowód wielomodowy``
  > W światłowodzie wielomodowym przez rdzeń przesyłanych jest więcej wiązek światła, czego konsekwencją jest znacznie większy w porównaniu do światłowodu jednomodowego stopień rozmycia sygnału. Wynika to z faktu, ze każda wiązka światła przysłana przez rdzeń musi pokonać inna drogę od nadawcy do odbiorcy.

  ![Wiązka wielomodowa](https://user-images.githubusercontent.com/125214141/220204271-b9b91655-332a-44a9-88cd-abfa8ca9ec6f.png)

  W związku z tym światłowody wielomodowe stosuje się na ``niewielkich odległościach``, maksymalnie do kilku kilometrów.

  Kolejną różnicą pomiędzy światłowodem jedno i wielomodowym jest zastosowana ``średnica rdzenia``. W przypadku jednomodowego światłowodu wynosi ona między ``8 a 10 mikrometrów [μm]``, natomiast w przypadku światłowodu wielomodowego ``50 [μm]`` lub ``62,5 [μm]``.

  ### Media bezprzewodowe

  W przypadku mediów bezprzewodowych, stosuje się kilka rozwiązań, jednak w praktyce wykorzystuje się tylko jedno z nich, są to ``fale radiowe``. Znana wszystkim technologia ``Wi-Fi`` wykorzystuje właśnie to medium do transmisji danych.

  Fale radiowe są ``promieniowaniem elektromagnetycznym`` z zakresu częstotliwości od ``3 [Hz]`` do około ``3 [THz]``. Źródła fal radiowych mogą być zarówno naturalne, jak i sztuczne, np. emitowane przez stacje nadawcze telefonii komórkowej. 
  
  Ich głównym celem jest przenoszenie informacji, a w przypadku telekomunikacji transmisja danych. Wyróżnia się kilka rodzajów fal radiowych, natomiast do transmisji danych stosuje się fale ``długie``, ``średnie`` i ``krótkie`` oraz ``ultrakrótkie``.

  Przy okazji omawiania fal radiowych warto wspomnieć o standardach jakie wykorzystywane są w sieciach bezprzewodowych. Są one istotne z punktu widzenia doboru odpowiedniego rutera ``Wi-Fi``.

  <div align="center">

  |Standard sieci | Częstotliwość | Przepustowość |
  |:---:           |:---:                 |:---:|
  | 802.11a     | 5 [GHz] | 54 [Mb/s] |
  | 802.11b     | 2,4 [GHz] | 11 [Mb/s] |
  | 802.11g     | 2,4 [GHz] | 54 [Mb/s] |
  | 802.11n     | 2,4 [GHz]; 5 [GHz] | 150 [Mb/s]; 600 [Mb/s] |
  | 802.11ac    | 5 [GHz] | do kilku [Gb/s] |

  </div>


  ### Podsumowanie

   - #### Media miedziane

      |Zalety |Wady | 
      |:---: |:---: |
      |Niski koszt| Wrażliwość na zakłócenia ``elektromagnetyczne`` |
      |Łatwość montażu i instalacji | Niewielka odległość pomiędzy węzłami sieci |
      |Łatwość diagnozowania i naprawy usterek | Mniejsza przepustowość |

   - #### Media światłowodowe

      |Zalety |Wady | 
      |:---: |:---: |
      |Wysoka przepustowość| Rozmycie sygnału|
      |Transmisja na dużych odległościach | Trudność instalacji |
      |Znikoma wrażliwość na zakłócenia ``elektromagnetyczne`` | Drogi koszt osprzętu sieciowego |


