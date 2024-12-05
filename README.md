<div align="center">

# 📮 Adresowanie sieciowe 📢

</div>

Adresacja sieciowa to element nieodłączny i fundamentalny względem założeń logiki topologii sieciowych, na jej podstawie odbywa się dostarczanie informacji. W momencie gdy kurier dostarcza nam paczkę, dokonuje tego dzięki adresowi zamieszkania, a w sieciach komputerowych bity informacji są dostarczane do odpowiedniego hosta po przez określony adres - adres IP. Dzięki niemu możliwe jest funkcjonowanie protokołów warstwy sieciowej.

> Adres IP jest adresem logicznym interfejsu sieciowego (hosta) to znaczy, że nie musi to być tylko adres konkretnego komputera, może to być również adres interfejsu (interfejsów) rutera czy access pointa.

Każdy adres `IPv4` składa się z `32-bitowego` ciągu zer i jedynek. Wynika to z faktu, że działanie urządzeń w sieciach komputerowych oparte jest na logice cyfrowej, co oznacza, że adresy te interpretowane są jako liczby `binarne`. Dla prostszego stosowania adresacji i zapamiętywania adresów, na co dzień stosuje się jednak zapis `dziesiętny`. Zapis ten składa się z `4 części` (każda z nich to 1 bajt czyli 8 bitów), zwanych `oktetami`.

> [!NOTE]
> Adres IP w zapisie dziesiętnym  `192.168.210.102`
> 
> będzie miał postać binarną równą `11000000.10101000.11010010.01100110`

Każdy oktet posiada przelicznik na wartość dziesiętną, a liczenie zaczynamy zawsze od `prawej strony`.
![1248163264128-removebg-preview](https://github.com/user-attachments/assets/dd02e7de-0e0f-40de-8352-7c360e1b8d00)

Więc jeżeli byśmy chcieli jeden z czterech oktetów obliczyć to musimy go sobie wydzielić i pod wartością `1` podpisać odpowiednią jej wartość `dziesiętną`, z tego przykładu wybierzmy sobie pierwszy oktet (od końca)

![bin-removebg-preview](https://github.com/user-attachments/assets/e207c67f-149b-49f4-a106-b229a2d0721d)


Jak widać rozliczenie takiego oktetu przebiega w sposób następujący:

![binary2-removebg-preview](https://github.com/user-attachments/assets/c0e35aab-f228-4f48-bb06-91c9eecc3c79)

Jeżeli pod nad daną wartością występuje `1` to zostawiamy wartość dolną (dziesiętną), a pod wartościami `0` wymazujemy wartość pod spodem.
W efekcie uzyskujemy wartości dziesiętne które musimy zsumować ze sobą aby uzyskać przeliczoną wartość `z systemu binarnego na dziesiętny`.

W efekcie powyższego przykładu wartości dziesiętne które nam pozostają (patrząc od prawej do lewej) to: `2, 4, 32, 64`. Gdy je zsumujemy to wyjdzie przekonwertowana wartość dziesiętna czyli `102`.
Proces ten działa w obie strony i jest analogiczny.

### ✨ Zadania utrwalające

1. Zamień `1010101` (system binarny) na system dziesiętny.
2. Przekształć `10110` (system binarny) na system dziesiętny.
3. Znajdź wartość dziesiętną liczby `1100100`.
4. Sporządź zapis dziesiętny liczby `1011011`.
5. Przedstaw w systemie dziesiętnym liczbę `10001`.
6. Zapisz w systemie dziesiętnym liczbę `111010`
7. Dokonaj konwersji `1001110` do systemu dziesiętnego.
8. Znajdź reprezentację dziesiętną liczby `10011`.
9. Przekształć `1101` na system dziesiętny.
10. Sporządź zapis dziesiętny liczby `10111`.
11. Zamień adres `192.168.1.1` na zapis binarny.
12. Zamień adres `00001010.00000000.00000000.00000001` na zapis dziesiętny. 
13. Zapisz adres `172.16.254.1` na zapis binarny.
14. Zapisz adres `8.8.8.8` na zapis binarny
15. Zamień adres `11111111.11111111.11111111.00000000` na zapis dziesiętny.
16. Zapisz adres `11011001.10100000.00100010.00111000` na zapis dziesiętny.
17. Zapisz adres `234.111.34.22` na zapis binarny.
18. Zapisz adres `00101110.01100101.11001010.00110110` na zapis dziesiętny.
19. Zapisz adres `104.16.41.20` na zapis binarny.
20. Zapisz adres `10111100.10100110.01010111.10111111` na zapis dziesiętny.
