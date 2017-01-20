---
title: "Using IDispEventSimpleImpl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class, Verwenden"
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Using IDispEventSimpleImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie `IDispEventSimpleImpl` verwenden, um Ereignisse zu behandeln, benötigen Sie:  
  
-   Leiten Sie die Klasse von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   Fügen Sie [Ereignissenkenzuordnung](../Topic/BEGIN_SINK_MAP.md) der Klasse hinzu.  
  
-   Definieren Sie [\_ATL\_FUNC\_INFORMATION](../atl/reference/atl-func-info-structure.md)\-Strukturen, die die Ereignisse beschreiben.  
  
-   Fügen Sie Einträge der Ereignissenkenzuordnung mithilfe des [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md)\-Makros hinzu.  
  
-   Implementieren Sie die Methoden, dass Sie bei der Behandlung von Interesse sind.  
  
-   Melden Sie sich an und benachrichtigen Sie die Ereignisquelle ab.  
  
## Beispiel  
 Im Beispiel unten wird gezeigt, wie Sie das **DocumentChange**\-Ereignisses, das von Word **Application**\-Objekt ausgelöst wird.  Dieses Ereignis wird als Methode auf der **ApplicationEvents** Dispatchschnittstelle definiert.  
  
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
  
 Die einzigen Informationen aus der Typbibliothek, die tatsächlich in diesem Beispiel verwendet wird, sind die CLSID des Objekts Word **Application** und des IID der **ApplicationEvents**\-Schnittstelle.  Diese Informationen werden nur zur Kompilierzeit verwendet.  
  
 Im folgenden Code wird in Simple.h.  Der relevante Code wird durch Kommentare erwähnt:  
  
 [!CODE [NVC_ATL_EventHandlingSample#3](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_EventHandlingSample#3)]  
  
 Der folgende Code ist von Simple.cpp:  
  
 [!CODE [NVC_ATL_EventHandlingSample#4](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_EventHandlingSample#4)]  
  
## Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [ATLEventHandling\-Beispiel](../top/visual-cpp-samples.md)