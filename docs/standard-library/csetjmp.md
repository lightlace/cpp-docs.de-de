---
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: 3eba0b4521c0abf414de1416f02039a67c896644
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244508"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

Schließt den Standard-C-Bibliotheksheader \<setjmp.h> ein und fügt die verknüpften Namen zum `std`-Namespace hinzu

## <a name="syntax"></a>Syntax

```cpp
#include <csetjmp>

using jmp_buf = see below;
```

## <a name="functions"></a>Funktionen

```cpp
[[noreturn]] void longjmp(jmp_buf env, int val);
```

## <a name="macros"></a>Makros

```cpp
#define setjmp(env)
```

## <a name="remarks"></a>Hinweise

Durch Einschließen dieses Headers wird sichergestellt, dass die mit externer Bindung im Standard-C-Bibliotheksheader deklarierten Namen im `std`-Namespace deklariert werden.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
