---
title: InvokeModeOptions Struktur | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b1eb0e7f6cf49a7c6ac12a4810ae1622e263e2f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions-Struktur

Gibt an, ob alle Ereignisse in der Warteschlange Delegaten ausgelöst werden, oder beenden ausgelöst wird, nachdem ein Fehler ausgelöst wird. Die zulässigen Werte werden angegeben, der `InvokeMode` Enum.

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

[Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)
[Microsoft::WRL::AgileEventSource-Klasse](../windows/agileeventsource-class.md)