---
title: "Laden aller Importe f&#252;r eine verz&#246;gert geladene DLL"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__HrLoadAllImportsForDll (Linkeroption)"
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Laden aller Importe f&#252;r eine verz&#246;gert geladene DLL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die in **delayhlp.cpp** definierte **\_\_HrLoadAllImportsForDll**\-Funktion weist den Linker an, alle Importe aus einer DLL zu laden, die mit der Linkeroption [\/delayload](../../build/reference/delayload-delay-load-import.md) festgelegt wurde.  
  
 Das Laden aller Importe ermöglicht Ihnen, die Fehlerbehandlung an einer Stelle im Code zu zentrieren, sodass in den eigentlichen Aufrufen der Importe keine Ausnahmebehandlung erforderlich ist.  Außerdem wird dadurch eine Situation vermieden, in der ein Anwendungsprozess fehlschlägt, da ein Import vom Hilfscode nicht geladen werden konnte.  
  
 Das Verhalten von Hooks und der Fehlerbehandlung wird durch Aufrufen von **\_\_HrLoadAllImportsForDll** nicht geändert; weitere Informationen finden Sie unter [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md).  
  
 Der DLL\-Name, der **\_\_HrLoadAllImportsForDll** übergeben wird, wird mit dem in der DLL selbst gespeicherten Namen verglichen; bei ihm wird die Groß\- und Kleinschreibung berücksichtigt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie **\_\_HrLoadAllImportsForDll** aufrufen:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)