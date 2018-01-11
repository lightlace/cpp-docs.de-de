---
title: 'Module:: registerwinrtobject-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs: C++
helpviewer_keywords: RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 279a661fae0def63443c9a42d2f290b8d23fa2a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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