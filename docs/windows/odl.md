---
title: ODL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.odl
dev_langs:
- C++
helpviewer_keywords:
- odl attribute
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ca2f8135ead802e0486cdffc7b3e3a64140f6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375980"
---
# <a name="odl"></a>odl

Gibt eine Schnittstelle als Schnittstelle Objekt Description Language (ODL). Der MIDL-Compiler ist nicht erforderlich. die **Odl** Attributgruppen; es wird nur für die Kompatibilität mit älteren ODL-Dateien erkannt.

## <a name="syntax"></a>Syntax

```cpp
[odl]
```

## <a name="remarks"></a>Hinweise

Die **Odl** C++-Attribut hat die gleiche Funktionalität wie die [Odl](/windows/desktop/Midl/odl) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_odl.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLIb")];

[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyInterface
{
   HRESULT x();
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
class cmyClass : public IMyInterface
{
public:
   HRESULT x(){}
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Schnittstellenattribut](../windows/interface-attributes.md)  