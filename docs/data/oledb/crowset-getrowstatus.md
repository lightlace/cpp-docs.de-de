---
title: 'CRowset:: GetRowStatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset.GetRowStatus
- ATL.CRowset<TAccessor>.GetRowStatus
- ATL::CRowset<TAccessor>::GetRowStatus
- CRowset::GetRowStatus
- ATL::CRowset::GetRowStatus
- CRowset<TAccessor>::GetRowStatus
- ATL.CRowset.GetRowStatus
- CRowset<TAccessor>.GetRowStatus
- GetRowStatus
dev_langs:
- C++
helpviewer_keywords:
- GetRowStatus method
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3e3a0fb71a06a407a80a98717af53da926436f57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097158"
---
# <a name="crowsetgetrowstatus"></a>CRowset::GetRowStatus
Gibt den Status aller Zeilen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetRowStatus(DBPENDINGSTATUS* pStatus) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `pStatus`  
 [out] Ein Zeiger auf einen Speicherort, in dem `GetRowStatus` den Statuswert zurückgibt. Finden Sie in der OLE DB Programmer's Reference DBPENDINGSTATUS.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)