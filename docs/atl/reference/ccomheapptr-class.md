---
title: CComHeapPtr Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs: C++
helpviewer_keywords: CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d851e2c6fb4892bd65cf26ea747a6b99a8006cee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomheapptr-class"></a>CComHeapPtr-Klasse
Ein intelligenter Zeiger-Klasse zum Verwalten von Heaps Zeiger.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp, auf dem Heap gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Der Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
 `CComHeapPtr`leitet sich von `CHeapPtr`, verwendet jedoch [CComAllocator](../../atl/reference/ccomallocator-class.md) mit COM-Routinen Arbeitsspeicher belegt werden. Finden Sie unter [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) für die verfügbaren Methoden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 Der Konstruktor.  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Ein vorhandenes `CComHeapPtr`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Heapzeiger kann optional mithilfe eines vorhandenen erstellt werden `CComHeapPtr` Objekt. Wenn dies der Fall ist, die neue `CComHeapPtr` Objekt übernimmt die Verantwortung für die Verwaltung der neue Zeiger und der Ressourcen.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase-Klasse](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator-Klasse](../../atl/reference/ccomallocator-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
