---
title: 'CRowset:: Movetoratio | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MoveToRatio
- CRowset<TAccessor>::MoveToRatio
- CRowset::MoveToRatio
- CRowset<TAccessor>.MoveToRatio
- ATL.CRowset.MoveToRatio
- ATL::CRowset::MoveToRatio
- CRowset.MoveToRatio
- ATL.CRowset<TAccessor>.MoveToRatio
- ATL::CRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8515e99b6c249761c3044b566938c29bfc35974f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
Ruft Zeilen ab der ein Bruchteilen Position im Rowset ab.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,bool bForward = true) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nNumerator`  
 [in] Der Zähler, der die Sekundenbruchteile bestimmt mit Feldern fester Breite aus den Daten abgerufen werden sollen.  
  
 `nDenominator`  
 [in] Der Nenner verwendet, um die Sekundenbruchteile bestimmen mit Feldern fester Breite aus den Daten abgerufen werden sollen.  
  
 `bForward`  
 [in] Gibt an, ob vorwärts oder rückwärts verschoben werden soll. Der Standardwert ist weiterleiten.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 `MoveToRatio` Zeilen, die gemäß der folgenden Formel ungefähr abruft:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 wobei `RowsetSize` ist die Größe des Rowsets, gemessen in Zeilen. Die Genauigkeit dieser Formel hängt von dem Anbieter ab. Weitere Informationen finden Sie unter [IRowsetScroll:: GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetScroll`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetScroll** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)