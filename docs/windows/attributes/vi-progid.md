---
title: Vi_progid (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 468b5c5dcadc1715384684062f203ae9179ef044
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791974"
---
# <a name="viprogid"></a>vi_progid

Gibt eine Art versionsunabhängige Programm-ID an.

## <a name="syntax"></a>Syntax

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parameter

*name*<br/>
Die versionsunabhängigen-ProgID, die das Objekt darstellt.

Versionsabhängige Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.

## <a name="remarks"></a>Hinweise

Die **Vi_progid** C++-Attribut können Sie eine versionsunabhängige ProgID eines COM-Objekts angeben. Eine ProgID hat das Format *name1.name2.version*. Eine versionsunabhängige Programm-ID verfügt nicht über eine *Version*. Es ist möglich, beide geben die `progid` und **Vi_progid** Attribute einer `coclass`. Wenn Sie keinen angeben **Vi_progid**, wird die versionsunabhängige Programm-ID ist der Wert von der [progid](progid.md) Attribut.

**Vi_progid** impliziert die `coclass` -Attributs, d. h. Wenn Sie angeben, **Vi_progid**, es ist dasselbe wie beim Angeben der `coclass` und **Vi_progid** Attribute.

Die **Vi_progid** Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert werden. Der generierten IDL-Datei wird den ProgID-Wert nicht angezeigt werden.

In ATL-Projekte Wenn die [Co-Klasse](coclass.md) Attribut ebenfalls vorhanden ist, wird durch die angegebene ProgID verwendet die `GetVersionIndependentProgID` Funktion (eingefügt, indem die `coclass` Attribut).

## <a name="example"></a>Beispiel

Finden Sie unter den [Co-Klasse](coclass.md) Beispiel für ein Beispiel für die Verwendung von **Vi_progid**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Programm-ID-Schlüssel](/windows/desktop/com/-progid--key)  
