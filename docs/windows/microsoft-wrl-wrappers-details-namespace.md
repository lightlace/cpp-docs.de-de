---
title: Microsoft::wrl::Wrappers::Details-Namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
dev_langs:
- C++
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3af5add0a934b59cf3027b7beb0ea000a7ae1415
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595706"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Microsoft::WRL::Wrappers::Details-Namespace

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[SyncLockT-Klasse](../windows/synclockt-class.md)|Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.|
|[SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)|Stellt einen Typ, der exklusiven annehmen kann, oder den gemeinsamen Besitz einer Ressource.|

### <a name="methods"></a>Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CompareStringOrdinal-Methode](../windows/comparestringordinal-method.md)|Vergleicht zwei angegebene `HSTRING` Objekte und gibt eine ganze Zahl, die ihre relative Position in einer Sortierreihenfolge angibt.|

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)