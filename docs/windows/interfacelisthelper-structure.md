---
title: InterfaceListHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: ae9bf9d9c1301c142f94cb23cf6b0c2774f79bb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464778"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>Parameter

*T0*<br/>
Template-Parameter 0 (null) ist erforderlich.

*T1*<br/>
Template-Parameter 1, die standardmäßig nicht angegeben wird.

*T2*<br/>
Vorlagenparameter 2, die standardmäßig nicht angegeben wird. Der dritte Vorlagenparameter.

*T3*<br/>
Template-Parameter 3, die standardmäßig nicht angegeben wird.

*T4*<br/>
Vorlagenparameter 4, die standardmäßig nicht angegeben wird.

*T5*<br/>
Template-Parameter 5, die standardmäßig nicht angegeben wird.

*T6*<br/>
Vorlagenparameter 6, die standardmäßig nicht angegeben wird.

*T7*<br/>
Vorlagenparameter 7, die standardmäßig nicht angegeben wird.

*T8*<br/>
Vorlagenparameter 8, die standardmäßig nicht angegeben wird.

*T9*<br/>
Vorlagenparameter 9, die standardmäßig nicht angegeben wird.

## <a name="remarks"></a>Hinweise

Erstellt eine `InterfaceList` Typs rekursiv die angegebenen Parameter Vorlagenargumente angewendet.

Die **InterfaceListHelper** Vorlage verwendet die Template-Parameter *T0* definieren Sie das erste Element der Daten in eine `InterfaceList` -Struktur, und klicken Sie dann rekursiv gilt die  **InterfaceListHelper** Vorlage, um alle verbleibenden Vorlagenparameter. **InterfaceListHelper** wird beendet, wenn keine verbleibenden Vorlagenparameter vorhanden sind.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`TypeT`|Ein Synonym für den InterfaceList-Typ.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InterfaceListHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)