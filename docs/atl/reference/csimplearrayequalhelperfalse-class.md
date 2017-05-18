---
title: Klasse CSimpleArrayEqualHelperFalse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: cd5ed7058194880ef1ceaebe788e3deb60d4ac8e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse-Klasse
Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statisch) Gibt False zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese "traits"-Klasse ist eine Ergänzung der `CSimpleArray` Klasse. IT immer gibt "false", und darüber hinaus ruft `ATLASSERT` mit dem Argument False, wenn es jemals verwiesen wird. In Situationen, in denen der Gleichheitstest auf nicht ausreichend definiert ist, ermöglicht diese Klasse ein Array mit Elementen, um eine klar definierte Weise für Methoden, die für Vergleiche, wie z. B. abhängen tritt jedoch ordnungsgemäß für die meisten Methoden [CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find).  
  
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
 Diese Methode immer "false" zurückgibt und ruft `ATLASSERT` mit dem Argument False, wenn auf die verwiesen wird. Der Zweck der `CSimpleArrayEqualHelperFalse::IsEqual` besteht darin, erzwingen Methoden mit Vergleiche in einer klar definierten Weise fehlschlägt, wenn Tests auf Gleichheit nicht angemessen definiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleArrayEqualHelper-Klasse](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

