---
title: "Gewusst wie: Umwandeln von char * String nach System::Byte Array"
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
  - "Arrays [C++], Zeichen"
  - "Zeichenarrays, Konvertieren in System::Bytearrays"
  - "Beispiele [C++], Arrays"
  - "Beispiele [C++], Zeichenfolgen"
ms.assetid: de9bc4eb-773c-4796-a496-9b90ca986503
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Umwandeln von char * String nach System::Byte Array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die effizienteste Umwandlung einer `char *`\-Zeichenfolge in ein <xref:System.Byte>\-Array verwendet die <xref:System.Runtime.InteropServices.Marshal>\-Klasse.  
  
## Beispiel  
  
```  
// convert_native_string_to_Byte_array.cpp  
// compile with: /clr  
#include <string.h>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
int main() {  
   char buf[] = "Native String";  
   int len = strlen(buf);  
  
   array< Byte >^ byteArray = gcnew array< Byte >(len + 2);  
  
   // convert native pointer to System::IntPtr with C-Style cast  
   Marshal::Copy((IntPtr)buf,byteArray, 0, len);  
  
   for ( int i = byteArray->GetLowerBound(0); i <= byteArray->GetUpperBound(0); i++ ) {  
      char dc =  *(Byte^)   byteArray->GetValue(i);  
      Console::Write((Char)dc);  
   }  
  
   Console::WriteLine();  
}  
```  
  
```  
Native String  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)