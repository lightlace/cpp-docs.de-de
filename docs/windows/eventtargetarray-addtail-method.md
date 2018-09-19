---
title: 'Eventtargetarray:: Addtail-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6609bba6d7adbddda152007e4db45c82f8039bc0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603677"
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parameter

*Element*  
Zeiger auf den Ereignishandler, angefügt werden soll.

## <a name="remarks"></a>Hinweise

Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.

**AddTail()** soll nur intern von verwendet werden. die `EventSource` Klasse.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)