---
title: "PROPERTY_INFO_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY-Makro"
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
## Syntax  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### Parameter  
 *dwPropID*  
 \[in\] Ein [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx)\-Wert, der in Verbindung mit dem Eigenschaftensatz GUID verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
## Hinweise  
 Dieses Makro legt den Wert der Eigenschaft vom Typ `DWORD` auf einen in ATLDB.H definierten Standardwert fest. Verwenden Sie [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md), um die Eigenschaft auf einen Wert Ihrer Wahl festzulegen. Zum gleichzeitigen Festlegen von [VARTYPE](assetId:///317b911b-1805-402d-a9cb-159546bc88b4) und [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) für die Eigenschaft verwenden Sie [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Beispiel  
 Siehe [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)