---
title: local (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 853331ce191f8fe41d5967d2d625a3dac8543a4d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514414"
---
# <a name="local-c"></a>local (C++)

Wenn Sie im Schnittstellen Header verwendet wird, können Sie den Mittel l-Compiler als Header Generator verwenden. Gibt bei Verwendung in einer einzelnen Funktion eine lokale Prozedur an, für die keine stubals generiert werden.

## <a name="syntax"></a>Syntax

```cpp
[local]
```

## <a name="remarks"></a>Hinweise

Das **lokale** C++ Attribut verfügt über die gleiche Funktionalität wie das [lokale](/windows/win32/Midl/local) Attribut "Mittel l".

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **local**finden Sie unter [Call_as](call-as.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|`dispinterface`|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[call_as](call-as.md)