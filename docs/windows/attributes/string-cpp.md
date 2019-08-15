---
title: String (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 978f1f546c0df8de4ff167ddf5ddf724feb31b6e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514004"
---
# <a name="string-c"></a>string (C++)

Gibt an, dass das eindimensionale **char**-, `byte` **wchar_t**-, (oder äquivalente) Array oder der Zeiger auf ein solches Array als Zeichenfolge behandelt werden muss.

## <a name="syntax"></a>Syntax

```cpp
[string]
```

## <a name="remarks"></a>Hinweise

Das **String** C++ -Attribut verfügt über die gleiche Funktionalität wie das-Attribut der- [Zeichenfolge](/windows/win32/Midl/string) .

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie die **Zeichenfolge** für eine Schnittstelle und für eine typedef verwenden:

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Array oder Zeiger auf ein Array, Schnittstellenparameter, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Arrayattribute](array-attributes.md)<br/>
[export](export.md)