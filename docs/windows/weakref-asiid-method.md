---
title: 'Weakref:: Asiid-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::AsIID
dev_langs: C++
helpviewer_keywords: AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fdefa73ac14e807c5e4100fd81e1d931f4bf6e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID-Methode
Legt den angegebenen ComPtr-Zeigerparameter so fest, dass er die angegebene Schnittstellen-ID darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Eine Schnittstellen-ID.  
  
 `ptr`  
 Wenn dieser Vorgang abgeschlossen wird, ein Objekt, das den Parameter `riid`darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde; andernfalls ein HRESULT, das den Grund für den Fehler beim Vorgang angibt, und `ptr` wird auf `nullptr`festgelegt.  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef-Objekt aber bereits freigegeben wurde. Der `ptr` -Parameter wird auf `nullptr`festgelegt.  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef-Objekt aber nicht vom Parameter `riid`abgeleitet ist. Der `ptr` -Parameter wird auf `nullptr`festgelegt. (Weitere Informationen finden Sie in den Hinweisen.)  
  
## <a name="remarks"></a>Hinweise  
 Ein Fehler wird ausgegeben, wenn der Parameter `riid` nicht von „IInspectable“ abgeleitet ist. Dieser Fehler hat Vorrang vor den Rückgabewert.  
  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage (die hier nicht dargestellt, aber in der Headerdatei deklariert ist) ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr`überprüft. Überprüfen Sie stattdessen `ptr` für `nullptr`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)