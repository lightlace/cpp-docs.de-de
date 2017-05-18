---
title: Klasse CComHeapPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0e5196a98b8fd76b2e7e791fd2cd9549099a1cc9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheapptr-class"></a>CComHeapPtr-Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von Heap Zeiger.  
  
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
 `CComHeapPtr`leitet sich von `CHeapPtr`, verwendet jedoch [CComAllocator](../../atl/reference/ccomallocator-class.md) Speicher mithilfe von COM-Routinen. Finden Sie unter [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) für die Methoden zur Verfügung.  
  
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
 Der Heapzeiger kann optional erstellt werden unter Verwendung einer vorhandenen `CComHeapPtr` Objekt. Wenn dies der Fall ist, die neue `CComHeapPtr` Objekt übernimmt die Verantwortung für die Verwaltung der neue Zeiger und Ressourcen.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase-Klasse](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator-Klasse](../../atl/reference/ccomallocator-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

