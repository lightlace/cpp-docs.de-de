---
title: Helpstringcontext (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: a6df5b63291fbc54d6c12a116fccd8372e8ced9a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026109"
---
# <a name="helpstringcontext"></a>helpstringcontext

Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Parameter

*contextID*<br/>
Eine 32-Bit-Hilfekontextbezeichner in die **Hilfe** Datei.

## <a name="remarks"></a>Hinweise

Die **Helpstringcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Schnittstelle**,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[module](module-cpp.md)