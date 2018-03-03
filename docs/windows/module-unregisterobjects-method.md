---
title: 'Module:: unregisterobjects-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7e55afb96805fba6558cb900d2421a86379791c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects-Methode
Hebt die Registrierung auf die Objekte im angegebenen Modul, damit andere Clientanwendungen auf sie keine Verbindung herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parameter  
 `module`  
 Ein Zeiger auf ein Modul.  
  
 `serverName`  
 Eine qualifizierte Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls failed Fehler HRESULT, das den Grund angibt, diesen Vorgang.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)