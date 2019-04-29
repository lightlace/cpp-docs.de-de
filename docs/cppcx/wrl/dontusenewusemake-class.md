---
title: DontUseNewUseMake-Klasse
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: 02420f2657c7d7d6a7a0294f0321717a3bb2b5d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398536"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Hinweise

Verhindert die Verwendung von Operator `new` in `RuntimeClass`. Folglich müssen Sie verwenden die [Funktion](make-function.md) stattdessen.

## <a name="members"></a>Member

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                             | Beschreibung
------------------------------------------------ | ---------------------------------------------------------------------------
[Dontusenewusemake:: neue](#operator-new) | Überlädt `new` und verhindert, dass deren verwendeten `RuntimeClass`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`DontUseNewUseMake`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="operator-new"></a>Dontusenewusemake:: neue

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parameter

*__unnamed0*<br/>
Einen unbenannten Parameter, der angibt, die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.

*placement*<br/>
Der Typ, zugeordnet werden.

### <a name="return-value"></a>Rückgabewert

Bietet eine Möglichkeit, zusätzliche Argumente zu übergeben, wenn Sie beim Überladen `new`.

### <a name="remarks"></a>Hinweise

Überlädt `new` und verhindert, dass deren verwendeten `RuntimeClass`.
