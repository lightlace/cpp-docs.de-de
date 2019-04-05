---
title: Vi_progid (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: 7050543c9acf3801a99d3e32e119325900bdb050
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033588"
---
# <a name="viprogid"></a>vi_progid

Gibt eine Art versionsunabhängige Programm-ID an.

## <a name="syntax"></a>Syntax

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parameter

*Name*<br/>
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
|**Betrifft**|**class**, **struct**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Programm-ID-Schlüssel](/windows/desktop/com/-progid--key)
