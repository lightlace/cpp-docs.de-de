---
title: Version (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: a46a2f9b18a45e7ea627488881b0289e733ddd7b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608966"
---
# <a name="version-c"></a>version (C++)

Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.

## <a name="syntax"></a>Syntax

```cpp
[ version(
   "version"
) ]
```

### <a name="parameters"></a>Parameter

*version*  
Die Versionsnummer der `coclass`. Wenn nicht angegeben, wird 1.0 in der IDL-Datei platziert werden.

## <a name="remarks"></a>Hinweise

Die **Version** C++-Attribut hat die gleiche Funktionalität wie die [Version](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL-Attribut, und wird in der generierten IDL-Datei übergeben.

## <a name="example"></a>Beispiel

Finden Sie unter den [bindbare](../windows/bindable.md) Beispiel für ein Beispiel für die Verwendung von **Version**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  