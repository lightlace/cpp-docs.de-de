---
title: BoolStruct-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4981c7f82fe2c544bf907ac59d6e9ca22105cbd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592536"
---
# <a name="boolstruct-structure"></a>BoolStruct-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Hinweise

Die **BoolStruct** Struktur definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. **BoolStruct** werden intern von der [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[BoolStruct::Member-Datenmember](../windows/boolstruct-member-data-member.md)|Gibt an, dass eine [ComPtr](../windows/comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BoolStruct`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)  
[ComPtr::operator Microsoft::WRL::Details::BoolType-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)