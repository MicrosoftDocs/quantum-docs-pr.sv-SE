---
title: Broombridge schema specifikation (ver 0,1)
description: Information om specifikationerna för Broombridge Quantum kemi schema v 0,1 för Microsoft Quantum kemi-biblioteket.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: b99c90c434958f7b04712580789b203766cd084d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835748"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="60f37-103">Broombridge-specifikation v 0,1</span><span class="sxs-lookup"><span data-stu-id="60f37-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="60f37-104">Nyckelorden "måste", "måste", "krävs", ",", ",", ",", "ska inte", "ska inte", "rekommenderas", "maj" och "valfritt" i det här dokumentet tolkas enligt beskrivningen i [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="60f37-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="60f37-105">Eventuella marginaler med rubrikerna "anmärkning", "INFORMATION" eller "varning" är informativa.</span><span class="sxs-lookup"><span data-stu-id="60f37-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="60f37-106">Introduktion</span><span class="sxs-lookup"><span data-stu-id="60f37-106">Introduction</span></span> ##

<span data-ttu-id="60f37-107">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-107">This section is informative.</span></span>

<span data-ttu-id="60f37-108">Broombridge-dokument är avsedda att kommunicera instanser av simulerings problem i Quantum kemi för bearbetning med Quantum-simulering och programmerings verktygs kedjor.</span><span class="sxs-lookup"><span data-stu-id="60f37-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="60f37-109">Serialisering</span><span class="sxs-lookup"><span data-stu-id="60f37-109">Serialization</span></span> ##

<span data-ttu-id="60f37-110">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-110">This section is normative.</span></span>

<span data-ttu-id="60f37-111">Ett Broombridge-dokument måste serialiseras som ett [YAML 1,2-dokument](http://yaml.org/spec/) som representerar ett JSON-objekt enligt beskrivningen i [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2,2.</span><span class="sxs-lookup"><span data-stu-id="60f37-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="60f37-112">Objektet som serialiseras till YAML måste ha en egenskap `"$schema"` vars värde är `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` och måste vara giltigt enligt JSON-schemat Draft-06-specifikationer [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="60f37-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="60f37-113">I resten av den här specifikationen refererar "Broombridge-objektet" till JSON-objektet som är avserialiserat från ett Broombridge YAML-dokument.</span><span class="sxs-lookup"><span data-stu-id="60f37-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="60f37-114">Om inget annat uttryckligen anges får objekten inte ha ytterligare egenskaper utöver de som anges uttryckligen i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="60f37-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="60f37-115">Ytterligare definitioner</span><span class="sxs-lookup"><span data-stu-id="60f37-115">Additional Definitions</span></span> ##

<span data-ttu-id="60f37-116">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="60f37-117">Antal objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-117">Quantity Objects</span></span> ###

<span data-ttu-id="60f37-118">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-118">This section is normative.</span></span>

<span data-ttu-id="60f37-119">Ett _Quantity_ -objekt är ett JSON-objekt och måste ha en egenskap `units` vars värde är ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="60f37-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="60f37-120">Ett objekt av en kvantitet är ett _enkelt antal objekt_ om det har en enda egenskap `value` utöver dess `units` egenskap.</span><span class="sxs-lookup"><span data-stu-id="60f37-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="60f37-121">Värdet för `value` egenskapen måste vara ett tal.</span><span class="sxs-lookup"><span data-stu-id="60f37-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="60f37-122">Ett objekt av en kvantitet är ett objekt med ett _begränsat antal_ om det innehåller egenskaperna `lower` och `upper` förutom dess `units` egenskap.</span><span class="sxs-lookup"><span data-stu-id="60f37-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="60f37-123">Värdena för `lower` `upper` egenskaperna och måste vara siffror.</span><span class="sxs-lookup"><span data-stu-id="60f37-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="60f37-124">Ett objekt med en begränsad kvantitet kan ha en egenskap `value` vars värde är ett tal.</span><span class="sxs-lookup"><span data-stu-id="60f37-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="60f37-125">Ett Quantity-objekt är ett objekt av reserverad _array-kvantitet_ om det har egenskapen `format` och en egenskap `values` förutom `units` egenskapen.</span><span class="sxs-lookup"><span data-stu-id="60f37-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="60f37-126">Värdet för `format` måste vara strängen `sparse` .</span><span class="sxs-lookup"><span data-stu-id="60f37-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="60f37-127">Värdet för `values` egenskapen måste vara en matris.</span><span class="sxs-lookup"><span data-stu-id="60f37-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="60f37-128">Varje-element i `values` måste vara en matris som representerar index och värde för den glesa mat ris mängden.</span><span class="sxs-lookup"><span data-stu-id="60f37-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="60f37-129">Indexen för varje element i ett objekt med sparse-kvantitet måste vara unika för hela objektet för renulled array Quantity.</span><span class="sxs-lookup"><span data-stu-id="60f37-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="60f37-130">Om det finns ett index med värdet för `0` måste en parser behandla objektet null-optimerad array-kvantitet identiskt med ett objekt av sparse-kvantitet för matriser där indexet inte finns alls.</span><span class="sxs-lookup"><span data-stu-id="60f37-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="60f37-131">Ett objekt av en kvantitet måste antingen vara</span><span class="sxs-lookup"><span data-stu-id="60f37-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="60f37-132">ett enkelt antal objekt,</span><span class="sxs-lookup"><span data-stu-id="60f37-132">a simple quantity object,</span></span>
- <span data-ttu-id="60f37-133">ett objekt med ett begränsat antal eller</span><span class="sxs-lookup"><span data-stu-id="60f37-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="60f37-134">ett kvantitets objekt för sparse-matris.</span><span class="sxs-lookup"><span data-stu-id="60f37-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="60f37-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="60f37-135">Examples</span></span> ###

<span data-ttu-id="60f37-136">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-136">This section is informative.</span></span>

<span data-ttu-id="60f37-137">En enkel kvantitet som representerar $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="60f37-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="60f37-138">En begränsad kvantitet som representerar en enhetlig distribution under intervallet $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="60f37-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="60f37-139">Följande är en null-optimerad mat ris mängd med ett element som `[1, 2]` är lika med `hello` och ett element som `[3, 4]` är lika med `world` :</span><span class="sxs-lookup"><span data-stu-id="60f37-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="60f37-140">Format avsnitt</span><span class="sxs-lookup"><span data-stu-id="60f37-140">Format Section</span></span> ##

<span data-ttu-id="60f37-141">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-141">This section is normative.</span></span>

<span data-ttu-id="60f37-142">Broombridge-objektet måste ha en egenskap `format` vars värde är ett JSON-objekt med en egenskap som kallas `version` .</span><span class="sxs-lookup"><span data-stu-id="60f37-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="60f37-143">`version`Egenskapen måste ha värdet `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="60f37-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="60f37-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="60f37-144">Example</span></span> ###

<span data-ttu-id="60f37-145">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="60f37-146">Avsnittet integral uppsättningar</span><span class="sxs-lookup"><span data-stu-id="60f37-146">Integral Sets Section</span></span> ##

<span data-ttu-id="60f37-147">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-147">This section is normative.</span></span>

<span data-ttu-id="60f37-148">Broombridge-objektet måste ha en egenskap `integral_sets` vars värde är en JSON-matris.</span><span class="sxs-lookup"><span data-stu-id="60f37-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="60f37-149">Varje objekt i `integral_sets` egenskapens värde måste vara ett JSON-objekt som beskriver en uppsättning integraler, enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="60f37-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="60f37-150">I resten av det här avsnittet refererar termen "Integral uppsättnings objekt" till ett objekt i värdet för `integral_sets` egenskapen för Broombridge-objektet.</span><span class="sxs-lookup"><span data-stu-id="60f37-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="60f37-151">Varje heltals uppsättnings objekt måste ha en egenskap `metadata` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="60f37-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="60f37-152">Värdet för `metadata` kan vara det tomma JSON-objektet (det vill säga `{}` ) eller innehålla ytterligare egenskaper som definierats av Implementeraren.</span><span class="sxs-lookup"><span data-stu-id="60f37-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="60f37-153">Avsnittet Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="60f37-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="60f37-154">Översikt</span><span class="sxs-lookup"><span data-stu-id="60f37-154">Overview</span></span> ####

<span data-ttu-id="60f37-155">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-155">This section is informative.</span></span>

<span data-ttu-id="60f37-156">`hamiltonian`Egenskapen för varje heltals uppsättnings objekt beskriver Hamiltonian för ett visst Quantum kemi-problem genom att visa en lista med en och två Body-termer som sparse-matriser med reella tal.</span><span class="sxs-lookup"><span data-stu-id="60f37-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="60f37-157">Hamiltonian-operatörer som beskrivs av varje heltals uppsättnings objekt tar formuläret</span><span class="sxs-lookup"><span data-stu-id="60f37-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="60f37-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ \} per timme a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="60f37-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="60f37-159">här $h _ {ijkl} = (till och med | kl) $ i Mulliken-konventionen.</span><span class="sxs-lookup"><span data-stu-id="60f37-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="60f37-160">För tydlighetens skull är en-Electron-termen</span><span class="sxs-lookup"><span data-stu-id="60f37-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="60f37-161">$ $ h_ {\int} = {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="60f37-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="60f37-162">och två-Electron-termen är</span><span class="sxs-lookup"><span data-stu-id="60f37-162">and the two-electron term is</span></span>

<span data-ttu-id="60f37-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="60f37-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="60f37-164">Som anges i beskrivningen av [ `basis_set` egenskapen](#basis-set-object) för varje element i `integral_sets` egenskapen, förutsätter vi ytterligare att de bas funktioner som används är Real-värde.</span><span class="sxs-lookup"><span data-stu-id="60f37-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="60f37-165">Detta gör att vi kan använda följande symmetries mellan villkoren för att komprimera representationen av Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="60f37-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="60f37-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="60f37-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="60f37-167">Innehåll</span><span class="sxs-lookup"><span data-stu-id="60f37-167">Contents</span></span> ####

<span data-ttu-id="60f37-168">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-168">This section is normative.</span></span>

<span data-ttu-id="60f37-169">Varje heltals uppsättning måste ha en egenskap `hamiltonian` vars värde är ett JSON-objekt.</span><span class="sxs-lookup"><span data-stu-id="60f37-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="60f37-170">Värdet för `hamiltonian` egenskapen kallas för ett Hamiltonian-objekt och måste ha egenskaperna `one_electron_integrals` och `two_electron_integrals` enligt beskrivningen i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="60f37-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="60f37-171">Ett Hamiltonian-objekt kan också ha en egenskap `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="60f37-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="60f37-172">Om det finns något måste värdet för `particle_hole_representation` följa det format som beskrivs i resten av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="60f37-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="60f37-173">Ett-Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="60f37-174">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-174">This section is normative.</span></span>

<span data-ttu-id="60f37-175">`one_electron_integrals`Egenskapen för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd vars index är två heltal och vars värden är tal.</span><span class="sxs-lookup"><span data-stu-id="60f37-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="60f37-176">Varje term måste innehålla index `[i, j]` där `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="60f37-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="60f37-177">Lägg Detta återspeglar den symmetri som $h _ {Ji} = h_ {} $, vilket är en följd av det faktum att Hamiltonian är Hermitian.</span><span class="sxs-lookup"><span data-stu-id="60f37-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="60f37-178">Exempel</span><span class="sxs-lookup"><span data-stu-id="60f37-178">Example</span></span> ######

<span data-ttu-id="60f37-179">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-179">This section is informative.</span></span>

<span data-ttu-id="60f37-180">Följande kvantitet för sparse-matris representerar Hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="60f37-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="60f37-181">Broombridge använder 1-baserad indexering.</span><span class="sxs-lookup"><span data-stu-id="60f37-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="60f37-182">Två Electron integraler-objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="60f37-183">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-183">This section is normative.</span></span>

<span data-ttu-id="60f37-184">`two_electron_integrals`Egenskapen för Hamiltonian-objektet måste vara en null-optimerad mat ris mängd med en ytterligare egenskap som kallas `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="60f37-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="60f37-185">Varje element av värdet i `two_electron_integrals` måste ha fyra index.</span><span class="sxs-lookup"><span data-stu-id="60f37-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="60f37-186">Varje `two_electron_integrals` egenskap måste ha en `index_convention` egenskap.</span><span class="sxs-lookup"><span data-stu-id="60f37-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="60f37-187">Värdet för `index_convention` egenskapen måste vara ett av de tillåtna värdena som anges i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="60f37-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="60f37-188">Om värdet för `index_convention` är `mulliken` , `two_electron_integrals` måste en parser som läser in ett Broombridge-dokument instansiera en Hamiltonian-term som är lika med Electron-$h operatorn _ {i, j, för varje element i mängden sparse-matris k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, där $i $, $j $, $k $ och $l $ måste vara heltal i intervallet från 1 till det antal electrons som anges av `n_electrons` egenskapen för objektet integral, och där $h _ {i, j, k, l} $ är elementet `[i, j, k, l, h(i, j, k, l)]` för antalet sparse-matriser.</span><span class="sxs-lookup"><span data-stu-id="60f37-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="60f37-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="60f37-189">Symmetries</span></span> ######

<span data-ttu-id="60f37-190">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-190">This section is normative.</span></span>

<span data-ttu-id="60f37-191">Om `index_convention` egenskapen för ett `two_electron_integrals` objekt är lika med `mulliken` , och om ett element med index finns `[i, j, k, l]` , får inte följande index förekomma, om de inte är lika med `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="60f37-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="60f37-192">Eftersom `index_convention` egenskapen är ett objekt med sparse-kvantitet kan inga index upprepas på olika element.</span><span class="sxs-lookup"><span data-stu-id="60f37-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="60f37-193">I synnerhet, om ett element med index finns `[i, j, k, l]` , kan inget annat element ha dessa index.</span><span class="sxs-lookup"><span data-stu-id="60f37-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="60f37-194">Exempel</span><span class="sxs-lookup"><span data-stu-id="60f37-194">Example</span></span> #######

<span data-ttu-id="60f37-195">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-195">This section is informative.</span></span>

<span data-ttu-id="60f37-196">Följande objekt anger Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="60f37-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="60f37-197">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="60f37-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="60f37-198">Partikel – håls representation av objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="60f37-199">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-199">This section is normative.</span></span>

<span data-ttu-id="60f37-200">Objektet partikel – håls representation anger att de integraler som lagras är definierade med avseende på partikel håls ställningen, där Annihilation-operatörerna beskriver excitations bort från det referens tillstånd som används, t. ex. ett Hartree – Fock tillstånd.</span><span class="sxs-lookup"><span data-stu-id="60f37-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="60f37-201">Objektet är valfritt.</span><span class="sxs-lookup"><span data-stu-id="60f37-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="60f37-202">Om objektet inte anges, ska Hamiltonian tolkas som ej angivet i partikel-håls-representation.</span><span class="sxs-lookup"><span data-stu-id="60f37-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="60f37-203">Om det finns `particle_hole_representation` ett måste värdet för vara ett objekt av null-optimerade matriser vars index är fyra heltal och vars värden är ett tal och en sträng.</span><span class="sxs-lookup"><span data-stu-id="60f37-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="60f37-204">Sträng delen av värdet för varje element får bara innehålla de tecken `'+'` och `'-'` som anger om en viss faktor i termen är en skapande-eller Annihilation-operator i partikel-håls-representationen.</span><span class="sxs-lookup"><span data-stu-id="60f37-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="60f37-205">Till exempel `"-+++"` samverkar ett hål som skapas på platsen $i $ och partiklar som skapas på platserna $j, k $ och $l $.</span><span class="sxs-lookup"><span data-stu-id="60f37-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="60f37-206">Eftersom värdet för `particle_hole_representation` är ett objekt av renulled array Quantity `unit` måste-och- `format` egenskaperna anges.</span><span class="sxs-lookup"><span data-stu-id="60f37-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="60f37-207">Godkända enheter är listade i tabell 1.</span><span class="sxs-lookup"><span data-stu-id="60f37-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="60f37-208">`format`Egenskapen är obligatorisk och anger om Hamiltonian-koefficienter anges som en kompakt eller sparse-matris.</span><span class="sxs-lookup"><span data-stu-id="60f37-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="60f37-209">I den aktuella versionen stöds endast sparse-matriser, med tolkningen att alla ospecificerade element är $0 $, men framtida versioner kan lägga till stöd för ytterligare värden för `format` egenskapen.</span><span class="sxs-lookup"><span data-stu-id="60f37-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="60f37-210">Avsnittet inledande tillstånd</span><span class="sxs-lookup"><span data-stu-id="60f37-210">Initial State Section</span></span> ###

<span data-ttu-id="60f37-211">Initial_state_suggestion-objektet anger inledande Quantum-tillstånd för det angivna Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="60f37-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="60f37-212">Objektet måste vara en matris med JSON- `state` objekt.</span><span class="sxs-lookup"><span data-stu-id="60f37-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="60f37-213">Tillstånds objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-213">State object</span></span> ####

<span data-ttu-id="60f37-214">Varje tillstånd representerar en superposition av upptagna banor.</span><span class="sxs-lookup"><span data-stu-id="60f37-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="60f37-215">Varje tillstånds objekt måste ha en `label` egenskap som innehåller en sträng.</span><span class="sxs-lookup"><span data-stu-id="60f37-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="60f37-216">Varje tillstånds objekt måste ha en `superposition` egenskap som innehåller en matris med bas tillstånd och deras normaliserade amplituder.</span><span class="sxs-lookup"><span data-stu-id="60f37-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="60f37-217">Till exempel är de första tillstånden $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} $ $ representeras av</span><span class="sxs-lookup"><span data-stu-id="60f37-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="60f37-218">Bas uppsättnings objekt</span><span class="sxs-lookup"><span data-stu-id="60f37-218">Basis Set Object</span></span> ####

<span data-ttu-id="60f37-219">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-219">This section is normative.</span></span>

<span data-ttu-id="60f37-220">Varje heltals uppsättnings objekt kan ha en `basis_set` egenskap.</span><span class="sxs-lookup"><span data-stu-id="60f37-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="60f37-221">Om värdet för egenskapen finns måste det `basis_set` vara ett objekt med två egenskaper, `type` och `name` .</span><span class="sxs-lookup"><span data-stu-id="60f37-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="60f37-222">Bas funktionerna som identifieras av `basis_set` egenskapens värde måste vara Real-värde.</span><span class="sxs-lookup"><span data-stu-id="60f37-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="60f37-223">Antagandet om att alla bas funktioner är verkliga värden kan vara avslappnad i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="60f37-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="60f37-224">Tabeller och listor</span><span class="sxs-lookup"><span data-stu-id="60f37-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="60f37-225">Tabell 1.</span><span class="sxs-lookup"><span data-stu-id="60f37-225">Table 1.</span></span> <span data-ttu-id="60f37-226">Tillåtna fysiska enheter</span><span class="sxs-lookup"><span data-stu-id="60f37-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="60f37-227">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-227">This section is normative.</span></span>

<span data-ttu-id="60f37-228">En sträng som anger en enhet måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="60f37-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="60f37-229">Tolkare och producenter måste behandla följande enkla antal objekt som likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="60f37-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="60f37-230">Tabell 2.</span><span class="sxs-lookup"><span data-stu-id="60f37-230">Table 2.</span></span> <span data-ttu-id="60f37-231">Tillåtna index konventioner</span><span class="sxs-lookup"><span data-stu-id="60f37-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="60f37-232">Det här avsnittet är normativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-232">This section is normative.</span></span>

<span data-ttu-id="60f37-233">En sträng som anger en index konvention måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="60f37-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="60f37-234">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-234">This section is informative.</span></span>

<span data-ttu-id="60f37-235">Ytterligare index konventioner kan införas i framtida versioner av den här specifikationen.</span><span class="sxs-lookup"><span data-stu-id="60f37-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="60f37-236">Tolkning av index konventioner</span><span class="sxs-lookup"><span data-stu-id="60f37-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="60f37-237">Det här avsnittet är informativt.</span><span class="sxs-lookup"><span data-stu-id="60f37-237">This section is informative.</span></span>
