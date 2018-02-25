---
title: 'CBulkRowset:: Movetoratio | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 675d2ec6c9a43e7f5b17acdb0c546e003fd5e986
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
Ruft Zeilen ab der ein Bruchteilen Position im Rowset ab.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nNumerator`  
 [in] Der Zähler verwendet, um die Sekundenbruchteile Position aus der zum Abrufen von Daten zu ermitteln.  
  
 `nDenominator`  
 [in] Der Nenner verwendet, um die Sekundenbruchteile Position aus der zum Abrufen von Daten zu ermitteln.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 `MoveToRatio` die Zeilen gemäß der folgenden Formel ungefähr abruft:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 wobei `RowsetSize` ist die Größe des Rowsets, gemessen in Zeilen. Die Genauigkeit dieser Formel hängt von dem Anbieter ab. Weitere Informationen finden Sie unter [IRowsetScroll:: GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)