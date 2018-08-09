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
ms.openlocfilehash: 240ab47099b9e97e9a6bb794083858fe042605d2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018694"
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