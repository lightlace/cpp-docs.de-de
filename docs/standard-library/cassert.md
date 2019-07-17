---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 14dda03e835ec411013b2d827bd1ccaa77f8982e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245016"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Schließt den Standard C-bibliotheksheader \<assert.h > und fügt die verknüpften Namen zum die `std` Namespace. Einschließen dieses Headers wird sichergestellt, dass die Namen deklariert, mit externer Bindung im Standard C-bibliotheksheader, in deklariert werden der `std` Namespace.

> [!NOTE]
> \<Assert.h > definiert nicht den `static_assert` Makro.

## <a name="syntax"></a>Syntax

```cpp
#include <cassert>
```

## <a name="macros"></a>Makros

```cpp
#define assert(E)
```

### <a name="remarks"></a>Hinweise

`assert(E)` ist nur Konstanten, wenn NDEBUG definiert ist, in denen `assert` zuletzt definiert oder neu definiert, oder *E* konvertiert "bool" ergibt **"true"** .

## <a name="see-also"></a>Siehe auch

[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
