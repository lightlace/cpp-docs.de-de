---
title: "BEGIN_PROPERTY_SET_EX"
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
  - "BEGIN_PROPERTY_SET_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPERTY_SET_EX-Makro"
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PROPERTY_SET_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert den Beginn eines Eigenschaftensatzes in einer Eigenschaftensetzuordnung.  
  
## Syntax  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### Parameter  
 `guid`  
 \[in\] Eigenschaft die GUID.  
  
 `flags`  
 \[in\] **UPROPSET\_HIDDEN** für eine Eigenschaft, die nicht verfügbar machen möchten oder **UPROPSET\_PASSTHROUGH** für einen Anbieter, der die Eigenschaften definiert außerhalb des Projektumfangs des Anbieters verfügbar macht.  
  
## Beispiel  
 Siehe [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)