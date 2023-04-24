<div align="center">

# 📦 Protokoły warstwy internetowej 🌐

</div>

Warstwa transportowa to jedna z pięciu warstw modelu ``OSI`` (``Open Systems Interconnection``), która odpowiada za przesyłanie danych między aplikacjami działającymi na różnych urządzeniach w sieci komputerowej. Jej głównym zadaniem jest ``zapewnienie niezawodnej i efektywnej komunikacji między hostami``.

Warstwa ta zapewnia usługi takie jak ``multiplexing``, ``segmentacja``, ``kontrola przepływu`` oraz ``kontrola błędów``. 

###### ``Multiplexing`` - polega na umożliwieniu jednoczesnej komunikacji wielu aplikacji na jednym urządzeniu, przez co możliwe jest korzystanie z jednego łącza sieciowego przez wiele użytkowników. Segmentacja natomiast dzieli strumień danych na mniejsze części, co umożliwia efektywniejsze przesyłanie dużych plików.

Natomiast ``kontrola przepływu`` umożliwia monitorowanie i kontrolowanie ilości danych, które są przesyłane między urządzeniami, co zapobiega przeciążeniu sieci. Kontrola błędów natomiast umożliwia wykrywanie i naprawianie błędów w danych, które zostały przesłane między urządzeniami.

### 📑 Protokoły warstwy transportowej

Do najpopularniejszych protokołów warstwy transportowej należą ``TCP`` (``Transmission Control Protocol``) oraz ``UDP`` (``User Datagram Protocol``). 

###### ``TCP`` - zapewnia niezawodną transmisję danych, poprzez kontrolę przepływu oraz kontrolę błędów, ale jest mniej efektywny od protokołu UDP. 
###### ``UDP`` - zapewnia mniej niezawodną transmisję, ale zapewnia szybsze przesyłanie danych i jest często wykorzystywany do strumieniowania multimediów oraz gier sieciowych.

Aby łatwiej skojarzyć różnicę pomiędzy nimi przedstawiam kilka memów:

<div align="center">

<details>
<summary>Pokaż mema</summary>

![tcp/udp meme](https://user-images.githubusercontent.com/125214141/234080680-6bfb85b1-c192-4545-b937-5f6af625d649.png)

</details>

<details>
<summary>Pokaż mema</summary>

![tcp/udp meme2](https://user-images.githubusercontent.com/125214141/234081065-20556cf4-0dab-4e88-a002-c6fb047ce213.png)

</details>

<details>
<summary>Pokaż mema</summary>

![tcp/udp meme3](https://user-images.githubusercontent.com/125214141/234081241-c7a9a850-aa7c-4a26-8f2b-3d8324bf1e77.png)

</details>
</div>


W skrócie, warstwa transportowa to kluczowy element w zapewnieniu niezawodnej i efektywnej komunikacji między urządzeniami w sieci komputerowej, a protokoły takie jak TCP i UDP umożliwiają spełnienie jej głównych zadań.

#### 📜 Protokół ``TCP``

``Transmission Control Protocol`` (TCP) to protokół warstwy transportowej, który zapewnia niezawodne i uporządkowane przesyłanie danych między aplikacjami działającymi w sieciach komputerowych. Protokół TCP jest połączeniowy, co oznacza, że przed przesyłaniem danych, inicjowane jest połączenie między dwoma punktami końcowymi.

Proces przesyłania danych w protokole TCP składa się z trzech etapów: nawiązanie połączenia, przesyłanie danych i zakończenie połączenia. Pierwszy etap, nawiązanie połączenia, obejmuje wymianę informacji między punktem źródłowym a punktem docelowym, w celu ustalenia parametrów połączenia, takich jak numer portu, numery sekwencyjne i potwierdzenia.

Po nawiązaniu połączenia, dane przesyłane są w postaci strumieniowej, czyli w ciągłych strumieniach bitów, które są podzielone na mniejsze jednostki nazywane segmentami. Każdy segment zawiera nagłówek, w którym znajdują się informacje o numerze sekwencyjnym, potwierdzeniu odbioru i flagach kontrolnych.

W trakcie przesyłania danych, protokół TCP zapewnia niezawodność poprzez potwierdzanie otrzymania każdego segmentu i ponawianie przesyłania utraconych lub uszkodzonych danych. Protokół TCP wykorzystuje również mechanizmy kontroli przepływu, które pozwalają na kontrolowanie tempa przesyłania danych między punktami końcowymi.

Po zakończeniu przesyłania danych, następuje zakończenie połączenia, które obejmuje wymianę informacji między punktem źródłowym a punktem docelowym w celu zakończenia połączenia i zwolnienia zasobów.

Protokół TCP jest bardzo niezawodny, ale ma większe opóźnienie w porównaniu z protokołem UDP. Jest często wykorzystywany w aplikacjach, w których ważniejsza jest niezawodność i integralność danych, takich jak przesyłanie poczty e-mail, przesyłanie plików lub przeglądanie stron internetowych.

#### 📜 Protokół ``UDP``

``User Datagram Protocol`` (UDP) to protokół warstwy transportowej, który umożliwia przesyłanie datagramów w sieciach komputerowych. UDP jest protokołem bezpołączeniowym, co oznacza, że nie zapewnia on utrzymywania połączenia i kontroli nad przesyłanymi danymi. Protokół UDP jest często wykorzystywany w aplikacjach, w których szybkość przesyłania danych jest ważniejsza niż ich niezawodność i integralność.

W protokole UDP, dane przesyłane są w postaci datagramów, czyli pakietów, które nie są podzielone na mniejsze jednostki. Każdy datagram składa się z nagłówka, który zawiera informacje o źródle i celu przesyłania danych, oraz samej treści, która jest przesyłana bez dodatkowych informacji kontrolnych.

UDP jest protokołem szybszym niż TCP, ponieważ nie wymaga on ustanawiania połączenia i nie przeprowadza procesu potwierdzania otrzymania danych. W związku z tym, przesyłanie danych w protokole UDP jest mniej skomplikowane i wymaga mniejszej liczby operacji, co oznacza, że jest bardziej wydajne. Protokół UDP jest stosowany w aplikacjach, w których czas reakcji jest kluczowy, np. w transmisji strumieniowej wideo czy w grach sieciowych.

Jednakże, ze względu na brak kontroli nad danymi i brak potwierdzeń otrzymania, protokół UDP jest mniej niezawodny niż TCP. W przypadku utraty datagramu lub jego uszkodzenia w trakcie przesyłania, nie ma mechanizmu automatycznego ponawiania przesyłania, co oznacza, że niektóre dane mogą zostać utracone. W związku z tym, protokół UDP jest stosowany w aplikacjach, w których niezawodność nie jest kluczowa, a szybkość przesyłania danych jest bardziej istotna.

### 🧠 Proces przesyłania danych

Proces przesyłania danych przez warstwę transportową jest złożony i obejmuje kilka kroków, które opisuję poniżej:

##### 1. ``Segmentacja`` - Dane, które mają zostać przesłane między urządzeniami, są dzielone na mniejsze bloki, zwane segmentami. Segmentacja umożliwia przesyłanie dużych plików w sposób bardziej efektywny, ponieważ umożliwia równomierne rozłożenie ruchu sieciowego i zmniejsza ryzyko utraty danych w przypadku awarii sieci.

##### 2. ``Numeracja segmentów`` - Każdy segment otrzymuje numer sekwencji, dzięki czemu można je zidentyfikować i w razie potrzeby ponownie wysłać, jeśli zostaną utracone lub uszkodzone.

##### 3. ``Kontrola przepływu`` - Warstwa transportowa monitoruje przepływ danych, aby zapobiec przeciążeniu sieci. Jeśli urządzenie odbiorcze nie jest w stanie przetworzyć wszystkich segmentów, które zostały mu przesłane, warstwa transportowa wysyła sygnał zwrotny do urządzenia nadawczego, aby zatrzymać przesyłanie danych do momentu, gdy odbiorca będzie gotowy na ich odbiór.

##### 4. ``Kontrola błędów`` - Warstwa transportowa korzysta z różnych mechanizmów, aby zapewnić niezawodność przesyłania danych. Na przykład protokół TCP wykorzystuje mechanizmy kontroli błędów, takie jak potwierdzenia odbioru danych i retransmisje, aby zapewnić, że dane dotrą do celu w całości i bez błędów.

##### 5. ``Multiplexing`` - Warstwa transportowa umożliwia jednoczesne przesyłanie danych przez wiele aplikacji na jednym urządzeniu. Dzięki temu wiele użytkowników może korzystać z jednego łącza sieciowego.

##### 6. ``Demultiplexing`` - Warstwa transportowa identyfikuje aplikacje, do których są przesyłane dane, na podstawie portów źródłowych i docelowych. Demultiplexing umożliwia aplikacjom na urządzeniu odbiorczym odbieranie tylko tych danych, które są skierowane do nich.

> Podsumowując warstwa transportowa dzieli dane na segmenty, kontroluje ich przepływ i błędy, umożliwia jednoczesne przesyłanie danych przez wiele aplikacji, a następnie identyfikuje i kieruje dane do odpowiednich aplikacji na urządzeniu odbiorczym.

### 🏛️ Organizacja IANA

Organizacja ``IANA`` (``Internet Assigned Numbers Authority``) jest jednym z kluczowych podmiotów odpowiedzialnych za zarządzanie protokołami i adresami w systemie sieciowym Internet. W kontekście warstwy transportowej, IANA jest odpowiedzialna za przydział numerów portów protokołów transportowych.

> Numer portu to 16-bitowy numer identyfikujący aplikację lub usługę w warstwie transportowej. Przykładowo, port 80 jest zarezerwowany dla protokołu HTTP (Hypertext Transfer Protocol), który jest wykorzystywany przez serwery WWW, a port 25 jest zarezerwowany dla protokołu SMTP (Simple Mail Transfer Protocol), który służy do przesyłania poczty elektronicznej.

IANA przydziela numery portów dla nowych protokołów i usług oraz zarządza istniejącymi numerami portów, aby zapobiegać konfliktom i zapewnić spójność systemu. Wraz z rozwojem Internetu, coraz więcej aplikacji i usług wymaga unikalnych numerów portów, dlatego IANA jest ważnym elementem w zapewnianiu stabilnego i zorganizowanego rozwoju sieci.

W ramach IANA działa specjalna jednostka, zwana Internet Assigned Numbers Authority Port Numbers (IANA Port Numbers), która zarządza przypisywaniem numerów portów dla protokołów transportowych. Przypisane numery portów są następnie publikowane w oficjalnym rejestrze, który jest dostępny publicznie i umożliwia aplikacjom i usługom korzystanie z unikalnych numerów portów w sposób zgodny z protokołami transportowymi.

### 🚢 Podział portów

Porty w systemie sieciowym Internet dzielą się na trzy główne grupy:

1. ``Well-known ports`` (porty dobrze znane) - są to porty o numerach od ``0`` do ``1023``, które zostały zarezerwowane dla powszechnie stosowanych protokołów, takich jak ``HTTP`` (port 80), ``FTP`` (port 21), ``SSH`` (port 22) czy ``SMTP`` (port 25). Porty te są przypisywane przez IANA i są powszechnie znane wśród użytkowników i administratorów sieci.

2. ``Registered ports`` (porty zarejestrowane) - są to porty o numerach od ``1024`` do ``49151``, które mogą być wykorzystywane przez aplikacje lub usługi, które nie są związane z protokołami dobrze znanymi. Porty te są rezerwowane dla konkretnych aplikacji lub usług i są przypisywane przez IANA lub organizacje zewnętrzne.

3. ``Dynamic and/or private ports`` (porty dynamiczne i/lub prywatne) - są to porty o numerach od ``49152`` do ``65535``, które mogą być wykorzystywane przez aplikacje lub usługi na zasadzie losowego przypisania przez system operacyjny. Porty te są zwykle wykorzystywane do komunikacji pomiędzy klientem a serwerem w ramach jednej sesji i nie są przypisywane przez IANA.


> Druga grupa, czyli zarejestrowane porty wykorzystywane są przez aplikację zainstalowane na komputerze użytkownika. 

Jeśli przykładowo zainstalujemy na swoim komputerze aplikację będącą systemem zarządzania bazami danych ``MySQL``, to będzie ona pracować na porcie ``3306``. Trzecia, ostatnia grupa czyli dynamiczne numery portów, z kolei są przydzielane losowo do aplikacji klienckich, np. kiedy klient wysyła żądanie udostępnienia strony WWW do serwera, to serwer przyjmuje to żądanie domyślnie na porcie ``80``, ale już odpowiedź, którą od serwera klient otrzymuje nie jest przesyłana na port 80, bo ten zarezerwowany jest dla procesów serwera WWW, ale na przydzielonym losowo numerze portów z puli portów dynamicznych.

Działanie kilku aplikacji na tym samym numerze portu nie jest możliwe. Kiedy dana aplikacja pracuje na porcie np. ``53`` (``DNS``), to inna aplikacja już na tym porcie działać nie może, nie jest to możliwe.

Jeśli wiemy już czym są porty aplikacji to wprowadźmy sobie kolejne pojęcie. Będzie nim gniazdo (ang. Socket). Z pojęciem Socketu spotkaliście się już przy okazji omawiania płyt główny i procesorów na zajęciach z urządzeń techniki komputerowej, w sieciach komputerowych również ono występuje. Gniazdo to kombinacja adresu IP i numeru portu:

<div align="center">

## 192.168.210.13:80

</div>

Gniazdo jednoznacznie identyfikuje dany proces działający na urządzeniu i tak przykładowo, kiedy nasza przeglądarka będzie odwoływała się do serwera WWW o udostępnienie jakiejś strony internetowej, to zapytania do serwera zostanie przesłane do jego gniazda czyli procesu (aplikacji serwera WWW).

Podział portów na te trzy grupy pomaga w organizacji i zarządzaniu protokołami transportowymi w systemie sieciowym Internet oraz umożliwia uniknięcie konfliktów między aplikacjami i usługami, które korzystają z tych samych portów.


### 🤝 3-Way Handshake

Uzgodnienie trój-etapowe (ang. ``three-way handshake``) to proces ustanawiania połączenia w protokole TCP (Transmission Control Protocol), który umożliwia dwóm hostom komunikację w sieci. 

Proces ten składa się z trzech etapów:

1. ``SYN`` - w pierwszym etapie host inicjujący połączenie wysyła pakiet z ustawioną flagą SYN (synchronizacja) do hosta docelowego. Pakiet ten zawiera także numer sekwencyjny, który jest wykorzystywany do identyfikacji poszczególnych pakietów w trakcie komunikacji.

2. ``SYN-ACK`` - w drugim etapie host docelowy odpowiada na żądanie SYN, wysyłając pakiet z ustawionymi flagami SYN i ACK (acknowledgment). Pakiet ten zawiera także numer sekwencyjny i numer potwierdzenia, które potwierdzają poprawność otrzymania pakietu SYN przez host docelowy.

3. ``ACK`` - w trzecim etapie host inicjujący potwierdza poprawność otrzymania pakietu SYN-ACK od hosta docelowego, wysyłając pakiet z ustawioną flagą ACK. Pakiet ten zawiera także numer potwierdzenia, który potwierdza poprawność otrzymania pakietu SYN-ACK przez host inicjujący.

<div align="center">

![3-way](https://user-images.githubusercontent.com/125214141/234091399-c3ac4402-84af-4ede-a396-a60dbd7a3916.png)

</div>


Po ukończeniu procesu uzgodnienia trój-etapowego, połączenie jest ustanawiane i dane mogą być przesyłane między hostami. W trakcie komunikacji, każdy przesyłany pakiet zawiera numery sekwencyjne i numery potwierdzenia, które umożliwiają identyfikację poszczególnych pakietów oraz potwierdzenie ich poprawnego otrzymania.

Uzgodnienie trój-etapowe jest jednym z elementów protokołu TCP, który umożliwia niezawodną i bezpieczną komunikację między hostami w sieci. Dzięki temu mechanizmowi, hosty są w stanie ustalić stabilne połączenie i przesyłać dane w sposób kontrolowany i zabezpieczony przed ewentualnymi błędami lub zagrożeniami z zewnątrz.

