---
title: vector&lt;bool&gt;::reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- vector/vector<bool>::reference
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
ms.openlocfilehash: 7930c1cd93cd05a752d4997b9480c766ee26bd99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471499"
---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference-Klasse

Die `vector<bool>::reference`-Klasse ist eine Proxyklasse, die von der [vector\<bool>-Klasse](../standard-library/vector-bool-class.md) bereitgestellt wird, um `bool&` zu simulieren.

## <a name="remarks"></a>Hinweise

Ein simulierter Verweis ist erforderlich, da C++ systemintern keine direkten Verweise auf Bits zulässt. `vector<bool>` verwendet nur ein Bit pro Element, auf das anhand dieser Proxyklasse verwiesen werden kann. Allerdings ist die Verweissimulation nicht vollständig, da bestimmte Zuweisungen ungültig sind. Z. B. weil die Adresse der `vector<bool>::reference` Objekt kann nicht ausgeführt werden, wird den folgenden Code, der versucht, verwenden Sie `vector<bool>::operator&` ist nicht korrekt:

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
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Stellt eine implizite Konvertierung von `vector<bool>::reference` zu **"bool"**.|
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|Weist einen booleschen Wert einem Bit zu oder weist den Wert, der in einem Element enthalten ist, auf das verwiesen wird, einem Bit zu.|

## <a name="requirements"></a>Anforderungen

**Header**: \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<vector>](../standard-library/vector.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
