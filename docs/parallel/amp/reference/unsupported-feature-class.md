---
title: Unsupported_feature-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4be595382436f26ed43215c86d3f350532c52af
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="unsupportedfeature-class"></a>unsupported_feature-Klasse
Die Ausnahme, die ausgelöst wird, wenn eine nicht unterstützte Funktion verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Unsupported_feature-Konstruktor](#ctor)|Erstellt eine neue Instanz der `unsupported_feature`-Ausnahme.|  

  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## <a name="unsupported_feature__ctor"></a> unsupported_feature 

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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
