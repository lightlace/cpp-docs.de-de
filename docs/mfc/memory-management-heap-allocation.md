---
title: "Speicherverwaltung: Heapbelegung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete-Operator, Verwenden mit Debuggen (MFC)"
  - "Erkennen von Speicherverlusten"
  - "Heapzuordnung"
  - "Heapzuordnung, Beschreibung"
  - "Speicherreservierung, Heapspeicher"
  - "Speicherverluste, Ermitteln"
  - "Speicher, Erkennen von Verlusten"
  - "new-Operator, Verwenden mit Debuggen (MFC)"
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Speicherverwaltung: Heapbelegung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Heap ist für die Speicherbelegungsanforderungen des Programms reserviert.  Es ist ein Bereich unabhängig von dem Programmcode und dem Stapel.  Typische C\-Programme verwenden die Funktionen `malloc` und **free**, um Heapspeicher reserviert und freizugeben.  Die Debugversion von MFC bietet geänderte Versionen der integrierten Operatoren **neu** und **löschen** C\+\+, um Objekte im Heapspeicher reserviert und freizugeben.  
  
 Wenn Sie **neu** und **löschen** anstelle von `malloc` und **free** verwenden, können Sie, die Speicherverwaltungs\-Debuggingserweiterungen der Klassenbibliothek zu nutzen, die hilfreich sein können, wenn von Speicherverlusten erkennt.  Wenn Sie das Programm mit der Releaseversion von MFC erstellen, stellen die Standardversionen der **neu** und **löschen**\-Operatoren eine effiziente Möglichkeit, Arbeitsspeicher Reservieren und Freigeben \(die Releaseversion von MFC bietet nicht geänderten Versionen dieser Operatoren.\)  
  
 Beachten Sie, dass die Gesamtgröße von Objekten, die auf dem Heap zugeordnet sind, nur durch den verfügbaren virtuellen Arbeitsspeicher des Systems beschränkt ist.  
  
## Siehe auch  
 [Speicherverwaltung](../mfc/memory-management.md)