---
title: 'CDBPropSet:: SetGuid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 140bc76968780efff826ccc42343f27b2cd2eae6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093999"
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
Legt die **GuidPropertySet** -Feld in der **DBPROPSET** Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Eine GUID zum Festlegen der **GuidPropertySet** Feld der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Feld kann festgelegt werden, indem Sie die [Konstruktor](../../data/oledb/cdbpropset-cdbpropset.md) ebenfalls.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBPropSet-Klasse](../../data/oledb/cdbpropset-class.md)