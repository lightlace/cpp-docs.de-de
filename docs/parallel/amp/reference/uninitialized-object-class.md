---
title: Uninitialized_object-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
dev_langs: C++
helpviewer_keywords: uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75d3050c128b067833352ea82aee38bcd2a7019d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="uninitializedobject-class"></a>uninitialized_object-Klasse
Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class uninitialized_object : public runtime_exception;  
```  
  
## <a name="members"></a>Member  
  
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
## <a name="uninitialized_object__ctor"></a>unsupported_feature 

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
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
