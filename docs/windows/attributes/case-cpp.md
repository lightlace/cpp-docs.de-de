---
title: Fall (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: b3058f2fe6f35e1b11d4790780cb0fcdcaada706
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148435"
---
# <a name="case-c"></a>case (C++)

Verwendung der [Switch_type](switch-type.md) -Attribut in einer **Union**.

## <a name="syntax"></a>Syntax

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parameter

*value*<br/>
Geben Sie ein möglicher Wert für die Sie verarbeiten möchten. Der Typ des **Wert** kann eine der folgenden Typen:

- `int`

- `char`

- `boolean`

- `enum`

oder ein Bezeichner eines solchen Typs.

## <a name="remarks"></a>Hinweise

Die **Fall** C++-Attribut hat die gleiche Funktionalität wie die **Fall** MIDL-Attribut. Dieses Attribut wird nur verwendet, mit der [Switch_type](switch-type.md) Attribut.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung der der **Fall** Attribut:

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Mitglied einer **Klasse** oder **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Klassenattribute](class-attributes.md)