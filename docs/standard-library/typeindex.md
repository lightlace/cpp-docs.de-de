---
title: '&lt;typeindex&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 189fb7cd3757a3f71a50badc682b7b4db611b4e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
