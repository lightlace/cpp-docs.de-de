---
title: 'Module:: unregisterobjects-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ee7e6deeda17d2ac374b39edf70ab28fa1457fa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603380"
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects-Methode

Hebt die Registrierung auf die Objekte in das angegebene Modul, damit andere Anwendungen darauf keine Verbindung herstellen können.

## <a name="syntax"></a>Syntax

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parameter

*Modul*  
Zeiger auf ein Modul.

*ServerName*  
Einen qualifizierten Namen, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls Fehler Fehler HRESULT, das den Grund angibt, diesen Vorgang.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)