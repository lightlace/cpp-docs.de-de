---
title: AsyncResultType-Enumeration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a79ef02302208aa14bc1620e486fcfbc6e12253
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591262"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType-Enumeration

Gibt den Typ der zurückgegebenen Ergebnisse der `GetResults()` Methode.

## <a name="syntax"></a>Syntax

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Member

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`MultipleResults`|Mehrere Resultsets, die progressiv zwischen dargestellt werden `Start` Zustand und vor dem `Close()` aufgerufen wird.|
|`SingleResult`|Ein einzelnes Ergebnis, das nach dem vorgelegt wird die `Complete` Ereignis auftritt.|

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)