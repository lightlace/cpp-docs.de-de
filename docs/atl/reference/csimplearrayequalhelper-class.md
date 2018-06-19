---
title: CSimpleArrayEqualHelper Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6660f72dbd91a41670b3c5f8772d21caf4b8abc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362127"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper-Klasse
Diese Klasse ist ein Hilfsprogramm für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statisch) Prüft zwei `CSimpleArray` -Objekt Elementen auf Gleichheit.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur der `CSimpleArray` Klasse. Es bietet eine Methode für Vergleichen von zwei Elementen gespeichert ein `CSimpleArray` Objekt. Standardmäßig werden die Elemente verglichen, mit **operator=()**, aber wenn das Array komplexen Datentypen, die keine eigene Gleichheitsoperator enthält, benötigen Sie diese Klasse zu überschreiben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual  
 Prüft zwei `CSimpleArray` -Objekt Elementen auf Gleichheit.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Parameter  
 *T1*  
 Ein Objekt vom Typ T.  
  
 *T2*  
 Ein Objekt vom Typ T.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleArray-Klasse](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse-Klasse](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
