---
title: Max_is (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fd90cc386686d78ca7bcb862ab60e079e29832a7
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791707"
---
# <a name="maxis"></a>max_is

Legt fest, den maximalen Wert für ein gültiges Array-Index.

## <a name="syntax"></a>Syntax

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argumentliste Slots sind zulässig.

## <a name="remarks"></a>Hinweise

Die **Max_is** C++-Attribut hat die gleiche Funktionalität wie die [Max_is](/windows/desktop/Midl/max-is) MIDL-Attribut.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|**size_is**|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Beispiel

Finden Sie unter [First_is](first-is.md) ein Beispiel für einen Abschnitt eines Arrays angeben.

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)  