---
title: 'InvokeHelper:: Callback_-Datenmember | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::callback_
dev_langs:
- C++
helpviewer_keywords:
- callback_ data member
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e602a8d2eef8e495ad732dcd61d0e8aa0b242130
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600999"
---
# <a name="invokehelpercallback-data-member"></a>InvokeHelper::callback_-Datenmember

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
TCallback callback_;
```

## <a name="remarks"></a>Hinweise

Stellt den Ereignishandler aufgerufen wird, wenn ein Ereignis auftritt.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[InvokeHelper-Struktur](../windows/invokehelper-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)