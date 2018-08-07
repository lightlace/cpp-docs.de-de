---
title: 'InvokeHelper:: InvokeHelper-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6618d5fc219e5f4e6533eb4d31cf7cd14fc4b1d5
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602548"
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper-Konstruktor
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *Rückruf*  
 Ein Ereignishandler.  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem **InvokeHelper** Klasse.  
  
 Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [InvokeHelper-Struktur](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)