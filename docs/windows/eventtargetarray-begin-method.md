---
title: 'Eventtargetarray:: Begin-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs:
- C++
helpviewer_keywords:
- Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 738ee52eb68cfbb03a380ffac52efdb4010b5205
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602130"
---
# <a name="eventtargetarraybegin-method"></a>EventTargetArray::Begin-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
ComPtr<IUnknown>* Begin();
```

## <a name="return-value"></a>Rückgabewert

Die Adresse des ersten Elements im internen Array von Ereignishandlern.

## <a name="remarks"></a>Hinweise

Ruft die Adresse des ersten Elements in das interne Array der Ereignishandler ab.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)