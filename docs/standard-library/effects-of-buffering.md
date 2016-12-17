---
title: "Pufferungseffekte"
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
  - "Puffer, Pufferungseffekte"
  - "Pufferung, Effekte"
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Pufferungseffekte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel werden die Effekte von Pufferung veranschaulicht. Sie erwarten wahrscheinlich, dass das Programm `please wait` ausgibt, 5 Sekunden wartet, und dann den nächsten Vorgang ausführt. Das Programm wird aber nicht unbedingt so funktionieren, weil die Ausgabe gepuffert wird.  
  
```  
// effects_buffering.cpp // compile with: /EHsc #include <iostream> #include <time.h> using namespace std; int main( ) { time_t tm = time( NULL ) + 5; cout << "Please wait..."; while ( time( NULL ) < tm ) ; cout << "\nAll done" << endl; }  
```  
  
 Damit das Programm logisch funktioniert, muss sich das `cout`\-Objekt selbst leeren, wenn die Meldung angezeigt werden soll. Um ein `ostream`\-Objekt zu leeren, senden Sie ihm den `flush`\-Manipulator:  
  
```  
cout << "Please wait..." << flush;  
```  
  
 In diesem Schritt wird der Puffer geleert, wodurch sichergestellt wird, dass die Meldung vor dem Wartevorgang ausgegeben wird. Sie können auch den `endl`\-Manipulator verwenden, der den Puffer leert und einen Wagenrücklauf und Zeilenvorschub ausgibt, oder Sie können das `cin` Objekt verwenden. Dieses Objekt \(mit dem `cerr`\- oder dem `clog`\-Objekt\) ist in der Regel mit dem `cout`\-Objekt verknüpft. Daher wird bei jeder Verwendung von `cin` \(oder einem der Objekte `cerr` oder `clog`\) das `cout`\-Objekt geleert.  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)