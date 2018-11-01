---
title: und
ms.date: 11/04/2016
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- And
- std.and
- std::and
helpviewer_keywords:
- and macro
ms.assetid: 2644ab57-8e1b-48f0-9021-cafe3e26bdc4
ms.openlocfilehash: 20f490a38ca8f92eadedf02396d1165b301e9e25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429973"
---
# <a name="and"></a>und

Eine Alternative zum &&-Operator.

## <a name="syntax"></a>Syntax

```C

#define and &&

```

## <a name="remarks"></a>Hinweise

Das Makro gibt den Operator && aus.

## <a name="example"></a>Beispiel

```cpp
// iso646_and.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   bool a = true, b = false, result;

   boolalpha(cout);

   result= a && b;
   cout << result << endl;

   result= a and b;
   cout << result << endl;
}
```

```Output
false
false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<iso646.h>