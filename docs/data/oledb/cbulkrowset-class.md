---
title: "CBulkRowset-Klasse"
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
  - "ATL::CBulkRowset"
  - "ATL.CBulkRowset"
  - "ATL::CBulkRowset<TAccessor>"
  - "CBulkRowset"
  - "ATL.CBulkRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBulkRowset-Klasse"
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abrufe und bearbeitet Zeilen, um mit Daten in einer Sammeloperation zu arbeiten, indem sie mehrere Zeilenhandles mit einem einzelnen Aufruf abrufen.  
  
## Syntax  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Inkrementiert den Verweiszähler.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Konstruktor.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Ruft die erste Datenzeile ab und übergibt ggf. einen neuen Massenabruf aus.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Wechselt in die letzte Zeile.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Ruft die nächste Zeile der Daten ab.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Wechselt zur vorherigen Zeile.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Ruft die Zeile ab, die von ein Lesezeichen gekennzeichnet oder die Zeile an einem angegebenen Offset von diesem Lesezeichen.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Ruft den Start\- Zeilen aus einer Bruchposition im Rowset.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Stellt die aktuelle Zeile \(**m\_nCurrentRow**\) auf Null und Versionen alle Zeilen.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Legt die Anzahl der durch fest einen Aufruf abgefragt werden Zeilenhandles.|  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der `CBulkRowset`\-Klasse.  
  
 [!CODE [NVC_OLEDB_Consumer#1](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#1)]  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)