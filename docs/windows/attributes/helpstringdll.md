---
title: Helpstringdll (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 17e70a54024b8e5a3ab29e2420f60fbf3eec08a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677239"
---
# <a name="helpstringdll"></a>helpstringdll

Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.

## <a name="syntax"></a>Syntax

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Parameter

*string*<br/>
Die DLL zu verwenden, um die Suche nach Dokument auszuführen.

## <a name="remarks"></a>Hinweise

Die **Helpstringdll** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringdll](/windows/desktop/Midl/helpstringdll) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
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
[Methodenattribut](method-attributes.md)