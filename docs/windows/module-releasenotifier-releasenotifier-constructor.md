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
ms.openlocfilehash: f4ab2d5d03516147acda38ea2133d7445695de80
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598787"
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Module::ReleaseNotifier::ReleaseNotifier-Konstruktor

Initialisiert eine neue Instanz der dem **releasenotifier** Klasse.

## <a name="syntax"></a>Syntax

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Parameter

*release*  
**"true"** So löschen Sie diese Instanz bei der `Release` Methode wird aufgerufen. **"false"** diese Instanz nicht gelöscht.

## <a name="exceptions"></a>Ausnahmen

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module::ReleaseNotifier-Klasse](../windows/module-releasenotifier-class.md)