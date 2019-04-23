---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 227e67696e679452a9c6c0e18c04e3d918f7a93f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029433"
---
# <a name="custom-c"></a>custom (C++)

Definiert die Metadaten für ein Objekt in der Typbibliothek.

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
Ein Wert, der in eine Variante platziert werden kann.

## <a name="remarks"></a>Hinweise

Die **benutzerdefinierte** C++-Attribut bewirkt, dass die Informationen in der Typbibliothek versetzt werden soll. Sie benötigen ein Tool, das den benutzerdefinierten Wert aus der Typbibliothek liest.

Die **benutzerdefinierte** Attribut hat die gleiche Funktionalität wie die [benutzerdefinierte](/windows/desktop/Midl/custom) MIDL-Attribut.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Nicht-COM- **Schnittstelle**, **Klasse**, **Enum**s, `idl_module` Methoden, die Schnittstellenmember, die Parameter für die Benutzeroberfläche, **Typedef**s, **Union**s, **Struktur**s|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|**Co-Klasse** (wenn es sich um eine Klasse verwendet wird)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)