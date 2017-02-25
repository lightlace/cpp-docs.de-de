---
title: "WeakRef::CopyTo-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo-Methode"
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# WeakRef::CopyTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.  
  
## Syntax  
  
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
  
#### Parameter  
 `U`  
 Zeiger auf eine „IInspectable“\-Schnittstelle. Ein Fehler wird ausgegeben, wenn `U` nicht von „IInspectable“ abgeleitet ist.  
  
 `riid`  
 Eine Schnittstellen\-ID. Ein Fehler wird ausgegeben, wenn `riid` nicht von **IWeakReference** abgeleitet ist.  
  
 `ptr`  
 Ein doppelt indirekter Zeiger auf „IInspectable“ oder „IWeakReference“.  
  
## Rückgabewert  
 „S\_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Weitere Informationen finden Sie in den Hinweisen.  
  
## Hinweise  
 Der Rückgabewert „S\_OK“ bedeutet, dass dieser Vorgang erfolgreich war, gibt aber nicht an, ob der schwache Verweis zu einem starken Verweis aufgelöst wurde. Wenn „S\_OK“ zurückgegeben wird, prüfen Sie, ob der Parameter `p` ein starker Verweis ist; das heißt, der Parameter `p` ist kein `nullptr`.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef\-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr` überprüft. Überprüfen Sie stattdessen das zurückgegebene HRESULT, um zu bestimmen, ob die Methode erfolgreich ausgeführt wurde, oder überprüfen Sie `ptr` auf `nullptr`.  
  
## Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [WeakRef\-Klasse](../windows/weakref-class.md)