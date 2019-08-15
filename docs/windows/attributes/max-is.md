---
title: Max_is (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: f2e6db997891817620c1b2c1f70cb310818dd346
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514430"
---
# <a name="max_is"></a>max_is

Legt den maximalen Wert für einen gültigen Array Index fest.

## <a name="syntax"></a>Syntax

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Parameter

*expression*<br/>
Mindestens ein C-sprach Ausdruck. Leere Argument Slots sind zulässig.

## <a name="remarks"></a>Hinweise

Das **Max_is** C++ -Attribut verfügt über die gleiche Funktionalität wie das [Max_is](/windows/win32/Midl/max-is) -Mittell-Attribut.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Feld in **Struktur** oder **Union**, Schnittstellenparameter, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|**size_is**|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Beispiel

Ein Beispiel für die Angabe eines Abschnitts eines Arrays finden Sie unter [First_is](first-is.md) .

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)