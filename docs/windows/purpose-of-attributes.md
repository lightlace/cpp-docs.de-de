---
title: "Purpose of Attributes"
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
  - "attributes [C++], about attributes"
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Purpose of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erweitern von Attributen in C\+\+ die Anweisungen zur Zeit nicht möglich, ohne die klassische Struktur der Sprache zu unterbrechen.  Attribute können Anbieter \(separaten DLL\) Um die Sprache dynamisch zu erweitern.  Das Hauptziel von Attributen ist die Erstellung von COM\-Komponenten zusätzlich zum Verbessern der Produktivität zu vereinfachen, die vom Komponentenentwickler.  Attribute können in nahezu jedem beliebigen C\+\+\-Konstrukt, z. B. Klassen, Datenmember oder Memberfunktionen angewendet werden.  Im Folgenden finden Sie eine Hervorhebung von den Vorteilen, die von dieser neuen Technologie bereitgestellt werden:  
  
-   Macht eine vertraute und einfache Aufrufkonvention.  
  
-   Wird eingefügten Code, außer Makros vom Debugger erkannt wird.  
  
-   Ermöglicht einfache Ableitung von den Basisklassen ohne lästige Implementierungsdetails.  
  
-   Ersetzt die große Menge von IDL\-Code von einer COM\-Komponente müssen einige kurze Attribute.  
  
 Um beispielsweise eine einfache Ereignissenke für eine generische ATL\-Klasse zu implementieren, können Sie das [event\_receiver](../windows/event-receiver.md)\-Attribut auf eine bestimmte Klasse wie `CMyReceiver`anwenden.  Das **event\_receiver**\-Attribut wird dann vom Visual C\+\+\-Compiler kompiliert, der den richtigen Code in der Objektdatei einfügt.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Sie können die **CMyReceiver**\-Methoden `handler1``handler2` und dann auf Installieren, um Ereignisse \(unter Verwendung der systeminternen Funktion [\_\_hook](../cpp/hook.md)\) aus einer Ereignisquelle zu behandeln, die Sie mithilfe [event\_source](../windows/event-source.md)erstellen können.  
  
## Siehe auch  
 [Concepts](../windows/attributed-programming-concepts.md)