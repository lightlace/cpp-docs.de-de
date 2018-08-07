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
ms.openlocfilehash: c19e7b5388438b8c3c2359672360e4a2ee3001a3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602629"
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject-Methode
Hebt die Registrierung für ein oder mehrere COM-Objekte, die verhindert, dass andere Anwendungen herstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
### <a name="parameters"></a>Parameter  
 *ServerName*  
 (Nicht verwendeten)  
  
 *Cookies*  
 Ein Array von Zeigern auf Werte, die identifizieren, Objekte der Klasse, deren Registrierung aufgehoben werden. Das Array erstellt wurde, indem die [RegisterCOMObject](../windows/module-registercomobject-method.md) Methode.  
  
 *count*  
 Die Anzahl der Klassen zum Aufheben der Registrierung.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das den Grund angibt Fehler aufgetreten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)