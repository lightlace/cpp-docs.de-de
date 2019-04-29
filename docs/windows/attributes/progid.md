---
title: ProgID (C++ COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 5b0c688ad4d9b607cc1f5fb6b1c6d536a1c7888e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407431"
---
# <a name="progid"></a>progid

Gibt an, die ProgID für ein COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parameter

*name*<br/>
Die ProgID, die das Objekt darstellt.

Versionsabhängige Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.

## <a name="remarks"></a>Hinweise

Die **progid** C++-Attribut können Sie angeben, die ProgID für ein COM-Objekt. Eine ProgID hat das Format *name1.name2.version*. Wenn Sie keinen angeben einer *Version* für ProgID, die Standardversion ist 1. Wenn Sie keinen angeben *name1.name2*, der Standardname lautet *classname.classname*. Wenn Sie keinen angeben **progid** angegeben `vi_progid`, *name1.name2* stammen aus `vi_progid` und die (nächste laufende Nummer) Version angefügt wird.

Wenn ein Attributblock, die verwendet **progid** nicht gleichzeitig verwenden **Uuid**, der Compiler überprüft die Registrierung, um festzustellen, ob eine **Uuid** vorhanden ist, für den angegebenen **progid** . Wenn **progid** nicht angegeben ist, wird die Version (und den Namen der Co-Klasse, sofern es sich bei eine Co-Klasse zu erstellen) verwendet werden, generieren eine **progid**.

**ProgID** impliziert die `coclass` -Attributs, d. h. Wenn Sie angeben, **progid**, es ist dasselbe wie beim Angeben der `coclass` und **progid** Attribute.

Die **progid** Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert werden. Der generierten IDL-Datei wird nicht angezeigt. die **progid** Wert.

Wenn dieses Attribut in einem Projekt, das ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Mit diesem Attribut angegebene Informationen werden zusätzlich zu den oben beschriebenen Verhalten in der `GetProgID` Funktion eingefügt werden, indem die `coclass` Attribut. Weitere Informationen finden Sie unter den [Co-Klasse](coclass.md) Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Co-Klasse](coclass.md) für ein Beispiel für die Verwendung von **progid**.

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
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Programm-ID-Schlüssel](/windows/desktop/com/-progid--key)
