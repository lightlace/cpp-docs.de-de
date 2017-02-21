---
title: "CUtlProps::SetPropValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetPropValue"
  - "ATL::CUtlProps<T>::SetPropValue"
  - "ATL.CUtlProps<T>.SetPropValue"
  - "ATL.CUtlProps.SetPropValue"
  - "CUtlProps::SetPropValue"
  - "CUtlProps<T>::SetPropValue"
  - "CUtlProps.SetPropValue"
  - "CUtlProps<T>.SetPropValue"
  - "ATL::CUtlProps::SetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetPropValue-Methode"
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::SetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt eine Eigenschaft in einem Eigenschaft fest.  
  
## Syntax  
  
```  
  
      HRESULT SetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### Parameter  
 `pguidPropSet`  
 \[in\] die GUID für das PropSet.  
  
 `dwPropId`  
 \[in\] der Eigenschaftenindex.  
  
 `pvValue`  
 \[in\] Ein Zeiger auf eine Variante, die den neuen Eigenschaftswert enthält.  
  
## Rückgabewert  
 `Failure` auf Fehler und `S_OK`, wenn der Vorgang erfolgreich ist.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CUtlProps\-Klasse](../../data/oledb/cutlprops-class.md)