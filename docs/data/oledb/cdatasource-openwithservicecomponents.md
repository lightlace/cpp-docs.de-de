---
title: "CDataSource::OpenWithServiceComponents | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::OpenWithServiceComponents"
  - "OpenWithServiceComponents"
  - "CDataSource.OpenWithServiceComponents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithServiceComponents-Methode"
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDataSource::OpenWithServiceComponents
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet ein Datenquellenobjekt mithilfe der Dienstkomponenten in „oledb32.dll“.  
  
## Syntax  
  
```  
  
        HRESULT OpenWithServiceComponents (  
   const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
HRESULT OpenWithServiceComponents (  
   LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
```  
  
#### Parameter  
 `clsid`  
 \[in\] Die **CLSID** des Datenanbieters.  
  
 `szProgID`  
 \[in\] Programm\-ID eines Datenanbieters.  
  
 `pPropset`  
 \[in\] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen mit festzulegenden Eigenschaften und Werten.  Weitere Informationen finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Wenn das Datenquellenobjekt initialisiert wird, müssen die Eigenschaften zur Eigenschaftsquelle „Datenquelle“ gehören.  Wenn dieselbe Eigenschaft mehrfach in `pPropset` angegeben wird, ist es anbieterspezifisch, welcher Wert verwendet wird.  Wenn `ulPropSets` 0 ist, wird dieser Parameter ignoriert.  
  
 `ulPropSets`  
 \[in\] Die Anzahl der im *pPropSet*\-Argument übergebenen [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen.  Wenn dies 0 ist, ignoriert der Anbieter `pPropset`.  
  
## Rückgabewert  
 Ein Standard `HRESULT`\-Objekt.  
  
## Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfeatures wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  Weitere Informationen finden Sie unter „OLE DB\-Dienste“ in der OLE DB\-Programmierreferenz unter [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)