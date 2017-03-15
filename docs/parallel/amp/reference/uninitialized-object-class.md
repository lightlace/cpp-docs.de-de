---
title: Uninitialized_object-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::uninitialized_object
dev_langs:
- C++
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1ff7840ec3ff4ab00b7e13d647c329a892dade42
ms.lasthandoff: 02/24/2017

---
# <a name="uninitializedobject-class"></a>uninitialized_object-Klasse
Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class uninitialized_object : public runtime_exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Uninitialized_object-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `uninitialized_object`-Klasse.|  

  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
## <a name="a-nameuninitializedobjectctora-unsupportedfeature"></a><a name="uninitialized_object__ctor"></a>unsupported_feature 

Erstellt eine neue Instanz der unsupported_feature-Ausnahme.  
  
### <a name="syntax"></a>Syntax  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine Beschreibung des Fehlers.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `unsupported_feature`-Objekt. 

## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

