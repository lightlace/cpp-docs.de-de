---
title: "CRowset::GetRowStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset.GetRowStatus"
  - "ATL.CRowset<TAccessor>.GetRowStatus"
  - "ATL::CRowset<TAccessor>::GetRowStatus"
  - "CRowset::GetRowStatus"
  - "ATL::CRowset::GetRowStatus"
  - "CRowset<TAccessor>::GetRowStatus"
  - "ATL.CRowset.GetRowStatus"
  - "CRowset<TAccessor>.GetRowStatus"
  - "GetRowStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowStatus-Methode"
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::GetRowStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Status aller Zeilen zurück.  
  
## Syntax  
  
```  
  
      HRESULT GetRowStatus(   
   DBPENDINGSTATUS* pStatus    
) const throw( );  
```  
  
#### Parameter  
 `pStatus`  
 \[out\] Ein Zeiger an einen Speicherort, an dem `GetRowStatus` den Statuswert zurückgibt.  Siehe DBPENDINGSTATUS im OLE DB\-Programmierreferenz.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale `IRowsetUpdate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetUpdate** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)