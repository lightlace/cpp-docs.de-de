---
title: DontUseNewUseMake-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c1f3a57401a3ab2efd45cab2dace127010c24e6
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235281"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Hinweise

Verhindert die Verwendung von Operator `new` in `RuntimeClass`. Folglich müssen Sie verwenden die [Funktion](../windows/make-function.md) stattdessen.

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

*Platzierung*<br/>
Der Typ, zugeordnet werden.

### <a name="return-value"></a>Rückgabewert

Bietet eine Möglichkeit, zusätzliche Argumente zu übergeben, wenn Sie beim Überladen `new`.

### <a name="remarks"></a>Hinweise

Überlädt `new` und verhindert, dass deren verwendeten `RuntimeClass`.
