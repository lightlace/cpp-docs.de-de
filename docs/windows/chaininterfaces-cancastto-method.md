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
ms.openlocfilehash: 8398f0bd4d9fdc786926782b13ebcac913a6a351
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612869"
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

*riid*  
Eine Schnittstellen-ID.

*ppv*  
Ein Zeiger auf die letzte Schnittstellen-ID, die erfolgreich umgewandelt wurde.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn alle Umwandlungsvorgänge erfolgreich war; andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)