---
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: 237356a0862ec3fc591264b482b23e62ef2c51cb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455061"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

Verwenden Sie den Standardheader \<typeindex>, um eine Klasse und eine Funktion zu definieren, die die Indizierung von Objekten der Klasse [type_info](../cpp/type-info-class.md) unterstützen.

## <a name="syntax"></a>Syntax

```cpp
#include <typeindex>
```

## <a name="remarks"></a>Hinweise

Die [hash-Struktur](../standard-library/hash-structure.md) definiert eine `hash function`, die geeignet ist, um Werte des Typs [type_index](../standard-library/type-index-class.md) einer Verteilung von Indexwerten zuzuordnen.

Die `type_index`-Klasse umschließt einen Zeiger auf ein `type_info`-Objekt zur Unterstützung der Indizierung.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
