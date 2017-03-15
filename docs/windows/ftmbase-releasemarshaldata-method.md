---
title: "FtmBase::ReleaseMarshalData-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseMarshalData-Methode"
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::ReleaseMarshalData-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zerstört ein gemarshalltes Datenpaket.  
  
## Syntax  
  
```  
STDMETHODIMP ReleaseMarshalData(  
   __in IStream *pStm  
) override;  
```  
  
#### Parameter  
 `pStm`  
 Zeiger an einen Stream, der zerstört das werden enthält Datenpaket.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)