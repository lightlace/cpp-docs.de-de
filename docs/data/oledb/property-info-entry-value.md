---
title: "PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE-Makro"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROPERTY_INFO_ENTRY_VALUE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Eigenschaft in einem bestimmte Eigenschaft dar.  
  
## Syntax  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### Parameter  
 *dwPropID*  
 \[in\] Wert A der [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx), der in Kombination mit der Eigenschaft GUID verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
 *Wert*  
 \[in\] der Eigenschaftswert des Typs `DWORD`.  
  
## Hinweise  
 Mit diesem Makro können Sie den Eigenschaftswert des Typs `DWORD` direkt angeben.  Um die Eigenschaft auf den Standardwert festzulegen, der in ATLDB.H definiert ist, verwenden Sie [PROPERTY\_INFORMATION\_ENTRY](../../data/oledb/property-info-entry.md).  Um den Wert festzulegen, verwenden Flags und Optionen für die Eigenschaft, [PROPERTY\_INFORMATION\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Beispiel  
 Siehe [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)