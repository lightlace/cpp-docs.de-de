---
title: CSimpleArrayEqualHelperFalse Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs: C++
helpviewer_keywords: CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28d43b6a83842373c2fc169ce43022f1912c4e0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse-Klasse
Diese Klasse ist ein Hilfsprogramm für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statisch) Gibt "false".|  
  
## <a name="remarks"></a>Hinweise  
 Diese Merkmalklasse ist eine Ergänzung der `CSimpleArray` Klasse. IT immer gibt "false", und darüber hinaus ruft `ATLASSERT` mit dem Argument "false", wenn es jemals verwiesen wird. In Situationen, in denen der Gleichheitstest auf ist nicht ausreichend definiert, kann diese Klasse ein Array mit Elementen, um für die meisten Methoden ordnungsgemäß ausgeführt werden, aber in einer klar definierten Weise für Methoden, die für Vergleiche, wie z. B. abhängen fehl [CSimpleArray:: Suchen](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 Gibt false zurück.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt false zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode immer "false" zurückgegeben, und rufen `ATLASSERT` mit dem Argument "false", wenn auf die verwiesen wird. Der Zweck der `CSimpleArrayEqualHelperFalse::IsEqual` wird gezwungen Methoden mit, dass Vergleiche in einer klar definierten Weise fehl, wenn Gleichheitstests nicht adäquat definiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleArrayEqualHelper-Klasse](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
