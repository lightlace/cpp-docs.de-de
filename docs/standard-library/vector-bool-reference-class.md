---
title: vector&lt;bool&gt;::reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- vector/vector<bool>::reference
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
ms.openlocfilehash: 65bfc91cf5dc79fb1e5151a6f62c394b4579883b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453213"
---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference-Klasse

Die `vector<bool>::reference`-Klasse ist eine Proxyklasse, die von der [vector\<bool>-Klasse](../standard-library/vector-bool-class.md) bereitgestellt wird, um `bool&` zu simulieren.

## <a name="remarks"></a>Hinweise

Ein simulierter Verweis ist erforderlich, da C++ systemintern keine direkten Verweise auf Bits zulässt. `vector<bool>` verwendet nur ein Bit pro Element, auf das anhand dieser Proxyklasse verwiesen werden kann. Allerdings ist die Verweissimulation nicht vollständig, da bestimmte Zuweisungen ungültig sind. Da die Adresse des `vector<bool>::reference` Objekts beispielsweise nicht akzeptiert werden kann, ist der folgende Code, der verwendet `vector<bool>::operator&` werden soll, nicht korrekt:

```cpp
vector<bool> vb;
// ...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[flip](../standard-library/vector-bool-reference-flip.md)|Kehrt den booleschen Wert eines Vektorelements um.|
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Stellt eine implizite Konvertierung von `vector<bool>::reference` in **bool**bereit.|
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|Weist einen booleschen Wert einem Bit zu oder weist den Wert, der in einem Element enthalten ist, auf das verwiesen wird, einem Bit zu.|

## <a name="requirements"></a>Anforderungen

**Header**: \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<vector>](../standard-library/vector.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
