---
title: Version (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee79fca8784ade6509cfc5854eaaa165b68edee0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791966"
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

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[Klassenattribute](class-attributes.md)  