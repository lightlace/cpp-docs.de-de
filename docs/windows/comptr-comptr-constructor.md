---
title: 'Comptr:: Comptr-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8f6234bf2dff0dab801c982a585dc30e338bb7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr-Konstruktor
Initialisiert eine neue Instanz der ComPtr-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Der Typ des `other`-Parameters.  
  
 `other`  
 Ein Objekt vom Typ `U`.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor ist der Standardkonstruktor, welche Parameterarrayelements ein leeres Objekt erstellt. Gibt an, der zweite Konstruktor [__nullptr](../windows/nullptr-cpp-component-extensions.md), denen explizit ein leeres Objekt erstellt.  
  
 Der dritte Konstruktor erstellt ein Objekt aus dem Objekt, das durch einen Zeiger angegeben.  
  
 Die vierten und fünften Konstruktoren sind Kopierkonstruktoren. Der fünfte Konstruktor kopiert ein Objekt aus, wenn er in den aktuellen Typ konvertiert wird.  
  
 Die sechsten und siebten Konstruktoren sind bewegungskonstruktoren. Der siebte Konstruktor verschiebt ein Objekt aus, wenn er in den aktuellen Typ konvertiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)