---
rubrik: Beskrivning av avancerade Matrix-begrepp: Lär dig mer om eigenvectors, Eigenvalues och matriser, de grundläggande verktyg som används för att beskriva och simulera Quantum-algoritmer.
författare: QuantumWriter-UID: Microsoft. Quantum. Concepts. Matrix-Advanced MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuell No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="advanced-matrix-concepts"></a>Avancerade mat ris koncept #

Vi utökar nu vår modifiering av matriser till [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) och [*exponentieller*](https://en.wikipedia.org/wiki/Matrix_exponential) som utgör en grundläggande uppsättning verktyg som vi behöver för att beskriva och implementera Quantum-algoritmer.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues och Eigenvectors ##

Låt $ M $ vara en fyrkantig matris och $ v $ vara en Vector som inte är en vektor som inte är noll (dvs. Vector med alla poster som är lika med $ 0 $ ).

Vi säger att $ v $ är en [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) av  $ M $ om $ MV = ka $ för lite nummer $ c $ . Vi antar att $ c $ är den [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) som motsvarar eigenvector $ v $ . I allmänhet kan en matris $ M $ transformera en vektor till någon annan Vector, men en eigenvector är speciell eftersom den lämnas oförändrad, förutom om den multipliceras med ett tal. Observera att om $ v $ är en eigenvector med eigenvalue $ c $ , $ är det $ också av en eigenvector (för alla som inte $ är noll a $ ) med samma eigenvalue.

För Identity-matrisen är till exempel $ $ en eigenvector med eigenvalue 1 för varje Vector $ v $ .

Ett annat exempel är om du vill ha en [*Diagonal matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ som bara innehåller poster som inte är noll i diagonalen:

$$
\begin{bmatrix}
d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .
$$

Vektorerna

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} och \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

är eigenvectors i den här matrisen med Eigenvalues  $ D_1 $ , $ D_2 $ $ $ respektive D_3. Om $ D_1 $ , $ D_2 $ och $ D_3 $ är distinkta tal, är dessa vektorer (och deras multiplar) de enda eigenvectors i matrisen $ d $ . I allmänhet är det enkelt att läsa av Eigenvalues och eigenvectors för en diagonal matris. Eigenvalues är alla siffror som visas i diagonalen och deras respektive eigenvectors är enhets vektorerna med en post lika med $ 1 $ och de återstående posterna motsvarar $ 0 $ .

Observera i exemplet ovan att eigenvectors i $ D $ utgör grunden för tredimensionella $ $ vektorer. En basis är en uppsättning vektorer så att alla vektorer kan skrivas som en linjär kombination av dem. Mer explicit, $ v_1 $ , $ v_2 $ och $ v_3 $ form a grund om en Vector $ v $ kan skrivas som $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ för vissa siffror $ A_1 $ , $ a_2 $ och $ a_3 $ .

Kom ihåg att en Hermitian-matris (även kallat eget) är en komplex fyrkantig mat ris som motsvarar dess egna komplexa konjugat, medan en enhetlig matris är en komplex fyrkantig mat ris vars invertering är lika med dess intilliggande eller komplexa konjugat.
För Hermitian-och enhetliga matriser, som i huvudsak är de enda matriser som påträffas i Quantum Computing, finns det ett allmänt resultat som kallas för [*Spectral-satsen*](https://en.wikipedia.org/wiki/Spectral_theorem), vilket förutsätter följande: för alla Hermitian eller en enhetlig matris $ M $ finns det en enhetlig $ U $ , till exempel $ m = u ^ \dagger D U $ för en diagonal matris $ D $ . Dessutom är de diagonala posterna i $ D $ Eigenvalues i $ M $ .

Vi vet redan hur man beräknar Eigenvalues och eigenvectors för en diagonal matris $ D $ . Med den här satsen vet vi att om $ v $ är en eigenvector av $ D $ med eigenvalue $ c $ , d.v.s. $ DV = ka $ , $ kommer U ^ \dagger v $ att vara en eigenvector av $ M $ med eigenvalue $ c $ . Detta beror på att

$$M (U ^ \dagger v) = u ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = U ^ \dagger d v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Mat ris exponenter
En [*mat ris exponent*](https://en.wikipedia.org/wiki/Matrix_exponential) kan också definieras i exakt analog till exponentiell funktionen.  Mat ris exponenten för en matris $ a $ kan uttryckas som

$$
e ^ A = \boldone + a + a \frac { ^ 2 } { 2! } + \frac { En ^ 3 } { 3!}+\cdots
$$

Detta är viktigt eftersom en Quantum mekanisk tids utveckling beskrivs av en enhetlig matris i formatet $ e ^ { IB } $ för Hermitian Matrix $ B $ .  Av den anledningen är framställningen av matriser en grundläggande del av Quantum data behandling och det Q# finns inbyggda rutiner för att beskriva dessa åtgärder.
Det finns många sätt att beräkna en matris på en klassisk dator, och i stort sett en så stor uppskattning som en exponent är fraught med Peril.  Se [*Cleve moler och Charles Van-lånet. "Nineteen misstänkta-sätt att beräkna exponenten för en matris." SIAM granska 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) för mer information om de utmaningar som uppstår.

Det enklaste sättet att förstå hur du beräknar exponenten för en matris är genom Eigenvalues och eigenvectors i matrisen.  Mer specifikt säger Spectral-satsen ovan om att $ $ det finns en enhetlig matris $ U $ och en diagonal matris $ D $ , till exempel en $ = u ^ \dagger D u $ för varje Hermitian eller en enhetlig matris.  På grund av egenskaperna för unitarity har vi $ en ^ 2 = u ^ \dagger d ^ 2 u $ och på samma sätt för alla Power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ .  Om vi ersätter detta i Operator definitionen för operatorn exponentiell, får vi:

$$
e ^ a = U ^ \dagger \left ( \boldone + d + \frac { D ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 & \cdots & \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$

Om du till andra ord omvandlar till eigenbasis i matris A, motsvarar det att du beräknar $ $ matrisen exponentiellt för att beräkna den vanliga exponenten för Eigenvalues i matrisen.  Så många åtgärder som används i Quantum Computing är det här syftet med att omvandla till eigenbasis i en matris för att förenkla utförandet av operatören exponentiellt visas ofta och är grunden bakom många Quantum-algoritmer som Trotter – Suzuki Quantum simulerings metoder som beskrivs senare i den här hand boken.

En annan användbar egenskap är om $ B $ är både enhetligt och Hermitian, t. ex. $ b = b ^ { -1 } = B ^ \dagger $ och $ b ^ 2 = \boldone $ . Genom att tillämpa den här regeln på ovanstående expansion av matrisen exponent och genom att gruppera $ \boldone $ och $ B $ -termerna tillsammans, kan det se att för alla verkliga värden $ x $ identiteten

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


innehålla. Det här sticket är särskilt användbart eftersom det kan vara orsaken till att måtten för åtgärder i matrisen har, även om dimensionen för $ b $ är exponentiellt stor, för det särskilda fallet när $ B $ är både enhetligt och Hermitian.
