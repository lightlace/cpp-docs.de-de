---
title: "Ereignisbehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attribute [C++], Ereignisbehandlung"
  - "Ereignisbehandlung, Visual C++"
  - "Systeminterne Funktionen, Ereignisbehandlung"
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ereignisbehandlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ereignisbehandlung wird hauptsächlich für COM\-Klassen unterstützt \(C\+\+\-Klassen, die COM\-Objekte implementieren, in der Regel mit ATL\-Klassen oder dem [coclass](../windows/coclass.md)\-Attribut\).  Weitere Informationen finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).  
  
 Ereignisbehandlung wird auch für systemeigene C\+\+\-Klassen \(C\+\+\-Klassen, die keine COM\-Objekte implementieren\) unterstützt. Die Unterstützung ist jedoch veraltet und wird in einer der nächsten Versionen entfernt werden.  Weitere Informationen finden Sie unter [Ereignisbehandlung in systemeigenem C\+\+](../cpp/event-handling-in-native-cpp.md).  
  
 Die Ereignisbehandlung unterstützt Einzel\- und Multithreadverwendung und schützt Daten vor gleichzeitigem Multithreadzugriff.  Sie ermöglicht Ihnen auch das Ableiten von Unterklassen aus Ereignisquellklassen oder Ereignisempfängerklassen und unterstützt die erweiterte Ereignisquellentnahme bzw. den Ereignisempfang in der abgeleiteten Klasse.  
  
 Visual C\+\+ enthält Attribute und Schlüsselwörter zum Deklarieren von Ereignissen und Ereignishandlern.  Die Ereignisattribute und Schlüsselwörter können in CLR\-Programmen und in systemeigenen C\+\+\-Programmen verwendet werden.  
  
|Thema|Beschreibung|  
|-----------|------------------|  
|[event\_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[event\_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger \(Senke\).|  
|[\_\_event](../cpp/event.md)|Deklariert ein Ereignis.|  
|[\_\_raise](../cpp/raise.md)|Hebt die Aufrufsite eines Ereignisses hervor.|  
|[\_\_hook](../cpp/hook.md)|Ordnet eine Handlermethode einem Ereignis zu.|  
|[\_\_unhook](../cpp/unhook.md)|Trennt eine Handlermethode von einem Ereignis.|  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Event Handling Samples](assetId:///cc0287d4-f92b-4da5-85fc-a0f186e16424)