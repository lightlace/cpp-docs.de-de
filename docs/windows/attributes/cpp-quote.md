---
title: cpp_quote (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 905c9fc41b1b42dffe9c7b39fae0b096cdc24950
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501769"
---
# <a name="cpp_quote"></a>cpp_quote

Gibt die angegebene Zeichenfolge ohne Anführungszeichen in der generierten IDL-Datei aus.

## <a name="syntax"></a>Syntax

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Parameter

*statement*<br/>
Eine C-Anweisung.

## <a name="remarks"></a>Hinweise

Das **cpp_quote** C++ -Attribut ist nützlich, wenn Sie eine Präprozessordirektive in eine IDL-Datei einfügen möchten.

Sie können auch **cpp_quote** verwenden und eine h-Datei als Teil der Mittell-Kompilierung generieren. Wenn Sie z. b. über C++ eine Header Datei verfügen C++ , die IDL-Attribute verwendet, diese Datei jedoch nicht für eine Aufgabe verwenden kann, können Sie Sie kompilieren, um eine von der Mittel l generierte h-Datei zu erstellen, die Sie verwenden können.

Das **cpp_quote** -Attribut verfügt über die gleiche Funktionalität wie das [cpp_quote](/windows/win32/Midl/cpp-quote) -Mittell-Attribut.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **cpp_quote**finden Sie im Beispiel für [Dual](dual.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)