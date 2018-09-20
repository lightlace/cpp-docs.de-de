---
title: Defaultcollelem | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultcollelem
dev_langs:
- C++
helpviewer_keywords:
- defaultcollelem attribute
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b65cb8c9fb5f46568d5449b3e54157f63a16b3e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422531"
---
# <a name="defaultcollelem"></a>defaultcollelem

Für die Optimierung für Visual Basic-Code verwendet.

## <a name="syntax"></a>Syntax

```cpp
[defaultcollelem]
```

## <a name="remarks"></a>Hinweise

Die **Defaultcollelem** C++-Attribut hat die gleiche Funktionalität wie die [Defaultcollelem](/windows/desktop/Midl/defaultcollelem) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt eine Schnittstelle-Methode mit dem **Defaultcollelem** Attribut:

```cpp
// cpp_attr_ref_defaultcollelem.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyForm
{
   [propget, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([in] long nSize);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)  