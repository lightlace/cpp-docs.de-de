---
title: "Gewusst wie: Laden von nicht verwalteten Ressourcen in ein Byte-Array | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systemeigene Ressourcen"
  - "Systemeigene Ressourcen, Laden in Bytearray"
  - "Nicht verwaltete Ressourcen, Laden in Bytearray"
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Gewusst wie: Laden von nicht verwalteten Ressourcen in ein Byte-Array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unter diesem Thema werden mehrere Möglichkeiten erläutert, nicht verwaltete Ressourcen in einen <xref:System.Byte>\-Array zu laden.  
  
## Beispiel  
 Wenn Sie die Größe der nicht verwalteten Ressource kennen, können Sie einen CLR\-Array vorreservieren und anschließend die Ressource mithilfe eines Zeigers auf den Array\-Block des CLR\-Arrays in den Array laden.  
  
```  
// load_unmanaged_resources_into_Byte_array.cpp  
// compile with: /clr  
using namespace System;  
void unmanaged_func( unsigned char * p ) {  
   for ( int i = 0; i < 10; i++ )  
      p[ i ] = i;  
}  
  
public ref class A {  
public:  
   void func() {  
      array<Byte> ^b = gcnew array<Byte>(10);  
      pin_ptr<Byte> p =  &b[ 0 ];  
      Byte * np = p;  
      unmanaged_func( np );   // pass pointer to the block of CLR array.  
      for ( int i = 0; i < 10; i++ )  
         Console::Write( b[ i ] );  
      Console::WriteLine();  
   }  
};  
  
int main() {  
   A^ g = gcnew A;  
   g->func();  
}  
```  
  
  **0123456789**   
## Beispiel  
 Anhand dieses Beispiels wird gezeigt, wie Daten aus einem nicht verwalteten Speicherblock in einen verwalteten Array kopiert werden.  
  
```  
// load_unmanaged_resources_into_Byte_array_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <string.h>  
int main() {  
   char buf[] = "Native String";  
   int len = strlen(buf);  
   array<Byte> ^byteArray = gcnew array<Byte>(len + 2);  
  
   // convert any native pointer to IntPtr by doing C-Style cast  
   Marshal::Copy( (IntPtr)buf, byteArray, 0, len );  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)