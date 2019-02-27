---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 864236e86b4aeb6ce7b3315df57af1b577693c26
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954938"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler

**Microsoft-spezifisch**

Ersetzt die Standardfunktion für die COM-Fehlerbehandlung.

## <a name="syntax"></a>Syntax

```
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>Parameter

*pHandler*<br/>
Zeiger auf die Ersetzungsfunktion.

*hr*<br/>
HRESULT-Informationen.

*perrinfo*<br/>
`IErrorInfo`-Objekt

## <a name="remarks"></a>Hinweise

In der Standardeinstellung [_com_raise_error](../cpp/com-raise-error.md) behandelt alle COM-Fehler. Sie können dieses Verhalten ändern, indem Sie mithilfe von **_set_com_error_handler** , eigene Fehlerbehandlungsfunktion aufzurufen.

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

## <a name="requirements"></a>Anforderungen

**Header:** \<comdef.h>

**Lib:** Wenn die **/Zc: wchar_t** -Compileroption angegeben ist (Standardeinstellung), verwenden Sie comsuppw.lib oder comsuppwd.lib. Wenn die **/Zc:** -Compileroption angegeben ist, sollten Sie comsupp.lib verwenden. Weitere Informationen einschließlich Informationen zum Festlegen dieser Option in der IDE finden Sie unter [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Siehe auch

[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)
