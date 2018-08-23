---
title: AsyncStatusInternal-Enumeration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b389e5b137ef3cdb94ffbb1fc381ebe2e5813963
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603969"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal-Enumeration

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Hinweise

Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.

## <a name="members"></a>Member

`_Created`  
Entspricht `::Windows::Foundation::AsyncStatus::Created`.

`_Started`  
Entspricht `::Windows::Foundation::AsyncStatus::Started`.

`_Completed`  
Entspricht `::Windows::Foundation::AsyncStatus::Completed`.

`_Cancelled`  
Entspricht `::Windows::Foundation::AsyncStatus::Cancelled`.

`_Error`  
Entspricht `::Windows::Foundation::AsyncStatus::Error`.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)