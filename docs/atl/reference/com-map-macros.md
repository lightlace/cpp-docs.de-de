---
title: "COM Map Macros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM-Schnittstellen, COM map macros"
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# COM Map Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Makros definieren COM\-Schnittstellen\-Zuordnungen.  
  
|||  
|-|-|  
|[BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)|Markiert den Beginn der COM\-Schnittstellen\-Zuordnungseinträge.|  
|[COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md)|Gibt Schnittstellen in die COM\-Schnittstellenzuordnung ein.|  
|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)|Verwenden Sie dieses Makro, um zwei Verzweigungen Vererbung zu herzustellen.|  
|[COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)|Verwenden Sie dieses Makro, um die Schnittstelle in die COM\-Zuordnung einzugeben und sein IID anzugeben.|  
|[COM\_INTERFACE\_ENTRY2\_IID](../Topic/COM_INTERFACE_ENTRY2_IID.md)|Identisch mit [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md), außer Sie ein anderes IID angeben können.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)|Wenn die Schnittstelle, die von `iid` identifiziert wird, für abgefragt wird, leitet `COM_INTERFACE_ENTRY_AGGREGATE` zu `punk` weiter.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AGGREGATE_BLIND.md)|Wie das [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), außer dass das Abfragen für jedes IID führt das Weiterleiten der Abfrage zu `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)|Identisch mit [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), außer, wenn `punk`**NULL** ist, erstellt sie automatisch das Aggregat, das von `clsid` beschrieben wird.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)|Wie das [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md), außer dass das Abfragen für jedes IID führt das Weiterleiten der Abfrage zu `punk` und wenn `punk`**NULL** ist und automatisch erstellt das Aggregat, das von `clsid` beschrieben wird.|  
|[COM\_INTERFACE\_ENTRY\_BREAK](../Topic/COM_INTERFACE_ENTRY_BREAK.md)|Veranlasst das Programm, [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) aufzurufen, wenn die angegebene Schnittstelle für abgefragt wird.|  
|[COM\_INTERFACE\_ENTRY\_CACHED\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_CACHED_TEAR_OFF.md)|Speichert die Schnittstellebesondere Daten für jede Instanz.|  
|[COM\_INTERFACE\_ENTRY\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_TEAR_OFF.md)|Macht die Tearoff\-Schnittstellen verfügbar.|  
|[COM\_INTERFACE\_ENTRY\_CHAIN](../Topic/COM_INTERFACE_ENTRY_CHAIN.md)|Verarbeitet die COM\-Zuordnung der Basisklasse, wenn die Verarbeitung diesen Eintrag in der COM\-Zuordnung erreicht.|  
|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)|Ein allgemeiner Mechanismus zum Verbinden in `QueryInterface` ATL der Logik.|  
|[COM\_INTERFACE\_ENTRY\_FUNC\_BLIND](../Topic/COM_INTERFACE_ENTRY_FUNC_BLIND.md)|Wie das [COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md), außer dass das Abfragen für jedes IID führt einen Aufruf `func`.|  
|[COM\_INTERFACE\_ENTRY\_NOINTERFACE](../Topic/COM_INTERFACE_ENTRY_NOINTERFACE.md)|Gibt **E\_NOINTERFACE** zurück und beendet COM\-Zuordnungsverarbeitung, wenn die angegebene Schnittstelle für abgefragt wird.|  
|[END\_COM\_MAP](../Topic/END_COM_MAP.md)|Markiert das Ende der COM\-Schnittstellen\-Zuordnungseinträge.|  
  
## Siehe auch  
 [Macros](../../atl/reference/atl-macros.md)   
 [COM Map Global Functions](../../atl/reference/com-map-global-functions.md)