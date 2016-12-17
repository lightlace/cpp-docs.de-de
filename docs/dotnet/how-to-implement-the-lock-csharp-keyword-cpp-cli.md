---
title: "Gewusst wie: Implementieren des C#-Schl&#252;sselworts &quot;lock&quot; (C++/CLI)"
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
  - "lock (C#-Schlüsselwort) [C++]"
  - "lock-Anweisung"
ms.assetid: 436fe544-ffb7-49b9-9798-90794e9974de
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Implementieren des C#-Schl&#252;sselworts &quot;lock&quot; (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie das C\#\-Schlüsselwort `lock` in Visual C\+\+ implementiert wird.  Weitere Informationen finden Sie unter [lock\-Anweisung](../Topic/lock%20Statement%20\(C%23%20Reference\).md).  
  
 Sie können auch die `lock`\-Klasse in der C\+\+\-Unterstützungsbibliothek verwenden.  Weitere Informationen finden Sie unter [Synchronisierung \(lock\-Klasse\)](../dotnet/synchronization-lock-class.md).  
  
## Beispiel  
  
```  
// CS_lock_in_CPP.cpp  
// compile with: /clr  
using namespace System::Threading;  
ref class Lock {  
   Object^ m_pObject;  
public:  
   Lock( Object ^ pObject ) : m_pObject( pObject ) {  
      Monitor::Enter( m_pObject );  
   }  
   ~Lock() {  
      Monitor::Exit( m_pObject );  
   }  
};  
  
ref struct LockHelper {  
   void DoSomething();  
};  
  
void LockHelper::DoSomething() {  
   // Note: Reference type with stack allocation semantics to provide   
   // deterministic finalization  
  
   Lock lock( this );     
   // LockHelper instance is locked  
}  
  
int main()  
{  
   LockHelper lockHelper;  
   lockHelper.DoSomething();  
   return 0;  
}  
```  
  
## Siehe auch  
 [Interoperabilität mit anderen .NET\-Sprachen](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)