---
title: iid_is (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 8bfa20f55afd85019795fdd40548158c2f49e126
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514659"
---
# <a name="iid_is"></a>iid_is

Gibt die IID der COM-Schnittstelle an, auf die durch einen Schnittstellen Zeiger gezeigt wird.

## <a name="syntax"></a>Syntax

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parameter

*expression*<br/>
Ein C-sprach Ausdruck, der eine IID einer COM-Schnittstelle angibt, auf die von einem Schnittstellen Zeiger gezeigt wird.

## <a name="remarks"></a>Hinweise

Das **iid_is** C++ -Attribut verfügt über die gleiche Funktionalität wie das [iid_is](/windows/win32/Midl/iid-is) -Mittell-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Verwendung von **iid_is**:

```cpp
// cpp_attr_ref_iid_is.cpp
// compile with: /LD
#include "wtypes.h"
#include "unknwn.h"
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]
   IUnknown ** ppvObject);
};

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter, Datenmember|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)