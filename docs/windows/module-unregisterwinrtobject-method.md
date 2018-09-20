---
title: 'Module:: unregisterwinrtobject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39bb86206aec72d918df482ee1d01214b4fbb03b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381750"
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject-Methode

Hebt die Registrierung für ein oder mehrere Windows-Runtime-Objekte, damit andere Anwendungen darauf keine Verbindung herstellen können.

## <a name="syntax"></a>Syntax

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Parameter

*Cookie*<br/>
Ein Zeiger auf ein Wert, der das Klassenobjekt identifiziert, dessen Registrierung aufgehoben werden.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)