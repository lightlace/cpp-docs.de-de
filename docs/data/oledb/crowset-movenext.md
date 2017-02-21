---
title: "CRowset::MoveNext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.MoveNext"
  - "ATL.CRowset.MoveNext"
  - "ATL::CRowset<TAccessor>::MoveNext"
  - "CRowset<TAccessor>.MoveNext"
  - "CRowset.MoveNext"
  - "CRowset<TAccessor>::MoveNext"
  - "CRowset::MoveNext"
  - "ATL::CRowset::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext-Methode"
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt den Cursor zum nächsten Datensatz.  
  
## Syntax  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### Parameter  
 `lSkip`  
 \[in\] Die Anzahl der Zeilen, um vor dem Abrufen zu überspringen.  
  
 `bForward`  
 \[in\] führen Sie **true**, um vorwärts zum nächsten Datensatz zu verschieben, **false**, um sich zu bewegen.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  Wenn das Ende des Rowsets erreicht wurde, gibt **DB\_S\_ENDOFROWSET** zurück.  
  
## Hinweise  
 Ruft die nächste sequenzielle Zeile vom `CRowset`\-Objekt ab und speichert die an vorherigen Position.  Optional können Sie auswählen, dass `lSkip` voran Zeilen zu überspringen oder rückwärts wechseln.  
  
 Diese Methode erfordert, dass Sie die folgenden Eigenschaften, bevor auf dem Tisch **Öffnen** oder der Befehl, der das Rowset enthält aufgerufen werden:  
  
-   **DBPROP\_CANSCROLLBACKWARDS** muss `VARIANT_TRUE` sein wenn `lSkip` \< 0  
  
-   **DBPROP\_CANFETCHBACKWARDS** muss `VARIANT_TRUE` sein wenn `bForward` \= false  
  
 Andernfalls \(wenn `lSkip` \>\= 0 und `bForward` \= true\), müssen Sie, dass keine zusätzlichen Eigenschaften festzulegen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)