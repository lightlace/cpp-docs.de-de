---
title: "Gewusst wie: Objektverweis in nicht verwaltetem Arbeitsspeicher | Microsoft Docs"
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
  - "gcroot-Schlüsselwort [C++], Objektverweis in systemeigener Funktion"
  - "Objektverweise, In systemeigenen Funktionen"
  - "Objekte [C++], Verweise in systemeigenen Funktionen"
  - "Referenzen, Auf Objekte in systemeigenen Funktionen"
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Gewusst wie: Objektverweis in nicht verwaltetem Arbeitsspeicher
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können gcroot.h verwenden, das <xref:System.Runtime.InteropServices.GCHandle> umschließt, um einen CLR\-Objektverweis in nicht verwaltetem Arbeitsspeicher zu halten.  Wahlweise können Sie `GCHandle` direkt verwenden.  
  
## Beispiel  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
  **StringWrapper::x \=\= ManagedString**   
## Beispiel  
 `GCHandle` ermöglicht Ihnen, in einem nicht verwalteten Arbeitsspeicher einen verwalteten Objektverweis zu halten.  Mit der <xref:System.Runtime.InteropServices.GCHandle.Alloc*>\-Methode erstellen Sie ein nicht transparentes Handle für ein verwaltetes Objekt, und mit <xref:System.Runtime.InteropServices.GCHandle.Free*> geben Sie es frei.  Außerdem können Sie den Objektverweis von dem Handle in verwaltetem Code zurückholen, indem Sie die <xref:System.Runtime.InteropServices.GCHandle.Target*>\-Methode verwenden.  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
  **StringWrapper::m\_handle \=\= ManagedString**   
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)