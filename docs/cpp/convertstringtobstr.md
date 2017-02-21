---
title: "ConvertStringToBSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ConvertStringToBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertStringToBSTR-Funktion"
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ConvertStringToBSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Konvertiert einen **char \***\-Wert in einen `BSTR`.  
  
## Syntax  
  
```  
  
      BSTR __stdcall ConvertStringToBSTR(  
   const char* pSrc  
)  
```  
  
#### Parameter  
 `pSrc`  
 Eine **char \***\-Variable.  
  
## Beispiel  
  
```  
// ConvertStringToBSTR.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
#pragma comment(lib, "kernel32.lib")  
  
int main() {  
   char* lpszText = "Test";  
   printf_s("char * text: %s\n", lpszText);  
  
   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   SysFreeString(bstrText);  
}  
```  
  
  **char \* text: Test**  
**BSTR text: Test**   
## END Microsoft\-spezifisch  
  
## Anforderungen  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib oder comsuppwd.lib \(Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).\)  
  
## Siehe auch  
 [Globale Funktionen des Compiler\-COM](../cpp/compiler-com-global-functions.md)