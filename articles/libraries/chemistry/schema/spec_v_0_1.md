---
title: Broombridge schema specifikation
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185366"
---
# <a name="broombridge-specification-v01"></a>Broombridge-specifikation v 0,1 #

Nyckelorden "måste", "måste", "krävs", ",", ",", ",", "ska inte", "ska inte", "rekommenderas", "maj" och "valfritt" i det här dokumentet tolkas enligt beskrivningen i [RFC 2119](https://tools.ietf.org/html/rfc2119).

Eventuella marginaler med rubrikerna "anmärkning", "INFORMATION" eller "varning" är informativa.

## <a name="introduction"></a>Introduktion ##

Det här avsnittet är informativt.

Broombridge-dokument är avsedda att kommunicera instanser av simulerings problem i Quantum kemi för bearbetning med Quantum-simulering och programmerings verktygs kedjor.

## <a name="serialization"></a>Serialisering ##

Det här avsnittet är normativt.

Ett Broombridge-dokument måste serialiseras som ett [YAML 1,2-dokument](http://yaml.org/spec/) som representerar ett JSON-objekt enligt beskrivningen i [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2,2.
Objektet som serialiseras till YAML måste ha en egenskap `"$schema"` vars värde är `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`och måste vara giltigt enligt JSON-schemat Draft-06-specifikationer [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

I resten av den här specifikationen refererar "Broombridge-objektet" till JSON-objektet som är avserialiserat från ett Broombridge YAML-dokument.

Om inget annat uttryckligen anges får objekten inte ha ytterligare egenskaper utöver de som anges uttryckligen i det här dokumentet.

## <a name="additional-definitions"></a>Ytterligare definitioner ##

Det här avsnittet är normativt.

### <a name="quantity-objects"></a>Antal objekt ###

Det här avsnittet är normativt.

Ett _Quantity_ -objekt är ett JSON-objekt och måste ha en egenskap `units` vars värde är ett av de tillåtna värdena som anges i tabell 1.

Ett objekt av en kvantitet är ett _enkelt antal objekt_ om det har en enda egenskap `value` förutom egenskapen `units`.
Värdet för egenskapen `value` måste vara ett tal.

Ett objekt av en kvantitet är ett _objekt med gränser_ om det innehåller egenskaperna `lower` och `upper` utöver dess `units`-egenskap.
Värdena för `lower` och `upper` egenskaper måste vara siffror.
Ett objekt med en begränsad kvantitet kan ha en egenskap `value` vars värde är ett tal.

Ett Quantity-objekt är ett objekt av reserverad _array-kvantitet_ om det har egenskapen `format` och en egenskap `values` utöver dess `units`-egenskap.
Värdet för `format` måste vara strängen `sparse`.
Värdet för egenskapen `values` måste vara en matris.
Varje element i `values` måste vara en matris som representerar index och värdet för antalet sparse-matriser.

Indexen för varje element i ett objekt med sparse-kvantitet måste vara unika för hela objektet för renulled array Quantity.
Om det finns ett index med värdet `0`måste en parser behandla objektet null-optimerad array-kvantitet identiskt med ett objekt av sparse-kvantitet för matriser där indexet inte finns alls.


Ett objekt av en kvantitet måste antingen vara

- ett enkelt antal objekt,
- ett objekt med ett begränsat antal eller
- ett kvantitets objekt för sparse-matris.


### <a name="examples"></a>Exempel ###

Det här avsnittet är informativt.

En enkel kvantitet som representerar $1.9844146837\,\mathrm{Ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

En begränsad kvantitet som representerar en enhetlig distribution under intervallet $ [-7,-6]\,\mathrm{Ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Följande är en null-optimerad mat ris mängd med ett element `[1, 2]` lika med `hello` och ett element `[3, 4]` lika med `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Format avsnitt ##

Det här avsnittet är normativt.

Broombridge-objektet måste ha en egenskap `format` vars värde är ett JSON-objekt med en egenskap som kallas `version`.
Värdet `"0.1"`måste anges för egenskapen `version`.

### <a name="example"></a>Exempel ###

Det här avsnittet är informativt.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Avsnittet integral uppsättningar ##

Det här avsnittet är normativt.

Broombridge-objektet måste ha en egenskap `integral_sets` vars värde är en JSON-matris.
Varje objekt i värdet för egenskapen `integral_sets` måste vara ett JSON-objekt som beskriver en uppsättning integraler, enligt beskrivningen i resten av det här avsnittet.
I resten av det här avsnittet refererar termen "Integral uppsättnings objekt" till ett objekt i värdet för egenskapen `integral_sets` i Broombridge-objektet.

Varje heltals uppsättnings objekt måste ha en egenskap `metadata` vars värde är ett JSON-objekt.
Värdet för `metadata` kan vara det tomma JSON-objektet (det vill säga `{}`) eller kan innehålla ytterligare egenskaper som definierats av Implementeraren.

### <a name="hamiltonian-section"></a>Avsnittet Hamiltonian ###

#### <a name="overview"></a>Översikt ####

Det här avsnittet är informativt.

Egenskapen `hamiltonian` för varje heltals uppsättnings objekt beskriver Hamiltonian för ett visst Quantum kemi-problem genom att visa en lista med en och två Body-termer som sparse-matriser med reella tal.
Hamiltonian-operatörer som beskrivs av varje heltals uppsättnings objekt tar formuläret

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

här $h _ {ijkl} = (till och med | kl) $ i Mulliken-konventionen.

För tydlighetens skull är en-Electron-termen

$ $ H_ {} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

och två-Electron-termen är

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Som anges i vår Beskrivning av [egenskapen`basis_set`](#basis-set-object) för varje element i egenskapen `integral_sets`, förutsätter vi ytterligare att de bas funktioner som används är Real-värde.
Detta gör att vi kan använda följande symmetries mellan villkoren för att komprimera representationen av Hamiltonian.

$ $ H_ {ijkl} = H_ {ijlk} = H_ {jikl} = H_ {jilk} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {lkji}.
$$


#### <a name="contents"></a>Innehåll ####

Det här avsnittet är normativt.

Varje heltals uppsättning måste ha en egenskap `hamiltonian` vars värde är ett JSON-objekt.
Värdet för egenskapen `hamiltonian` kallas för ett Hamiltonian-objekt och måste ha egenskaperna `one_electron_integrals` och `two_electron_integrals` enligt beskrivningen i resten av det här avsnittet.
Ett Hamiltonian-objekt kan också ha en egenskap `particle_hole_representation`.
Om detta är tillgängligt måste värdet för `particle_hole_representation` följa det format som beskrivs i resten av det här avsnittet.

##### <a name="one-electron-integrals-object"></a>Ett-Electron integraler-objekt #####

Det här avsnittet är normativt.

Egenskapen `one_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd vars index är två heltal och vars värden är tal.
Varje term måste innehålla index `[i, j]` där `i >= j`.

> Lägg Detta återspeglar den symmetri som $h _ {H_} = {Ji} $ som är en följd av det faktum att Hamiltonian är Hermitian.


###### <a name="example"></a>Exempel ######

Det här avsnittet är informativt.

Följande kvantitet för sparse-matris representerar Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> Broombridge använder 1-baserad indexering.


##### <a name="two-electron-integrals-object"></a>Två Electron integraler-objekt #####

Det här avsnittet är normativt.

Egenskapen `two_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd med en ytterligare egenskap som kallas `index_convention`.
Varje element av värdet för `two_electron_integrals` måste ha fyra index.

Varje `two_electron_integrals`-egenskap måste ha en `index_convention`-egenskap.
Värdet för egenskapen `index_convention` måste vara ett av de tillåtna värdena som anges i tabell 1.
Om värdet för `index_convention` är `mulliken`, och för varje element i mängden `two_electron_integrals` sparse-matris måste en parser som läser in ett Broombridge-dokument instansiera en Hamiltonian-term som är lika med $h Electron _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , där $i $, $j $, $k $, och $l $ måste vara heltal i intervallet från 1 till det antal electrons som anges av egenskapen `n_electrons` för objektet integral, och där $h _ {i, j, k, l} $ är element `[i, j, k, l, h(i, j, k, l)]` för antalet sparse-matriser.

###### <a name="symmetries"></a>Symmetries ######

Det här avsnittet är normativt.

Om egenskapen `index_convention` för ett `two_electron_integrals`-objekt är lika med `mulliken`, och om ett element med index `[i, j, k, l]` finns, får följande index inte förekomma om de inte är lika med `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Eftersom `index_convention`-egenskapen är en null-optimerad artikelkvantitet, kan inga index upprepas på olika element.
> I synnerhet, om ett element med index `[i, j, k, l]` finns, kan inget annat element ha dessa index.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exempel #######

Det här avsnittet är informativt.

Följande objekt anger Hamiltonian

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} en\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a>Partikel – håls representation av objekt #####

Det här avsnittet är normativt.

Objektet partikel – håls representation anger att de integraler som lagras definieras med avseende på partikel håls ställningen, där Annihilation-operatörerna beskriver excitations bort från det referens tillstånd som används, till exempel en Hartree – Fock-tillstånd.
Objektet är valfritt.
Om objektet inte anges, ska Hamiltonian tolkas som ej angivet i partikel-håls-representation.
Om värdet för `particle_hole_representation`, måste värdet för vara ett objekt av sparse-arrayelement vars index är fyra heltal och vars värden är ett tal och en sträng.
Sträng delen av värdet för varje element får bara innehålla de tecken `'+'` och `'-'` som anger om en viss faktor i termen är en skapande-eller Annihilation-operator i partikel-håls-representationen.  Till exempel `"-+++"` samverkar till ett hål som skapas på platsen $i $ och partiklar som skapas på platser $j, k $ och $l $.

> [!NOTE]
> Eftersom värdet för `particle_hole_representation` är ett objekt av renulled array Quantity måste `unit`-och `format`-egenskaperna anges.
> Godkända enheter är listade i tabell 1.
> Egenskapen `format` är obligatorisk och anger om Hamiltonian-koefficienterna anges som en kompakt eller sparse-matris.
> I den aktuella versionen stöds endast sparse-matriser, med tolkningen att alla ospecificerade element är $0 $, men framtida versioner kan lägga till stöd för ytterligare värden för egenskapen `format`.

### <a name="initial-state-section"></a>Avsnittet inledande tillstånd ###

Initial_state_suggestion-objektet anger inledande Quantum-tillstånd för den angivna Hamiltonian. Objektet måste vara en matris med JSON-`state` objekt.

#### <a name="state-object"></a>Tillstånds objekt ####

Varje tillstånd representerar en superposition av upptagna banor. Varje tillstånds objekt måste ha en `label`-egenskap som innehåller en sträng. Varje tillstånds objekt måste ha en `superposition`-egenskap som innehåller en matris med bas tillstånd och deras normaliserade amplituder.

Till exempel är de initiala tillstånden $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ representeras av
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>Bas uppsättnings objekt ####

Det här avsnittet är normativt.

Varje heltals uppsättnings objekt kan ha en `basis_set`-egenskap.
Om den är tillgänglig måste värdet för egenskapen `basis_set` vara ett objekt med två egenskaper `type` och `name`.

Bas funktionerna som identifieras av värdet för egenskapen `basis_set` måste vara Real-värde.

> [!NOTE]
> Antagandet om att alla bas funktioner är verkliga värden kan vara avslappnad i framtida versioner av den här specifikationen.

## <a name="tables-and-lists"></a>Tabeller och listor ##

### <a name="table-1-allowed-physical-units"></a>Tabell 1. Tillåtna fysiska enheter ###

Det här avsnittet är normativt.

En sträng som anger en enhet måste vara något av följande:

- `hartree`
- `ev`

Tolkare och producenter måste behandla följande enkla antal objekt som likvärdiga:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabell 2. Tillåtna index konventioner ###

Det här avsnittet är normativt.

En sträng som anger en index konvention måste vara något av följande:

- `mulliken`

Det här avsnittet är informativt.

Ytterligare index konventioner kan införas i framtida versioner av den här specifikationen.

#### <a name="interpretation-of-index-conventions"></a>Tolkning av index konventioner ####

Det här avsnittet är informativt.
