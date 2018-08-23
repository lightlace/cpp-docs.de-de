---
title: Helpstringcontext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34aed4325d2e946f59a4f17275d6b0aabe4de06c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589972"
---
# <a name="helpstringcontext"></a>helpstringcontext

Gibt die ID des Hilfethemas in eine .hlp oder CHM-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ helpstringcontext(
   contextID
) ]
```

### <a name="parameters"></a>Parameter

*contextID*  
Eine 32-Bit-Hilfekontextbezeichner in die **Hilfe** Datei.

## <a name="remarks"></a>Hinweise

Die **Helpstringcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object,
   helpstring("help string"),
   helpstringcontext(1),
   uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Schnittstelle**,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[Modul](../windows/module-cpp.md)  