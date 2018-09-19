---
title: Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98bcc3d3fcaf7aea3b2632cacb1ff38eedb868b8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612311"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor

Initialisiert eine neue Instanz der dem **genericreleasenotifier** Klasse.

## <a name="syntax"></a>Syntax

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Parameter

*Rückruf*  
Ein Lambda, Funktionselement oder Zeiger auf Funktion-Ereignishandler, der mit dem Klammernoperator-Funktion aufgerufen werden kann (`()`).

*release*  
Geben Sie **"true"** aktivieren aufrufen, die zugrunde liegende [Modul:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) Methode geben Sie andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module::GenericReleaseNotifier-Klasse](../windows/module-genericreleasenotifier-class.md)