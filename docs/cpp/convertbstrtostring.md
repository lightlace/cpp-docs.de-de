---
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: df123dc218aa770a67536bf1bad7d8bafcf4c318
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392322"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Microsoft-spezifisch**

Konvertiert eine `BSTR` -Werts in einen `char *`.

## <a name="syntax"></a>Syntax

```
char* __stdcall ConvertBSTRToString(BSTR pSrc);
```

#### <a name="parameters"></a>Parameter

*pSrc*<br/>
Eine BSTR-Variable.

## <a name="remarks"></a>Hinweise

**ConvertBSTRToString** ordnet eine Zeichenfolge, die Sie löschen müssen.

## <a name="example"></a>Beispiel

```cpp
// ConvertBSTRToString.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")

int main() {
   BSTR bstrText = ::SysAllocString(L"Test");
   wprintf_s(L"BSTR text: %s\n", bstrText);

   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);
   printf_s("char * text: %s\n", lpszText2);

   SysFreeString(bstrText);
   delete[] lpszText2;
}
```

```Output
BSTR text: Test
char * text: Test
```

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

**Header:** \<comutil.h>

**LIB:** comsuppw.lib oder comsuppwd.lib (finden Sie unter [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Informationen)

## <a name="see-also"></a>Siehe auch

[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)