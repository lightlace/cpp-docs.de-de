---
title: "Gewusst wie: Umwandeln von System::String nach wchar_t* oder char*"
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
  - "char-Datentyp, Konvertieren von System::String in"
  - "PtrToStringChars-Methode"
  - "System::String"
  - "System::String, Konvertieren in char oder wchar_t"
  - "wchart-Typ, Konvertieren von System::String"
ms.assetid: 385da01b-5649-4543-8076-e3e251243ff0
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Umwandeln von System::String nach wchar_t* oder char*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit `PtrToStringChars` in Vcclr.h können Sie <xref:System.String> in das systemeigene `wchar_t *` oder `char *` konvertieren.  Dadurch wird immer ein Zeiger mit breiter Unicode\-Zeichenfolge zurückgegeben, da CLR\-Zeichenfolgen intern Unicode sind.  Sie können dann von breit konvertieren, wie im folgenden Beispiel gezeigt wird.  
  
## Beispiel  
  
```  
// convert_string_to_wchar.cpp  
// compile with: /clr  
#include < stdio.h >  
#include < stdlib.h >  
#include < vcclr.h >  
  
using namespace System;  
  
int main() {  
   String ^str = "Hello";  
  
   // Pin memory so GC can't move it while native function is called  
   pin_ptr<const wchar_t> wch = PtrToStringChars(str);  
   printf_s("%S\n", wch);  
  
   // Conversion to char* :  
   // Can just convert wchar_t* to char* using one of the   
   // conversion functions such as:   
   // WideCharToMultiByte()  
   // wcstombs_s()  
   // ... etc  
   size_t convertedChars = 0;  
   size_t  sizeInBytes = ((str->Length + 1) * 2);  
   errno_t err = 0;  
   char    *ch = (char *)malloc(sizeInBytes);  
  
   err = wcstombs_s(&convertedChars,   
                    ch, sizeInBytes,  
                    wch, sizeInBytes);  
   if (err != 0)  
      printf_s("wcstombs_s  failed!\n");  
  
    printf_s("%s\n", ch);  
}  
```  
  
  **Hello**  
**Hello**   
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)