---
title: 'Module:: registerobjects-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterObjects
dev_langs: C++
helpviewer_keywords: RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e73a59ff18c16a898ca1a9d7919615a2dec18bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects-Methode
Registriert COM oder Windows-Runtime-Objekte an, damit andere Anwendungen herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parameter  
 `module`  
 Ein Array mit COM oder Windows-Runtime-Objekten.  
  
 `serverName`  
 Der Name des Servers, der die Objekte erstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Andernfalls ist fehlgeschlagen ein HRESULT, das den Grund angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)