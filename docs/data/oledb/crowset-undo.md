---
title: 'CRowset:: Undo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset.Undo
- ATL::CRowset<TAccessor>::Undo
- CRowset<TAccessor>::Undo
- ATL.CRowset.Undo
- ATL.CRowset<TAccessor>.Undo
- CRowset<TAccessor>.Undo
- ATL::CRowset::Undo
- CRowset::Undo
- Undo
dev_langs:
- C++
helpviewer_keywords:
- Undo method
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1dc12cbb5228afd3ab8750b5a2121247d7d3c901
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetundo"></a>CRowset::Undo
Macht alle Änderungen an einer Zeile seit der letzten Fetch oder [Update](../../data/oledb/crowset-update.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Undo(DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `pcRows`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** gibt die Anzahl der Zeilen, die versucht wurde, rückgängig machen, wenn erforderlich.  
  
 `phRow`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** gibt ein Array von Handles, alle Zeilen, die versucht wurde, rückgängig machen, wenn erforderlich.  
  
 `pStatus`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** den Statuswert Zeile zurückgibt. Es wird kein Status zurückgegeben, wenn `pStatus` ist null.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)