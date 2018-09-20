---
title: 'Handlet:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c6aeca188f51f35c739c32f5290aac011781b41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396895"
---
# <a name="handletoperator-operator"></a>HandleT::operator=-Operator

Verschiebt den Wert des angegebenen **HandleT** -Objekt mit dem aktuellen **HandleT** Objekt.

## <a name="syntax"></a>Syntax

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf ein Handle.

## <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle **HandleT** Objekt.

## <a name="remarks"></a>Hinweise

Dieser Vorgang erklärt die **HandleT** vom Parameter angegebenen Objekts *h*.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HandleT-Klasse](../windows/handlet-class.md)