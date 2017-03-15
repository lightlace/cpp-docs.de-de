---
title: "Using IDispEventImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class, Verwenden"
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie `IDispEventImpl` verwenden, um Ereignisse zu behandeln, benötigen Sie:  
  
-   Leiten Sie die Klasse von [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Fügen Sie [Ereignissenkenzuordnung](../Topic/BEGIN_SINK_MAP.md) der Klasse hinzu.  
  
-   Fügen Sie Einträge der Ereignissenkenzuordnung mithilfe des [SINK\_ENTRY](../Topic/SINK_ENTRY.md) oder [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)\-Makros hinzu.  
  
-   Implementieren Sie die Methoden, dass Sie bei der Behandlung von Interesse sind.  
  
-   Melden Sie sich an und benachrichtigen Sie die Ereignisquelle ab.  
  
## Beispiel  
 Im Beispiel unten zeigt, wie das **DocumentChange**\-Ereignisses, das von Word **Application**\-Objekt ausgelöst wird.  Dieses Ereignis wird als Methode auf der **ApplicationEvents** Dispatchschnittstelle definiert.  
  
 Das Beispiel ist von [ATLEventHandling\-Beispiel](../top/visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 Im Beispiel wird `#import`, um die erforderlichen Headerdateien von Word Typbibliothek zu generieren.  Wenn Sie dieses Beispiel mit anderen Versionen von Word verwenden möchten, müssen Sie die richtige Datei mso.dll angeben.  stellt beispielsweise mso9.dll Office 2000 und Office Xp stellt mso.dll.  Dieser Code wird von stdafx.h vereinfacht:  
  
 [!CODE [NVC_ATL_EventHandlingSample#1](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_EventHandlingSample#1)]  
  
 Im folgenden Code wird in NotSoSimple.h.  Der relevante Code wird durch Kommentare erwähnt:  
  
 [!CODE [NVC_ATL_EventHandlingSample#2](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_EventHandlingSample#2)]  
  
## Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [ATLEventHandling\-Beispiel](../top/visual-cpp-samples.md)