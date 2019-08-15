---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 19f28963a18abf42c6f629ac0f6491628387aa6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490998"
---
# <a name="custom-c"></a>custom (C++)

Definiert Metadaten für ein Objekt in der Typbibliothek.

## <a name="syntax"></a>Syntax

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Parameter

*uuid*<br/>
Eine eindeutige ID.

*value*<br/>
Ein Wert, der in eine Variante eingefügt werden kann.

## <a name="remarks"></a>Hinweise

Das **benutzerdefinierte** C++ Attribut bewirkt, dass Informationen in die Typbibliothek eingefügt werden. Sie benötigen ein Tool, das den benutzerdefinierten Wert aus der Typbibliothek liest.

Das **benutzerdefinierte** Attribut verfügt über die gleiche Funktionalität wie das [benutzerdefinierte](/windows/win32/Midl/custom) Attribut "Mittel l".

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Nicht-com- **Schnittstelle**, **Klasse**, Enumeration `idl_module` s, Methoden, Schnittstellenmember, Schnittstellenparameter, **typedef**s, **Union**s, **Struktur**s|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|**Co-Klasse** (bei Verwendung in der-Klasse)|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)