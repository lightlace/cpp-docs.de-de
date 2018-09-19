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
ms.openlocfilehash: 848ea415d0638b6135c69cd14e442f45dab40237
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220360"
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

*uuid*  
Eine eindeutige ID.

*Wert*  
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

[IDL-Attribute](../windows/idl-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  