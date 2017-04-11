---
title: CAtlException Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 471ba42f25a4e237db03f2516288a7b33a0efd63
ms.lasthandoff: 03/31/2017

---
# <a name="catlexception-class"></a>CAtlException-Klasse
Diese Klasse definiert eine ATL-Ausnahme.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlException
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|Der Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|Wandelt das aktuelle Objekt, das einen HRESULT-Wert.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|Die Variable vom Typ HRESULT vom Objekt erstellt und verwendet, um den Fehlerzustand zu speichern.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CAtlException` -Objekt stellt eine Ausnahmebedingung bezieht sich auf eine ATL-Vorgang dar. Die `CAtlException` Klasse enthält einen öffentlichen Datenmember, die den Statuscode, der angibt, des Grund für die Ausnahme und Umwandlungsoperatoren, mit dem Sie die Ausnahme zu behandeln, als handele es sich um ein HRESULT speichert.  
  
 Rufen Sie im allgemeinen `AtlThrow` anstatt zu erstellen eine `CAtlException` -Objekts direkt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlexcept.h  
  
##  <a name="catlexception"></a>CAtlException::CAtlException  
 Der Konstruktor.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hr`  
 Die `HRESULT` Fehlercode.  
  
##  <a name="operator_hresult"></a>CAtlException::operator HRESULT 
 Wandelt das aktuelle Objekt, das einen HRESULT-Wert.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 Die `HRESULT` -Datenmember.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Datenmember, die die fehlerbedingung speichert. Der HRESULT-Wert wird durch den Konstruktor festgelegte [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>Siehe auch  
 ["Atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

