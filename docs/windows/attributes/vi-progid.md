---
title: Vi_progid (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: fbf5ab2bc4263356a1cfcf789865a3f7e286ccd7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514866"
---
# <a name="vi_progid"></a>vi_progid

Gibt eine Versions unabhängige Form der ProgID an.

## <a name="syntax"></a>Syntax

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parameter

*name*<br/>
Die Versions unabhängige ProgID, die das-Objekt darstellt.

ProgIDs stellen eine lesbare Version des Klassen Bezeichners (CLSID) dar, mit der com-/ActiveX-Objekte identifiziert werden.

## <a name="remarks"></a>Hinweise

Mit dem **Vi_progid** C++ -Attribut können Sie eine Versions unabhängige ProgID für ein COM-Objekt angeben. Eine ProgID hat das Format *Name1. name2. Version*. Eine Versions unabhängige ProgID hat keine *Version*. Es ist möglich, sowohl das `progid` -Attribut als auch das **Vi_progid** - `coclass`Attribut in einem anzugeben. Wenn Sie **Vi_progid**nicht angeben, ist die Versions unabhängige ProgID der Wert, der durch das [ProgID](progid.md) -Attribut angegeben wird.

**Vi_progid** impliziert das `coclass` -Attribut, d. h., wenn Sie **Vi_progid**angeben, ist dies dasselbe wie das `coclass` angeben der Attribute und **Vi_progid** .

Das **Vi_progid** -Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert wird. In der generierten IDL-Datei wird der ProgID-Wert nicht angezeigt.

Wenn in ATL-Projekten auch das [Co-Klasse](coclass.md) -Attribut vorhanden ist, wird die angegebene ProgID von der `GetVersionIndependentProgID` Funktion verwendet (eingefügt durch `coclass` das-Attribut).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **Vi_progid**finden Sie unter dem [Co-Klasse](coclass.md) -Beispiel.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[ProgID-Schlüssel](/windows/win32/com/-progid--key)
