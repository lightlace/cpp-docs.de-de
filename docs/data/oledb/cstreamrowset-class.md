---
title: "CStreamRowset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CStreamRowset<TAccessor>"
  - "ATL::CStreamRowset"
  - "CStreamRowset"
  - "ATL.CStreamRowset<TAccessor>"
  - "ATL.CStreamRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset-Klasse"
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CStreamRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird in einer `CCommand` oder `CTable`\-Deklaration.  
  
## Syntax  
  
```  
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Konstruktor.  Instanziiert und initialisiert das `CStreamRowset`\-Objekt.|  
|[Schließen](../../data/oledb/cstreamrowset-close.md)|Gibt den [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) von Schnittstellenzeigern in der Klasse frei.|  
  
## Hinweise  
 Verwenden Sie `CStreamRowset` in der `CCommand``CTable` oder Deklaration, beispielsweise:  
  
 [!CODE [NVC_OLEDB_Consumer#11](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#11)]  
  
 oder  
  
 [!CODE [NVC_OLEDB_Consumer#12](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#12)]  
  
 `ICommand::Execute` gibt ein `ISequentialStream` \- Zeiger zurück, der im `m_spStream` gespeichert wird.  Sie verwenden dann die **Lesen**\-Methode, um die Daten \(Unicode\-Zeichenfolge\) im XML\-Format abzurufen.  Beispiel:  
  
 [!CODE [NVC_OLEDB_Consumer#13](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#13)]  
  
 SQL Server 2000 führt die XML\-Formatierung durch und wird alle Spalten und Zeilen des Rowsets als eine XML\-Zeichenfolge zurück.  
  
> [!NOTE]
>  Diese Funktion ist nur mit SQL Server 2000.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)