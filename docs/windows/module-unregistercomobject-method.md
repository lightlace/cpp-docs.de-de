---
title: 'Module:: unregistercomobject-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs: C++
helpviewer_keywords: UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45a6dc776feb1534cd7e58240a40cc173e7459de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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