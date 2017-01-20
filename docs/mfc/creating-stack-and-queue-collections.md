---
title: "Erstellen von Stack- und Warteschlangenauflistungen"
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
  - "Auflistungsklassen, Erstellen"
  - "Auflistungen, queue"
  - "Auflistungen, Stapel"
  - "MFC-Auflistungsklassen, Queue-Auflistungen"
  - "MFC-Auflistungsklassen, Stack-Auflistungen"
  - "Queue-Auflistungen"
  - "Stapel"
  - "Stack-Auflistungen"
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von Stack- und Warteschlangenauflistungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie andere Datenstrukturen, wie [Stapel](#_core_stacks) und [Warteschlangen](#_core_queues), von den MFC\-Listenklassen erstellt.  Die Beispiele verwenden die Klassen, die von `CList` abgeleitet werden, jedoch können Sie `CList` direkt verwenden, es sei denn, Sie Funktionen hinzufügen müssen.  
  
##  <a name="_core_stacks"></a> Stapel  
 Da die Standardlistenauflistung einen Anfang und ein Ende verfügt, ist es einfach, eine abgeleitete Listenauflistung zu erstellen, die das Verhalten eines Last\-in\-First\-out\-Stapels imitiert.  Ein Stapel entspricht einem Stapel Infobereiche in einer Cafeteria.  Während Infobereiche dem Stapel hinzugefügt werden, um sie auf dem Stapel.  Der letzte hinzugefügte Infobereich ist der zu entfernende erste.  Die Listenauflistungsmemberfunktionen `AddHead` und `RemoveHead` können verwendet werden, um Elementen vom Anfang der Liste speziell hinzuzufügen und zu entfernen; so ist das zuletzt hinzugefügte Element das erste, entfernt werden.  
  
#### Um eine Stapelauflistung erstellen  
  
1.  Ableiten einer neuen Listenklasse einer der vorhandenen MFC\-Listenklassen und fügen Sie weiteren Memberfunktionen hinzu, um die Funktionalität von Stapelvorgängen zu unterstützen.  
  
     Das folgende Beispiel zeigt, wie die Memberfunktionen Push\-Elementen an dem Stapel hinzugefügt, oben Element des Stapels einsieht und das oberste Element vom Stapel aufnimmt:  
  
     [!CODE [NVC_MFCCollections#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#20)]  
  
 Beachten Sie, dass dieser Ansatz die zugrunde liegende `CObList`\-Klasse verfügbar macht.  Der Benutzer kann jede `CObList`\-Memberfunktion aufrufen, ob es Sinn für einen Stapel oder nicht.  
  
##  <a name="_core_queues"></a> Warteschlangen  
 Da die Standardlistenauflistung einen Anfang und ein Ende verfügt, ist sie auch einfach, eine abgeleitete Listenauflistung zu erstellen, die das Verhalten einer First\-in\-First\-out\-Warteschlange imitiert.  Eine Warteschlange steht wie eine Zeile von Personen in einer Cafeteria.  Die erste Person in der angeboten werden Zeile ist die erste.  Sobald weitere Personen stammen, indem diese an das Ende der Zeile, die Drehung zu warten.  Die Listenauflistungsmemberfunktionen `AddTail` und `RemoveHead` können verwendet werden, um Elementen vom Anfang oder am Ende der Liste speziell hinzuzufügen und zu entfernen; so ist das zuletzt hinzugefügte Element immer das zu entfernende letzte.  
  
#### Um eine Warteschlangenauflistung erstellen  
  
1.  Ableiten einer neuen Listenklasse einer der vordefinierten Listenklassen, die mit der Microsoft Foundation Class\-Bibliothek bereitgestellten und fügen Sie weiteren Memberfunktionen, die die Semantik von Warteschlangenvorgängen zu unterstützen hinzu.  
  
     Das folgende Beispiel zeigt, wie Sie Memberfunktionen anfügen können, um ein Element am Ende der Warteschlange hinzuzufügen und das Element von der Vorderseite der Warteschlange abrufen.  
  
     [!CODE [NVC_MFCCollections#21](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#21)]  
  
## Siehe auch  
 [Auflistungen](../mfc/collections.md)