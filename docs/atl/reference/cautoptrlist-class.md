---
title: CAutoPtrList Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs: C++
helpviewer_keywords: CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 79ca570b8f4534287ae4ec40167de3bc3d947139
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cautoptrlist-class"></a>CAutoPtrList-Klasse
Diese Klasse enthält Methoden, die hilfreich beim Erstellen einer Liste von intelligenten Zeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Parameter  
 `E`  
 Der Zeigertyp.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Der Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor bereit, und leitet Sie Methoden aus [CAtlList](../../atl/reference/catllist-class.md) und [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) für die Erstellung eines List-Objekts, das Speichern von intelligenten Zeigern verwendet. Die Klasse [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) bietet eine ähnliche Funktion für ein Arrayobjekt.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 Der Konstruktor.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße hat den Standardwert 10.  
  
### <a name="remarks"></a>Hinweise  
 Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlList-Klasse](../../atl/reference/catllist-class.md)   
 [CAutoPtrElementTraits-Klasse](../../atl/reference/cautoptrelementtraits-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
