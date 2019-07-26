---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 58ebd91fb4fa32cf31d2c49429d0445b92fe0c82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449907"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Schließt den C-Standard Bibliotheks \<Header Assert. h > ein und fügt die verknüpften `std` Namen zum-Namespace hinzu. Durch einschließen dieses Headers wird sichergestellt, dass die mit externer Verknüpfung im C-Standard Bibliotheks Header deklarierten `std` Namen im-Namespace deklariert werden.

> [!NOTE]
> \<Assert. h > das `static_assert` Makro nicht definiert.

## <a name="syntax"></a>Syntax

```cpp
#include <cassert>
```

## <a name="macros"></a>Makros

```cpp
#define assert(E)
```

### <a name="remarks"></a>Hinweise

`assert(E)`ist nur konstant, wenn NDEBUG definiert ist, `assert` wo zuletzt definiert oder neu definiert wurde oder *E* in bool konvertiert in " **true**" ausgewertet wird.

## <a name="see-also"></a>Siehe auch

[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
