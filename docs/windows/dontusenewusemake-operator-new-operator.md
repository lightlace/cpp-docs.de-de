---
title: 'Dontusenewusemake:: Neuer Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c2de62df47e46183c1169956a18ddc10822b22a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611920"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new-Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parameter

*__unnamed0*  
Einen unbenannten Parameter, der angibt, die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.

*Platzierung*  
Der Typ, zugeordnet werden.

## <a name="return-value"></a>Rückgabewert

Bietet eine Möglichkeit, zusätzliche Argumente zu übergeben, wenn Sie beim Überladen **neue**.

## <a name="remarks"></a>Hinweise

Überlädt **neue** und verhindert, dass deren verwendeten `RuntimeClass`.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)