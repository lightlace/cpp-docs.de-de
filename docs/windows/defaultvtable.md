---
title: Defaultvtable | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bbbc225e4fee1aba380694fc3b39a7f59e1a294
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611485"
---
# <a name="defaultvtable"></a>defaultvtable

Definiert eine Schnittstelle als die standardmäßige Vtable-Schnittstelle für ein COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ defaultvtable(
   interface
) ]
```

### <a name="parameters"></a>Parameter

*interface*  
Die angegebene-Schnittstelle, die Sie die Standard-Vtable für das COM-Objekt möchten.

## <a name="remarks"></a>Hinweise

Die **Defaultvtable** C++-Attribut hat die gleiche Funktionalität wie die [Defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL-Attribut.

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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  