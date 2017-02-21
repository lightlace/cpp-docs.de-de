---
title: "CDataSource::GetInitializationString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::GetInitializationString"
  - "CDataSource.GetInitializationString"
  - "GetInitializationString"
  - "CDataSource::GetInitializationString"
  - "ATL.CDataSource.GetInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInitializationString-Methode"
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataSource::GetInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Initialisierungszeichenfolge einer Datenquelle ab, die gerade geöffnet ist.  
  
## Syntax  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### Parameter  
 *PInitializationString*  
 \[out\] Ein Zeiger auf die Initialisierungszeichenfolge.  
  
 *bIncludePassword*  
 \[in\] **true**, wenn Zeichenfolge ein Kennwort enthält; andernfalls **false**.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Die resultierende Initialisierungszeichenfolge kann verwendet werden, um diese Datenquellenverbindung später erneut zu öffnen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)