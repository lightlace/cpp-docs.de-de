---
title: 'Module:: registerobjects-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04281b87584d10d36f5f2eeea05dfae0923b2d9f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013313"
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects-Methode
COM- oder Windows-Runtime-Objekte registriert, damit andere Anwendungen eine Verbindung damit herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
### <a name="parameters"></a>Parameter  
 *Modul*  
 Ein Array von COM- oder Windows-Runtime-Objekte.  
  
 *ServerName*  
 Der Name des Servers, der die Objekte erstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, der den Grund angibt. der Vorgang konnte nicht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)