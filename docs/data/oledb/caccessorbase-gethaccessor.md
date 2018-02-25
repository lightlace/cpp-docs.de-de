---
title: 'CAccessorBase:: Gethaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27bdf0058c2152f8797be54b28eeee7ac3e21135
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Ruft die Accessorhandle für einen angegebenen Accessor ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Zahl 0 (null)-Offset für den Accessor.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Accessorhandle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAccessorBase-Klasse](../../data/oledb/caccessorbase-class.md)