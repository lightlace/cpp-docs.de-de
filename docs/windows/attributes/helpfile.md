---
title: HelpFile (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 538cdbb38ac525cfee03a641f3e62e22a69f8e2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501552"
---
# <a name="helpfile"></a>helpfile

Legt den Namen der Hilfedatei für eine Typbibliothek fest.

## <a name="syntax"></a>Syntax

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der Datei, die die Hilfe Themen enthält.

## <a name="remarks"></a>Hinweise

Das **HelpFile** C++ -Attribut verfügt über die gleiche Funktionalität wie das Mittel l-Attribut [HelpFile](/windows/win32/Midl/helpfile) .

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **HelpFile**finden Sie im Beispiel für das [Modul](module-cpp.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **typedef**, **Klasse**, Methode, **Eigenschaft**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)