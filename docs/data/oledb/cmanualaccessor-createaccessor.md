---
title: "CManualAccessor::CreateAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::CreateAccessor"
  - "CreateAccessor"
  - "ATL.CManualAccessor.CreateAccessor"
  - "CManualAccessor.CreateAccessor"
  - "CManualAccessor::CreateAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateAccessor-Methode"
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::CreateAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt Spaltenbindung für die strukturierte und initialisiert die Spaltendatenmembern Speicher.  
  
## Syntax  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### Parameter  
 `nBindEntries`  
 \[in\] Anzahl.  Dieser Wert sollte die Anzahl der Aufrufe an die [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)\-Funktion anpassen.  
  
 `pBuffer`  
 \[in\] Ein Zeiger auf den Puffer, in dem die Ausgabespalten gespeichert werden.  
  
 `nBufferSize`  
 \[in\] Die Größe des Puffers in Bytes.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Rufen Sie diese Funktion, bevor Sie die Funktion `CManualAccessor::AddBindEntry` aufrufen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer\-Beispiel](../../top/visual-cpp-samples.md)