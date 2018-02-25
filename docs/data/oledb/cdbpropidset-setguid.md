---
title: CDBPropIDSet::SetGUID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 807b4cf13c01952ed811e6a7058eaf974e685154
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
Legt die GUID-Feld der **DBPROPIDSET** Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Eine GUID zum Festlegen der **GuidPropertySet** Feld der [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Feld kann festgelegt werden, indem Sie die [Konstruktor](../../data/oledb/cdbpropidset-cdbpropidset.md) ebenfalls. Rufen Sie diese Funktion, wenn Sie den Standardkonstruktor für diese Klasse verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBPropIDSet-Klasse](../../data/oledb/cdbpropidset-class.md)