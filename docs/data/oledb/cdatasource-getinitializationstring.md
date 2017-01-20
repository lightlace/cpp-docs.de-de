---
title: "CDataSource::GetInitializationString"
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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