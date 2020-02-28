---
title: Broombridge schema specifikation (ver 0,2)
description: Information om specifikationerna för Broombridge Quantum kemi schema v 0,2 för Microsoft Quantum kemi-biblioteket.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907281"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="db33a-103">Broombridge-specifikation v 0,2</span><span class="sxs-lookup"><span data-stu-id="db33a-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="db33a-104">Nyckelorden "måste", "måste", "krävs", ",", ",", ",", "ska inte", "ska inte", "rekommenderas", "maj" och "valfritt" i det här dokumentet tolkas enligt beskrivningen i [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="db33a-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="db33a-105">Eventuella marginaler med rubrikerna "anmärkning", "INFORMATION" eller "varning" är informativa.</span><span class="sxs-lookup"><span data-stu-id="db33a-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="db33a-106">Introduktion</span><span class="sxs-lookup"><span data-stu-id="db33a-106">Introduction</span></span> ##

<span data-ttu-id="db33a-107">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-107">This section is informative.</span></span>

<span data-ttu-id="db33a-108">Broombridge-dokument är avsedda att kommunicera instanser av simulerings problem i Quantum kemi för bearbetning med Quantum-simulering och programmerings verktygs kedjor.</span><span class="sxs-lookup"><span data-stu-id="db33a-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="db33a-109">Serialisering</span><span class="sxs-lookup"><span data-stu-id="db33a-109">Serialization</span></span> ##

<span data-ttu-id="db33a-110">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-110">This section is normative.</span></span>

<span data-ttu-id="db33a-111">Ett Broombridge-dokument måste serialiseras som ett [YAML 1,2-dokument](http://yaml.org/spec/) som representerar ett JSON-objekt enligt beskrivningen i [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2,2.</span><span class="sxs-lookup"><span data-stu-id="db33a-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="db33a-112">Objektet som serialiseras till YAML måste ha en egenskap `"$schema"` vars värde är `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`och måste vara giltigt enligt JSON-schemat Draft-06-specifikationer [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="db33a-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="db33a-113">I resten av den här specifikationen refererar "Broombridge-objektet" till JSON-objektet som är avserialiserat från ett Broombridge YAML-dokument.</span><span class="sxs-lookup"><span data-stu-id="db33a-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="db33a-114">Om inget annat uttryckligen anges får objekten inte ha ytterligare egenskaper utöver de som anges uttryckligen i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="db33a-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="db33a-115">Ytterligare definitioner</span><span class="sxs-lookup"><span data-stu-id="db33a-115">Additional Definitions</span></span> ##

<span data-ttu-id="db33a-116">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="db33a-117">Antal objekt</span><span class="sxs-lookup"><span data-stu-id="db33a-117">Quantity Objects</span></span> ###

<span data-ttu-id="db33a-118">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-118">This section is normative.</span></span>

<span data-ttu-id="db33a-119">Ett _Quantity_ -objekt är ett JSON-objekt och måste ha en egenskap `units` vars värde är ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="db33a-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="db33a-120">Ett objekt av en kvantitet är ett _enkelt antal objekt_ om det har en enda egenskap `value` förutom egenskapen `units`.</span><span class="sxs-lookup"><span data-stu-id="db33a-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="db33a-121">Värdet för egenskapen `value` måste vara ett tal.</span><span class="sxs-lookup"><span data-stu-id="db33a-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="db33a-122">Ett objekt av en kvantitet är ett _objekt med gränser_ om det innehåller egenskaperna `lower` och `upper` utöver dess `units`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="db33a-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="db33a-123">Värdena för `lower` och `upper` egenskaper måste vara siffror.</span><span class="sxs-lookup"><span data-stu-id="db33a-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="db33a-124">Ett objekt med en begränsad kvantitet kan ha en egenskap `value` vars värde är ett tal.</span><span class="sxs-lookup"><span data-stu-id="db33a-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="db33a-125">Ett Quantity-objekt är ett objekt av reserverad _array-kvantitet_ om det har egenskapen `format` och en egenskap `values` utöver dess `units`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="db33a-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="db33a-126">Värdet för `format` måste vara strängen `sparse`.</span><span class="sxs-lookup"><span data-stu-id="db33a-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="db33a-127">Värdet för egenskapen `values` måste vara en matris.</span><span class="sxs-lookup"><span data-stu-id="db33a-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="db33a-128">Varje element i `values` måste vara en matris som representerar index och värdet för antalet sparse-matriser.</span><span class="sxs-lookup"><span data-stu-id="db33a-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="db33a-129">Indexen för varje element i ett objekt med sparse-kvantitet måste vara unika för hela objektet för renulled array Quantity.</span><span class="sxs-lookup"><span data-stu-id="db33a-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="db33a-130">Om det finns ett index med värdet `0`måste en parser behandla objektet null-optimerad array-kvantitet identiskt med ett objekt av sparse-kvantitet för matriser där indexet inte finns alls.</span><span class="sxs-lookup"><span data-stu-id="db33a-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="db33a-131">Ett objekt av en kvantitet måste antingen vara</span><span class="sxs-lookup"><span data-stu-id="db33a-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="db33a-132">ett enkelt antal objekt,</span><span class="sxs-lookup"><span data-stu-id="db33a-132">a simple quantity object,</span></span>
- <span data-ttu-id="db33a-133">ett objekt med ett begränsat antal eller</span><span class="sxs-lookup"><span data-stu-id="db33a-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="db33a-134">ett kvantitets objekt för sparse-matris.</span><span class="sxs-lookup"><span data-stu-id="db33a-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="db33a-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="db33a-135">Examples</span></span> ###

<span data-ttu-id="db33a-136">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-136">This section is informative.</span></span>

<span data-ttu-id="db33a-137">En enkel kvantitet som representerar $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="db33a-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="db33a-138">En begränsad kvantitet som representerar en enhetlig distribution under intervallet $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="db33a-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="db33a-139">Följande är en null-optimerad mat ris mängd med ett element `[1, 2]` lika med `hello` och ett element `[3, 4]` lika med `world`:</span><span class="sxs-lookup"><span data-stu-id="db33a-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="db33a-140">Format avsnitt</span><span class="sxs-lookup"><span data-stu-id="db33a-140">Format Section</span></span> ##

<span data-ttu-id="db33a-141">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-141">This section is normative.</span></span>

<span data-ttu-id="db33a-142">Broombridge-objektet måste ha en egenskap `format` vars värde är ett JSON-objekt med en egenskap som kallas `version`.</span><span class="sxs-lookup"><span data-stu-id="db33a-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="db33a-143">Värdet `"0.2"`måste anges för egenskapen `version`.</span><span class="sxs-lookup"><span data-stu-id="db33a-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="db33a-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="db33a-144">Example</span></span> ###

<span data-ttu-id="db33a-145">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="db33a-146">Avsnittet problem Beskrivning</span><span class="sxs-lookup"><span data-stu-id="db33a-146">Problem Description Section</span></span> ##

<span data-ttu-id="db33a-147">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-147">This section is normative.</span></span>

<span data-ttu-id="db33a-148">Broombridge-objektet måste ha en egenskap `problem_description` vars värde är en JSON-matris.</span><span class="sxs-lookup"><span data-stu-id="db33a-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="db33a-149">Varje objekt i värdet för egenskapen `problem_description` måste vara ett JSON-objekt som beskriver en uppsättning integraler, enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="db33a-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="db33a-150">I resten av det här avsnittet hänvisar termen "problem beskrivnings objekt" till ett objekt i värdet för egenskapen `problem_description` i Broombridge-objektet.</span><span class="sxs-lookup"><span data-stu-id="db33a-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="db33a-151">Varje problem beskrivnings objekt måste ha en egenskap `metadata` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="db33a-152">Värdet för `metadata` kan vara det tomma JSON-objektet (det vill säga `{}`) eller kan innehålla ytterligare egenskaper som definierats av Implementeraren.</span><span class="sxs-lookup"><span data-stu-id="db33a-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="db33a-153">Avsnittet Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="db33a-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="db33a-154">Översikt</span><span class="sxs-lookup"><span data-stu-id="db33a-154">Overview</span></span> ####

<span data-ttu-id="db33a-155">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-155">This section is informative.</span></span>

<span data-ttu-id="db33a-156">Egenskapen `hamiltonian` för varje problem beskrivnings objekt beskriver Hamiltonian för ett visst Quantum kemi-problem genom att visa en lista med en och två Body-termer som sparse-matriser med reella tal.</span><span class="sxs-lookup"><span data-stu-id="db33a-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="db33a-157">Hamiltonian-operatörer som beskrivs av varje problem beskrivnings objekt tar formuläret</span><span class="sxs-lookup"><span data-stu-id="db33a-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="db33a-158">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} h\_\{\} a ^\{\dagger\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="db33a-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="db33a-159">här $h _ {ijkl} = (till och med | kl) $ i Mulliken-konventionen.</span><span class="sxs-lookup"><span data-stu-id="db33a-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="db33a-160">För tydlighetens skull är en-Electron-termen</span><span class="sxs-lookup"><span data-stu-id="db33a-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="db33a-161">$ $ h_ {\int} = {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="db33a-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="db33a-162">och två-Electron-termen är</span><span class="sxs-lookup"><span data-stu-id="db33a-162">and the two-electron term is</span></span>

<span data-ttu-id="db33a-163">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="db33a-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="db33a-164">Som anges i vår Beskrivning av [egenskapen`basis_set`](#basis-set-object) för varje element i egenskapen `integral_sets`, förutsätter vi ytterligare att de bas funktioner som används är Real-värde.</span><span class="sxs-lookup"><span data-stu-id="db33a-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="db33a-165">Detta gör att vi kan använda följande symmetries mellan villkoren för att komprimera representationen av Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="db33a-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="db33a-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="db33a-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="db33a-167">Innehåll</span><span class="sxs-lookup"><span data-stu-id="db33a-167">Contents</span></span> ####

<span data-ttu-id="db33a-168">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-168">This section is normative.</span></span>

<span data-ttu-id="db33a-169">Varje problem beskrivnings objekt måste ha en egenskap `hamiltonian` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="db33a-170">Värdet för egenskapen `hamiltonian` kallas för ett Hamiltonian-objekt och måste ha egenskaperna `one_electron_integrals` och `two_electron_integrals` enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="db33a-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="db33a-171">Varje problem beskrivnings objekt måste ha en egenskap `coulomb_repulsion` vars värde är ett enkelt antal objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="db33a-172">Varje problem beskrivnings objekt måste ha en egenskap `energy_offet` vars värde är ett enkelt antal objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="db33a-173">Lägg Värdena för `coulomb_repulsion` och `energy_offet` som läggs till tillsammans fångar identitets perioden för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="db33a-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="db33a-174">Ett-Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="db33a-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="db33a-175">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-175">This section is normative.</span></span>

<span data-ttu-id="db33a-176">Egenskapen `one_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd vars index är två heltal och vars värden är tal.</span><span class="sxs-lookup"><span data-stu-id="db33a-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="db33a-177">Varje term måste innehålla index `[i, j]` där `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="db33a-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="db33a-178">Lägg Detta återspeglar den symmetri som $h _ {Ji} = h_ {} $, vilket är en följd av det faktum att Hamiltonian är Hermitian.</span><span class="sxs-lookup"><span data-stu-id="db33a-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="db33a-179">Exempel</span><span class="sxs-lookup"><span data-stu-id="db33a-179">Example</span></span> ######

<span data-ttu-id="db33a-180">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-180">This section is informative.</span></span>

<span data-ttu-id="db33a-181">Följande kvantitet för sparse-matris representerar Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="db33a-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="db33a-182">Broombridge använder 1-baserad indexering.</span><span class="sxs-lookup"><span data-stu-id="db33a-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="db33a-183">Två Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="db33a-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="db33a-184">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-184">This section is normative.</span></span>

<span data-ttu-id="db33a-185">Egenskapen `two_electron_integrals` för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd med en ytterligare egenskap som kallas `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="db33a-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="db33a-186">Varje element av värdet för `two_electron_integrals` måste ha fyra index.</span><span class="sxs-lookup"><span data-stu-id="db33a-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="db33a-187">Varje `two_electron_integrals`-egenskap måste ha en `index_convention`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="db33a-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="db33a-188">Värdet för egenskapen `index_convention` måste vara ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="db33a-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="db33a-189">Om värdet för `index_convention` är `mulliken`måste en parser som läser in ett Broombridge-dokument instansiera en Hamiltonian-term som är lika med $h Electron _ {i, för varje element i mängden `two_electron_integrals` sparse-matrisen. j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, där $i $, $j $, $k $ och $l $ måste vara heltal av värde minst 1, och där $h _ {i, j, k, l} $ är element `[i, j, k, l, h(i, j, k, l)]` för antalet sparse-matriser.</span><span class="sxs-lookup"><span data-stu-id="db33a-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="db33a-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="db33a-190">Symmetries</span></span> ######

<span data-ttu-id="db33a-191">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-191">This section is normative.</span></span>

<span data-ttu-id="db33a-192">Om egenskapen `index_convention` för ett `two_electron_integrals`-objekt är lika med `mulliken`, och om ett element med index `[i, j, k, l]` finns, får följande index inte förekomma om de inte är lika med `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="db33a-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="db33a-193">Eftersom `index_convention`-egenskapen är en null-optimerad artikelkvantitet, kan inga index upprepas på olika element.</span><span class="sxs-lookup"><span data-stu-id="db33a-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="db33a-194">I synnerhet, om ett element med index `[i, j, k, l]` finns, kan inget annat element ha dessa index.</span><span class="sxs-lookup"><span data-stu-id="db33a-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="db33a-195">Exempel</span><span class="sxs-lookup"><span data-stu-id="db33a-195">Example</span></span> #######

<span data-ttu-id="db33a-196">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-196">This section is informative.</span></span>

<span data-ttu-id="db33a-197">Följande objekt anger Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="db33a-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="db33a-198">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 , \sigma} a ^ {\dagger}\_{2, \rho} a\_{1, \rho} en\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="db33a-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="db33a-199">Avsnittet inledande tillstånd</span><span class="sxs-lookup"><span data-stu-id="db33a-199">Initial State Section</span></span> ###

<span data-ttu-id="db33a-200">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-200">This section is normative.</span></span>

<span data-ttu-id="db33a-201">`initial_state_suggestion`-objektet vars värde är en JSON-matris anger inledande Quantum-lägen som är intressanta för den angivna Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="db33a-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="db33a-202">Varje objekt i värdet för egenskapen `initial_state_suggestion` måste vara ett JSON-objekt som beskriver ett Quantum-tillstånd, enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="db33a-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="db33a-203">I resten av det här avsnittet hänvisar termen "tillstånds objekt" till ett objekt i värdet för egenskapen `initial_state_suggestion` i Broombridge-objektet.</span><span class="sxs-lookup"><span data-stu-id="db33a-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="db33a-204">Tillstånds objekt</span><span class="sxs-lookup"><span data-stu-id="db33a-204">State object</span></span> ####

<span data-ttu-id="db33a-205">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-205">This section is normative.</span></span>

<span data-ttu-id="db33a-206">Varje tillstånds objekt måste ha en `label`-egenskap som innehåller en sträng.</span><span class="sxs-lookup"><span data-stu-id="db33a-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="db33a-207">Varje tillstånds objekt måste ha en `method`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="db33a-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="db33a-208">Värdet för egenskapen `method` måste vara ett av de tillåtna värdena som anges i tabell 3.</span><span class="sxs-lookup"><span data-stu-id="db33a-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="db33a-209">Varje tillstånds objekt kan ha en egenskap `energy` vars värde måste vara ett enkelt antal objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="db33a-210">Om värdet för egenskapen `method` är `sparse_multi_configurational`måste State-objektet ha en `superposition`-egenskap som innehåller en matris med bas tillstånd och deras normaliserade amplituder.</span><span class="sxs-lookup"><span data-stu-id="db33a-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="db33a-211">Till exempel är de första tillstånden $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0}, $ $ där $ \ket{E} $ har Energy $0,987-\textrm{Ha} $, representeras av</span><span class="sxs-lookup"><span data-stu-id="db33a-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="db33a-212">Om värdet för egenskapen `method` är `unitary_coupled_cluster`måste State-objektet ha en `cluster_operator`-egenskap vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="db33a-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="db33a-213">JSON-objektet måste ha en `reference_state`-egenskap vars värde är ett bas tillstånd.</span><span class="sxs-lookup"><span data-stu-id="db33a-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="db33a-214">JSON-objektet kan ha en `one_body_amplitudes`-egenskap vars värde är en matris med en-Body kluster operatörer och deras amplituder.</span><span class="sxs-lookup"><span data-stu-id="db33a-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="db33a-215">JSON-objektet kan ha en `two_body_amplitudes`-egenskap vars värde är en matris med två huvud kluster operatörer och deras amplitud.</span><span class="sxs-lookup"><span data-stu-id="db33a-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="db33a-216">innehåller en matris med bas tillstånd och deras normaliserade amplituder.</span><span class="sxs-lookup"><span data-stu-id="db33a-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="db33a-217">Till exempel tillstånd $ $ \ket{\text{Reference}} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="db33a-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="db33a-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="db33a-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="db33a-219">$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3, \uparrow}a\_{2, \downarrow} $ $ representeras av</span><span class="sxs-lookup"><span data-stu-id="db33a-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="db33a-220">Bas uppsättnings objekt</span><span class="sxs-lookup"><span data-stu-id="db33a-220">Basis Set Object</span></span> ####

<span data-ttu-id="db33a-221">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-221">This section is normative.</span></span>

<span data-ttu-id="db33a-222">Varje problem beskrivnings objekt kan ha en `basis_set`-egenskap.</span><span class="sxs-lookup"><span data-stu-id="db33a-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="db33a-223">Om den är tillgänglig måste värdet för egenskapen `basis_set` vara ett objekt med två egenskaper `type` och `name`.</span><span class="sxs-lookup"><span data-stu-id="db33a-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="db33a-224">Bas funktionerna som identifieras av värdet för egenskapen `basis_set` måste vara Real-värde.</span><span class="sxs-lookup"><span data-stu-id="db33a-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="db33a-225">Antagandet om att alla bas funktioner är verkliga värden kan vara avslappnad i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="db33a-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="db33a-226">Tabeller och listor</span><span class="sxs-lookup"><span data-stu-id="db33a-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="db33a-227">Tabell 1.</span><span class="sxs-lookup"><span data-stu-id="db33a-227">Table 1.</span></span> <span data-ttu-id="db33a-228">Tillåtna fysiska enheter</span><span class="sxs-lookup"><span data-stu-id="db33a-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="db33a-229">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-229">This section is normative.</span></span>

<span data-ttu-id="db33a-230">En sträng som anger en enhet måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="db33a-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="db33a-231">Tolkare och producenter måste behandla följande enkla antal objekt som likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="db33a-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="db33a-232">Tabell 2.</span><span class="sxs-lookup"><span data-stu-id="db33a-232">Table 2.</span></span> <span data-ttu-id="db33a-233">Tillåtna index konventioner</span><span class="sxs-lookup"><span data-stu-id="db33a-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="db33a-234">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-234">This section is normative.</span></span>

<span data-ttu-id="db33a-235">En sträng som anger en index konvention måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="db33a-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="db33a-236">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-236">This section is informative.</span></span>

<span data-ttu-id="db33a-237">Ytterligare index konventioner kan införas i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="db33a-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="db33a-238">Tolkning av index konventioner</span><span class="sxs-lookup"><span data-stu-id="db33a-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="db33a-239">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="db33a-240">Tabell 3.</span><span class="sxs-lookup"><span data-stu-id="db33a-240">Table 3.</span></span> <span data-ttu-id="db33a-241">Tillåtna tillstånds metoder</span><span class="sxs-lookup"><span data-stu-id="db33a-241">Allowed State methods</span></span> ###

<span data-ttu-id="db33a-242">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-242">This section is normative.</span></span>

<span data-ttu-id="db33a-243">En sträng som anger en tillstånds metod måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="db33a-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="db33a-244">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="db33a-244">This section is informative.</span></span>

<span data-ttu-id="db33a-245">Ytterligare tillstånds metoder kan införas i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="db33a-245">Additional state methods may be introduced in future versions of this specification.</span></span>
