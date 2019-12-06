---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 226dce24de68edd66ca68c43e41ce0cb5b8a1b48
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857293"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

Ersetzt die Standardfunktion für die COM-Fehlerbehandlung. **_set_com_error_handler** ist Microsoft-spezifisch.

## <a name="syntax"></a>Syntax

```
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>Parameters

*pHandler*<br/>
Zeiger auf die Ersetzungsfunktion.

*hr*<br/>
HRESULT-Informationen.

*perrinfo*<br/>
`IErrorInfo`-Objekt

## <a name="remarks"></a>Hinweise

Standardmäßig verarbeitet [_com_raise_error](../cpp/com-raise-error.md) alle com-Fehler. Sie können dieses Verhalten ändern, indem Sie **_set_com_error_handler** verwenden, um eine eigene Fehler Behandlungs Funktion aufzurufen.

Die Ersetzungsfunktion muss über eine Signatur verfügen, die der von `_com_raise_error` entspricht.

## <a name="example"></a>Beispiel

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>-Anforderungen

**Header:** \<comdef.h>

**Lib:** Wenn die **/Zc: wchar_t** -Compileroption angegeben ist (Standardeinstellung), verwenden Sie "comsuppw. lib" oder "comsuppwd. lib". Wenn die **/Zc: wchar_t-Compileroption** angegeben ist, verwenden Sie comsupp. lib. Weitere Informationen, einschließlich Informationen zum Festlegen dieser Option in der IDE, finden Sie unter [/Zc: wchar_t (wchar_t ist System eigener Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Siehe auch

[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)
