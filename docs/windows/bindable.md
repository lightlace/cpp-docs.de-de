---
title: Bindbare | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.bindable
dev_langs:
- C++
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aedfde2559e79d400b3fc16dd998f3f282c282bf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388146"
---
# <a name="bindable"></a>bindable

Gibt an, dass die Eigenschaft die Datenbindung unterstützt.

## <a name="syntax"></a>Syntax

```cpp
[bindable]
```

## <a name="remarks"></a>Hinweise

Die **bindbare** C++-Attribut hat die gleiche Funktionalität wie die [bindbare](/windows/desktop/Midl/bindable) MIDL-Attribut. Können Sie sie auf die definierte Eigenschaften mit dem die [Propget](../windows/propget.md), [Propput](../windows/propput.md), oder [Propputref](../windows/propputref.md) Attribute, oder Sie können eine bindbare Methode manuell definieren.

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
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),
   dispinterface,
   helpstring("property demo Interface")  
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

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)<br/>
[defaultbind](../windows/defaultbind.md)<br/>
[displaybind](../windows/displaybind.md)<br/>
[immediatebind](../windows/immediatebind.md)<br/>
[requestedit](../windows/requestedit.md)  