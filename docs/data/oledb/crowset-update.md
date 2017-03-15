---
title: "CRowset::Update | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset.Update"
  - "ATL.CRowset.Update"
  - "ATL.CRowset<TAccessor>.Update"
  - "ATL::CRowset<TAccessor>::Update"
  - "CRowset<TAccessor>::Update"
  - "CRowset::Update"
  - "CRowset<TAccessor>.Update"
  - "ATL::CRowset::Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Updatemethode"
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sendet alle ausstehenden Änderungen, die der aktuellen Zeile seit dem letzten Sammeln oder der **Aktualisieren** Aufruf auf ihm vorgenommen werden.  
  
## Syntax  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### Parameter  
 `pcRows`  
 \[out\] Ein Zeiger zum Speicherort, in dem die **Aktualisieren** der Anzahl von Zeilen zurückgibt, die, versucht sie aktualisieren, nach Bedarf.  
  
 `phRow`  
 \[out\] Ein Zeiger versuchte dem Speicherort, an den **Aktualisieren** das Handle die Zeile es zurückgibt, zu aktualisieren.  Kein Handle wird zurückgegeben, wenn der `phRow` NULL ist.  
  
 `pStatus`  
 \[out\] Ein Zeiger dem Speicherort, an den **Aktualisieren** das Zeilenstatuswert zurückgibt.  Kein Status wird zurückgegeben, wenn der `pStatus` NULL ist.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Sendet alle ausstehenden Änderungen, die seit dem der aktuellen Zeile vorgenommen werden, die Zeile zuletzt abgerufen oder aktualisiert wurde \(mit **Aktualisieren** oder [UpdateAll](../../data/oledb/crowset-updateall.md)\).  Normalerweise rufen Sie [SetData](../../data/oledb/crowset-setdata.md) auf, um Datenwerte in den Spalten einer Zeile festzulegen und dann **Aktualisieren** auf, um diese Änderungen zu senden.  
  
 Diese Methode erfordert die optionale `IRowsetUpdate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetUpdate** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)