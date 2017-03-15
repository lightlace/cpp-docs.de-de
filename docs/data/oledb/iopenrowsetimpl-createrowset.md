---
title: "IOpenRowsetImpl::CreateRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOpenRowsetImpl.CreateRowset"
  - "IOpenRowsetImpl::CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset-Methode"
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IOpenRowsetImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Rowsetobjekt.  Wird nicht direkt nach Benutzer.  Siehe [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in *der OLE DB\-Programmierreferenz.*  
  
## Syntax  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### Parameter  
 `RowsetClass`  
 Ein Vorlagenklassenmember, der die Rowsetklasse des Benutzers darstellt.  generiert gewöhnlich durch den Assistenten.  
  
 `pRowsetObj`  
 \[out\] Ein Zeiger auf ein Rowsetobjekt.  In der Regel wird dieser Parameter nicht verwendet, aber er kann verwendet werden, wenn mehr Arbeiten auf das Rowset ausführen müssen, bevor sie an ein COM\-Objekt übergeben.  Die Lebensdauer von `pRowsetObj` wird von `ppRowset` gebunden.  
  
 Für weitere Parameter finden Sie unter [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in der *OLE DB\-Programmierreferenz.*  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IOpenRowsetImpl\-Klasse](../../data/oledb/iopenrowsetimpl-class.md)