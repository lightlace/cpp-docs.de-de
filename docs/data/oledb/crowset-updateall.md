---
title: "CRowset::UpdateAll"
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
  - "CRowset::UpdateAll"
  - "ATL.CRowset.UpdateAll"
  - "CRowset<TAccessor>.UpdateAll"
  - "ATL.CRowset<TAccessor>.UpdateAll"
  - "UpdateAll"
  - "CRowset.UpdateAll"
  - "ATL::CRowset<TAccessor>::UpdateAll"
  - "CRowset<TAccessor>::UpdateAll"
  - "ATL::CRowset::UpdateAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UpdateAll-Methode"
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::UpdateAll
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sendet alle ausstehenden Änderungen, die an allen Zeilen seit dem letzten Sammeln oder der **Aktualisieren** Aufruf auf ihm vorgenommen werden.  
  
## Syntax  
  
```  
  
      HRESULT UpdateAll(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL    
) throw( );  
```  
  
#### Parameter  
 `pcRows`  
 \[out\] Ein Zeiger zum Speicherort, wobei `UpdateAll` der Anzahl von Zeilen zurückgibt, die, versucht sie aktualisieren, nach Bedarf.  
  
 `pphRow`  
 \[out\] Ein Zeiger versuchte im Speicher, in dem `UpdateAll` das Handle die Zeile es zurückgibt, zu aktualisieren.  Kein Handle wird zurückgegeben, wenn der `pphRow` NULL ist.  
  
 `ppStatus`  
 \[out\] Ein Zeiger dem Speicherort, an den **Aktualisieren** das Zeilenstatuswert zurückgibt.  Kein Status wird zurückgegeben, wenn der `ppStatus` NULL ist.  
  
## Hinweise  
 Sendet alle ausstehenden Änderungen, die an allen Zeilen vorgenommen werden, da diese Zeilen zuletzt mit [Aktualisieren](../../data/oledb/crowset-update.md) oder `UpdateAll` abgerufen oder aktualisiert wurden.  `UpdateAll` aktualisiert jede Zeile, die geändert, unabhängig davon, ob Sie noch das Handle für diese \(siehe `pphRow`\) oder nicht haben.  
  
 Wenn Sie verwendete **Einfügen**, um von fünf Zeilen in einem Rowset, einzufügen Sie entweder **Aktualisieren** fünfmal aufrufen oder `UpdateAll` einmal aufrufen können, um alle zu aktualisieren.  
  
 Diese Methode erfordert die optionale `IRowsetUpdate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetUpdate** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)