---
title: 'Weakref:: As-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 938c7c796bf88d4ea1e49f1f59d274b5017aa7de
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649301"
---
# <a name="weakrefas-method"></a>WeakRef::As-Methode
Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstelle darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *U*  
 Eine Schnittstellen-ID.  
  
 *ptr*  
 Wenn dieser Vorgang abgeschlossen ist, ein Objekt, das Parameter repräsentiert *U*.  
  
## <a name="return-value"></a>Rückgabewert  
  
-   S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein HRESULT, der den Grund angibt. der Vorgang fehlgeschlagen ist, und *Ptr* nastaven NA hodnotu **"nullptr"**.  
  
-   S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich **WeakRef** Objekt bereits freigegeben wurde. Parameter *Ptr* nastaven NA hodnotu **"nullptr"**.  
  
-   S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich **WeakRef** abgeleitetes Objekt ist nicht vom Parameter *U*. Parameter *Ptr* nastaven NA hodnotu **"nullptr"**.  
  
## <a name="remarks"></a>Hinweise  
 Ein Fehler wird ausgegeben, wenn Parameter *U* ist `IWeakReference`, oder Sie stammt nicht aus `IInspectable`.  
  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.  
  
 Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt die **WeakRef** -Instanz **"nullptr"** Wenn der schwache Verweis nicht abgerufen werden konnte, so vermeiden Sie Code zur fehlerüberprüfung, die der WeakRef überprüft **"nullptr"**. Überprüfen Sie stattdessen *Ptr* für **"nullptr"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)