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
ms.openlocfilehash: 88cafb7796ba0dfd1e37902821872e860ddc4baf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592183"
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

*Cookie*  
Ein Zeiger auf ein Wert, der das Klassenobjekt identifiziert, dessen Registrierung aufgehoben werden.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)