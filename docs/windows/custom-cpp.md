---
title: Benutzerdefiniert (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec3ba8280ab481211d98c9dc5256c94e76e193e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396442"
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

*Wert*<br/>
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

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Eigenständige Attribute](../windows/stand-alone-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](../windows/parameter-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)<br/>
[Klassenattribute](../windows/class-attributes.md)<br/>
[Schnittstellenattribut](../windows/interface-attributes.md)  