---
title: 'Vorgehensweise: Angeben eines Out Parameter | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c755be8e9a2358935bcfe9892f308cd2faedacd3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-specify-an-out-parameter"></a>Gewusst wie: Angeben eines out-Parameters
In diesem Beispiel wird gezeigt, um anzugeben, dass ein Funktionsparameter Out-Parameter ist und zum Aufrufen dieser Funktion aus einem C#-Programm.  
  
 Out-Parameter wird angegeben, in Visual C++ mit <xref:System.Runtime.InteropServices.OutAttribute> .  
  
## <a name="example"></a>Beispiel  
 Der erste Teil dieses Beispiels ist ein Visual C++-DLL mit einem Typ, der eine Funktion mit der Out-Parameter enthält.  
  
```  
// cpp_out_param.cpp  
// compile with: /LD /clr:safe  
using namespace System;  
public value struct TestStruct {  
   static void Test([Runtime::InteropServices::Out] String^ %s) {  
      s = "a string";  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
 Dies ist ein C#-Client, der im vorherigen Beispiel erstellte Visual C++-Komponente verwendet.  
  
```  
// cpp_out_param_2.cs  
// compile with: /reference:cpp_out_param.dll  
using System;  
class TestClass {  
   public static void Main() {  
      String t;  
      TestStruct.Test(out t);  
      System.Console.WriteLine(t);  
   }  
}  
```  
  
```Output  
a string  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)