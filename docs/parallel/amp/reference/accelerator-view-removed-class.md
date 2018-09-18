---
title: Accelerator_view_removed-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:get_view_removed_reason
dev_langs:
- C++
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1c8963fee0fa7718c6ea8fe67904613b2dca8ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020255"
---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed-Klasse
Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX-Aufruf aufgrund des Windows-TDR-Mechanismus (Timeout Detection and Recovery) fehlschlägt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator_view_removed-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `accelerator_view_removed`-Klasse.|  

### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_view_removed_reason](#get_view_removed_reason)|Gibt einen HRESULT-Fehlercode, der angibt, der Ursache für die `accelerator_view` Entfernung des Objekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="ctor"></a> accelerator_view_removed 

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
*_Nachricht*<br/>
Eine Beschreibung des Fehlers.  
  
*_View_removed_reason*<br/>
Ein HRESULT-Fehlercode, der angibt, der Ursache für das Entfernen der `accelerator_view` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine neue Instanz der Accelerator_view_removed-Klasse.  
  
## <a name="get_view_removed_reason_method"></a> get_view_removed_reason 

Gibt einen HRESULT-Fehlercode, der angibt, der Ursache für die `accelerator_view` Entfernung des Objekts.  
  
### <a name="syntax"></a>Syntax  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
