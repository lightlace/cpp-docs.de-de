---
title: lock::operator==
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
ms.openlocfilehash: 2e7e78f5d03074058dadd969f150855f305cf85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647862"
---
# <a name="lockoperator"></a>lock::operator==

Equality-Operator.

## <a name="syntax"></a>Syntax

```
template<class T> bool operator==(
   T t
);
```

#### <a name="parameters"></a>Parameter

*t*<br/>
Das Objekt auf Gleichheit verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn `t` entspricht das Sperrobjekt und **"false"** andernfalls.

## <a name="example"></a>Beispiel

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\lock.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[lock-Members](../dotnet/lock-members.md)<br/>
[lock::operator!=](../dotnet/lock-operator-inequality.md)