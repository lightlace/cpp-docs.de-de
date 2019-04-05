---
title: AsyncStatusInternal-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: f12bf4aafc87e44a6e2fb15ba79de4a9744bea58
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029725"
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
Äquivalent zu `::Windows::Foundation::AsyncStatus::Created`

`_Started`<br/>
Äquivalent zu `::Windows::Foundation::AsyncStatus::Started`

`_Completed`<br/>
Äquivalent zu `::Windows::Foundation::AsyncStatus::Completed`

`_Cancelled`<br/>
Äquivalent zu `::Windows::Foundation::AsyncStatus::Cancelled`

`_Error`<br/>
Äquivalent zu `::Windows::Foundation::AsyncStatus::Error`

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)