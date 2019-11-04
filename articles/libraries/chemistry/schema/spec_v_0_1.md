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
# <a name="broombridge-specification-v01"></a><span data-ttu-id="8cf31-102">Broombridge-specifikation v 0,1</span><span class="sxs-lookup"><span data-stu-id="8cf31-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="8cf31-103">Nyckelorden "måste", "måste", "krävs", ",", ",", ",", "ska inte", "ska inte", "rekommenderas", "maj" och "valfritt" i det här dokumentet tolkas enligt beskrivningen i [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="8cf31-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="8cf31-104">Eventuella marginaler med rubrikerna "anmärkning", "INFORMATION" eller "varning" är informativa.</span><span class="sxs-lookup"><span data-stu-id="8cf31-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="8cf31-105">Introduktion</span><span class="sxs-lookup"><span data-stu-id="8cf31-105">Introduction</span></span> ##

<span data-ttu-id="8cf31-106">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-106">This section is informative.</span></span>

<span data-ttu-id="8cf31-107">Broombridge-dokument är avsedda att kommunicera instanser av simulerings problem i Quantum kemi för bearbetning med Quantum-simulering och programmerings verktygs kedjor.</span><span class="sxs-lookup"><span data-stu-id="8cf31-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="8cf31-108">Serialisering</span><span class="sxs-lookup"><span data-stu-id="8cf31-108">Serialization</span></span> ##

<span data-ttu-id="8cf31-109">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-109">This section is normative.</span></span>

<span data-ttu-id="8cf31-110">Ett Broombridge-dokument måste serialiseras som ett [YAML 1,2-dokument](http://yaml.org/spec/) som representerar ett JSON-objekt enligt beskrivningen i [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2,2.</span><span class="sxs-lookup"><span data-stu-id="8cf31-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="8cf31-111">Objektet som serialiseras till YAML måste ha en egenskap `"$schema"` vars värde är `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`och måste vara giltigt enligt JSON-schemat Draft-06-specifikationer [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="8cf31-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="8cf31-112">I resten av den här specifikationen refererar "Broombridge-objektet" till JSON-objektet som är avserialiserat från ett Broombridge YAML-dokument.</span><span class="sxs-lookup"><span data-stu-id="8cf31-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="8cf31-113">Om inget annat uttryckligen anges får objekten inte ha ytterligare egenskaper utöver de som anges uttryckligen i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="8cf31-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="8cf31-114">Ytterligare definitioner</span><span class="sxs-lookup"><span data-stu-id="8cf31-114">Additional Definitions</span></span> ##

<span data-ttu-id="8cf31-115">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="8cf31-116">Antal objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-116">Quantity Objects</span></span> ###

<span data-ttu-id="8cf31-117">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-117">This section is normative.</span></span>

<span data-ttu-id="8cf31-118">Ett _Quantity_ -objekt är ett JSON-objekt och måste ha en egenskap `units` vars värde är ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="8cf31-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="8cf31-119">Ett objekt av en kvantitet är ett _enkelt antal objekt_ om det har en enda egenskap `value` förutom egenskapen `units`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="8cf31-120">Värdet för egenskapen `value` måste vara ett tal.</span><span class="sxs-lookup"><span data-stu-id="8cf31-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="8cf31-121">Ett objekt av en kvantitet är ett _objekt med gränser_ om det innehåller egenskaperna `lower` och `upper` utöver dess `units`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="8cf31-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="8cf31-122">Värdena för `lower` och `upper` egenskaper måste vara siffror.</span><span class="sxs-lookup"><span data-stu-id="8cf31-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="8cf31-123">Ett objekt med en begränsad kvantitet kan ha en egenskap `value` vars värde är ett tal.</span><span class="sxs-lookup"><span data-stu-id="8cf31-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="8cf31-124">Ett Quantity-objekt är ett objekt av reserverad _array-kvantitet_ om det har egenskapen `format` och en egenskap `values` utöver dess `units`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="8cf31-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="8cf31-125">Värdet för `format` måste vara strängen `sparse`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="8cf31-126">Värdet för egenskapen `values` måste vara en matris.</span><span class="sxs-lookup"><span data-stu-id="8cf31-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="8cf31-127">Varje element i `values` måste vara en matris som representerar index och värdet för antalet sparse-matriser.</span><span class="sxs-lookup"><span data-stu-id="8cf31-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="8cf31-128">Indexen för varje element i ett objekt med sparse-kvantitet måste vara unika för hela objektet för renulled array Quantity.</span><span class="sxs-lookup"><span data-stu-id="8cf31-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="8cf31-129">Om det finns ett index med värdet `0`måste en parser behandla objektet null-optimerad array-kvantitet identiskt med ett objekt av sparse-kvantitet för matriser där indexet inte finns alls.</span><span class="sxs-lookup"><span data-stu-id="8cf31-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="8cf31-130">Ett objekt av en kvantitet måste antingen vara</span><span class="sxs-lookup"><span data-stu-id="8cf31-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="8cf31-131">ett enkelt antal objekt,</span><span class="sxs-lookup"><span data-stu-id="8cf31-131">a simple quantity object,</span></span>
- <span data-ttu-id="8cf31-132">ett objekt med ett begränsat antal eller</span><span class="sxs-lookup"><span data-stu-id="8cf31-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="8cf31-133">ett kvantitets objekt för sparse-matris.</span><span class="sxs-lookup"><span data-stu-id="8cf31-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="8cf31-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="8cf31-134">Examples</span></span> ###

<span data-ttu-id="8cf31-135">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-135">This section is informative.</span></span>

<span data-ttu-id="8cf31-136">En enkel kvantitet som representerar $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="8cf31-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="8cf31-137">En begränsad kvantitet som representerar en enhetlig distribution under intervallet $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="8cf31-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="8cf31-138">Följande är en null-optimerad mat ris mängd med ett element `[1, 2]` lika med `hello` och ett element `[3, 4]` lika med `world`:</span><span class="sxs-lookup"><span data-stu-id="8cf31-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="8cf31-139">Format avsnitt</span><span class="sxs-lookup"><span data-stu-id="8cf31-139">Format Section</span></span> ##

<span data-ttu-id="8cf31-140">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-140">This section is normative.</span></span>

<span data-ttu-id="8cf31-141">Broombridge-objektet måste ha en egenskap `format` vars värde är ett JSON-objekt med en egenskap som kallas `version`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="8cf31-142">Värdet `"0.1"`måste anges för egenskapen `version`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="8cf31-143">Exempel</span><span class="sxs-lookup"><span data-stu-id="8cf31-143">Example</span></span> ###

<span data-ttu-id="8cf31-144">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="8cf31-145">Avsnittet integral uppsättningar</span><span class="sxs-lookup"><span data-stu-id="8cf31-145">Integral Sets Section</span></span> ##

<span data-ttu-id="8cf31-146">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-146">This section is normative.</span></span>

<span data-ttu-id="8cf31-147">Broombridge-objektet måste ha en egenskap `integral_sets` vars värde är en JSON-matris.</span><span class="sxs-lookup"><span data-stu-id="8cf31-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="8cf31-148">Varje objekt i värdet för egenskapen `integral_sets` måste vara ett JSON-objekt som beskriver en uppsättning integraler, enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8cf31-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="8cf31-149">I resten av det här avsnittet refererar termen "Integral uppsättnings objekt" till ett objekt i värdet för egenskapen `integral_sets` i Broombridge-objektet.</span><span class="sxs-lookup"><span data-stu-id="8cf31-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="8cf31-150">Varje heltals uppsättnings objekt måste ha en egenskap `metadata` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="8cf31-151">Värdet för `metadata` kan vara det tomma JSON-objektet (det vill säga `{}`) eller kan innehålla ytterligare egenskaper som definierats av Implementeraren.</span><span class="sxs-lookup"><span data-stu-id="8cf31-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="8cf31-152">Avsnittet Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="8cf31-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="8cf31-153">Översikt</span><span class="sxs-lookup"><span data-stu-id="8cf31-153">Overview</span></span> ####

<span data-ttu-id="8cf31-154">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-154">This section is informative.</span></span>

<span data-ttu-id="8cf31-155">Egenskapen `hamiltonian` för varje heltals uppsättnings objekt beskriver Hamiltonian för ett visst Quantum kemi-problem genom att visa en lista med en och två Body-termer som sparse-matriser med reella tal.</span><span class="sxs-lookup"><span data-stu-id="8cf31-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="8cf31-156">Hamiltonian-operatörer som beskrivs av varje heltals uppsättnings objekt tar formuläret</span><span class="sxs-lookup"><span data-stu-id="8cf31-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="8cf31-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="8cf31-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="8cf31-158">här $h _ {ijkl} = (till och med | kl) $ i Mulliken-konventionen.</span><span class="sxs-lookup"><span data-stu-id="8cf31-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="8cf31-159">För tydlighetens skull är en-Electron-termen</span><span class="sxs-lookup"><span data-stu-id="8cf31-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="8cf31-160">$ $ H_ {} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="8cf31-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="8cf31-161">och två-Electron-termen är</span><span class="sxs-lookup"><span data-stu-id="8cf31-161">and the two-electron term is</span></span>

<span data-ttu-id="8cf31-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="8cf31-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="8cf31-163">Som anges i vår Beskrivning av [egenskapen`basis_set`](#basis-set-object) för varje element i egenskapen `integral_sets`, förutsätter vi ytterligare att de bas funktioner som används är Real-värde.</span><span class="sxs-lookup"><span data-stu-id="8cf31-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="8cf31-164">Detta gör att vi kan använda följande symmetries mellan villkoren för att komprimera representationen av Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8cf31-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="8cf31-165">$ $ H_ {ijkl} = H_ {ijlk} = H_ {jikl} = H_ {jilk} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="8cf31-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="8cf31-166">Innehåll</span><span class="sxs-lookup"><span data-stu-id="8cf31-166">Contents</span></span> ####

<span data-ttu-id="8cf31-167">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-167">This section is normative.</span></span>

<span data-ttu-id="8cf31-168">Varje heltals uppsättning måste ha en egenskap `hamiltonian` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="8cf31-169">Värdet för egenskapen `hamiltonian` kallas för ett Hamiltonian-objekt och måste ha egenskaperna `one_electron_integrals` och `two_electron_integrals` enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8cf31-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="8cf31-170">Ett Hamiltonian-objekt kan också ha en egenskap `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="8cf31-171">Om detta är tillgängligt måste värdet för `particle_hole_representation` följa det format som beskrivs i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8cf31-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="8cf31-172">Ett-Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="8cf31-173">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-173">This section is normative.</span></span>

<span data-ttu-id="8cf31-174">Egenskapen `one_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd vars index är två heltal och vars värden är tal.</span><span class="sxs-lookup"><span data-stu-id="8cf31-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="8cf31-175">Varje term måste innehålla index `[i, j]` där `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="8cf31-176">Lägg Detta återspeglar den symmetri som $h _ {H_} = {Ji} $ som är en följd av det faktum att Hamiltonian är Hermitian.</span><span class="sxs-lookup"><span data-stu-id="8cf31-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="8cf31-177">Exempel</span><span class="sxs-lookup"><span data-stu-id="8cf31-177">Example</span></span> ######

<span data-ttu-id="8cf31-178">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-178">This section is informative.</span></span>

<span data-ttu-id="8cf31-179">Följande kvantitet för sparse-matris representerar Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="8cf31-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="8cf31-180">Broombridge använder 1-baserad indexering.</span><span class="sxs-lookup"><span data-stu-id="8cf31-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="8cf31-181">Två Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="8cf31-182">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-182">This section is normative.</span></span>

<span data-ttu-id="8cf31-183">Egenskapen `two_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd med en ytterligare egenskap som kallas `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="8cf31-184">Varje element av värdet för `two_electron_integrals` måste ha fyra index.</span><span class="sxs-lookup"><span data-stu-id="8cf31-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="8cf31-185">Varje `two_electron_integrals`-egenskap måste ha en `index_convention`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="8cf31-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="8cf31-186">Värdet för egenskapen `index_convention` måste vara ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="8cf31-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="8cf31-187">Om värdet för `index_convention` är `mulliken`, och för varje element i mängden `two_electron_integrals` sparse-matris måste en parser som läser in ett Broombridge-dokument instansiera en Hamiltonian-term som är lika med $h Electron _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , där $i $, $j $, $k $, och $l $ måste vara heltal i intervallet från 1 till det antal electrons som anges av egenskapen `n_electrons` för objektet integral, och där $h _ {i, j, k, l} $ är element `[i, j, k, l, h(i, j, k, l)]` för antalet sparse-matriser.</span><span class="sxs-lookup"><span data-stu-id="8cf31-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="8cf31-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="8cf31-188">Symmetries</span></span> ######

<span data-ttu-id="8cf31-189">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-189">This section is normative.</span></span>

<span data-ttu-id="8cf31-190">Om egenskapen `index_convention` för ett `two_electron_integrals`-objekt är lika med `mulliken`, och om ett element med index `[i, j, k, l]` finns, får följande index inte förekomma om de inte är lika med `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="8cf31-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="8cf31-191">Eftersom `index_convention`-egenskapen är en null-optimerad artikelkvantitet, kan inga index upprepas på olika element.</span><span class="sxs-lookup"><span data-stu-id="8cf31-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="8cf31-192">I synnerhet, om ett element med index `[i, j, k, l]` finns, kan inget annat element ha dessa index.</span><span class="sxs-lookup"><span data-stu-id="8cf31-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="8cf31-193">Exempel</span><span class="sxs-lookup"><span data-stu-id="8cf31-193">Example</span></span> #######

<span data-ttu-id="8cf31-194">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-194">This section is informative.</span></span>

<span data-ttu-id="8cf31-195">Följande objekt anger Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="8cf31-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="8cf31-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} en\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="8cf31-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="8cf31-197">Partikel – håls representation av objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="8cf31-198">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-198">This section is normative.</span></span>

<span data-ttu-id="8cf31-199">Objektet partikel – håls representation anger att de integraler som lagras definieras med avseende på partikel håls ställningen, där Annihilation-operatörerna beskriver excitations bort från det referens tillstånd som används, till exempel en Hartree – Fock-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="8cf31-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="8cf31-200">Objektet är valfritt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="8cf31-201">Om objektet inte anges, ska Hamiltonian tolkas som ej angivet i partikel-håls-representation.</span><span class="sxs-lookup"><span data-stu-id="8cf31-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="8cf31-202">Om värdet för `particle_hole_representation`, måste värdet för vara ett objekt av sparse-arrayelement vars index är fyra heltal och vars värden är ett tal och en sträng.</span><span class="sxs-lookup"><span data-stu-id="8cf31-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="8cf31-203">Sträng delen av värdet för varje element får bara innehålla de tecken `'+'` och `'-'` som anger om en viss faktor i termen är en skapande-eller Annihilation-operator i partikel-håls-representationen.</span><span class="sxs-lookup"><span data-stu-id="8cf31-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="8cf31-204">Till exempel `"-+++"` samverkar till ett hål som skapas på platsen $i $ och partiklar som skapas på platser $j, k $ och $l $.</span><span class="sxs-lookup"><span data-stu-id="8cf31-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf31-205">Eftersom värdet för `particle_hole_representation` är ett objekt av renulled array Quantity måste `unit`-och `format`-egenskaperna anges.</span><span class="sxs-lookup"><span data-stu-id="8cf31-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="8cf31-206">Godkända enheter är listade i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="8cf31-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="8cf31-207">Egenskapen `format` är obligatorisk och anger om Hamiltonian-koefficienterna anges som en kompakt eller sparse-matris.</span><span class="sxs-lookup"><span data-stu-id="8cf31-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="8cf31-208">I den aktuella versionen stöds endast sparse-matriser, med tolkningen att alla ospecificerade element är $0 $, men framtida versioner kan lägga till stöd för ytterligare värden för egenskapen `format`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="8cf31-209">Avsnittet inledande tillstånd</span><span class="sxs-lookup"><span data-stu-id="8cf31-209">Initial State Section</span></span> ###

<span data-ttu-id="8cf31-210">Initial_state_suggestion-objektet anger inledande Quantum-tillstånd för den angivna Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8cf31-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="8cf31-211">Objektet måste vara en matris med JSON-`state` objekt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="8cf31-212">Tillstånds objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-212">State object</span></span> ####

<span data-ttu-id="8cf31-213">Varje tillstånd representerar en superposition av upptagna banor.</span><span class="sxs-lookup"><span data-stu-id="8cf31-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="8cf31-214">Varje tillstånds objekt måste ha en `label`-egenskap som innehåller en sträng.</span><span class="sxs-lookup"><span data-stu-id="8cf31-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="8cf31-215">Varje tillstånds objekt måste ha en `superposition`-egenskap som innehåller en matris med bas tillstånd och deras normaliserade amplituder.</span><span class="sxs-lookup"><span data-stu-id="8cf31-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="8cf31-216">Till exempel är de initiala tillstånden $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ representeras av</span><span class="sxs-lookup"><span data-stu-id="8cf31-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="8cf31-217">Bas uppsättnings objekt</span><span class="sxs-lookup"><span data-stu-id="8cf31-217">Basis Set Object</span></span> ####

<span data-ttu-id="8cf31-218">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-218">This section is normative.</span></span>

<span data-ttu-id="8cf31-219">Varje heltals uppsättnings objekt kan ha en `basis_set`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="8cf31-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="8cf31-220">Om den är tillgänglig måste värdet för egenskapen `basis_set` vara ett objekt med två egenskaper `type` och `name`.</span><span class="sxs-lookup"><span data-stu-id="8cf31-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="8cf31-221">Bas funktionerna som identifieras av värdet för egenskapen `basis_set` måste vara Real-värde.</span><span class="sxs-lookup"><span data-stu-id="8cf31-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf31-222">Antagandet om att alla bas funktioner är verkliga värden kan vara avslappnad i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="8cf31-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="8cf31-223">Tabeller och listor</span><span class="sxs-lookup"><span data-stu-id="8cf31-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="8cf31-224">Tabell 1.</span><span class="sxs-lookup"><span data-stu-id="8cf31-224">Table 1.</span></span> <span data-ttu-id="8cf31-225">Tillåtna fysiska enheter</span><span class="sxs-lookup"><span data-stu-id="8cf31-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="8cf31-226">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-226">This section is normative.</span></span>

<span data-ttu-id="8cf31-227">En sträng som anger en enhet måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="8cf31-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="8cf31-228">Tolkare och producenter måste behandla följande enkla antal objekt som likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="8cf31-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="8cf31-229">Tabell 2.</span><span class="sxs-lookup"><span data-stu-id="8cf31-229">Table 2.</span></span> <span data-ttu-id="8cf31-230">Tillåtna index konventioner</span><span class="sxs-lookup"><span data-stu-id="8cf31-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="8cf31-231">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-231">This section is normative.</span></span>

<span data-ttu-id="8cf31-232">En sträng som anger en index konvention måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="8cf31-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="8cf31-233">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-233">This section is informative.</span></span>

<span data-ttu-id="8cf31-234">Ytterligare index konventioner kan införas i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="8cf31-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="8cf31-235">Tolkning av index konventioner</span><span class="sxs-lookup"><span data-stu-id="8cf31-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="8cf31-236">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="8cf31-236">This section is informative.</span></span>
