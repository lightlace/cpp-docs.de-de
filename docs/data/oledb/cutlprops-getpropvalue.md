---
title: "CUtlProps::GetPropValue"
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
  - "CUtlProps::GetPropValue"
  - "CUtlProps.GetPropValue"
  - "GetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPropValue-Methode"
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::GetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft eine Eigenschaft aus einem Eigenschaft ab.  
  
## Syntax  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
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
 \[out\] Ein Zeiger auf eine Variante, die den neuen Eigenschaftswert enthält.  
  
## Rückgabewert  
 `Failure` auf Fehler und `S_OK`, wenn der Vorgang erfolgreich ist.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CUtlProps\-Klasse](../../data/oledb/cutlprops-class.md)