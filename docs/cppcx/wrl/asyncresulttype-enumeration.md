---
title: AsyncResultType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 309ed876c71f453336ecc2ed10eedc07f2a80be8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785026"
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

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)