---
title: "CArrayRowset::operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CArrayRowset::operator[]"
  - "CArrayRowset.operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[]-Operator, Arrays"
  - "[]-Operator"
  - "[]-Operator, Arrays"
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CArrayRowset::operator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt arrayähnliche Syntax für den Zugriff auf eine Zeile im Rowset bereit.  
  
## Syntax  
  
```  
  
      TAccessor  
      & operator[](int nRow);  
```  
  
#### Parameter  
 `TAccessor`  
 Ein auf Vorlagen basierenden Parameter, der den Typ angibt Accessor, gespeicherten im Rowset.  
  
 `nRow`  
 \[in\] Zahl der Zeile \(Arrayelement\), das Sie zugreifen möchten.  
  
## Rückgabewert  
 Der Inhalt der angeforderten Zeile.  
  
## Hinweise  
 Wenn `nRow` die Anzahl der Zeilen im Rowset überschreitet, wird eine Ausnahme ausgelöst.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CArrayRowset\-Klasse](../../data/oledb/carrayrowset-class.md)