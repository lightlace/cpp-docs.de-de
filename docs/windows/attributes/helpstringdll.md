---
title: Helpstringdll (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringdll
dev_langs:
- C++
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdac159baf51d7143083eb1369d1a83233f0f022
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791181"
---
# <a name="helpstringdll"></a>helpstringdll

Gibt den Namen der DLL zu verwenden, um die Suche nach Dokument (Lokalisierung) ausführen.

## <a name="syntax"></a>Syntax

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Parameter

*string*<br/>
Die DLL zu verwenden, um die Suche nach Dokument auszuführen.

## <a name="remarks"></a>Hinweise

Die **Helpstringdll** C++-Attribut hat die gleiche Funktionalität wie die [Helpstringdll](/windows/desktop/Midl/helpstringdll) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
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

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)  