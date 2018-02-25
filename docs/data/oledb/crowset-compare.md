---
title: 'CRowset:: Compare | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>.Compare
- CRowset<TAccessor>::Compare
- ATL.CRowset<TAccessor>.Compare
- ATL::CRowset<TAccessor>::Compare
- CRowset.Compare
- ATL::CRowset::Compare
- ATL.CRowset.Compare
- CRowset::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d77c24847a58bace5ff5aca8276dc605811ab7a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetcompare"></a>CRowset::Compare
Vergleicht zwei Lesezeichen mit [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Compare(const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *Bookmark1*  
 [in] Das erste zu vergleichende Lesezeichen.  
  
 *Bookmark2*  
 [in] Das zweite zu vergleichende Lesezeichen.  
  
 `pComparison`  
 [out] Ein Zeiger auf das Ergebnis des Vergleichs.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetLocate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetLocate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
 Informationen zur Verwendung von Lesezeichen in Consumer finden Sie unter [mithilfe von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)