---
title: "CBookmark-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBookmark"
  - "ATL::CBookmark<nSize>"
  - "CBookmark"
  - "ATL.CBookmark<nSize>"
  - "ATL::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark-Klasse"
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CBookmark-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hält einen Lesezeichenwert in den Puffer an.  
  
## Syntax  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### Parameter  
 `nSize`  
 Die Größe des Lesezeichenpuffers in Bytes.  Wenn `nSize` null ist, wird der Lesezeichenpuffer dynamisch zur Laufzeit erstellt.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|Der Konstruktor|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|Ruft der Zeiger auf den Puffer ab.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Ruft die Größe des Puffers in Bytes ab.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Legt den Lesezeichenwert fest.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cbookmark-operator-equal.md)|Weist eine `CBookmark`\-Klasse für andere zu.|  
  
## Hinweise  
 **CBookmark \<0\>** ist einer Vorlagenspezialisierung von `CBookmark`; sein Puffer kann zur Laufzeit dynamisch erstellt.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)