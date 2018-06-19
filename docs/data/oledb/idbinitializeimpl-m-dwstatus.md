---
title: 'Idbinitializeimpl:: M_dwstatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
dev_langs:
- C++
helpviewer_keywords:
- m_dwStatus
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6bf195a314189232b197709d7d6c6e0c4ac405f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102562"
---
# <a name="idbinitializeimplmdwstatus"></a>IDBInitializeImpl::m_dwStatus
Datenquellen-Flags.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
DWORD m_dwStatus;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Flags angeben, oder geben den Status der verschiedenen Attribute für das Datenquellenobjekt. Enthält eine oder mehrere der folgenden `enum` Werte:  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|**DSF_MASK_INIT**|Eine Maske zum Aktivieren der Wiederherstellung von nicht initialisierten Status.|  
|**DSF_PERSIST_DIRTY**|Festlegen Sie, wenn das Datenquellenobjekt Persistenz erfordert (d. h., wenn Änderungen vorgenommen wurden).|  
|**DSF_INITIALIZED**|Legen Sie die Datenquelle initialisiert wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBInitializeImpl-Klasse](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)