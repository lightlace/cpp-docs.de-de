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
ms.openlocfilehash: cdec425e317585abbd9730447e2c4fbb19b8250a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785367"
---
# <a name="boolstruct-structure"></a>BoolStruct-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Hinweise

Die `BoolStruct` Struktur definiert, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet. `BoolStruct` wird intern von verwendet die [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) Operator.

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                          | Beschreibung
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Member](#member) | Gibt an, dass eine [ComPtr](comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BoolStruct`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="member"></a>BoolStruct::Member

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
int Member;
```

### <a name="remarks"></a>Hinweise

Gibt an, dass eine [ComPtr](comptr-class.md) ist, oder ist nicht der Fall, die Objektlebensdauer einer Schnittstelle verwalten.
