---
title: "CNoRowset-Klasse"
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
  - "ATL.CNoRowset"
  - "ATL::CNoRowset<TAccessor>"
  - "CNoRowset"
  - "ATL.CNoRowset<TAccessor>"
  - "ATL::CNoRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoRowset-Klasse"
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CNoRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kann als Vorlagenargument \(`TRowset`\) für [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md) verwendet werden.  
  
## Syntax  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  Die Standardeinstellung ist `CAccessorBase`.  
  
## Hinweise  
 Verwenden Sie `CNoRowset` als Vorlagenargument, wenn der Befehl keinen Rowset zurückgibt.  
  
 `CNoRowset` implementiert die folgenden Stubmethoden, die jeweils anderen Accessorklassenmethoden entsprechen:  
  
-   **BindFinished** \- gibt an, wenn die Bindung vollständig ist \( `S_OK`\) zurückgibt.  
  
-   **Schließen**\-Versionszeilen und die aktuelle IRowset\-Schnittstelle.  
  
-   `GetIID` \- Ruft die Schnittstellen\-ID eines Verbindungspunktes ab.  
  
-   **GetInterface** \- Ruft eine Schnittstelle ab.  
  
-   `GetInterfacePtr` \- Ruft einen Schnittstellenzeiger Encapsulated ab.  
  
-   **SetAccessor** \- Ruft ein Zeiger auf den Accessor.  
  
-   **SetupOptionalRowsetInterfaces** \- der optionale Schnittstellen Setups für das Rowset.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)