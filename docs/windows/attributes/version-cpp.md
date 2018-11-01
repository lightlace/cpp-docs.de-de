---
title: Version (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 01c4cca846326d237fdacd19187a44e21bd15913
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519313"
---
# <a name="version-c"></a>version (C++)

Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.

## <a name="syntax"></a>Syntax

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parameter

*version*<br/>
Die Versionsnummer der `coclass`. Wenn nicht angegeben, wird 1.0 in der IDL-Datei platziert werden.

## <a name="remarks"></a>Hinweise

Die **Version** C++-Attribut hat die gleiche Funktionalität wie die [Version](/windows/desktop/Midl/version) MIDL-Attribut, und wird in der generierten IDL-Datei übergeben.

## <a name="example"></a>Beispiel

Finden Sie unter den [bindbare](bindable.md) Beispiel für ein Beispiel für die Verwendung von **Version**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[Klassenattribute](class-attributes.md)