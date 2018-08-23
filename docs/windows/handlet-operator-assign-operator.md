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
ms.openlocfilehash: cf539082ef88abb5fb27f09d92b73403dc2d03a5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611341"
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

*h*  
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