---
title: Quelle (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccd5f5220a49ddb63554b4c3b96533a3066d4d4b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214592"
---
# <a name="source-c"></a>source (C++)

Gibt an für eine Klasse das COM-Objekt-Schnittstellen für Verbindungspunkte aus. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.

## <a name="syntax"></a>Syntax

```cpp
[ source(
   interfaces
) ]
```

### <a name="parameters"></a>Parameter

*interfaces*  
Eine oder mehrere Schnittstellen, die Sie angeben, wenn Sie die Quelle anwenden Attribut auf eine Klasse. Dieser Parameter wird nicht verwendet werden, wenn Quelle auf eine Eigenschaft oder Methode angewendet wird.

## <a name="remarks"></a>Hinweise

Die **Quelle** C++-Attribut hat die gleiche Funktionalität wie die [Quelle](/windows/desktop/Midl/source) MIDL-Attribut.

Können Sie die [Standard](../windows/default-cpp.md) Attribut, um die Standard-Quellschnittstelle für ein Objekt anzugeben.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, **Schnittstelle**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`coclass` (wenn es sich um eine Klasse oder Struktur angewendet wird)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[coclass](../windows/coclass.md)  