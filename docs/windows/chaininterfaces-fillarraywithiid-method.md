---
title: 'Chaininterfaces:: Fillarraywithiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09e0dc3b9caf059bb8ecdce0468dfc118ce9ebfa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594943"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>ChainInterfaces::FillArrayWithIid-Methode

Speichert die Schnittstellen-ID, durch definiert die *I0* Template-Parameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.

## <a name="syntax"></a>Syntax

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameter

*index*  
Zeiger auf einen Indexwert in der *Iids* Array.

*IIDs*  
Ein Array von Schnittstellen-IDs.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)