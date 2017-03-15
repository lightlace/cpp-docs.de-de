---
title: "CDBPropSet-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropSet"
  - "ATL.CDBPropSet"
  - "ATL::CDBPropSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropSet-Klasse"
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDBPropSet-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erbt aus der **DBPROPSET**\-Struktur und fügt einen Konstruktor hinzu, der Schlüsselfelder sowie `AddProperty` Zugriffsmethode initialisiert.  
  
## Syntax  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Fügt einer Eigenschaft dem Eigenschaftensatz hinzu.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Konstruktor.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Legt das Feld **guidPropertySet** der **DBPROPSET**\-Struktur fest.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cdbpropset-operator-equal.md)|Weist den Inhalt eines Eigenschaft auf anderen zu.|  
  
## Hinweise  
 OLE DB\-Anbieter und Consumer **DBPROPSET**\-Strukturen verwenden, um Arrays `DBPROP`\-Strukturen zu übergeben.  Jede `DBPROP`\-Struktur stellt eine einzelne Eigenschaft dar, die festgelegt werden kann.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet\-Klasse](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET Structure](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)