---
title: 'Module:: unregistercomobject-Methode | Microsoft Docs'
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
ms.openlocfilehash: de4cc44d88f59e18f2c1644e9b27a9214ad32962
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881935"
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject-Methode
Hebt die Registrierung auf ein oder mehrere COM-Objekte, wird verhindert, dass andere Anwendungen eine Verbindung zu ihnen herstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
#### <a name="parameters"></a>Parameter  
 `serverName`  
 (Nicht verwendet wird)  
  
 `cookies`  
 Ein Array von Zeigern auf Werte, die die Objekte der Klasse um aufgehoben werden. Das Array erstellt wurde, durch die [RegisterCOMObject](../windows/module-registercomobject-method.md) Methode.  
  
 `count`  
 Die Anzahl der Klassen zum Aufheben der Registrierung.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn dieser Vorgang erfolgreich ist; Andernfalls ist fehlgeschlagen Fehler HRESULT, das den Grund angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)