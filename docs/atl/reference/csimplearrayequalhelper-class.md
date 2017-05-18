---
title: Klasse CSimpleArrayEqualHelper | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
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
ms.openlocfilehash: 4a87879683257c66de5fe4e720dd29fa4c47031d
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper-Klasse
Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statisch) Prüft zwei `CSimpleArray` Objektelemente hinsichtlich ihrer Gleichheit.|  
  
## <a name="remarks"></a>Hinweise  
 Diese "traits"-Klasse ist eine Ergänzung zu den `CSimpleArray` Klasse. Es bietet eine Methode für das Vergleichen von zwei Elementen gespeicherten in ein `CSimpleArray` Objekt. Standardmäßig werden die Elemente verglichen, mit **operator=()**, aber wenn das Array komplexe Datentypen, die keine eigene Gleichheitsoperator enthält, benötigen Sie diese Klasse überschrieben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 Prüft zwei `CSimpleArray` Objektelemente hinsichtlich ihrer Gleichheit.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Parameter  
 *T1*  
 Ein Objekt vom Typ "t".  
  
 *T2*  
 Ein Objekt vom Typ "t".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Elemente gleich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleArray-Klasse](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse-Klasse](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

