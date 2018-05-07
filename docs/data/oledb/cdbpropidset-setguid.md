---
title: 'Cdbpropidset:: SetGuid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87878b6cc7ae38f2c9ffcf597a56ab020d8e9c8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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