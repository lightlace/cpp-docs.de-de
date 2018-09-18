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
ms.openlocfilehash: 4c7751929a55993876034bb3c1918b82193681fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016883"
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

`_Created`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Created`.

`_Started`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Started`.

`_Completed`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Completed`.

`_Cancelled`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Cancelled`.

`_Error`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Error`.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)