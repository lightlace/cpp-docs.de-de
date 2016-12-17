---
title: "Gewusst wie: Angeben eines out-Parameters"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsparameter"
  - "out-Parameter"
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Angeben eines out-Parameters
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Beispiel veranschaulicht, wie ein Funktionsparameter als out\-Parameter angegeben und die betreffende Funktion in einem C\#\-Programm aufgerufen wird.  
  
 Ein out\-Parameter wird in Visual C\+\+ mit <xref:System.Runtime.InteropServices.OutAttribute> angegeben.  
  
## Beispiel  
 Der erste Teil dieses Beispiels ist eine Visual C\+\+\-DLL mit einem Typ, die eine Funktion mit einem out\-Parameter enthält.  
  
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
  
## Beispiel  
 Dies ist ein C\#\-Client, der die im vorherigen Beispiel erstellte Visual C\+\+\-Komponente verwendet.  
  
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
  
  **eine Zeichenfolge**   
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)