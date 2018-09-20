---
title: Module::ReleaseNotifier::ReleaseNotifier-Konstruktor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e43abd46ccfb150936ff435360611289f18a1270
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405020"
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Module::ReleaseNotifier::ReleaseNotifier-Konstruktor

Initialisiert eine neue Instanz der dem **releasenotifier** Klasse.

## <a name="syntax"></a>Syntax

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parameter

*release*<br/>
**"true"** So löschen Sie diese Instanz bei der `Release` Methode wird aufgerufen. **"false"** diese Instanz nicht gelöscht.

## <a name="exceptions"></a>Ausnahmen

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module::ReleaseNotifier-Klasse](../windows/module-releasenotifier-class.md)