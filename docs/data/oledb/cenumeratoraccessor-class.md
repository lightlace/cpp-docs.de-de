---
title: "CEnumeratorAccessor-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CEnumeratorAccessor"
  - "CEnumeratorAccessor"
  - "ATL.CEnumeratorAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumeratorAccessor-Klasse"
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CEnumeratorAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird von [CEnumerator](../../data/oledb/cenumerator-class.md), um Daten vom Enumeratorrowset zuzugreifen.  
  
## Syntax  
  
```  
class CEnumeratorAccessor  
```  
  
## Member  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Eine die Variable, ob der Enumerator ein übergeordneter Enumerator ist, wenn die Zeile ein Enumerator ist.|  
|[m\_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Eine die Variable, dass die Zeile eine Datenquelle oder einen Enumerator beschreibt.|  
|[m\_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|Die Beschreibung der Datenquelle oder des Enumerators.|  
|[m\_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Der Name der Datenquelle oder des Enumerators.|  
|[m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Zeichenfolge, an [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) übergeben, um einen Moniker für die Datenquelle oder den Enumerator zu erhalten.|  
  
## Hinweise  
 Dieses Rowset besteht Datenquellen und den Enumeratoren, die vom aktuellen Enumerator sichtbar sind.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)