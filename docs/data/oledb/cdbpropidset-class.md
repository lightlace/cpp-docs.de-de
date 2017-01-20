---
title: "CDBPropIDSet-Klasse"
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
  - "CDBPropIDSet"
  - "ATL.CDBPropIDSet"
  - "ATL::CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet-Klasse"
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropIDSet-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erbt aus der **DBPROPIDSET**\-Struktur und fügt einen Konstruktor hinzu, der Schlüsselfelder sowie [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) Zugriffsmethode initialisiert.  
  
## Syntax  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Fügt einer Eigenschaft zum Eigenschafts\-ID\-Satz hinzu.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Konstruktor.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|Legt den GUID des Eigenschafts\-ID\-Satzes fest.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cdbpropidset-operator-equal.md)|Weist den Inhalt einer Eigenschafts\-ID zu, die auf anderen festgelegt wird.|  
  
## Hinweise  
 OLE DB\-Consumer\-Verwendungs\- **DBPROPIDSET**\-Strukturen, um eines Arrays Eigenschaften\-IDs übergeben, für die der Consumer Eigenschafteninformationen abrufen möchte.  Die Eigenschaften, die in einer einzelnen [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx)\-Struktur identifiziert werden, gehören einem Eigenschaft.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)