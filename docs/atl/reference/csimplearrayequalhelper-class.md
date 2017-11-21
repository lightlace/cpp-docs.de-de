---
title: CSimpleArrayEqualHelper Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs: C++
helpviewer_keywords: CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d53e09c64aa19b4e843297b64bad132c64a75a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statisch) Prüft zwei `CSimpleArray` -Objekt Elementen auf Gleichheit.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur der `CSimpleArray` Klasse. Es bietet eine Methode für Vergleichen von zwei Elementen gespeichert ein `CSimpleArray` Objekt. Standardmäßig werden die Elemente verglichen, mit **operator=()**, aber wenn das Array komplexen Datentypen, die keine eigene Gleichheitsoperator enthält, benötigen Sie diese Klasse zu überschreiben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
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
