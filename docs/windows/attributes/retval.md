---
title: Retval (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 4ac6b72095620a3e857f2877d776e91b273e8f33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566646"
---
# <a name="retval"></a>retval

Legt fest, den Parameter, der den Rückgabewert des Members empfängt.

## <a name="syntax"></a>Syntax

```cpp
[retval]
```

## <a name="remarks"></a>Hinweise

Die **Retval** C++-Attribut hat die gleiche Funktionalität wie die [Retval](/windows/desktop/Midl/retval) MIDL-Attribut.

**Retval** muss für das letzte Argument in einer Funktion Deklaration angezeigt werden.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) für ein Beispiel für die Verwendung von **Retval**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter, für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**out**|
|**Ungültige Attribute**|**in**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)