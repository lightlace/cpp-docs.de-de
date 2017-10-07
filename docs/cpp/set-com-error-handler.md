---
title: _set_com_error_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 626227fb9c5162e5b9fc72fc64348b75ecb27e44
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
 `pHandler`  
 Zeiger auf die Ersetzungsfunktion.  
  
 `hr`  
 `HRESULT`-Informationen.  
  
 `perrinfo`  
 `IErrorInfo`-Objekt  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig [_com_raise_error](../cpp/com-raise-error.md) behandelt alle COM-Fehler. Sie können dieses Verhalten ändern, indem Sie `_set_com_error_handler` verwenden, um eine eigene Fehlerbehandlungsfunktion aufzurufen.  
  
 Die Ersetzungsfunktion muss über eine Signatur verfügen, die der von `_com_raise_error` entspricht.  
  
## <a name="example"></a>Beispiel  
  
```  
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
 **Header:** comdef.h  
  
 **LIB:** Wenn die **Wchar_t ist der systemeigene Typ** Compileroption ist, verwenden Sie "comsuppw.lib" oder "comsuppwd.lib". Wenn **Wchar_t ist der systemeigene Typ** deaktiviert ist, verwenden "comsupp.lib". Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)
