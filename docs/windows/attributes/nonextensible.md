---
title: nonextensible (C++ COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 332f61148ccf8cb5816e8bd347181ac9d130a730
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512446"
---
# <a name="nonextensible"></a>nonextensible

Gibt an, dass die `IDispatch` -Implementierung enthält nur die Eigenschaften und Methoden aufgeführt, die in der schnittstellenbeschreibung und können nicht zur Laufzeit zusätzliche Member erweitert werden.

## <a name="syntax"></a>Syntax

```cpp
[nonextensible]
```

## <a name="remarks"></a>Hinweise

Die **nonextensible** C++-Attribut hat die gleiche Funktionalität wie die [nonextensible](/windows/desktop/Midl/nonextensible) MIDL-Attribut.

Verwenden von **nonextensible** erfordert außerdem die [Oleautomation](oleautomation.md) Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt eine Verwendung der **nonextensible** Attribut:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`dual` und `oleautomation`, oder `dispinterface`|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)