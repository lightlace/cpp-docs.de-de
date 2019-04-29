---
title: AsyncResultType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: d3f99fa85a777ae8361ed6f7cb82fe97ddd8d667
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398796"
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