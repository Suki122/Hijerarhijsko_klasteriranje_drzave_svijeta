📊 Hijerarhijsko klasteriranje država prema socio-ekonomskim pokazateljima
📌 Opis projekta

Ovaj projekt bavi se primjenom hijerarhijskog (aglomerativnog) klasteriranja nad državama svijeta s ciljem grupiranja zemalja prema njihovim stvarnim socio-ekonomskim karakteristikama.

Uobičajene podjele država temelje se na geografiji (Europa, Azija, Afrika itd.), no takva klasifikacija često ne odražava stvarne razlike ili sličnosti u:

životnom standardu

ekonomskoj razvijenosti

demografskim trendovima

društvenim pokazateljima

Cilj ovog rada je korištenjem metoda strojnog učenja identificirati objektivne skupine država na temelju numeričkih pokazatelja razvoja.

🎯 Ciljevi projekta

Analizirati socio-ekonomske podatke država

Očistiti i standardizirati podatke

Primijeniti više metoda hijerarhijskog klasteriranja

Usporediti različite metode spajanja (linkage)

Odrediti optimalan broj klastera

Evaluirati kvalitetu klasteriranja pomoću metrika

Interpretirati dobivene socio-ekonomske skupine

📂 Skup podataka

Podaci su preuzeti s Kaggle platforme:

🔗 https://www.kaggle.com/datasets/nishanthsalian/socioeconomic-country-profiles

📊 Osnovne informacije:

66 država

96 socio-ekonomskih pokazatelja

Za potrebe analize odabrano je 7 ključnih pokazatelja

✅ Odabrani pokazatelji:

GDP per capita (current US$) – ekonomski standard

Life expectancy at birth – očekivano trajanje života

Fertility rate – stopa plodnosti

Unemployment rate – nezaposlenost

Urban population (%) – urbanizacija

Internet users (%) – digitalna razvijenost

Inflation rate – stabilnost gospodarstva

Odabrani pokazatelji pokrivaju ključne ekonomske, demografske i društvene aspekte razvoja.

🧹 Obrada podataka
1️⃣ Čišćenje podataka

Uklonjene su vrijednosti -99 (označene kao nedostajući podaci)

Uklonjeni su simboli poput ~

Pretvorba podataka u numerički format

Ovaj korak je nužan kako bi algoritmi klasteriranja mogli ispravno izračunavati udaljenosti.

2️⃣ Standardizacija podataka

Budući da klasteriranje koristi udaljenosti između točaka, varijable s velikim vrijednostima (npr. GDP = 50.000) dominirale bi nad manjim vrijednostima (npr. fertilitet = 1.5).

Zato je provedena standardizacija (Z-score normalizacija):

𝑧
=
𝑥
−
𝜇
𝜎
z=
σ
x−μ
	​


Nakon standardizacije:

prosjek = 0

standardna devijacija = 1

Time sve varijable imaju jednaku težinu u analizi.

🧠 Metodologija

Primijenjeno je aglomerativno hijerarhijsko klasteriranje.

🔹 Aglomerativni pristup

Svaka država počinje kao zaseban klaster

U svakom koraku spajaju se dva najsličnija klastera

Proces se nastavlja dok sve države ne postanu jedan klaster

Rezultat se prikazuje pomoću dendrograma

🔗 Korištene metode spajanja (Linkage Methods)

Testirane su četiri metode:

1️⃣ Ward metoda (Euclidean udaljenost)

Minimizira varijancu unutar klastera

Najčešće daje najuravnoteženije klastere

Pokazala se kao najstabilnija metoda

2️⃣ Complete linkage (Manhattan udaljenost)

Gleda maksimalnu udaljenost između elemenata klastera

Stvara kompaktnije i strože klastere

3️⃣ Average linkage (Cosine udaljenost)

Koristi prosječnu udaljenost između klastera

Dobra za analizu sličnosti smjera (strukture podataka)

4️⃣ Single linkage (Euclidean udaljenost)

Spaja klastere prema najmanjoj udaljenosti

Može dovesti do “chaining effect” (lančanog efekta)

📈 Metrike udaljenosti

Korištene metrike:

Euclidean distance

Manhattan (Cityblock)

Cosine distance

Različite metrike omogućuju usporedbu stabilnosti klastera.

🌳 Dendrogram

Dendrogram vizualno prikazuje:

Redoslijed spajanja klastera

Udaljenost na kojoj dolazi do spajanja

Moguće “prirodne rezove” za određivanje broja klastera

Na temelju vizualne analize dendrograma testirani su različiti pragovi rezanja.

🔢 Određivanje optimalnog broja klastera
1️⃣ Silhouette Score

Silhouette koeficijent mjeri:

Koheziju unutar klastera

Odvojenost između klastera

Vrijednosti se kreću od -1 do 1.

Rezultati:

3 klastera → 0.2403

5 klastera → 0.2620

Zaključak:
Podjela na 5 klastera daje bolju strukturu i jasnije razdvajanje država.

2️⃣ Dunnov indeks

Dunnov indeks mjeri:

Minimalnu udaljenost između klastera

Maksimalni promjer klastera

Veća vrijednost znači bolju separaciju.

Ova metrika dodatno potvrđuje optimalnost odabrane podjele.

📊 Rezultati analize

Dobiveno je 5 socio-ekonomskih skupina država koje ne slijede nužno geografske granice.

Klasteri reflektiraju:

Visoko razvijene digitalne i ekonomske države

Srednje razvijene ekonomije

Države u tranziciji

Države s visokom stopom fertiliteta i nižim GDP-om

Ekonomski nestabilnije zemlje

Ovakva podjela pruža realniju sliku globalnih razvojnih obrazaca nego klasična regionalna podjela.

🛠 Tehnologije i biblioteke

Projekt je izrađen u Google Colab okruženju.

Korištene Python biblioteke:

pandas

numpy

matplotlib

scipy

sklearn

▶️ Kako pokrenuti projekt
Opcija 1: Google Colab

Otvoriti .ipynb datoteku u Google Colabu

Povezati Google Drive:

from google.colab import drive
drive.mount('/content/drive')

Pokrenuti sve ćelije redom

Opcija 2: Lokalno

Instalirati potrebne pakete:

pip install pandas numpy matplotlib scipy scikit-learn

Pokrenuti Jupyter Notebook:

jupyter notebook

Otvoriti Hijerarhijsko_klasteriranje.ipynb

🔎 Struktura projekta
Hijerarhijsko_klasteriranje.ipynb
README.md

Notebook sadrži:

Uvod i opis problema

Učitavanje podataka

Čišćenje podataka

Standardizaciju

Implementaciju različitih metoda klasteriranja

Vizualizaciju dendrograma

Evaluaciju (Silhouette, Dunn)

Interpretaciju rezultata

📌 Zaključak

Hijerarhijsko klasteriranje pokazalo se kao učinkovita metoda za grupiranje država prema razini socio-ekonomskog razvoja.

Ključni zaključci:

Geografska blizina ne znači nužno socio-ekonomsku sličnost

Standardizacija podataka je ključna za ispravnu analizu

Ward metoda daje najstabilnije rezultate

5 klastera predstavlja optimalnu podjelu prema kvantitativnim metrikama

Projekt demonstrira praktičnu primjenu strojnog učenja u području društvenih i ekonomskih analiza.
