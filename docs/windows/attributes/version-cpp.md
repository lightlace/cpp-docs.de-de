---
title: Version (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 9a432267632b1f2a716a833a485b182cd93a27e2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514877"
---
# <a name="version-c"></a>version (C++)

Identifiziert eine bestimmte Version in mehreren Versionen einer Klasse.

## <a name="syntax"></a>Syntax

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parameter

*version*<br/>
Die Versionsnummer von `coclass`. Wenn nichts angegeben wird, wird 1,0 in die IDL-Datei eingefügt.

## <a name="remarks"></a>Hinweise

Das **Versions** C++ Attribut verfügt über die gleiche Funktionalität wie das runl-Attribut der [Version](/windows/win32/Midl/version) und wird an die generierte IDL-Datei übermittelt.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der- **Version**finden Sie im [bindbare](bindable.md) -Beispiel.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[Klassenattribute](class-attributes.md)