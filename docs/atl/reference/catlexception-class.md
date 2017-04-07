---
title: Klasse CAtlException | Microsoft-Dokumentation
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 30c9235f16581c86ab5612522909dc366b1ce17e
ms.lasthandoff: 02/24/2017

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
|[CAtlException::operator HRESULT](#operator_hresult)|Wandelt das aktuelle Objekt in einen HRESULT-Wert.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|Die Variable des Typs HRESULT vom-Objekt erstellt und verwendet, um den Fehlerzustand zu speichern.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CAtlException` Objekt stellt eine Ausnahmebedingung, die im Zusammenhang mit einem ATL-Vorgang dar. Die `CAtlException` -Klasse enthält einen öffentlichen Datenmember, die den Statuscode, die die Ursache für die Ausnahme und Umwandlungsoperatoren, mit dem Sie die Ausnahme behandelt, als handele es sich um ein HRESULT speichert.  
  
 In der Regel rufen Sie `AtlThrow` anstatt einer `CAtlException` direkt.  
  
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
 Wandelt das aktuelle Objekt in einen HRESULT-Wert.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 Der `HRESULT` -Datenmember.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Datenmember, die den Fehlerzustand speichert. Der HRESULT-Wert wird festgelegt, durch den Konstruktor [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>Siehe auch  
 [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

