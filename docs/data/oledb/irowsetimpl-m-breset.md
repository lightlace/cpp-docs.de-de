---
title: 'IRowsetImpl:: M_breset | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs:
- C++
helpviewer_keywords:
- m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ca38b0fa56f901d18e90d3305c92cc097452369
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
Ein Bitflag verwendet, um zu bestimmen, ob die Cursorposition auf das Rowset definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Consumer ruft [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) mit einem negativen `lOffset` oder *cRows* und `m_bReset` ist "true" `GetNextRows` verschiebt an das Ende des Rowsets. Wenn `m_bReset` wird "falsch", der Consumer erhält einen Fehlercode in Übereinstimmung mit der OLE DB-Spezifikation. Die `m_bReset` Ruft ein Flag festgelegt, um **"true"** Wenn das Rowset zuerst erstellt wird und wenn der Consumer ruft [IRowsetImpl:: RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Ruft festgelegt ist, dass **"false"** beim Aufruf `GetNextRows`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)