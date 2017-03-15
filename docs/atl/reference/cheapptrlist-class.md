---
title: Klasse CHeapPtrList | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CHeapPtrList
- CHeapPtrList
- ATL.CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 9acf18d0e0a72f27a335cefca81341c95d530ae5
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrlist-class"></a>CHeapPtrList-Klasse
Diese Klasse enthält Methoden, die hilfreich beim Erstellen einer Liste von.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>Parameter  
 `E`  
 Der Objekttyp in der Auflistungsklasse gespeichert werden.  
  
 `Allocator`  
 Die Speicher-Allocation-Klasse verwenden. Der Standardwert ist [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Der Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor bereit und leitet Sie Methoden von [CAtlList](../../atl/reference/catllist-class.md) und [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) zur Unterstützung der Erstellung eines Klassenobjekts Auflistung Heap Zeiger gespeichert.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namecheapptrlista--cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList  
 Der Konstruktor.  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 Die Blockgröße ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlList-Klasse](../../atl/reference/catllist-class.md)   
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits-Klasse](../../atl/reference/cheapptrelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

