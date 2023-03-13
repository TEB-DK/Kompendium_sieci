<div align="center">

# 💻 Protokoły warstwy aplikacji 💻

</div>

W momencie uruchomienia dowolnej aplikacji na komputerze osobistym, aplikacje te tworzą interfejs komunikacyjny między siecią komputerową, a użytkownikiem. Gdy zostaną dodane protokoły komunikacyjne (które w aplikacjach występują już) do tego połączenia, nasza komunikacja jest możliwa.


## 🌐 Protokół HTTP

Przykładowym protokołem warstwy aplikacji może być już wielokrotnie wspomniany ``protokoł HTTP`` (80), który zostaje domyślnie zaimplementowany w każdej przeglądarce internetowej, tak samo jak i w przypadku komunikatorów czy innych pogramów korzystających z komunikacji sieciowej, które posiadają własne protokoły oraz przypisane im porty.

W momencie wpisania w przeglądarce adresu ``URL`` (z ang. ``Uniform Resource Locator``) strony, to po zatwierdzeniu przeglądarka nawiąże połączenie z serwerem, na którym dana strona jest przechowywana i zażąda określonego zasobu (najczęściej pliku HTML).

Jeśli serwer posiada zażądany zasób to przesyła jego zawartość do przeglądarki, by ta mogła zinterpretować kod ``HTML``.

<div align="center">

![Diagram przykładowej komunikacji](https://user-images.githubusercontent.com/125214141/224800309-d9f6e0bc-a891-4639-84da-2c95258944ba.png)

</div>

> Wszystko to jest ujęte w dość mocny skrót. W rzeczywistości proces ten jest bardziej złożony.

W przypadku wysłania zapytania na konkretny adres ``URL``, na przykład:

    https://expressjs.com/index.html

Przeglądarka sprawdza rodzaj protokołu, a następnie nazwę domeny internetowej (która domyślnie zapisana jest pod postacią adresu IP), natomiast na końcu dopiero nazwa konkretnego pliku zostaje zinterpretowana. W kolejnych krokach przeglądarka wysyła do serwera ``DNS`` zapytanie w celu zmiany nazwy ``mnemonicznej`` (zrozumiałej dla człowieka) na adres IP serwera na którym konkretna strona jest przechowywana.

<div align="center">

![Diagram działania serwera DNS](https://user-images.githubusercontent.com/125214141/224813246-688f961d-ccbe-4cd7-91cf-b265fe6bd9ac.png)

</div>

Przeglądarka znając adres wysyła żądanie do serwera z zapytaniem ``GET`` odnośnie pliku index.html. Jeśli serwer posiada ten zasób to w odpowiedzi na zapytanie odpowie odpowiednim kodem ``200`` i przeglądarka będzie mogła otrzymany plik zinterpretować za pomocą języka ``HTML``. 

Protokoł ``HTTP`` standardowo działa na porcie ``80`` i definiuje podstawowe rodzaje wiadomości czyli ``zapytania``, takie jak na przykład: ``GET``, ``POST``, ``PATCH``, ``DELETE``; za pomocą których to komunikuje się z serwerem WWW.

### ❔ Zapytanie GET

Zapytanie ``GET`` służy do zażądania od serwera danego zasobu, który może posiadać. Nagłówek zapytania dokładnie wygląda tak:

    GET /index.html HTTP/1.1

Prócz nazwy żądanego zasobu, posiada również ``wersję protokołu``, który wykorzystuje. Gdy serwer odbierze takie żądanie, odpowiada stosownym komunikatem i ewentualnym zasobem:

    HTTP/1.1 200 OK /index.html

> W żądaniu GET znajdują się jeszcze takie informacje jak: ``nazwa hosta`` (np. expressjs.com), ``nazwa przeglądarki``, ``akceptowane przez przeglądarkę typy plików``, ``kodowanie znaków``.

> W odpowiedzi serwera, znajdują się informacje, takie jak: ``czas serwera``, ``nazwa aplikacji serwera (np. APACHE)``, ``czas wygaśnięcia dokumentu``.

Jeśli z jakiś przyczyn serwer WWW nie może odesłać zasobu, odsyła komunikat ze stosownym kodem, np. ``404``, który informuje, że żądany zasób nie został znaleziony, lub ``403`` informujący o zabronionym dostępie do zasobów.

Wybrane kody komunikatów i błędów widoczne są w poniższych tabelach.

<div align="center">

| Zakres kodów | Opis |
|:---:|:---:|
| 100 - 199 | Odpowiedzi informacyjne |
| 200 - 299  | Odpowiedzi powodzenia   | 
| 300 - 399  | Odpowiedzi przekierowania | 
| 400 - 499  | Odpowiedzi błędów klienta  |
| 500 - 599  | Odpowiedzi błędów serwera  |

</div>

Tabela poniżej przedstawia najważniejsze i wymagane zapamiętania kody.

<div align="center">

| Kod | Opis | Wyjaśnienie |
|:---:|:---:|:---:|
| *__400__*  | *__Bad Request__*  | *__Żądanie nie może być obsłużone przez serwer z powodu błędu klienta__*  |
| *__401__*  | *__Unauthorized__*  | *__Żądanie zasobu, który wymaga uwierzytelnienia__*  |
| *__403__*  | *__Forbidden__*  | *__Serwer zrozumiał zapytanie lecz konfiguracja bezpieczeństwa zabrania mu zwrócić żądany zasób__*  |
| *__404__*  | *__Not Found__*  | *__Serwer nie odnalazł zasobu według podanego URL__* |
| 405  | Method Not Allowed  | Metoda zawarta w żądaniu nie jest dozwolona dla wskazanego zasobu  | 
| 406  | Not Acceptable | Zażądany zasób nie jest w stanie zwrócić odpowiedzi mogącej być obsłużonej przez klienta |
| 407  | Proxy Authentication Required  | Wymagane uwierzytelnienie do serwera pośredniczącego |
| *__408__*  | *__Request Timeout__*    | *__Koniec czasu oczekiwania na żądanie – klient nie przesłał zapytania do serwera w określonym czasie__* |
| *__409__*  | *__Conflict__*   | *__Żądanie nie może być zrealizowane, ponieważ występuje konflikt z obecnym statusem zasobu__* |
| 411  | Length required    | Wymagana długość – serwer odmawia zrealizowania zapytania ze względu na brak nagłówka Content-Length w zapytaniu |
| 415  | Unsupported Media Type | Nieznany sposób żądania – serwer odmawia przyjęcia zapytania, ponieważ jego składnia jest niezrozumiała dla serwera |
| *__500__*  | *__Internal Server Error__*  | *__Wewnętrzny błąd serwera – serwer napotkał problemy, które uniemożliwiły zrealizowanie żądania__*  |
| *__501__*  | *__Not Implemented__*  | *__Serwer nie dysponuje funkcjonalnością wymaganą w zapytaniu__*  |
| *__502__*  | *__Bad Gateway__*  | *__łąd bramy – serwer – spełniający rolę bramy lub pośrednika – otrzymał niepoprawną odpowiedź od serwera nadrzędnego i nie jest w stanie zrealizować żądania klienta__*  |
| *__503__*  | *__Service Unavailable__*  | *__Usługa niedostępna – serwer nie jest w stanie w danej chwili zrealizować zapytania klienta ze względu na przeciążenie__* |
| 504  | Gateway Timeout  | Przekroczony czas bramy – serwer – spełniający rolę bramy lub pośrednika – nie otrzymał w ustalonym czasie odpowiedzi od wskazanego serwera HTTP, FTP, LDAP itp. lub serwer DNS jest potrzebny do obsłużenia zapytania  | 
| 505  | HTTP Version Not Supported | Nieobsługiwana wersja HTTP – serwer nie obsługuje bądź odmawia obsługi wskazanej przez klienta wersji HTTP |

</div>

W celu doczytania i doinformowania się więcej w zakresie kodów HTTP proponuję zerknąć na [ 🔗 dokumentację Mozilli](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).

### ❕ Zapytanie POST

Następnym zapytaniem jest ``POST``, służy do przesyłania danych na serwer.

Stosowana jest najczęściej w ``formularzach`` znajdujących się na stronie, które w języku ``HTML`` mają zdefiniowany znacznik ``form`` z atrybutem ``method`` do określenia zapytania. 

```html
<form action="/logowanie.php" method="POST" target="_blank">
  
  <label for="login">Login: </label>
  <input type="text" id="login" name="login">

  <label for="pass">Hasło: </label>
  <input type="password" id="pass" name="pass">

  <button type="submit" value="Wyślij">
</form>
```
Protokół ``HTTP`` mimo swojej popularności jest ``niebezpieczny``.

Metoda ``POST`` przesyła dane do serwera ``jawnym tekstem``. Kiedy uda się przechwycić transmisję pomiędzy klientem, a serwerem, można odczytać informacje jakie przesyłamy na serwer.

<div align="center">

![Diagram użycia metody POST](https://user-images.githubusercontent.com/125214141/224829889-611295d0-60b2-4759-830e-5d285787ee08.png)

</div>

Sytuacja jest bardzo niebezpieczna, dlatego obecnie większość stron WWW, na których istnieje możliwość przesłania na serwer jakieś informacji, czyli np. na tych stronach gdzie konieczne jest logowanie, stosowany jest już protokół ``HTTPS`` szyfrujący komunikację pomiędzy klientem a serwerem, działa on na porcie ``443``.

## 📫 Protokoły poczty elektronicznej

Poczta elektroniczna stosuje dwa współpracujące ze sobą protokoły warstwy aplikacji. Jeden służy do ``wysyłania poczty`` i jest to protokół ``SMTP``, a drugi do ``odbierania wiadomości`` i jest nim ``POP3``.

Obecnie do odbierania poczty elektronicznej stosowany może być również protokół ``IMAP``. Protokoły te ściśle powiązane są z aplikacjami, czyli procesami uruchomionymi zarówno na komputerze klienckim gdzie tworzona i odbierana jest wiadomość, jak również na serwerze.

Procesy te to ``MUA`` (z ang. ``Mail User Agent``), ``MTA`` (z ang. ``Mail Transfer Agent``) oraz ``MDA`` (za ang. ``Mail Delivery Agent``), Proces MUA działa na urządzeniu klienckim, natomiast pozostałe dwa na serwerach pocztowych.


### Uproszczony proces przesyłania wiadomości pocztowych z użyciem MTA/MDA

<div align="center">


![Diagram komunikacji MTA/MDA](https://user-images.githubusercontent.com/125214141/224836450-0f88e1b4-9298-45ac-b08d-02ef2590a44a.png)

</div>

1. Użytkownik tworzy wiadomość ``e-mail`` i za pomocą procesu ``MUA`` przekazuje ją do serwera poczty i procesu ``MTA`` działającego na tym serwerze.

2. Proces ten analizuje nagłówek wiadomości, m.in. po to aby określić adresata wiadomości i sprawdza czy użytkownik do którego wiadomość jest kierowana znajduje się na jego liście użytkowników.

3. Jeśli tak jest to przekazuje tą wiadomość do procesu ``MDA``, który odpowiedzialny jest za dostarczenie jej do odpowiedniego adresata.

4. Jeśli adresat wiadomości nie posiada konta na tym serwerze to proces MTA dostarcza wiadomość do procesu ``MTA`` innego serwera, na którym konto tego użytkownika istnieje.

5. Serwer ten przekazuje wiadomość do procesu ``MDA``, a ten dostarcza wiadomość do właściwego adresata.

Protokoły pocztowe

<div align="center">

| Protokół | Port |
|:---:|:---:|
|SMTP| 25|
|POP3| 110|
|IMAP| 143|
|SMTPS| 465 / 587|
|POP3S| 995 |
|IMAPS| 993 |

</div>

## 🗄️ Protokół FTP

Protokół przesyłania plików jest podstawowym protokołem wykorzystywanym jako usługa sieciowa, daje możliwość wysyłania i odbierania plików.

Usługa ta, jednocześnie protokół komunikacyjny, jest bardzo często wykorzystywana kiedy chcemy wysłać pliki strony internetowej, na serwer WWW lub też kiedy chcemy po prostu wysłać jakieś pliki na serwer i udostępnić je innym użytkownikom. Aby wykonać operacje przesłania pliku na serwer czy też pobrania zasobu z serwera musimy skorzystać z ``klienta FTP``. 

``Klient FTP`` dostępny jest na każdym systemie operacyjnym i można z niego korzystać np. za pomocą wiersza poleceń, co jednak jest dość nie wygodne, ale możliwe. Popularnym klientem do obsługi FTP, jest chociażby ``FileZilla`` czy ``WinSCP``.

> Warto zaznaczyć, że odczytywanie plików z serwera FTP można wykonać nawet za pomocą przeglądarki.

W przypadku tego protokołu, aby komunikacja mogła być zrealizowana we właściwy sposób należy zestawić dwa połączenia pomiędzy klientem a serwerem.

Pierwsze połączenie służy tylko do wysyłania poleceń i komunikatów i nazywane jest ``połączeniem sterującym`` (``port 21``).

Drugie połączenie, działające na ``porcie 20`` służy do przesyłania plików z i do serwera. Aby zabezpieczyć dostęp do serwera FTP stosuje się autoryzację użytkowników, dokładnie taką samą jak w przypadku logowania się do profilu na portalu społecznościowym czy do poczty elektronicznej, choć czasem, jeśli zasoby mają być dostępne dla większej liczby odbiorców, to realizuje się dostęp przez tak zwanego użytkownika anonimowego (ang. Anonymous), dzięki czemu niewymagana jest autoryzacja.

<div align="center">

![Diagram komunikacji FTP](https://user-images.githubusercontent.com/125214141/224841997-c2d2e306-e34a-49ed-87be-b89eb9082818.png)

</div>

> Takie rozwiązanie powinno się stosować tylko wówczas, kiedy użytkownicy mogą pobierać dane z serwera. Umieszczanie ich na serwerze zawsze dostępne jest tylko dla użytkowników posiadających login i hasło.

## 🎛️ Protokół SSH
Kolejnym często wykorzystywanym protokółem warstwy aplikacji, jest protokół zdalnego zarządzania hostami, zwany ``SSH`` (ang. ``Secure Shell``). 

Stosowany jest on przez administratorów do zarządzania serwerami znajdującymi się bardzo często w różnych geograficznie miejscach, niekoniecznie w miejscu pracy. Stosują go też osoby, które mają np. wykupione serwery ``VPS`` i w ten sposób nimi administrują. Protokół ten wywodzi się z innego protokołu zdalnego dostępu, protokołu ``TELNET`` i jest jego, lepszą bezpieczniejszą wersją.

> ``TELNET``, który jest najstarszym protokołem warstwy aplikacji, nie szyfruje komunikacji pomiędzy klientem a serwerem, komunikaty przesyłane są ``jawnym tekstem``, a co za tym idzie istnieje możliwość przechwycenia komunikacji i podejrzenia jakie informacje są w sesji przesyłane. Ocenie jest to sytuacja nie do przyjęcia, dlatego też do zdalnego zarządzania hostami stosowany jest właśnie szyfrowany protokół ``SSH``.

Domyślnym algorytmem szyfrowania komunikacji jest algorytm ``RSA``, istnieje również możliwość szyfrowania danych za pomocą nieco słabszego algorytmu ``DSA``. 

Podczas instalacji serwera ``SSH`` tworzona jest para kluczy – ``klucz publiczny`` i ``klucz prywatny`` serwera – służą one do ``szyfrowania`` i ``deszyfrowania`` komunikacji.

Podczas pierwszego połączenia z serwerem, klient, zapisuje publiczny klucz serwera na swoim dysku, w pliku ``known_hosts``.

Następnie tworzy tak zwany ``klucz sesji``, który będzie stosowany do szyfrowania całej komunikacji. ``Klucz sesji`` zostaje ``zaszyfrowany kluczem publicznym`` otrzymanym wcześniej od serwera i jest do niego odsyłany. Od tego momentu cała komunikacja szyfrowana jest ``kluczem sesji``.

Standardowo ``SSH`` działa na porcie ``22``. Jednym z najpopularniejszych programów klienckich wykorzystujących ``SSH``, jest program ``PuTTY``. 

> PuTTy to darmowy program w wersji portable, nie wymagający instalacji. Aby połączyć się zdalnie z hostem, wystarczy go uruchomić, podać nazwę hosta lub jego adres IP, wybrać SSH jeśli domyślnie nie jest zaznaczony i kliknąć Open. Jeśli po raz pierwszy łączymy się ze zdalnym hostem potwierdzamy chęć nawiązania połączenia i już możemy zdalnie nim zarządzać.

<div align="center">

![PuTTY](https://user-images.githubusercontent.com/125214141/224846370-8fe1d7f7-d6e3-4acd-82b0-7ce1d78a0b22.png)

</div>

## 💱 Protokół DNS
``DNS`` to protokół i usługa, zamieniająca nazwy domenowe, zrozumiałe dla człowieka na adresy IP urządzeń w sieci.

> Wyobraźmy sobie sytuacje, gdzie DNS nie istnieje, a my chcemy wyświetlić w przeglądarce stronę internetową. Zamiast nazwy domeny, czyli adresu w postaci słownej musimy wpisać adres IP w postaci dziesiętnej, np. 127.0.0.1. Dla większości osób nie jest to problem zapamiętać kombinację cyfr. Natomiast w Internecie jest wiele stron WWW i zapamiętanie wielu adresów liczbowych byłoby już trudne. Co więcej w takim zapisie liczbowym, łatwo jest się pomylić, a w świecie Internetu, taka drobna pomyłka może skutkować tym, że przeglądarka zostanie przekierowana na niechciany adres WWW.

Adresy IP serwerów rzadko, ale jednak wciąż potrafią się zmienić, w takim wypadku należałoby na nowo zapamiętać adres IP. Przy zastosowaniu serwera ``DNS`` problem ten zostaje rozwiązany, ponieważ DNS wykona automatycznie zamianę adresu na nowy, który będzie nadal widniał pod aliasem tekstowej nazwy strony WWW.

``DNS`` to usługa działająca w architekturze ``klient – serwer``, jednak nie mamy tutaj do czynienia z klientem jako programem komputerowym takim jak przeglądarka czy program do wymiany plików. Na komputerze uruchamiana jest ``usługa systemowa``, zwana z języka angielskiego ``DNS Resolver`` i ona obsługuje wszystkie aplikacje na komputerze klienta, które wymagają zamiany nazw. Zawsze, kiedy konfigurujemy urządzenie sieciowe, czy też zwyczajnie komputer powinny zostać zdefiniowane dwa adresy serwerów DNS, tak aby w przypadku braku komunikacji z jednym z nich, drugi realizował funkcję zamiany nazw.

<div align="center">

![Ustawienie DNS](https://user-images.githubusercontent.com/125214141/224848573-c35c4237-dd8d-406a-8fbc-03fb3a8a7ca3.png)

</div>

Serwer DNS przechowuje ``różne typy rekordów``, m.in rekordy ``typu A`` oraz ``AAAA`` zawierające ``adresy urządzeń końcowych``, jak również rekordy typu ``MX`` obsługujące ``wymianę poczty elektronicznej``, bo pamiętać należy, że DNS nie tylko zamienia adresy domenowe na adres IP dla stron WWW, ale także dla serwerów poczty elektronicznej.

Wysyłanie zapytań serwera DNS, który nie znalazł rekordów w swojej bazie do innych serwerów może powodować nadmierny ruch sieciowy, co jest sytuacją nieporządną. 

Aby zapobiec nadmiernemu i niepotrzebnemu ruchowi w sieci, kiedy inny serwer odnajdzie dany rekord i prześle go do serwera przypisanego do naszego urządzenia, ten zapisuje sobie ten rekord w pamięci podręcznej, tak aby w przyszłości nie musieć się odwoływać do innego serwera po ten sam adres. 

>Zdecydowanie przyspiesza to potem zamianę nazw, ponieważ nasz serwer DNS nie szuka już rekordu po innych serwerach tylko od razu zamienia nazwy. 

Podobnie usługa DNS na komputerze osobistym przechowuje poprzednio przekształcone nazwy. Można to sprawdzić, wprowadzając na komputerze z systemem Windows polecenie ``ipconfig/displaydns``. Zobaczymy wówczas jakie odwzorowania są zapisane w pamięci podręcznej usługi DNS naszego komputera.

## 🦸 Protokół DHCP

Podobnie jak omówiony wcześniej ``DNS`` również ``DHCP`` jest to protokół działający jako usługa.

``DHCP`` umożliwia podłączonym do sieci komputerom ``pobieranie adresu IP``, ``maski podsieci``, ``adresu bramy`` i ``serwera DNS`` oraz innych ustawień ze skonfigurowanej wcześniej puli adresów. Serwer DHCP może być skonfigurowany na osobnym komputerze i stanowił będzie osobne urządzenie w sieci przydzielające komputerom klienckim adresy IP, może również działać na już istniejącym serwerze jako osobna usługa lub osobny proces.

> Obecnie również rutery, które mamy w domach pozawalają na skonfigurowanie takiej usługi.

Przydzielanie adresów komputerom klienckim poprzez usługę ``DHCP``, zwane ``przydzielaniem dynamicznym``, z czego wywodzi się nazwa protokołu (z ang. ``Dynamic Host Configuration Protocol``) jest bardzo wygodnym rozwiązaniem dla administratorów, szczególnie w dużych sieciach, gdzie bardzo często pojawiają się nowe komputery i ich użytkownicy.
> W sieci, w której pracuje 100 czy 1000 komputerów, do tego sporo urządzeń przenośnych, sama konfiguracja adresów IP byłaby zajęciem uciążliwym, a przede wszystkim czasochłonnym.

Oczywiście nie wszystkie urządzenia w sieci mogą uzyskiwać adresy w ten sposób ponieważ niektóre z nich, takie jak serwery aplikacji, baz danych, uwierzytelniania użytkowników, ale również drukarki sieciowe czy rutery powinny, a wręcz muszą posiadać adresy ``przydzielone statycznie``, czyli ręcznie. 

> Dlaczego? Ponieważ usługa DHCP, skonfigurowana na serwerze nie przydziela komputerom danego adresu IP na stałe. Ona tylko oddaje w ``dzierżawę`` taki adres, na ``czas ustalony`` podczas konfiguracji DHCP, może to być kilka godzin, kilka dni, ale nie na stałe.

Komputer, który zostaje wyłączony, oddaje adres, który ``dzierżawił`` i ten adres wraca do puli. Inne urządzenie może wówczas ten adres wydzierżawić.

Aby komputery z systemem Windows, pobierały adresy z serwera DHCP, w konfiguracji sieci należy wybrać opcję ``Uzyskaj adres IP automatycznie``.

<div align="center">

![DHCP](https://user-images.githubusercontent.com/125214141/224850910-99521079-f6d8-444b-b174-ca2fd79650fc.png)

</div>

---


