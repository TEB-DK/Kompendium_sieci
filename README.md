<div align="center">

# 🧬 Modele warstwowe ``ISO/OSI`` i ``TCP/IP`` 🧬

</div>

Komunikacja urządzeń w sieci komputerowej składa się z kilku etapów. Każdy z nich jest tak samo ważny, gdyż na każdym z nich realizowane są zadania służace poprawnej komunikacji.

> Etapy określone są prze tak zwane ``modele warstwowe``.

Każdy z Was, kto spotkał się już z modelami warstwowymi wie, że zrozumienie tego tematu stanowi podwaliny do zdobywania dalszej wiedzy i umiejętności w zakresie sieci komputerowych.


Istnieją dwa warstwowe modele, są nimi model protokołów ``TCP/IP`` oraz model odniesienia ``ISO/OSI``. Z jednej strony są do siebie podobne, z drugiej jednak każdy z modeli charakteryzuje się nico innym podejściem do sposobu komunikacji.

> Obydwa modele stworzone zostały w latach siedemdziesiątych, czyli już spory kawał czasu temu, ale wciąż są aktualne i stosowane.

Podział procesu komunikacji sieciowej na poszczególne warstwy niesie za sobą wiele korzyści, najważniejsze z nich to:

 - [x] łatwiejsze określenie reguł i zasad komunikacji,
 - [x] możliwość współdziałania ze sobą urządzeń sieciowych i oprogramowania różnych producentów,
 - [x] możliwość łatwiejszego zrozumienia całego procesu komunikacji,
 - [x] możliwość zarządzania procesem komunikacji.

Zanim dane z urządzenia źródłowego zostaną przesłane do urządzenia końcowego muszą przejść długą drogę, podczas której najpierw są odpowiednio oznaczane, tagowane, opisywane określonymi informacjami pozwalającymi na ich identyfikację, potem przesyłane są pomiędzy wieloma urządzeniami pośredniczącymi, aż trafią do odbiorcy, który dane to potem musi zinterpretować.

Skoro już wiemy w jakim celu stosuje się modele warstwowe przejdźmy teraz do omówienia najważniejszych cech każdego z nich. 

## 🔢 Model warstwowy ``ISO/OSI``

Model ISO/OSI natomiast zwany ``modelem odniesienia``, stosowany jest raczej do analizy, która pozwala lepiej zrozumieć procesy komunikacyjne zachodzące w sieci oraz stanowi wzór do projektowania rozwiązań sieciowych zarówno sprzętowych jak i programowych.

 ### 🧮 Wygląd modelu i warstwy

 <div align="center" >

 <img src="https://user-images.githubusercontent.com/125214141/221695843-acf52e2f-83b2-4a56-83bc-3c114c25e21e.png" width="300px" alt="ISO/OSI">

 </div>

 Pierwsza warstwa modelu to ``warstwa aplikacji`` i służy ku temu aby użytkownicy końcowi sieci kogli korzystać z aplikacji sieciowych, czyli jest to warstwa bezpośredniej komunikacji użytkownika z siecią.

 Dalej mamy ``warstwę prezentacji``, która to przekazuje do warstwy aplikacji informacje o zastosowanym formacie danych, np. informuje jakie typy plików będą przesyłane, odpowiada ona również za odpowiednie ``zakodowanie danych`` na urządzeniu źródłowym i ich ``dekodowanie`` na urządzeniu docelowym.

 Kolejna jest na drodze stoi ``warstwa sesji``, zarządzająca sesjami użytkowników, którzy korzystają z protokołów internetowych, np. ``HTTP`` (strony internetowe).

 Idąc dalej mamy ``warstwę transportu``, której głównym zadaniem jest ``obsługa komunikacji`` pomiędzy urządzeniami i zapewnienie ``bezpiecznego transportu danych``. W warstwie tej dane dzielone są na mniejsze części, następnie opatrywane są dodatkowymi informacjami pozwalającymi zarówno przydzielić je do właściwej aplikacji na urządzeniu docelowym, jak i pozwalającymi złożyć je na urządzeniu docelowym w odpowiedniej kolejności.

 Następnie mamy ``warstwę sieci``, której zadaniem jest ``znalezienie najszybszej i najkrótszej drogi`` do urządzenia docelowego przez sieć rozległą w której dane są wysyłane.

 Dalej idąc w dół mamy warstwę ``łącza danych``, której głównym zadaniem jest ``kontrola dostępu`` do medium transmisyjnego, a także ``adresowanie danych``, tym razem jednak w celu przesyłania ich pomiędzy hostami w sieci ``LAN``.

 Ostatnią warstwą jest ``warstwa fizyczna``, która to koduje dane do postaci ``bitowej`` i przesyła je przez medium transmisyjne do odpowiednich urządzeń.

## 🔢 Model warstwowy ``TCP/IP``

Model TCP/IP określany jest jako ``model protokołów``. Każda z jego warstw wykonuje konkretne zadania, do realizacji który wykorzystywane są konkretne protokoły. 

 ### 🧮 Wygląd modelu i warstwy
 > W przypadku modelu TCP/IP wyróżnić możemy 4 warstwy, są nimi warstwa: ``aplikacji``, ``transportu``, ``internetowa`` oraz ``dostępu do sieci``.

 <div align="center">

 <img src="https://user-images.githubusercontent.com/125214141/221695590-3961b0f4-7e75-4eec-b8b3-411d7a1c1e98.png" width="400px" alt="TCP/IP"/>

 </div>

  ``Warstwa aplikacji`` udostępnia użytkownikom możliwość korzystania z usług sieciowych, takich jak WWW, poczta elektroniczna, wymiana plików, połączenia terminalowe czy komunikatory. Swoim uczniom mówię zawsze, że jest to warstwa najbliższa użytkownikowi, ponieważ to właśnie ona pozwala nam w pełni korzystać z dobrodziejstw współczesnych usług sieciowych. Kiedy siadamy przed komputerem i uruchamiamy np. przeglądarkę internetową to korzystamy z sieci właśnie na poziomie warstwy aplikacji.

  ``Warstwa transportu``, której głównym zadaniem jest sprawna obsługa komunikacji pomiędzy urządzeniami. W warstwie tej dane dzielone są na mniejsze części, następnie opatrywane są dodatkowymi informacjami pozwalającymi zarówno przydzielić je do właściwej aplikacji na urządzeniu docelowym, jak i pozwalającymi złożyć je na urządzeniu docelowym w odpowiedniej kolejności.

  ``Warstwa internetowa``, której głównym zadaniem jest odnalezienie najkrótszej i najszybszej drogi do urządzenia docelowego przez sieć rozległą, podobnie jak robią to samochodowe GPS’y, ale także adresowanie danych z wykorzystaniem adresów logicznych (``adresów IP``).

  ``Warstwa dostępu do sieci``, która koduje dane do postaci czystych bitów (zer i jedynek) i przekazuje je do medium transmisyjnego i także je adresuje, tym razem poprzez adresy fizyczne (``adresy MAC``).

## 📫 Proces komunikacji
> Proces komunikacji zostanie zaprezentowany na podstawie wysyłania wiadomości ``e-mail``.
 
 <div align="center">

 <img src="https://user-images.githubusercontent.com/125214141/221698357-c01a2da2-b5cd-442f-85cc-24af7afc4acf.png" width="650px" alt="Enkapsulacja/Dekapsulacja">

 </div>

### 🧇 Warstwa aplikacji
 1. Użytkownik sieci, korzystając z programu pocztowego lub przeglądarki internetowej tworzy wiadomość e-mail. 
 
 > Warstwa aplikacji w odpowiedni sposób koduje dane i przekazuje do warstwy transportu.

### 🧇 Warstwa transportu
 2. W tej warstwie następuje podział danych na mniejsze części, czyli ``segmenty``, które łatwiej jest przesłać przez sieć.
 
 > To tak jakbyśmy chcieli przenieść z miejsca na miejsce ogromny narożnik, trudno byłoby go przenieść w całości, skoro nawet nie mieści się w drzwiach, dlatego też rozłożylibyśmy go na części, a nie kombinowali z przeniesieniem go w całości.
 
 W warstwie tej również dodawane są informacje sterujące pozwalające później, na urządzeniu końcowym złożyć segmenty w odpowiedniej kolejności (chociaż nie są one dodawane zawsze, zależy to od zastosowanego protokołu tej warstwy). Prócz tego dodawane są numery portów aplikacji pozwalające potem stwierdzić, że jest to wiadomość e-mail, a nie np. strona WWW.

 > Z warstwy transportu ``segmenty`` przekazywane są do warstwy internetowej.

### 🧇 Warstwa internetowe
 3. Ta warstwa nadaje adresy IP - zarówno urządzenia, które dane wysyła, jak również tego, który jest ich adresatem. Zabieg ten stosowany jest po to aby ``rutery``, czyli urządzenia pośredniczące na drodze między nadawcą, a odbiorcą wiadomości, wiedziały gdzie mają ją przesłać. 
 
 Od tego momentu nasze segmenty są już zaadresowanymi pakietami.

 > Z warstwy internetowej ``pakiety`` są przekazywane do warstwy dostępu do sieci.

### 🧇 Warstwa dostępu do sieci
 4. Ta warstwa odpowiada za tworzenie ``ramek``, opatrywane adresem fizycznym urządzenia wysyłającego wiadomość oraz adresem fizycznym rutera, do którego podłączony jest komputer, z którego wysyłamy wiadomość. 
 
 Dzięki temu adresowi, ramki potem mogą trafić do tego rutera, który to dalej wyśle je do sieci rozległej.
 
 Zanim jednak nastąpi sama transmisja, ``ramki są kodowane do postaci bitów`` i przekazywane do urządzenia docelowego za pośrednictwem ruterów.


---
Proces zaprezentowany krok po kroku w powyższym przykładzie nosi konkretną nazwę - ``enkapsulacji``. Proces odwrotny, czyli odczytwanie przez drugie urządzenie tych danych to ``dekapsulacja``.

### 🔒 Enkapsulacja
> jest to proces przepływu danych przez stos modelu warstwowego w dół i nadawania informacji sterujących oraz adresów.

### 🔓 Dekapsulacja
> to proces odwrotny do enkapsulacji, dane przesyłane są w górę stosu modelu warstwowego w celu rozpakowania ich dla użytkownika końcowego.


Kiedy ``host docelowy`` odbierze bity, następuje proces odwrotny do enkapsulacji, czyli dekapsulacja, gdzie ramki zamieniane są w pakiety, pakiety w segmenty, a warstwa transportu składa je we właściwej kolejności. Kiedy proces ten się zakończy, dane przesyłane są do warstwy aplikacji gdzie następuje wyświetlanie wiadomości.

W sieciach komputerowych stosuje się modele warstwowe w celu łatwiejszego opisywania i sterowania poszczególnymi etapami komunikacji, a także w celu ``standaryzacji``, tak aby zarówno sprzęt jak i oprogramowania różnych producentów były ze sobą ``kompatybilne``. Komunikacja w sieci odbywa się z wykorzystaniem przyjętych reguł i zasad zwanych ``protokołami komunikacyjnymi``. Proces komunikacji w sieci polega na przekazywaniu danych w dół stosu na urządzeniu źródłowym, zakodowaniu ich do postaci bitów i przesłaniu do urządzenia docelowego, gdzie dane przekazywane są w górę stosu i interpretowane. W poszczególnych warstwach dane opatrywane są informacjami sterującymi, numerami portów oraz adresami logicznymi i fizycznymi, następnie są kodowane i przesyłane do odbiorcy.


---
