---
title: "CRowset::SetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.SetData"
  - "SetData"
  - "ATL::CRowset::SetData"
  - "CRowset<TAccessor>.SetData"
  - "CRowset::SetData"
  - "ATL.CRowset.SetData"
  - "CRowset.SetData"
  - "CRowset<TAccessor>::SetData"
  - "ATL::CRowset<TAccessor>::SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData-Methode"
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt Datenwerte in einer oder mehreren Spalten einer Zeile fest.  
  
## Syntax  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### Parameter  
 `nAccessor`  
 \[in\] Die Anzahl der für den Zugriff verwendet Accessor, auf die Daten.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Für das Formular `SetData`, das keine Argumente akzeptiert, werden alle Accessoren zum Aktualisieren verwendet.  Sie in der Regel rufen **SetData**  auf, um Datenwerte in den Spalten einer Zeile festzulegen, und rufen [Aktualisieren](../../data/oledb/crowset-update.md) auf, um diese Änderungen zu senden.  
  
 Diese Methode erfordert die optionale `IRowsetChange`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetChange** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 Der Einstellungsvorgang könnte fehlschlagen, wenn eine oder mehrere Spalten nicht möglich ist.  Ändern Sie die Cursorzuordnung, um diesen Fehler zu beheben.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)