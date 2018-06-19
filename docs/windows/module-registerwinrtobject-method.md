---
title: 'Module:: registerwinrtobject-Methode | Microsoft Docs'
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
ms.openlocfilehash: 097bf70ebd280d9494ff70ea1d80f53615f3d898
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874953"
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject-Methode
Registriert ein oder mehrere Windows-Runtime-Objekte an, damit andere Anwendungen herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>Parameter  
 `serverName`  
 Ein Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.  
  
 `activatableClassIds`  
 Ein Array von aktivierbare CLSIDs registrieren.  
  
 `cookie`  
 Ein Wert, der die Objekte der Klasse identifiziert, die registriert wurden. Dieser Wert wird später verwendet, um die Registrierung aufzuheben.  
  
 `count`  
 Die Anzahl von Objekten zu registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Andernfalls ist fehlgeschlagen Fehler HRESULT, z. B. CO_E_OBJISREG, die den Grund angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)