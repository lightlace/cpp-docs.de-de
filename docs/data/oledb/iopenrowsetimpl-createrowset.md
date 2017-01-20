---
title: "IOpenRowsetImpl::CreateRowset"
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
  - "IOpenRowsetImpl.CreateRowset"
  - "IOpenRowsetImpl::CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset-Methode"
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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