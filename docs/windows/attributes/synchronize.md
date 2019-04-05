---
title: Synchronisieren von (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: ea5236b887fb0df2a0acdd1e4050c66a4719072b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037049"
---
# <a name="synchronize"></a>synchronize

Synchronisiert den Zugriff auf die Zielmethode.

## <a name="syntax"></a>Syntax

```cpp
[synchronize]
```

## <a name="remarks"></a>Hinweise

Die **synchronisieren** C++-Attribut implementiert die Unterstützung für die Zielmethode eines Objekts zu synchronisieren. Synchronisierung kann mehrere Objekte, die eine gemeinsame Ressource (z. B. eine Methode einer Klasse) verwendet, indem Sie steuern den Zugriff auf die Zielmethode.

Der Code, der von diesem Attribut eingefügt aufruft, die richtigen `Lock` -Methode (bestimmt durch das threading-Modell) zu Beginn der Zielmethode. Wenn die Methode beendet wird, `Unlock` wird automatisch aufgerufen. Weitere Informationen zu diesen Funktionen finden Sie unter [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

Dieses Attribut erfordert, dass die Attribute [coclass](coclass.md), [progid](progid.md), oder [vi_progid](vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Z. B. wenn `progid` angewendet wird, `vi_progid` und `coclass` werden ebenfalls angewendet.

## <a name="example"></a>Beispiel

Der folgende Code stellt die Synchronisierung für die `UpdateBalance` Methode der `CMyClass` Objekt.

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|, Klassenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)