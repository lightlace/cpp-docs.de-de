---
title: Iid_is (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: b91fb7937bb0e20f2500eace9695bc0ddba21b26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409524"
---
# <a name="iidis"></a>iid_is

Gibt die IID für die COM-Schnittstelle, die einen Schnittstellenzeiger einen verweist.

## <a name="syntax"></a>Syntax

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parameter

*expression*<br/>
Ein Ausdruck der C-Sprache, der eine IID einer COM-Schnittstelle angibt, auf einen Schnittstellenzeiger zeigt.

## <a name="remarks"></a>Hinweise

Die **Iid_is** C++ Attribut hat die gleiche Funktionalität wie die [Iid_is](/windows/desktop/Midl/iid-is) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Verwendung von **Iid_is**:

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
|**Betrifft**|Schnittstellenparameter,-Datenmember|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)