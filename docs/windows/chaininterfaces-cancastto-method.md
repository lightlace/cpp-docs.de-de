---
title: 'Chaininterfaces:: Cancastto-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 752c3598a38117506154b0a2b7d7d3e578bf3c3e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417643"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo-Methode

Gibt an, ob die angegebene Schnittstellen-ID in jede der durch die nicht dem Standard-Vorlagenparameter definiert spezialisierungen umgewandelt werden kann.

## <a name="syntax"></a>Syntax

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*ppv*<br/>
Ein Zeiger auf die letzte Schnittstellen-ID, die erfolgreich umgewandelt wurde.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn alle Umwandlungsvorgänge erfolgreich war; andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)