---
title: vector&lt;bool&gt;::reference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector/vector<bool>::reference
dev_langs:
- C++
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c87975e0b27934d091e896867620011a51b78d52
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966523"
---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference-Klasse

Die `vector<bool>::reference`-Klasse ist eine Proxyklasse, die von der [vector\<bool>-Klasse](../standard-library/vector-bool-class.md) bereitgestellt wird, um `bool&` zu simulieren.

## <a name="remarks"></a>Hinweise

Ein simulierter Verweis ist erforderlich, da C++ systemintern keine direkten Verweise auf Bits zulässt. `vector<bool>` verwendet nur ein Bit pro Element, auf das anhand dieser Proxyklasse verwiesen werden kann. Allerdings ist die Verweissimulation nicht vollständig, da bestimmte Zuweisungen ungültig sind. Da die Adresse des `vector<bool>::reference`-Objekts beispielsweise nicht akzeptiert werden kann, ist der folgende Code, der [vector\<bool>::operator&#91;&#93;](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) verwendet, nicht richtig:

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
