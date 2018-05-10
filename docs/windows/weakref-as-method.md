---
title: 'Weakref:: As-Methode | Microsoft Docs'
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
ms.openlocfilehash: 70e694b4c86194402f48d335aac353e48c3de79a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="weakrefas-method"></a>WeakRef::As-Methode
Legt den angegebenen ComPtr-Zeigerparameter so fest, dass er die angegebene Schnittstelle darstellt.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Eine Schnittstellen-ID.  
  
 `ptr`  
 Wenn dieser Vorgang abgeschlossen wird, ein Objekt das den Parameter `U`darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde; andernfalls ein HRESULT, das den Grund für den Fehler beim Vorgang angibt, und `ptr` wird auf `nullptr`festgelegt.  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef-Objekt aber bereits freigegeben wurde. Der `ptr` -Parameter wird auf `nullptr`festgelegt.  
  
-   S_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef-Objekt aber nicht vom Parameter `U`abgeleitet ist. Der `ptr` -Parameter wird auf `nullptr`festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Fehler wird ausgegeben, wenn der Parameter `U` „IWeakReference“ ist oder nicht von „IInspectable“ abgeleitet ist.  
  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr`überprüft. Überprüfen Sie stattdessen `ptr` für `nullptr`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)