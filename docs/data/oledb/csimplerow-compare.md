---
title: "CSimpleRow::Compare"
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
  - "CSimpleRow.Compare"
  - "CSimpleRow::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare-Methode"
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Zeilen, um zu sehen, wenn sie dieselbe Zeile zugreifen.  
  
## Syntax  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### Parameter  
 `pRow`  
 Ein Zeiger auf ein `CSimpleRow`\-Objekt.  
  
## Rückgabewert  
 Ein `HRESULT`\-Wert, normalerweise `S_OK`, den zwei Zeilen angezeigt wurden durch dieselbe Zeile, oder **S\_FALSE**, den zwei Zeilen anzugeben sind unterschiedlich.  Siehe [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in *der OLE DB\-Programmierreferenz* für weitere mögliche Rückgabewerte.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CSimpleRow\-Klasse](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)