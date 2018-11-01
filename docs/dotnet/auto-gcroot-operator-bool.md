---
title: auto_gcroot::operator bool
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- auto_gcroot.operator bool
- auto_gcroot::operator bool
- msclr.auto_gcroot.operator bool
- msclr::auto_gcroot::operator bool
- operator bool
helpviewer_keywords:
- bool operator
ms.assetid: 87d38498-4221-4de8-8d02-c2dd2e6274ec
ms.openlocfilehash: f07cd378eea9c68542a50b579b9aff17ec2b3693
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659354"
---
# <a name="autogcrootoperator-bool"></a>auto_gcroot::operator bool

Operator für die Verwendung von `auto_gcroot` in einem bedingten Ausdruck.

## <a name="syntax"></a>Syntax

```
operator bool() const;
```

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn das umschlossene Objekt gültig ist. **"false"** andernfalls.

## <a name="remarks"></a>Hinweise

Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als **"bool"** , da es in einen ganzzahligen Typ konvertiert werden kann.

## <a name="example"></a>Beispiel

```cpp
// msl_auto_gcroot_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s;
   if ( s ) Console::WriteLine( "s is valid" );
   if ( !s ) Console::WriteLine( "s is invalid" );
   s = "something";
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
   s.reset();
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
}
```

```Output
s is invalid
now s is valid
now s is invalid
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\auto_gcroot.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[auto_gcroot-Members](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::operator!](../dotnet/auto-gcroot-operator-logical-not.md)