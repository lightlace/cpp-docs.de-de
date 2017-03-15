---
title: "CDBErrorInfo::GetErrorRecords | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo.GetErrorRecords"
  - "ATL.CDBErrorInfo.GetErrorRecords"
  - "ATL::CDBErrorInfo::GetErrorRecords"
  - "GetErrorRecords"
  - "CDBErrorInfo::GetErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorRecords-Methode"
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBErrorInfo::GetErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Fehlerdatensätze für das angegebene Objekt ab.  
  
## Syntax  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### Parameter  
 *pUnk*  
 \[in\] schließen Sie das Objekt an, damit das Fehlerdatensätze abruft.  
  
 `iid`  
 \[in\] die IID der Schnittstelle zugeordnet mit dem Fehler.  
  
 *pcRecords*  
 \[out\] Ein Zeiger auf \(1\-basierte\) Anzahl von Fehlerdatensätzen.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Verwenden Sie das erste Formular der Funktion, wenn Sie überprüfen möchten, dem Sie verbinden, um zu der die Fehlerinformationen aus.  Andernfalls verwenden Sie das zweite Format.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBErrorInfo\-Klasse](../../data/oledb/cdberrorinfo-class.md)