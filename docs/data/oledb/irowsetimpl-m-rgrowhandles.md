---
title: 'IRowsetImpl:: M_rgrowhandles | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs:
- C++
helpviewer_keywords:
- m_rgRowHandles
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a111325c53c1a774e858477a2030e9a6a0f60564
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplmrgrowhandles"></a>IRowsetImpl::m_rgRowHandles
Eine Zuordnung des Zeilenhandles, die derzeit vom Anbieter als Antwort auf enthaltenen `GetNextRows`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
MapClass  
 m_rgRowHandles;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Zeilenhandles werden entfernt, durch den Aufruf `ReleaseRows`. Finden Sie unter der [IRowsetImpl (Übersicht)](../../data/oledb/irowsetimpl-class.md) für die Definition des *MapClass*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)