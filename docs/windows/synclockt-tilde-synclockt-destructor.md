---
title: 'SyncLockT:: ~ SyncLockT-Destruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- ~SyncLockT, destructor
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d75e3e0592d21672397e8d54c565734d53e72614
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599779"
---
# <a name="synclocktsynclockt-destructor"></a>SyncLockT::~SyncLockT-Destruktor

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
~SyncLockT();
```

## <a name="remarks"></a>Hinweise

Hebt die Initialisierung einer Instanz von der **SyncLockT** Klasse.

Dieser Destruktor entsperrt auch die aktuelle **SyncLockT** Instanz.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[SyncLockT-Klasse](../windows/synclockt-class.md)