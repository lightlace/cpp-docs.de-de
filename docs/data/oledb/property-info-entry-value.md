---
title: "PROPERTY_INFO_ENTRY_VALUE"
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
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE-Makro"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
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