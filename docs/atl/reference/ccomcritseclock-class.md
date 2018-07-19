---
title: CComCritSecLock-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b03d22a7daff614c560c7531143b718de7351c0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880250"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock-Klasse
Diese Klasse stellt Methoden zum Sperren und Entsperren von einem kritischen Abschnittsobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Parameter  
 *TLock*  
 Das Objekt, das gesperrt und entsperrt werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Der Konstruktor.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Rufen Sie diese Methode, um den kritischen Abschnitt-Objekt zu sperren.|  
|[CComCritSecLock::Unlock](#unlock)|Rufen Sie diese Methode, um das Objekt des kritischen Abschnitts zu entsperren.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Klasse zum Sperren und entsperren Sie Objekte auf sicherere Weise als mit der [CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md) oder [CComAutoCriticalSection-Klasse](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 Der Konstruktor.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Ein Objekt des kritischen Abschnitts.  
  
 *bInitialLock*  
 Der Zustand der ersten Sperre: **"true"** bedeutet, dass gesperrt.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das Objekt des kritischen Abschnitts.  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 Der Destruktor.  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Hebt die Sperre Objekt des kritischen Abschnitts.  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 Rufen Sie diese Methode, um den kritischen Abschnitt-Objekt zu sperren.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn das Objekt wurde erfolgreich gesperrt wurde, oder einen HRESULT-Fehler bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt bereits gesperrt ist, tritt ein ASSERT-Fehler in Debugbuilds.  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 Rufen Sie diese Methode, um das Objekt des kritischen Abschnitts zu entsperren.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt bereits entsperrt ist, tritt ein ASSERT-Fehler in Debugbuilds.  
  
## <a name="see-also"></a>Siehe auch  
 [CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection-Klasse](../../atl/reference/ccomautocriticalsection-class.md)
