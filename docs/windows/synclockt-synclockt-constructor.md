---
title: 'Synclockt:: Synclockt-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2d8244b94a308970e87646505cdcade533b717f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376006"
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT-Konstruktor

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Rvalue-Verweis auf einen anderen **SyncLockT** Objekt.

*sync*<br/>
Ein Verweis auf einen anderen `SyncLockWithStatusT` Objekt.

## <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der dem **SyncLockT** Klasse.

Der erste Konstruktor initialisiert die aktuelle **SyncLockT** Objekt von einem anderen **SyncLockT** vom Parameter angegebenen Objekts *andere*, und klicken Sie dann werden die anderen ungültig **SyncLockT** Objekt. Der zweite Konstruktor ist **geschützt**, und initialisiert die aktuelle **SyncLockT** Objekt, das einen ungültigen Status.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[SyncLockT-Klasse](../windows/synclockt-class.md)