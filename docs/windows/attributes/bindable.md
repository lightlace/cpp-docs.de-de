---
title: bindbare (C++ COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.bindable
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
ms.openlocfilehash: 08ecd3e242d1e3601f7a5a3ea54c51a679dca97a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664151"
---
# <a name="bindable"></a>bindable

Gibt an, dass die Eigenschaft die Datenbindung unterstützt.

## <a name="syntax"></a>Syntax

```cpp
[bindable]
```

## <a name="remarks"></a>Hinweise

Die **bindbare** C++-Attribut hat die gleiche Funktionalität wie die [bindbare](/windows/desktop/Midl/bindable) MIDL-Attribut. Können Sie sie auf die definierte Eigenschaften mit dem die [Propget](propget.md), [Propput](propput.md), oder [Propputref](propputref.md) Attribute, oder Sie können eine bindbare Methode manuell definieren.

Die folgenden MFC-Beispiele veranschaulichen die Verwendung der **bindbare**:

- [Steuerelementbeispiele: MFC-basierte ActiveX-Steuerelemente](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [CIRC-Beispiel: ActiveX-Steuerelement](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

- [TESTHELP-Beispiel: ActiveX-Steuerelement mit QuickInfos und Hilfe](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/controls)

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie verwenden können **bindbare** für eine Eigenschaft:

```cpp
// cpp_attr_ref_bindable.cpp
// compile with: /LD
#include <windows.h>
[
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"), dispinterface, helpstring("property demo Interface")
]
__interface IPropDemo : IDispatch {

   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();
};

[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)