---
title: BoolStruct-Struktur
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: d79ea93bf95040efe79e3e3c57ceb3397fd257de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643403"
---
# <a name="boolstruct-structure"></a>BoolStruct-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Hinweise

Die `BoolStruct` Struktur definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. `BoolStruct` wird intern von verwendet die [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) Operator.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                          | Beschreibung
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[Boolstruct::](#member) | Gibt an, dass eine [ComPtr](../windows/comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BoolStruct`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="member"></a>Boolstruct::

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
int Member;
```

### <a name="remarks"></a>Hinweise

Gibt an, dass eine [ComPtr](../windows/comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.
