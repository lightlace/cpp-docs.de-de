---
title: 'Module:: unregistercomobject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46450142c0455dd4eb96f627abd077e478d96fea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383505"
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject-Methode

Hebt die Registrierung für ein oder mehrere COM-Objekte, die verhindert, dass andere Anwendungen herstellen können.

## <a name="syntax"></a>Syntax

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Parameter

*ServerName*<br/>
(Nicht verwendeten)

*Cookies*<br/>
Ein Array von Zeigern auf Werte, die identifizieren, Objekte der Klasse, deren Registrierung aufgehoben werden. Das Array erstellt wurde, indem die [RegisterCOMObject](../windows/module-registercomobject-method.md) Methode.

*count*<br/>
Die Anzahl der Klassen zum Aufheben der Registrierung.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das den Grund angibt Fehler aufgetreten.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)