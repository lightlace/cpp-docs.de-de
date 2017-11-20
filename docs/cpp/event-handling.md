---
title: Ereignisbehandlung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ae45cf1ea8b2540038bab12f28c244ed7b5de7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="event-handling"></a>Ereignisbehandlung
Ereignisbehandlung wird hauptsächlich für COM-Klassen unterstützt (C++-Klassen, COM-Objekten, die in der Regel mit ATL-Klassen implementieren, oder die [Coclass](../windows/coclass.md) Attribut).  Weitere Informationen finden Sie unter [Ereignisbehandlung in COM](../cpp/event-handling-in-com.md).  
  
 Ereignisbehandlung wird auch für native C++-Klassen (C++-Klassen, die keine COM-Objekte implementieren) unterstützt. Die Unterstützung ist jedoch veraltet und wird in einem der nächsten Releases entfernt werden.  Weitere Informationen finden Sie unter [Ereignisbehandlung in systemeigenem C++](../cpp/event-handling-in-native-cpp.md).  
  
 Die Ereignisbehandlung unterstützt Einzel- und Multithreadverwendung und schützt Daten vor gleichzeitigem Multithreadzugriff. Sie ermöglicht Ihnen auch das Ableiten von Unterklassen aus Ereignisquellklassen oder Ereignisempfängerklassen und unterstützt die erweiterte Ereignisquellentnahme bzw. den Ereignisempfang in der abgeleiteten Klasse.  
  
 Visual C++ enthält Attribute und Schlüsselwörter zum Deklarieren von Ereignissen und Ereignishandlern. Die Ereignisattribute und Schlüsselwörter können in CLR-Programmen und in systemeigenen C++-Programmen verwendet werden.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|Erstellt eine Ereignisquelle.|  
|[event_receiver](../windows/event-receiver.md)|Erstellt einen Ereignisempfänger (Senke).|  
|[__event](../cpp/event.md)|Deklariert ein Ereignis.|  
|[__raise](../cpp/raise.md)|Hebt die Aufrufsite eines Ereignisses hervor.|  
|[__hook](../cpp/hook.md)|Ordnet eine Handlermethode einem Ereignis zu.|  
|[__unhook](../cpp/unhook.md)|Trennt eine Handlermethode von einem Ereignis.|  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Beispiele für die Ereignisbehandlung](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)