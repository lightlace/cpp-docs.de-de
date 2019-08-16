---
title: retval (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 2a2865c1eda229f1a2fcd457c22119b2908c1caa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514045"
---
# <a name="retval"></a>retval

Gibt den Parameter an, der den Rückgabewert des Members empfängt.

## <a name="syntax"></a>Syntax

```cpp
[retval]
```

## <a name="remarks"></a>Hinweise

Das **retval** C++ -Attribut verfügt über die gleiche Funktionalität wie das " [retval](/windows/win32/Midl/retval) "-Attribut "Mittel l".

**retval** muss für das letzte Argument in der Deklaration einer Funktion angezeigt werden.

## <a name="example"></a>Beispiel

Eine Beispiel Verwendung von **retval**finden Sie im Beispiel für [bindbare](bindable.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**out**|
|**Ungültige Attribute**|**in**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)