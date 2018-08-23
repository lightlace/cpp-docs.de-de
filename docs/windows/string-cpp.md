---
title: Zeichenfolge (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb3a57cec78c0ea02e16edd890d2a66362bfc011
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594868"
---
# <a name="string-c"></a>string (C++)

Gibt an, dass das eindimensionale **Char**, **"wchar_t"**, `byte` (oder Äquivalent) Array oder der Zeiger auf ein solches Array muss als Zeichenfolge behandelt werden.

## <a name="syntax"></a>Syntax

```cpp
[string]
```

## <a name="remarks"></a>Hinweise

Die **Zeichenfolge** C++-Attribut hat die gleiche Funktionalität wie die [Zeichenfolge](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit **Zeichenfolge** auf eine Schnittstelle und eine Typdefinition:

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
|**Betrifft**|Array oder Zeiger auf ein Array, das Parameter für die, die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Arrayattribute](../windows/array-attributes.md)  
[export](../windows/export.md)  