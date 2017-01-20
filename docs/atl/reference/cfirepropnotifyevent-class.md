---
title: "CFirePropNotifyEvent Class"
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
  - "CFirePropNotifyEvent"
  - "ATL::CFirePropNotifyEvent"
  - "ATL.CFirePropNotifyEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFirePropNotifyEvent class"
  - "Verbindungspunkte [C++], notifying of events"
  - "sinks, notifying of ATL events"
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CFirePropNotifyEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Benachrichtigen der Senke des Containers zu Steuerelementeigenschaftenänderungen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CFirePropNotifyEvent  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](../Topic/CFirePropNotifyEvent::FireOnChanged.md)|\(Statisch\) benachrichtigt die Senke des Containers, dass eine Steuerelementeigenschaft geändert hat.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](../Topic/CFirePropNotifyEvent::FireOnRequestEdit.md)|\(Statisch\) benachrichtigt die Senke des Containers, dass eine Steuerelementeigenschaft im Begriff ist zu ändern.|  
  
## Hinweise  
 `CFirePropNotifyEvent` besitzt zwei Methoden, die die Senke des Containers benachrichtigen, dass eine Steuerelementeigenschaft geändert hat oder ist zu ändern.  
  
 Wenn die Klasse, die das Steuerelement implementiert, von `IPropertyNotifySink` abgeleitet ist, sind die `CFirePropNotifyEvent`\-Methoden aufgerufen, wenn Sie `FireOnRequestEdit` oder `FireOnChanged` aufrufen.  Wenn die Steuerelementklasse nicht von `IPropertyNotifySink` abgeleitet ist, geben Aufrufe dieser Funktionen  `S_OK` zurück.  
  
 Weitere Informationen zum Erstellen von Steuerelementen, finden Sie unter [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)