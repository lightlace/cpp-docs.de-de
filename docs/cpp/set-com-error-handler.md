---
title: "_set_com_error_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_com_error_handler-Funktion"
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# _set_com_error_handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ersetzt die Standardfunktion für die COM\-Fehlerbehandlung.  
  
## Syntax  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### Parameter  
 `pHandler`  
 Zeiger auf die Ersetzungsfunktion.  
  
 `hr`  
 `HRESULT`\-Informationen.  
  
 `perrinfo`  
 `IErrorInfo`\-Objekt  
  
## Hinweise  
 Standardmäßig behandelt [\_com\_raise\_error](../cpp/com-raise-error.md) alle COM\-Fehler.  Sie können dieses Verhalten ändern, indem Sie `_set_com_error_handler` verwenden, um eine eigene Fehlerbehandlungsfunktion aufzurufen.  
  
 Die Ersetzungsfunktion muss über eine Signatur verfügen, die der von `_com_raise_error` entspricht.  
  
## Beispiel  
  
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
  
  **Ausnahme ausgelöst: Es konnte keine Verbindung hergestellt werden\!**   
## Anforderungen  
 **Header:** comdef.h  
  
 **Lib:** wenn die Compileroption "wchar\_t ist der systemeigene Typ" aktiviert ist, verwenden Sie "comsuppw.lib" oder "comsuppwd.lib".  Wenn "wchar\_t ist der systemeigene Typ" deaktiviert ist, verwenden Sie "comsupp.lib".  Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## Siehe auch  
 [Globale Funktionen des Compiler\-COM](../cpp/compiler-com-global-functions.md)