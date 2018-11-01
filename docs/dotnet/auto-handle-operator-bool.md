---
title: auto_handle::operator bool
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- auto_handle.operator bool
- msclr.auto_handle.operator bool
- operator bool
- msclr::auto_handle::operator bool
- auto_handle::operator bool
helpviewer_keywords:
- auto_handle::operator bool
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
ms.openlocfilehash: 95a4b324194b2e1adf8cc9596f8e2440379e5a47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565944"
---
# <a name="autohandleoperator-bool"></a>auto_handle::operator bool

Operator für die Verwendung von `auto_handle` in einem bedingten Ausdruck.

## <a name="syntax"></a>Syntax

```
operator bool();
```

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn das umschlossene Objekt gültig ist. **"false"** andernfalls.

## <a name="remarks"></a>Hinweise

Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als **"bool"** , da es in einen ganzzahligen Typ konvertiert werden kann.

## <a name="example"></a>Beispiel

```
// msl_auto_handle_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1;
   auto_handle<String> s2 = "hi";
   if ( s1 ) Console::WriteLine( "s1 is valid" );
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );
   if ( s2 ) Console::WriteLine( "s2 is valid" );
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );
   s2.reset();
   if ( s2 ) Console::WriteLine( "s2 is now valid" );
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );
}
```

```Output
s1 is invalid
s2 is valid
s2 is now invalid
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\auto_handle.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[auto_handle-Members](../dotnet/auto-handle-members.md)<br/>
[auto_handle::operator!](../dotnet/auto-handle-operator-logical-not.md)