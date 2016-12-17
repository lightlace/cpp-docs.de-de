---
title: "CMessageMap Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMessageMap"
  - "ATL.CMessageMap"
  - "ATL::CMessageMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Meldungshandler"
  - "CMessageMap class"
  - "message maps, ATL"
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMessageMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ermöglicht den Meldungszuordnungen eines Objekts, um den Zugriff von einem anderen Objekt ist.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class ATL_NO_VTABLE CMessageMap  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](../Topic/CMessageMap::ProcessWindowMessage.md)|Greift auf eine Meldungszuordnung in `CMessageMap` von abgeleiteten Klasse in.|  
  
## Hinweise  
 `CMessageMap` ist eine abstrakte Basisklasse, die auf die von einem anderen Objekt kann zugegriffen werden, Meldungszuordnungen eines Objekts.  Damit ein Objekt seine Meldungszuordnungen, seine Klasse muss von `CMessageMap` berechnen verfügbar macht.  
  
 ATL verwendet `CMessageMap`, um enthaltende Fenster und dynamische Meldungszuordnungsverketten zu unterstützen.  Beispielsweise Klasse alle Manifestfragmenten [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) eines Objekts müssen von `CMessageMap` berechnen.  Der folgende Code wird vom [STELLEN Sie auf](../../top/visual-cpp-samples.md) Beispiel aufgezeichnet.  Durch [CComControl](../../atl/reference/ccomcontrol-class.md) berechnet die `CAtlEdit`\-Klasse automatisch von `CMessageMap`.  
  
 [!CODE [NVC_ATL_Windowing#90](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#90)]  
  
 Da das enthaltende Fenster, `m_EditCtrl`, eine Meldungszuordnung im enthaltenden Klasse verwendet, berechnet `CAtlEdit` von `CMessageMap`.  
  
 Weitere Informationen zu Meldungszuordnungen, [Meldungszuordnungen](../../atl/message-maps-atl.md) finden Sie im Artikel "ATL\-Fensterklassen."  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [CDynamicChain Class](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)