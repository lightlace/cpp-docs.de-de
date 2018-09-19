---
title: 'Modulebase:: Incrementobjectcount-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f226018d1c3cae6dd3dbab34537d7ada50140a92
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610291"
---
# <a name="modulebaseincrementobjectcount-method"></a>ModuleBase::IncrementObjectCount-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
virtual long IncrementObjectCount() = 0;
```

## <a name="return-value"></a>Rückgabewert

Die Anzahl der vor dem Inkrementieren negativ werden soll.

## <a name="remarks"></a>Hinweise

Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ModuleBase-Klasse](../windows/modulebase-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)