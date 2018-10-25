---
title: Size_is (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.size_is
dev_langs:
- C++
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6cbcc63e2fb9cadb576ec8272809b523a1138707
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063613"
---
# <a name="sizeis"></a>size_is

Geben Sie die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.

## <a name="syntax"></a>Syntax

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Die Größe des Arbeitsspeichers für Größe Zeiger.

## <a name="remarks"></a>Hinweise

Die **Size_is** C++-Attribut hat die gleiche Funktionalität wie die [Size_is](/windows/desktop/Midl/size-is) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [First_is](first-is.md) ein Beispiel dafür, wie Sie einen Abschnitt eines Arrays an.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`max_is`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)