---
title: ConvertStringToBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ConvertStringToBSTR
dev_langs: C++
helpviewer_keywords: ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4347fdcf25373e088a8d8bc54cc3219285aa347
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR
**Microsoft-spezifisch**  
  
 Konvertiert eine **Char \***  -Wert in einen `BSTR`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      BSTR __stdcall ConvertStringToBSTR(  
   const char* pSrc  
)  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSrc`  
 Ein **Char \***  Variable.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
char * text: Test  
BSTR text: Test  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** comutil.h  
  
 **LIB:** "comsuppw.lib" oder "comsuppwd.lib" (siehe [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) für Weitere Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)