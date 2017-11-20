---
title: CAutoPtrArray Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs: C++
helpviewer_keywords: CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 952f6a6d9fa06c0f0c34e5769b4302c6230abb43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
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