---
title: lokal (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 377d6ffbddb5f88533c8b4f054f0d658a9b19573
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489088"
---
# <a name="local-c"></a>local (C++)

Wenn in der Kopfzeile der Schnittstelle verwendet wird, können Sie Sie den MIDL-Compiler als ein Header-Generator zu verwenden. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.

## <a name="syntax"></a>Syntax

```cpp
[local]
```

## <a name="remarks"></a>Hinweise

Die **lokalen** C++-Attribut hat die gleiche Funktionalität wie die [lokalen](/windows/desktop/Midl/local) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [Call_as](call-as.md) ein Beispiel zur Verwendung für **lokalen**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`dispinterface`|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[call_as](call-as.md)