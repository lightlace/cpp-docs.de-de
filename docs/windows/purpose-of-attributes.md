---
title: Attributzwecke | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed20c29d017527d5c2ce0b0c5ab8053fc75dc6ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="purpose-of-attributes"></a>Attributzwecke
Attribute Erweiterung von C++ Richtungen derzeit nicht möglich ohne Unterbrechung der klassischen Struktur der Sprache. Attribute können Provider (separate DLLs) Sprachfunktionalität dynamisch zu erweitern. Das Hauptziel der Attribute ist zum Vereinfachen der Erstellung von COM-Komponenten, zusätzlich zu erhöhen die Produktivität Maß der Komponentenentwickler. Attribute können angewendet werden, nahezu alle C++-Konstrukt, z. B. Klassen, Datenmember oder Memberfunktionen. Im folgenden finden eine Hervorhebung der Vorteile dieser neuen Technologie:  
  
-   Stellt eine vertraute und einfache Aufrufkonvention.  
  
-   Verwendet eingefügten Code, der im Gegensatz zu Makros, die vom Debugger erkannt wird.  
  
-   Ermöglicht die einfache Ableitung von Basisklassen ohne aufwändige Implementierungsdetails.  
  
-   Ersetzt die großen Anteil der IDL-Code, die von einer COM‑Komponente mit wenigen präzise Attribute erforderlich.  
  
 Beispielsweise, um einen einfachen Ereignisempfänger für eine generische ATL-Klasse zu implementieren, Sie können gelten die [Event_receiver](../windows/event-receiver.md) Attribut an eine bestimmte Klasse z. B. `CMyReceiver`. Die **Event_receiver** Attribut wird dann kompiliert, vom Visual C++-Compiler, die richtige Codepage in der Objektdatei einfügt.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Sie können dann festlegen, um die **CMyReceiver** Methoden `handler1` und `handler2` zum Behandeln von Ereignissen (mit der systeminternen Funktion [__hook](../cpp/hook.md)) von einer Ereignisquelle, die Sie mithilfe von erstellen,können[Event_source](../windows/event-source.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../windows/attributed-programming-concepts.md)