---
title: 'Eventtargetarray:: End-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::End
dev_langs:
- C++
helpviewer_keywords:
- End method
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 341333b0c4f51c42004ad638a5a8f4fcb7d7e466
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596490"
---
# <a name="eventtargetarrayend-method"></a>EventTargetArray::End-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
ComPtr<IUnknown>* End();
```

## <a name="return-value"></a>Rückgabewert

Die Adresse des letzten Elements im internen Array von Ereignishandlern.

## <a name="remarks"></a>Hinweise

Ruft die Adresse des letzten Elements in das interne Array der Ereignishandler ab.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[EventTargetArray-Klasse](../windows/eventtargetarray-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)