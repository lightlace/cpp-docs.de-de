---
title: Standard (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: c6448b00fef50a7654816a2c39af2943db12d314
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024581"
---
# <a name="default-c"></a>default (C++)

Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.

## <a name="syntax"></a>Syntax

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>Parameter

*interface1*<br/>
Die Standardschnittstelle, die für Skriptumgebungen verfügbar gemacht wird, die ein Objekt auf Grundlage der Klasse erstellen, die mit dem **default** -Attribut definiert ist.

Wenn keine Standardschnittstelle angegeben wird, wird das erste Vorkommen einer Nicht-Quellschnittstelle als Standard verwendet.

*interface2*<br/>
(Optional) Die Standard-Quellschnittstelle. Sie müssen diese Schnittstelle auch beim [source](source-cpp.md) -Attribut angeben.

Wenn keine Standard-Quellschnittstelle angegeben ist, wird die erste Quellschnittstelle als Standard verwendet.

## <a name="remarks"></a>Hinweise

Das C++-Attribut **default** hat die gleiche Funktion wie das MIDL-Attribut [default](/windows/desktop/Midl/default) . Das **default** -Attribut wird auch mit dem [case](case-cpp.md) -Attribut verwendet.

## <a name="example"></a>Beispiel

Der folgende code zeigt, wie **Standard** werden auf der Definition einer Co-Klasse angegeben `ICustomDispatch` als Standard-Programmierschnittstelle:

```cpp
// cpp_attr_ref_default.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]
__interface IDual {
   HRESULT Dual([in] long l, [out, retval] long *pLong);
};

[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]
__interface ICustomDispatch : public IDispatch {
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);
};

[   coclass, default(ICustomDispatch), source(IDual), uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")
]
class CClass : public ICustom, public IDual, public ICustomDispatch {
   HRESULT Custom(long l, long *pLong) { return(S_OK); }
   HRESULT Dual(long l, long *pLong) { return(S_OK); }
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }
};

int main() {
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch
   CClass *pClass = new CClass;

   long llong;

   pClass->custom(1, &llong);
   pClass->dual(1, &llong);
   pClass->dispinterface(1, &llong);
   pClass->dispatch(1, &llong);

   delete pClass;
#endif
   return(0);
}
```

Das [source](source-cpp.md) -Attribut weist außerdem ein Beispiel zum Verwenden von **default**auf.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**,-Datenmember|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**Co-Klasse** (bei Anwendung auf **Klasse** oder **Struktur**)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[coclass](coclass.md)