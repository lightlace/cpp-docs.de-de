---
title: Propget (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 495c6e974bbe226a77d5685c7d1d8adb29e30830
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645999"
---
# <a name="propget"></a>propget

Gibt eine Eigenschaft Accessor-Funktion.

## <a name="syntax"></a>Syntax

```cpp
[propget]
```

## <a name="remarks"></a>Hinweise

Die **Propget** C++-Attribut hat die gleiche Funktionalität wie die [Propget](/windows/desktop/Midl/propget) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) für ein Beispiel für die Verwendung von **Propget**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`propput`, `propputref`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)