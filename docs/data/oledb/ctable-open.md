---
title: "CTable::Open"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.CTable.Open"
  - "ATL::CTable::Open"
  - "CTable::Open"
  - "CTable.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CTable::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet die Tabelle.  
  
## Syntax  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### Parameter  
 `session`  
 \[in\] Die Sitzung, für die die Tabelle geöffnet ist.  
  
 *wszTableName*  
 \[in\] der Name der Tabelle zum Öffnen, übergeben als Unicode\-Zeichenfolge.  
  
 *szTableName*  
 \[in\] der Name der Tabelle zum Öffnen, übergeben als ANSI\-Zeichenfolge.  
  
 *dbid*  
 \[in\] **DBID** der Tabelle zum Öffnen.  
  
 *pPropSet*  
 \[in\] strukturiert Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) das Einbinden von festgelegt werden Eigenschaften und Werte.  Siehe [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in *der OLE DB\-Programmierreferenz* in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Der Standardwert NULL keine Eigenschaften an.  
  
 `ulPropSets`  
 \[in\] hat die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen in das *pPropSet*\-Argument.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CTable\-Klasse](../../data/oledb/ctable-class.md)