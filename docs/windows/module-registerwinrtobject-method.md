---
title: 'Module:: registerwinrtobject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a7f5879a3a76e9af795a5dfc808423b43515662a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609300"
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject-Methode

Registriert ein oder mehrere Windows-Runtime-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.

## <a name="syntax"></a>Syntax

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)  
```

### <a name="parameters"></a>Parameter

*ServerName*  
Ein Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.

*activatableClassIds*  
Ein Array von aktivierbare CLSIDs registrieren.

*Cookie*  
Ein Wert, der die Objekte der Klasse identifiziert, die registriert wurden. Dieser Wert wird später verwendet, um die Registrierung aufzuheben.

*count*  
Die Anzahl von Objekten zu registrieren.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, z. B. CO_E_OBJISREG, die den Grund angibt Fehler aufgetreten.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)