---
title: "CManualAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::AddBindEntry"
  - "ATL.CManualAccessor.AddBindEntry"
  - "CManualAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CManualAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry-Methode"
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt einem Bindungseintrag den Ausgabespalten hinzu.  
  
## Syntax  
  
```  
  
      void AddBindEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL   
) throw ( );  
```  
  
#### Parameter  
 Siehe [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 `nOrdinal`  
 \[in\] Spaltennummer.  
  
 `wType`  
 \[in\] Datentyp.  
  
 `nColumnSize`  
 \[in\] Spaltengröße in Bytes.  
  
 `pData`  
 \[in\] Ein Zeiger auf die Daten anderer Spalten gespeichert im Puffer.  
  
 `pLength`  
 \[in\] Ein Zeiger auf die Feldlänge, nach Bedarf.  
  
 `pStatus`  
 \[in\] Ein Zeiger auf den Spaltenstatus gebunden werden Variablen, nach Bedarf.  
  
## Hinweise  
 Um diese Funktion verwenden, müssen Sie zuerst [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md).  Sie können mehr als Einträge die Anzahl nicht hinzufügen angegeben in `CreateAccessor`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer\-Beispiel](../../top/visual-cpp-samples.md)