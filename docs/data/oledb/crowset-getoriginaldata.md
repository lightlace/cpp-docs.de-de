---
title: "CRowset::GetOriginalData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.GetOriginalData"
  - "CRowset<TAccessor>::GetOriginalData"
  - "GetOriginalData"
  - "ATL::CRowset<TAccessor>::GetOriginalData"
  - "ATL.CRowset.GetOriginalData"
  - "CRowset::GetOriginalData"
  - "ATL::CRowset::GetOriginalData"
  - "CRowset.GetOriginalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOriginalData-Methode"
ms.assetid: 5b69d30e-34f4-41a4-a82d-cd175be88d53
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::GetOriginalData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aufrufe an **IRowsetUpdate::GetOriginalData**, um die Daten abgerufen von zuletzt abzurufen oder die Datenquelle übertragen.  
  
## Syntax  
  
```  
  
HRESULT GetOriginalData( ) throw( );  
  
```  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode ruft die Daten ab, die zuletzt von abgerufen werden oder die Datenquelle gesendet sind; sie ruft Werte nicht anhand ausstehende Änderungen ab.  
  
 Diese Methode erfordert die optionale `IRowsetUpdate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetUpdate** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx)