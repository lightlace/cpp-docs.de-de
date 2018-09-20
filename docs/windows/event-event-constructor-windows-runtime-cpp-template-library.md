---
title: 'Event:: Event Constructor (Windows Runtime C++-Vorlagenbibliothek) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs:
- C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bd9f02935d0d88976fd3b62c7276f106519fa74
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381009"
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event Constructor (C++-Vorlagenbibliothek der Windows Runtime)

Initialisiert eine neue Instanz der dem **Ereignis** Klasse.

## <a name="syntax"></a>Syntax

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein Ereignis. In der Standardeinstellung *h* wird initialisiert **"nullptr"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/event-class-windows-runtime-cpp-template-library.md)