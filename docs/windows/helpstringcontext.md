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
ms.openlocfilehash: 47afe841a2a8e4a1c41baf68dfd139a70b320c7d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394464"
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

*contextID*<br/>
Eine 32-Bit-Hilfekontextbezeichner in die **Hilfe** Datei.

## <a name="remarks"></a>Hinweise

Die **Helpstringcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL-Attribut.

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

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Schnittstellenattribut](../windows/interface-attributes.md)<br/>
[Klassenattribute](../windows/class-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)<br/>
[Modul](../windows/module-cpp.md)  