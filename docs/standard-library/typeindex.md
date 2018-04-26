---
title: '&lt;typeindex&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63eae51554003a2c12caf2522a912adc9b96ec02
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
