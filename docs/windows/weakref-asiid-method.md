---
title: 'Weakref:: Asiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60d2900876d7a9fbee7a193d0575bf3afdf4335b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012179"
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID-Methode
Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstellen-ID darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *riid*  
 Eine Schnittstellen-ID.  
  
 *ptr*  
 Wenn dieser Vorgang abgeschlossen ist, ein Objekt, das Parameter repräsentiert *Riid*.  
  
## <a name="return-value"></a>Rückgabewert  
  
-   S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein HRESULT, der den Grund angibt. der Vorgang fehlgeschlagen ist, und *Ptr* nastaven NA hodnotu **"nullptr"**.  
  
-   S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich **WeakRef** Objekt bereits freigegeben wurde. Parameter *Ptr* nastaven NA hodnotu **"nullptr"**.  
  
-   S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich **WeakRef** abgeleitetes Objekt ist nicht vom Parameter *Riid*. Parameter *Ptr* nastaven NA hodnotu **"nullptr"**. (Weitere Informationen finden Sie in den Hinweisen.)  
  
## <a name="remarks"></a>Hinweise  
 Ein Fehler wird ausgegeben, wenn Parameter *Riid* stammt nicht aus `IInspectable`. Dieser Fehler hat Vorrang vor den Rückgabewert.  
  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage (die hier nicht dargestellt, aber in der Headerdatei deklariert ist) ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.  
  
 Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt die **WeakRef** -Instanz **"nullptr"** Wenn der schwache Verweis nicht abgerufen werden kann, so vermeiden Sie Code zur fehlerüberprüfung, die die überprüft**WeakRef** für **"nullptr"**. Überprüfen Sie stattdessen *Ptr* für **"nullptr"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)