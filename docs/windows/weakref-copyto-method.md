---
title: 'Weakref:: CopyTo-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::CopyTo
dev_langs: C++
helpviewer_keywords: CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca0fe93e89b1a7115e816157fe1842d616850675
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo-Methode
Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Zeiger auf eine „IInspectable“-Schnittstelle. Ein Fehler wird ausgegeben, wenn `U` nicht von „IInspectable“ abgeleitet ist.  
  
 `riid`  
 Eine Schnittstellen-ID. Ein Fehler wird ausgegeben, wenn `riid` nicht von **IWeakReference**abgeleitet ist.  
  
 `ptr`  
 Ein doppelt indirekter Zeiger auf „IInspectable“ oder „IWeakReference“.  
  
## <a name="return-value"></a>Rückgabewert  
 „S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Weitere Informationen finden Sie in den Hinweisen.  
  
## <a name="remarks"></a>Hinweise  
 Der Rückgabewert „S_OK“ bedeutet, dass dieser Vorgang erfolgreich war, gibt aber nicht an, ob der schwache Verweis zu einem starken Verweis aufgelöst wurde. Wenn „S_OK“ zurückgegeben wird, prüfen Sie, ob der Parameter `p` ein starker Verweis ist; das heißt, der Parameter `p` ist kein `nullptr`.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr`überprüft. Überprüfen Sie stattdessen `ptr` für `nullptr`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)