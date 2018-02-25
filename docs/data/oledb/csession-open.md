---
title: 'CSession:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7ab796d19c45959aac608de5097e9112bd8543e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="csessionopen"></a>CSession::Open
Öffnet eine neue Sitzung für das Datenquellenobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ds`  
 [in] Die Datenquelle für die ist die Sitzung geöffnet werden.  
  
 *pPropSet*  
 [in] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen, die Eigenschaften und Werten festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
 `ulPropSets`  
 [in] Die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen zu übergeben, der *DBPROPSET* Argument.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen die Datenquelle Objekt mit öffnen [CDataSource:: Open](../../data/oledb/cdatasource-open.md) vor der Übergabe an `CSession::Open`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CSession-Klasse](../../data/oledb/csession-class.md)