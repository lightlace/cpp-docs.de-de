---
title: DefaultValue | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvalue
dev_langs:
- C++
helpviewer_keywords:
- defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4df3f6f72ec7a83186cc3d96b2dda837bdd1cfff
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207995"
---
# <a name="defaultvalue"></a>defaultvalue

Ermöglicht die Angabe eines Standardwerts für einen typisierten optionalen Parameter.

## <a name="syntax"></a>Syntax

```cpp
[ defaultvalue= value ]
```

### <a name="parameters"></a>Parameter

*Wert*  
Der Standardwert für den Parameter.

## <a name="remarks"></a>Hinweise

Die **Defaultvalue** C++-Attribut hat die gleiche Funktionalität wie die [Defaultvalue](/windows/desktop/Midl/defaultvalue) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt eine Schnittstelle-Methode mit dem **Defaultvalue** Attribut:

```cpp
// cpp_attr_ref_defaultvalue.cpp
// compile with: /LD
#include <windows.h>

[export] typedef long HRESULT;
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;

[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),
   dual, oleautomation,
   helpstring("IFireTabCtrl Interface"),
   helpcontext(122), pointer_default(unique) ]

__interface IFireTabCtrl : IDispatch {
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);
   [bindable, propput] HRESULT put_Size([in] int nSize);
};

[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[out](../windows/out-cpp.md)  
[retval](../windows/retval.md)  
[in](../windows/in-cpp.md)  
[pointer_default](../windows/pointer-default.md)  
[unique](../windows/unique-cpp.md)  