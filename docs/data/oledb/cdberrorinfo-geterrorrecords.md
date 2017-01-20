---
title: "CDBErrorInfo::GetErrorRecords"
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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