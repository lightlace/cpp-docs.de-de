---
title: "CArrayRowset::operator"
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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