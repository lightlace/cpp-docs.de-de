---
title: Out_of_memory-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs: C++
helpviewer_keywords: out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6eb7b4e46d0d91779bf7c4c9047cad2f49100cd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="outofmemory-class"></a>out_of_memory-Klasse
Die Ausnahme, die ausgelöst wird, wenn eine Methode aufgrund unzureichenden System- oder Gerätearbeitsspeichers fehlschlägt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Out_of_memory-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `out_of_memory`-Klasse.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
## <a name="ctor"></a>out_of_memory 

 Initialisiert eine neue Instanz der Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
explicit out_of_memory(  
    const char * _Message ) throw();  
  
out_of_memory () throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine Beschreibung des Fehlers.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine neue Instanz der `out_of_memory`-Klasse.  
  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
