---
title: 'IRowsetLocateImpl:: Compare | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 83c115e866aab8e2d2e34a601d805dc43311a0b8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
Vergleicht zwei Lesezeichen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Compare )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Eines der Textmarke kann ein Standard OLE DB-definierten [standard Lesezeichen](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST**, **DBBMK_LAST**, oder **DBBMK_INVALID**). Der zurückgegebene Wert in `pComparison` gibt die Beziehung zwischen den zwei Lesezeichen:  
  
-   **DBCOMPARE_LT** (`cbBookmark1` ist, bevor Sie `cbBookmark2`.)  
  
-   **DBCOMPARE_EQ** (`cbBookmark1` gleich `cbBookmark2`.)  
  
-   **DBCOMPARE_GT** (`cbBookmark1` ist nach `cbBookmark2`.)  
  
-   **DBCOMPARE_NE** (Lesezeichen sind gleich und nicht sortiert.)  
  
-   **DBCOMPARE_NOTCOMPARABLE** (das Lesezeichen können nicht verglichen werden.)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetLocateImpl-Klasse](../../data/oledb/irowsetlocateimpl-class.md)