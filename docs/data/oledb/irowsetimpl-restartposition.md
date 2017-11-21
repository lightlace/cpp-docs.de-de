---
title: 'IRowsetImpl:: RestartPosition | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs: C++
helpviewer_keywords: RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28aeb5548235fc49c8dd4c412e2a27eaa38a02d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Positioniert die nächste Abrufposition auf seine anfängliche Position; erstellt, d. h. seine Position, die bei der Erstinstallation des Rowsets.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowset:: RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Die Rowsetposition ist nicht definiert, bis **GetNextRow** aufgerufen wird. Sie können verschieben rückwärts in einem Rowet durch Aufrufen von `RestartPosition` , und klicken Sie dann Rückwärtsbildlauf oder-Abruf der Abwärtskompatibilität vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)