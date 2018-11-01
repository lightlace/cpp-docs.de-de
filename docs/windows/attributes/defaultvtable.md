---
title: Defaultvtable (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 40f901345601193db9752ea6c6dca980ded0625d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579932"
---
# <a name="defaultvtable"></a>defaultvtable

Definiert eine Schnittstelle als die standardmäßige Vtable-Schnittstelle für ein COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>Parameter

*interface*<br/>
Die angegebene-Schnittstelle, die Sie die Standard-Vtable für das COM-Objekt möchten.

## <a name="remarks"></a>Hinweise

Die **Defaultvtable** C++-Attribut hat die gleiche Funktionalität wie die [Defaultvtable](/windows/desktop/Midl/defaultvtable) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Attribute für eine Klasse, mit denen **Defaultvtable** eine Standardschnittstelle an:

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)