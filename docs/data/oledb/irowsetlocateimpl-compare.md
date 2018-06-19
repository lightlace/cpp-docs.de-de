---
title: 'IRowsetLocateImpl:: Compare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 208f912e92045daec36066e1dcc06fc38b5a8ed2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105282"
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