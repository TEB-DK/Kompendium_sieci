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

<div align='center'>

![1248163264128-removebg-preview](https://github.com/user-attachments/assets/dd02e7de-0e0f-40de-8352-7c360e1b8d00)

</div>

Więc jeżeli byśmy chcieli jeden z czterech oktetów obliczyć to musimy go sobie wydzielić i pod wartością `1` podpisać odpowiednią jej wartość `dziesiętną`, z tego przykładu wybierzmy sobie pierwszy oktet (od końca)

<div align='center'>
 
![bin-removebg-preview](https://github.com/user-attachments/assets/e207c67f-149b-49f4-a106-b229a2d0721d)

</div>

Jak widać rozliczenie takiego oktetu przebiega w sposób następujący:

<div align='center'>

![binary2-removebg-preview](https://github.com/user-attachments/assets/c0e35aab-f228-4f48-bb06-91c9eecc3c79)

</div>

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
21. Zapisz adres `132.101.31.99` na zapis binarny.
22. Zapisz adres `200.201.13.8` na zapis binarny.
23. Zapisz adres `176.88.102.205` na zapis binarny.

---

## System ósemkowy 🎱

System ósemkowy to system liczenia używający 8 cyfr (od 0 do 7). Każda pozycja w tym systemie reprezentuje kolejną potęgę liczby 8.

Struktura systemu ósemkowego wygląda następująco: `8^0 czyli 1`, `8^1 czyli 8`, `8^2 czyli 64`, `8^3 czyli 512`.
Naszym celem będzie nauczenie się przeliczania systemu ósemkowego na dwójkowy oraz dziesiętny i odwrotnie.

#### Przeliczenie `ósemkowego` na `dziesiętny`

Warto zaznaczyć, że system ósemkowy dzieli się w podobny sposób do binarny, natomiast "oktety" nie mają 8 cyfr, a `3`, które możemy przeliczyć z ósemkowego na binarny.
Natomiast dlaczego na binarny? ponieważ z binarnego bezpośrednio przeliczana jest ta wartość na dziesiętny - kilka kroków więcej do wykonania w takim przypadku.
Drugie pytanie jakie powinno się pojawić to "`Dlaczego na 3, a nie na 4?`" z tego względu, że wartość `111` w zapisie binarnym, daje nam wartość 7 czyli pełen zakres cyfr możliwy do wykorzystania w systemie ósemkowym.

Co za tym idzie, możliwe jest ułożenie liczb jedynie z wartości maksymalnie 7, cyfra jak 99 nie zaistnieje w tym systemie.

<div align='center'>

![8na2-removebg-preview(1)](https://github.com/user-attachments/assets/72f24e21-752a-4c00-af05-b42a13ed3745)

</div>

Natomiast wynik `1110111` już możemy przepisać do postaci dziesiętnej - 64+32+16+4+2+1 = `119`

Aby zastosować odwrotność tego działania to jest nieco prościej, ponieważ tylko trzeba podzielić wartość na 8 i zliczać resztę z dzielenia.

<div align='center'>

![10na8-removebg-preview](https://github.com/user-attachments/assets/ab90cf3d-1c5f-476e-aeb3-7ab574719cbb)

</div>

Zastosowanie przeliczenia jest proste:
1. Liczbę 119 dzielimy przez 8, ósemek mieści się 14, a 14*8 daje nam 112, a 119 - 112 = 7 więc i reszta jest 7, zapisujemy po prawej stronie.
2. Liczbę 14 dzielimy przez 8, ósemek mieści się jedna, 1*8 daje nam 8, a 14 - 8 = 6 więc i reszta to jest 6, zapisujemy po prawej stronie.
3. Liczbę 1 dzielimy przez 8, żadna ósemka nie mieści się w liczbie 1 więc tą liczbę przepisujemy jako resztę po prawej stronie.
4. Wynik odczytujemy od dołu do góry, zapisując od lewej do prawej.

 
### ✨ Zadania utrwalające

1. 24 (ósemkowo) = ? (dziesiętnie)
2. 56 (ósemkowo) = ? (dziesiętnie)
3. 73 (ósemkowo) = ? (dziesiętnie)
4. 11 (ósemkowo) = ? (dziesiętnie)
5. 42 (ósemkowo) = ? (dziesiętnie)
6. 65 (ósemkowo) = ? (dziesiętnie)
7. 37 (ósemkowo) = ? (dziesiętnie)
8. 50 (ósemkowo) = ? (dziesiętnie)
9. 16 (ósemkowo) = ? (dziesiętnie)
10. 77 (ósemkowo) = ? (dziesiętnie)
11. 25 (dziesiętnie) = ? (ósemkowo)
12. 64 (dziesiętnie) = ? (ósemkowo)
13. 39 (dziesiętnie) = ? (ósemkowo)
14. 17 (dziesiętnie) = ? (ósemkowo)
15. 52 (dziesiętnie) = ? (ósemkowo)
16. 88 (dziesiętnie) = ? (ósemkowo)
17. 43 (dziesiętnie) = ? (ósemkowo)
18. 61 (dziesiętnie) = ? (ósemkowo)
19. 36 (dziesiętnie) = ? (ósemkowo)
20. 75 (dziesiętnie) = ? (ósemkowo)
21. 127 (ósemkowo) = ? (dziesiętnie)
22. 246 (ósemkowo) = ? (dziesiętnie)
23. 345 (ósemkowo) = ? (dziesiętnie)
24. 102 (ósemkowo) = ? (dziesiętnie)
25. 567 (ósemkowo) = ? (dziesiętnie)
26. 146 (dziesiętnie) = ? (ósemkowo)
27. 289 (dziesiętnie) = ? (ósemkowo)
28. 413 (dziesiętnie) = ? (ósemkowo)
29. 532 (dziesiętnie) = ? (ósemkowo)
30. 678 (dziesiętnie) = ? (ósemkowo)
