---
title: Out (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 15b82ddca42f9b70ac16538cea19f8aedd799c05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574446"
---
# <a name="out-c"></a>out (C++)

Gibt die Zeigerparameter an, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben werden (vom Server an den Client).

## <a name="syntax"></a>Syntax

```cpp
[out]
```

## <a name="remarks"></a>Hinweise

Das C++-Attribut **out** hat die gleiche Funktion wie das MIDL-Attribut [out](/windows/desktop/Midl/out-idl) .

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von [bindable](bindable.md) finden Sie im Beispiel für **out**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[ID](id.md)