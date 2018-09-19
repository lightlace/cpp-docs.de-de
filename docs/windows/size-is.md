---
title: Size_is | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 677f28b1ca4a45a3033e1dc6a34bd024bec6e329
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211501"
---
# <a name="sizeis"></a>size_is

Geben Sie die Größe des Arbeitsspeichers für Größe Zeiger zugewiesen, Größe der Zeiger auf Zeiger, die Größe und Einzel- oder mehrdimensionale Arrays.

## <a name="syntax"></a>Syntax

```cpp
[ size_is(
   "expression"
) ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*  
Die Größe des Arbeitsspeichers für Größe Zeiger.

## <a name="remarks"></a>Hinweise

Die **Size_is** C++-Attribut hat die gleiche Funktionalität wie die [Size_is](/windows/desktop/Midl/size-is) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [First_is](../windows/first-is.md) ein Beispiel dafür, wie Sie einen Abschnitt eines Arrays an.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`max_is`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[first_is](../windows/first-is.md)  
[last_is](../windows/last-is.md)  
[max_is](../windows/max-is.md)  
[length_is](../windows/length-is.md)  