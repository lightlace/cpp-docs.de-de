---
title: "CManualAccessor::CreateParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::CreateParameterAccessor"
  - "ATL.CManualAccessor.CreateParameterAccessor"
  - "CManualAccessor.CreateParameterAccessor"
  - "CreateParameterAccessor"
  - "CManualAccessor::CreateParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateParameterAccessor-Methode"
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CManualAccessor::CreateParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt für die Parameterbindung strukturiert und initialisiert die Parameterdatenmember Speicher.  
  
## Syntax  
  
```  
  
      HRESULT CreateParameterAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### Parameter  
 `nBindEntries`  
 \[in\] Anzahl.  
  
 `pBuffer`  
 \[in\] Ein Zeiger auf den Puffer, in dem die Eingabespalten gespeichert werden.  
  
 `nBufferSize`  
 \[in\] Die Größe des Puffers in Bytes.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Sie müssen diese Funktion aufrufen, bevor Sie [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md) aufrufen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)   
 [CManualAccessor::AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)