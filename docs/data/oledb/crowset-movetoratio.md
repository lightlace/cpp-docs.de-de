---
title: "CRowset::MoveToRatio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MoveToRatio"
  - "CRowset<TAccessor>::MoveToRatio"
  - "CRowset::MoveToRatio"
  - "CRowset<TAccessor>.MoveToRatio"
  - "ATL.CRowset.MoveToRatio"
  - "ATL::CRowset::MoveToRatio"
  - "CRowset.MoveToRatio"
  - "ATL.CRowset<TAccessor>.MoveToRatio"
  - "ATL::CRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio-Methode"
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Start\- Zeilen aus einer Bruchposition im Rowset.  
  
## Syntax  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### Parameter  
 `nNumerator`  
 \[in\] der Zähler verwendet, um das Bruchpositions von welchem zu bestimmen, die Daten abzurufen.  
  
 `nDenominator`  
 \[in\] der Nenner verwendet, um das Bruchpositions von welchem zu bestimmen, die Daten abzurufen.  
  
 `bForward`  
 \[in\] gibt an, ob vorwärts oder rückwärts verschieben.  Der Standardwert ist vorwärts.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 `MoveToRatio` ruft die Zeilen, die ungefähr der folgenden Formel entsprechen:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 wobei `RowsetSize` die Größe des Rowsets ist, gemessen in Zeilen.  Die Genauigkeit dieser Formel hängt vom bestimmten Anbieter ab.  Ausführliche Informationen finden Sie unter [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Diese Methode erfordert die optionale `IRowsetScroll`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetScroll** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)