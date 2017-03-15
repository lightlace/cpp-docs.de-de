---
title: "IErrorRecordsImpl::GetErrorSource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl.GetErrorSource"
  - "GetErrorSource"
  - "IErrorRecordsImpl::GetErrorSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorSource-Methode"
ms.assetid: 5436f1ce-c5a4-403b-a62b-c58e70e5c925
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetErrorSource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Quellcode ab, der den Fehler aus einem Fehlerdatensatz verursacht hat.  
  
## Syntax  
  
```  
  
      LPOLESTR GetErrorSource(  
   ERRORINFO& rCurError   
);  
```  
  
#### Parameter  
 `rCurError`  
 Ein `ERRORINFO` Datensatz in einer **IErrorInfo**\-Schnittstelle.  
  
## Rückgabewert  
 Zeiger auf eine Zeichenfolge, die den Quellcode für den Fehler enthält.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IErrorRecordsImpl\-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)