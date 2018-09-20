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
ms.openlocfilehash: 97af2db56cab99412faf35efa8cd351946ab4828
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410298"
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

[FactoryCache-Struktur](../windows/factorycache-structure.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)