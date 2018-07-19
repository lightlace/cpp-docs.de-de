---
title: CAutoPtrArray Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b99fe8fde475453c9e6dc0b524a6b1b94821bf75
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358950"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray-Klasse
Diese Klasse bietet Methoden, die hilfreich beim Erstellen ein Array von intelligenten Zeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Parameter  
 `E`  
 Der Zeigertyp.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Der Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt einen Konstruktor bereit, und leitet Sie Methoden aus [CAtlArray](../../atl/reference/catlarray-class.md) und [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) für die Erstellung eines Klassenobjekts Auflistung Speichern von intelligenten Zeigern verwendet.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray  
 Der Konstruktor.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den intelligenten Zeiger-Array.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlArray-Klasse](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits-Klasse](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList-Klasse](../../atl/reference/cautoptrlist-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
