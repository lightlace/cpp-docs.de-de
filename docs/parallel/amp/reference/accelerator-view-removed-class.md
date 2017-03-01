---
title: Accelerator_view_removed-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view_removed
dev_langs:
- C++
helpviewer_keywords:
- amprt/Concurrency::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
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
ms.openlocfilehash: 6e7a56a3315dc38a9e7def2144f3a2f8efd363fc
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed-Klasse
Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX-Aufruf aufgrund des Windows-TDR-Mechanismus (Timeout Detection and Recovery) fehlschlägt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator_view_removed-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `accelerator_view_removed`-Klasse.|  

### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_view_removed_reason-Methode](#get_view_removed_reason)|Gibt einen HRESULT-Fehlercode, der angibt, der Ursache für die `accelerator_view` des Objekts entfernen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="a-namectora-acceleratorviewremoved"></a><a name="ctor"></a>accelerator_view_removed 

Initialisiert eine neue Instanz der dem [Accelerator_view_removed](accelerator-view-removed-class.md) Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine Beschreibung des Fehlers.  
  
 `_View_removed_reason`  
 Ein HRESULT-Fehlercode, der angibt, der Ursache für das Entfernen der `accelerator_view` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine neue Instanz der Accelerator_view_removed-Klasse.  
  
## <a name="a-namegetviewremovedreasonmethoda-getviewremovedreason"></a><a name="get_view_removed_reason_method"></a>get_view_removed_reason 

Gibt einen HRESULT-Fehlercode, der angibt, der Ursache für die `accelerator_view` des Objekts entfernen.  
  
### <a name="syntax"></a>Syntax  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

