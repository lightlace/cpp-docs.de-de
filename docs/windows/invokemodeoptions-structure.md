---
title: InvokeModeOptions-Struktur
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 315f1f0c49c4222bf525bbaf25c9ad0de8b9c7d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511696"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions-Struktur

Gibt an, ob alle Ereignisse in der Warteschlange Delegaten ausgelöst werden, oder beim Beenden ausgelöst wird, nachdem ein Fehler ausgelöst wird. Die zulässigen Werte werden angegeben, der `InvokeMode` Enum.

## <a name="syntax"></a>Syntax

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)<br/>
[Microsoft::wrl::AgileEventSource-Klasse](../windows/agileeventsource-class.md)