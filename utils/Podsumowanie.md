### Podsumowanie

#### Generowanie danych


Zdefiniowano “prawdziwą” funkcję generującą Y oraz globalny szum (ten sam poziom dla wszystkich scenariuszy), co umożliwia porównywanie MSE między przypadkami.


Rozkłady predyktorów: normalne (różne wariancje), jednostajne (wąskie/szerokie), wykładnicze, Poissona, t-Studenta, mieszane (w tym bimodalne) i kombinacje asymetryczne/ciężkoogonowe.


Przypadki: zmienne niezależne; zmienne zależne (liniowo i nieliniowo); relacja przez ukrytą przyczynę Z.


#### Modele i walidacja


Budowano modele dopasowane do struktury danych (proste vs „idealne” względem mechanizmu) i porównywano CV-MSE (K=5) wraz z przedziałami ufności.


Globalny szum utrzymywał wspólną skalę błędu, więc różnice w MSE wynikały głównie z rozkładów, postaci funkcjonalnej i obecności/siły Z.


#### Wpływ rozkładu na MSE 


Rozkłady skośne i ciężkoogonowe (t-Student, wykładniczy, mieszane) zwiększają MSE i jego zmienność między foldami; modele są bardziej czułe na obserwacje skrajne.


Niedopasowanie postaci funkcjonalnej (np. pominięcie nieliniowości) podnosi MSE silniej niż sama zmiana rozkładu – to koszt uogólniania.


Standaryzacja i rozsądny wybór featurów stabilizują MSE, ale nie kompensują błędnej postaci modelu.


#### Zmienna ukryta 


Z wprowadzono jako wspólną przyczynę, konstruowano proxy-Z (np. komponent główny).


####  Kluczowe obserwacje:


Specyfikacja modelu decyduje – poprawna postać potrafi „pośrednio” uchwycić wpływ Z i obniżyć MSE nawet bez jawnego Z.


Gdy wpływ Z jest dominujący, warto inwestować w dodatkowe zmienne/proxy/instrumenty; gdy dominuje błąd postaci, najpierw naprawiamy formę modelu.


Różnice MSE między modelem prostym a „idealnym” są czytelne i stabilne, co potwierdza powyższe tezy.


#### Epsilon progresu – realizacja


`Diana Morzhak` – pokazała, że wrażliwość MSE na strukturę danych jest użyteczną analogią do mechanizmów predictive coding


`Mateusz Walo` – przeprowadził causal approach: izolowanie efektu nieobserwowalnego czynnika, budowa proxy-Z, nadzorowanie i koordynowania prac i terminów realizacji projektu


`Dominika Zydorczyk` – usystematyzowała interpretację i komunikację wyników MSE dla różnych rozkładów/błędów, pokazując jak metryka odzwierciedla dopasowanie i kiedy myli modelarza.

#### Podsumowanie generalne
Zespół w krótkim czasie wykonał dużo pracy: od przemyślanego generatora danych, przez rzetelną walidację, po klarowne wnioski – każdy dowiózł swój epsilon progres, a razem osiągnęliśmy dojrzałe rozumienie, jak i dlaczego MSE zachowuje się tak, jak obserwowaliśmy.


