---
title: Cpp_quote (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 378435ced5a541785b7b32bc9d2f408034d5a2d8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024678"
---
# <a name="cppquote"></a>cpp_quote

Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.

## <a name="syntax"></a>Syntax

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Parameter

*Anweisung*<br/>
Eine C#-Anweisung.

## <a name="remarks"></a>Hinweise

Die **Cpp_quote** C++-Attribut ist nützlich, wenn es sich bei eine Präprozessordirektive in einer IDL-Datei aufgenommen werden soll.

Sie können auch **Cpp_quote** und eine h-Datei als Teil der Kompilierung von MIDL generiert werden soll. Z. B. Wenn Sie eine C++-Headerdatei, die C++-IDL-Attribute verwendet, aber verwenden Sie diese Datei kann nicht für eine Aufgabe verfügen, können Sie kompilieren es dann zum Erstellen einer MIDL-generierten h-Datei, die Sie verwenden können sollen.

Die **Cpp_quote** Attribut hat die gleiche Funktionalität wie die [Cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [dual](dual.md) verwenden Sie ein Beispiel mit **Cpp_quote**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)