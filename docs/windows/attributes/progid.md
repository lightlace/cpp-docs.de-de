---
title: ProgID (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: d529d7362dc62207cfd72576159f560a3e04c221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514248"
---
# <a name="progid"></a>progid

Gibt die ProgID für ein COM-Objekt an.

## <a name="syntax"></a>Syntax

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parameter

*name*<br/>
Die ProgID, die das-Objekt darstellt.

ProgIDs stellen eine lesbare Version des Klassen Bezeichners (CLSID) dar, mit der com-/ActiveX-Objekte identifiziert werden.

## <a name="remarks"></a>Hinweise

Mit dem **ProgID** C++ -Attribut können Sie die ProgID für ein COM-Objekt angeben. Eine ProgID hat das Format *Name1. name2. Version*. Wenn Sie keine *Version* für eine ProgID angeben, ist die Standardversion 1. Wenn Sie *Name1. name2*nicht angeben, lautet der Standardname *ClassName. ClassName*. Wenn Sie keine **ProgID** angeben und angeben `vi_progid`, werden *Name1. name2* von `vi_progid` und die (nächste sequenzielle Nummer) Version angehängt.

Wenn ein Attribut Block, der **ProgID** verwendet, nicht auch **UUID**verwendet, prüft der Compiler die Registrierung, um festzustellen, ob für die angegebene **ProgID**eine **UUID** vorhanden ist. Wenn **ProgID** nicht angegeben ist, wird die Version (und der Co-Klassenname beim Erstellen einer Co-Klasse) verwendet, um eine **ProgID**zu generieren.

**ProgID** impliziert das `coclass` -Attribut, d. h., wenn Sie **ProgID**angeben, entspricht dies dem Angeben der `coclass` **ProgID** -Attribute und.

Das **ProgID** -Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert wird. In der generierten IDL-Datei wird der **ProgID** -Wert nicht angezeigt.

Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Zusätzlich zum obigen Verhalten werden die mit diesem Attribut angegebenen Informationen in der `GetProgID` Funktion verwendet, die durch das `coclass` Attribut eingefügt wird. Weitere Informationen finden Sie unter dem [Co-Klasse](coclass.md) -Attribut.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **ProgID**finden Sie im Beispiel für die [Co-Klasse](coclass.md) .

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
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID-Schlüssel](/windows/win32/com/-progid--key)
