---
title: 'Factorycache:: Cookie-Datenmember | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache::cookie
dev_langs:
- C++
helpviewer_keywords:
- cookie data member
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6dba6e5d7fd478d198e48e9d8517d34e13b43484
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613665"
---
# <a name="factorycachecookie-data-member"></a>FactoryCache::cookie-Datenmember

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

## <a name="remarks"></a>Hinweise

Enthält einen Wert an, der ein registriertes Windows-Runtime oder COM-Klasse-Objekt identifiziert, und wird später beim Aufheben der Registrierung des Objekts verwendet.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[FactoryCache-Struktur](../windows/factorycache-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)