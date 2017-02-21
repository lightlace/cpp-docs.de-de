---
title: "CDynamicChain Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicChain class"
  - "chaining message maps"
  - "message maps, Verkettung"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDynamicChain Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, die die dynamischen Verketten von Meldungszuordnungen unterstützen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CDynamicChain  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|Der Konstruktor.|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|Verweist auf eine Windows\-Meldung auf die Meldungszuordnung eines anderen Objekts.|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|Entfernt einen Eintrag in der Meldungszuordnung aus der Auflistung.|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|Fügt der Auflistung einen Eintrag in der Meldungszuordnung hinzu oder ändert einen vorhandenen Eintrag.|  
  
## Hinweise  
 `CDynamicChain` verwaltet eine Auflistung Meldungszuordnungen und ermöglicht eine zur Laufzeit auf die Meldungszuordnung eines anderen Objekts verwiesen werden Windows\-Meldung.  
  
 Um Unterstützung für dynamische Verketten von Meldungszuordnungen hinzuzufügen, führen Sie Folgendes:  
  
-   Leiten Sie die Klasse von `CDynamicChain`.  In der Meldungszuordnung geben Sie das [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)\-Makro auf, um der Standardmeldungszuordnung eines anderen Objekts zu verketten.  
  
-   Leiten Sie jede Klasse, die an der [CMessageMap](../../atl/reference/cmessagemap-class.md) verketten möchten.  `CMessageMap` können Objekte, um seine Meldungszuordnungen anderen Objekten verfügbar zu machen.  
  
-   Rufen Sie `CDynamicChain::SetChainEntry` auf, um zu ermitteln, auf die das und die Meldungszuordnung Sie verketten möchten.  
  
 Angenommen, die Klasse definiert wurde, wie folgt:  
  
 [!CODE [NVC_ATL_Windowing#88](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#88)]  
  
 Der Client ruft dann `CMyWindow::SetChainEntry` auf:  
  
 [!CODE [NVC_ATL_Windowing#89](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#89)]  
  
 wobei `chainedObj` das verkettete Objekt ist und eine Instanz einer Klasse ist, die von `CMessageMap` abgeleitet wird.  Jetzt `myCtl` wenn eine Nachricht empfängt, die nicht von `OnPaint` oder `OnSetFocus` bearbeitet wird, verweist die Fensterprozedur die Meldung auf die Standardmeldungszuordnung von `chainedObj`.  
  
 Weitere Informationen zu Meldungszuordnungsverketten, [Meldungszuordnungen](../../atl/message-maps-atl.md) finden Sie im Artikel "ATL\-Fensterklassen."  
  
## Anforderungen  
 **Header:** atlwin.h  
  
## Siehe auch  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)