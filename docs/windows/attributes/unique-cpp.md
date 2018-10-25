---
title: eindeutige (C++ COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.unique
dev_langs:
- C++
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca5d2da5dc06b1cdf0e999939fcb110608ff3359
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062683"
---
# <a name="unique-c"></a>unique (C++)

Gibt einen eindeutigen Zeiger.

## <a name="syntax"></a>Syntax

```cpp
[unique]
```

## <a name="remarks"></a>Hinweise

Die **eindeutige** C++-Attribut hat die gleiche Funktionalität wie die [eindeutige](/windows/desktop/Midl/unique) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter den [Ref](ref-cpp.md) Beispiel für ein Beispiel für die Verwendung von **eindeutige**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**TypeDef**, **Struktur**, **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)