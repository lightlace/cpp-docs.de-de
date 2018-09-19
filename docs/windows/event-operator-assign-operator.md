---
title: 'Event:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c95ac2e16ef4f4b279f0da287a4ca2a3d0f18a7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610462"
---
# <a name="eventoperator-operator"></a>Event::operator=-Operator

Weist dem angegebenen **Ereignis** Verweis auf das aktuelle **Ereignis** Instanz.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*  
Ein Rvalue-Verweis auf ein **Ereignis** Instanz.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle **Ereignis** Instanz.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)](../windows/event-class-windows-runtime-cpp-template-library.md)