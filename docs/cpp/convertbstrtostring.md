---
title: ConvertBSTRToString | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e84b8fb27c926a4b61ae631638ea4708fcf538b7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463989"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft-spezifisch**  
  
 Konvertiert eine `BSTR` -Werts in einen `char *`.  
  
## <a name="syntax"></a>Syntax  
  
```  
char* __stdcall ConvertBSTRToString(BSTR pSrc);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pSrc*  
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