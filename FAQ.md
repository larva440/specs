**1) Moduł przetwarzający i analizujący dane historyczne analizuje dane i określa jakie TempID miały kontakt z osobą zarażoną spełniające kryteria kwalifikacji kontaktu (minimum 15 minut) jako narażający osobę na zarażenie. Moduł ten kojarzy TempID z ID użytkowników w systemie.**

Moduł/funkcja wymaga dużej mocy obliczeniowej. Urządzenie mobilne nie ma wystarczającej mocy potrzebnej do analizy danych historycznych dotyczących “napotkanych” urządzeń. Do wysłania powiadomień do innych użytkowników z którymi mieliśmy kontakt potrzeba znać aktualne tempID urządzeń które mamy zapisane w pamięci lokalnej (stare tempID).
Przechowywanie danych ID na telefonach byłoby mniej bezpieczne (ryzyko ataku na telefon). Ponadto konieczne jest założenie, że te dane kontaktów mogą wymagać czyszczenia, walidacji i ewentualnie wzmacniania danymi z serwera (na przykład dane kalibracyjne danego modelu telefonu). Dodatkowo w przypadku konieczności rozgłoszenia ID telefonów/ aplikacji wykorzystywanych przez osoby zakażone należałoby wysłać te ID nadmiarowo do wszystkich telefonów z zainstalowaną aplikacją.


**2) W jaki sposób zapewniono, że aplikacja nie zostanie wykorzystana do śledzenia osób z niej korzystających, ich aktywności?**

ProteGO Safe nie ma modułów ani funkcjonalności umożliwiających lokalizację . Aplikacja jest budowana na podstawie otwartego źródła opublikowanego w serwisie GitHub. Zrezygnowaliśmy z funkcji analitycznych oferowanych np. przez Google Analytics. Nie zbieramy nawet informacji nt. zachowania użytkownika korzystającego z aplikacji tj. nie analizujemy jak użytkownicy korzystają z ProteGo Safe. Informacje, które aplikacja przetwarza w ramach tzw. tracingu to natężenie sygnału Bluetooth urządzeń z którymi łączy się urządzenie użytkownika. Nie mamy możliwości wykorzystania tych danych do “śledzenia” tj. określania pozycji geograficznej. Nie ma możliwości ustalenia gdzie znajduje się użytkownik. W najlepszym wypadku można ustalić odległość między dwoma urządzeniami (dwoma użytkownikami). Niemniej jest to obarczone potencjalnym błędem w ustaleniach, który wynika z urządzeń korzystających z różnej klasy modułów łączności bluetooth (niektóre urządzenia są wyższej klasy i dostarczają bardziej prawidłowe pomiary, a niektóre mniej), a także z sytuacjami losowymi (np. dwie osoby, które stoją w korku w dwóch autach obok siebie lub sąsiedzi mieszkający w bloku, których dzieli ściana).


**3) Czy aplikacja wykorzystuje dane geolokalizacyjne?** 

Nie. Aplikacja nie wykorzystuje ani nie zapisuje żadnych danych geolokalizacyjnych. W urządzeniach klasy Android użytkownicy mogą być pytani o “zgodę na lokalizację”, niemniej dotyczy ona wykorzystania modułu Bluetooth w urządzeniu. ProteGO Safe nie przetwarza danych geolokalizacyjnych. 


**4) Jakie zastosowano zabezpieczenia, aby zapewnić, że nie dojdzie do zbierania danych osób na dużą skalę teraz i w przyszłości?** 

Nie przetwarzamy danych szczególnej kategorii (wszystkie dane zapisywane w Dzienniku Zdrowia są przechowywane jedynie na urządzeniu użytkownika, a dane podawane w triażu tj. samoocenie są przekazywane w sposób zanonimizowany do Infermedica, która nie przechowuje tych danych oraz nie może zidentyfikować użytkownika). 


**5) Jak zapewniono, że informacje o osobach nie zakażonych nie będą ujawniane?**

Aplikacja nie zbiera tych danych tj. na serwer GIS nie są przekazywane dane użytkowników wynikające z tracingu. Innymi słowy ani Ministerstwo Cyfryzacji, ani Główny Inspektor Sanitarny nie  wiedzą z jakimi dokładnie użytkownikami zetknęli się inni użytkownicy aplikacji.


**6) W jaki sposób ustalono zakres danych niezbędnych do zbierania w aplikacji, tak że jest on ograniczony wyłącznie do niezbędnych do walki z pandemią?**

Jest to zakres ustalony podczas analiz przez Głównego Inspektora Sanitarnego oraz Ministerstwo Cyfryzacji. Konieczność weryfikacji użytkownika w aplikacji za pośrednictwem kodu PIN przed wysłaniem danych do systemu umożliwia wprowadzenie do aplikacji potwierdzonych danych dotyczących zarażenia użytkownika chorobą COVID-19, a co za tym idzie ogranicza możliwość podania przez użytkownika nieprawdziwej informacji, która mogłaby spowodować niechcianą panikę. Obawiano się także, że użytkownicy, którzy będą wprowadzali informacje o zarażeniu w niekontrolowany sposób doprowadzą do spadku zaufania do aplikacji, która ma kluczową rolę w walce z pandemią COVID-19.


**7) Czy rozwiązanie jest transparentne? Jakie środki zastosowano?**

Kod aplikacji jest udostępniany na bieżąco w otwartym repozytorium serwisu GitHub (Od 20.04.2020), dokumentacja również jest publikowana (od 29.04.2020).


**8) Czy wybrano rozwiązania (komponenty/funkcjonalności), które są najkorzystniejsze z punktu widzenia prywatności? Jak przebiegał proces decyzyjny ich wyboru? Proszę uzasadnić wybór takich a nie innych rozwiązań z punktu widzenia najszerszego zapewnienia prywatności.**

Istnieje wiele rozwiązań bardziej ingerujących w prywatność użytkownika. Wybrana została najpewniejsza metoda niegromadzenia danych, które mogłyby być zakwalifikowane jako dane szczególnej kategorii (dane dotyczące zdrowia). GIS mógłby wymagać uwierzytelnienia wszystkich użytkowników (np. poprzez podanie numeru telefonu jak w aplikacji Kwarantanna Domowa lub jak w aplikacji tracingowej przygotowywanej przez Czechów), aplikacja mogłaby wykorzystywać geolokalizację, co skutkowałoby większą skutecznością pomiarów i analiz modułu tracingowego, ale wpływałoby to na przetwarzanie danych na wielką skalę. Z tego względu zdecydowano się na kompromis pomiędzy (aplikacja do tego dąży) absolutną prywatnością użytkowników a skuteczną walką z pandemią COVID-19. Przetwarzane w minimalnej skali (jedynie uwierzytelnienie osoby zarażonej COVID-19, za jej zgodą, za pośrednictwem numeru PIN generowanego przez aplikację) umożliwia zabezpieczenie prywatności użytkowników aplikacji, tym samym umożliwiając skuteczną weryfikację zarażenia użytkownika, który może (nie musi) wysłać dane na serwer.


**9) Jakie argumenty przeważyły za wyborem skoncentrowanego modelu gromadzenia danych?**

Jak wskazano powyżej - wybrano model mieszany. Głównym powodem jest większa pewność co do prawidłowości danych. Maksymalnie zabezpieczamy prywatność zdrowych osób - ich dane nigdy nie opuszczą ich telefonów. Ten model łączy zalety tych idealistycznych modeli rozwiązań. 


**10) Czy użytkownik może wyłączyć, skasować dane w każdej chwili?**

Tak. W Aplikacji umożliwione jest usunięcie wszystkich danych do niej wprowadzonych.


**11) Czy aplikacja zostanie dezaktywowana po zakończeniu obecnego kryzysu?**

Tak, w kolejnych wersjach aplikacji taka funkcjonalność zostanie dodana w ProteGO Safe. 


**12) Jakie dane i kiedy są przesyłane na serwer? Kto utrzymuje ten serwer? Kto ma dostęp do danych na serwerze? Komu są przekazywane? Jak długo będą przechowywane? Czy są zanonimizowane?**

Na serwer będą przesyłane jedynie z zapisów zgromadzonych przez potwierdzone osoby chore. Jest to tymczasowe tempID aplikacji oraz tymczasowe tempID aplikacji innych użytkowników, model telefonu i siła sygnału (doprecyzowując: dane dotyczące historii spotkań użytkownika oraz pomocniczo modele telefonu do ewentualnej korekty danych na podstawie charakterystyk znanych modeli telefonów). Serwer backend będzie utrzymywany przez Ministerstwo Cyfryzacji.

**13) Jakie zastosowano zabezpieczenia aplikacji? Co zapewnia, że aplikacja jest bezpieczna, a osoby niepożądane nie uzyskają dostępu do danych?**

Architektura - część dostępna publicznie w internecie jest aplikacją uruchamiającą się wyłącznie lokalnie w pamięci przeglądarki użytkownika. Tam też składuje wszystkie dane. Niezależnie od tego publiczna strona dostarczająca użytkownikowi taki program, jest zabezpieczona przed zapisem przez niepowołane osoby oraz chroniona przez zaawansowany system anty DDoS i WAF firmy Cloudflare. Hostingiem który dostarcza treści chronione przez Cloudflare jest usługa Firebase Hosting firmy Google. Zabezpieczamy również cały proces wytwarzania aplikacji web i natywnych aplikacji mobilnych kontrolując listę osób z uprawnieniami do ostatecznej publikacji nowych wersji aplikacji. Kod źródłowy aplikacji jest sprawdzany przez skanery korzystające z publicznych baz danych podatności oprogramowania i jego komponentów. W procesie korzystamy również z metody peer review i publicznego audytu społecznego otwartego kodu aplikacji poprzez system GitHub.

**14) Jakie testy aplikacji zostały przeprowadzone, w szczególności w zakresie cyberbezpieczeństwa?**

Prowadzimy testy bezpieczeństwa za pomocą statycznej analizy kodu. Zarówno za pomocą tak zwanego peer review w ramach zespołu jak i za pomocą narzędzi automatycznych (Whitesource i Snyk). Planowane są również zewnętrzne testy penetracyjne i specjalistyczny audyt. Publiczny adres aplikacji był skanowany za pomocą skanera Nessus. Kod aplikacji web oraz aplikacji mobilnych jest skanowany przez skanery podatności firm Whitesource i Snyk przy każdej kolejnej zmianie wersji testowych i produkcyjnych. Planowane są dalsze testy.


**15) Z kim były konsultowane założenia/funkcjonalności systemu?**

Założenia aplikacji są na bieżąco konsultowane z: GIS i MZ, środowiskiem zgromadzonym wokół inicjatyw koronazglowy.com (Stare SafeSafe) i ProteGo Safe, lekarzami, epidemiologami i specjalistami od technologii, a także z Prezesem Urzędu Ochrony Danych Osobowych oraz podczas spotkań sieci eHealth Komisji Europejskiej. Czekamy również na audyty zewnętrznych podmiotów, oraz - przede wszystkim - społeczności i NGOsów. 

**16) Czy ProteGO Safe umożliwi inwigilację osób chorych?**
Nie. Rozdzielenie systemów (serwerów backendowych), które analizują zanonimizowane dane realizowane jest właśnie po to, aby uniknąć przetwarzania danych na jednym centralnym systemie (serwerze). Przetwarzanie danych “w jednym miejscu” budziłoby bowiem uzasadnione i słuszne wątpliwości związane z prywatnością użytkowników. Obecne rozwiązanie, stara się maksymalnie ograniczyć dostęp do danych stosując zasadę adekwatności i minimalizacji, które zostały określone w RODO.
