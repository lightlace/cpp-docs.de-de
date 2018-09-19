---
title: 'InvokeHelper:: InvokeHelper-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ad09a5a4794a9db8882a088f90da5046b6f7b9d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609239"
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper-Konstruktor

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parameter

*Rückruf*  
Ein Ereignishandler.

## <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der dem **InvokeHelper** Klasse.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[InvokeHelper-Struktur](../windows/invokehelper-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)