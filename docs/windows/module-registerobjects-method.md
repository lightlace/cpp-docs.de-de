---
title: 'Module:: registerobjects-Methode | Microsoft Docs'
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
ms.openlocfilehash: 986dcfff49529eedd8d495f4c37e19fa2b6cb8bc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875343"
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