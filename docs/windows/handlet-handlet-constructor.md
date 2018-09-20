---
title: 'Handlet:: Handlet-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d84bde2a9c83dedf6fa509101dddff85bd27999
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426119"
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT-Konstruktor

Initialisiert eine neue Instanz der dem **HandleT** Klasse.

## <a name="syntax"></a>Syntax

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()  
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Handle.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein **HandleT** -Objekt, das kein gültiges Handle für ein Objekt ist. Der zweite Konstruktor erstellt ein neues **HandleT** -Sitzungsobjekts Parameter *h*.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HandleT-Klasse](../windows/handlet-class.md)