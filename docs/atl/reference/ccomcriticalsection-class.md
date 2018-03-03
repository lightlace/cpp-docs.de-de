---
title: Klasse "CComCriticalSection" | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 827ba99a141799af42fab65c36df1f22d212260a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcriticalsection-class"></a>"CComCriticalSection"-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComCriticalSection::Lock](#lock)|Ruft den Besitz des Objekts kritischen Abschnitt ab.|  
|[CComCriticalSection::Term](#term)|Gibt die Systemressourcen geschont, indem Sie die kritischen Abschnittsobjekt frei.|  
|[CComCriticalSection::Unlock](#unlock)|Gibt den Besitz des Objekts kritischen Abschnitt frei.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|Ein **CRITICAL_SECTION** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComCriticalSection`Klasse ähnelt [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), außer dass müssen Sie explizit initialisieren und den kritischen Abschnitt zur Version.  
  
 Verwenden Sie in der Regel `CComCriticalSection` über die `typedef` Namen [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Dieser Name verweist auf `CComCriticalSection` Wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  

  
 Finden Sie unter [CComCritSecLock Klasse](../../atl/reference/ccomcritseclock-class.md) für eine sicherere Möglichkeit, verwenden Sie diese Klasse als das Aufrufen `Lock` und `Unlock` direkt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 Der Konstruktor.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die [M_sec](#m_sec) -Datenmember auf NULL **.**  
  
##  <a name="init"></a>CComCriticalSection::Init  
 Ruft die Win32-Funktion [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), die die kritischen Abschnittsobjekt in enthaltenen initialisiert die [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg **E_OUTOFMEMORY** oder **E_FAIL** bei einem Fehler.  
  
##  <a name="lock"></a>CComCriticalSection::Lock  
 Ruft die Win32-Funktion [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), welche wartet, bis der Thread den kritischen Abschnittsobjekt in enthaltenen Besitz kann die [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg **E_OUTOFMEMORY** oder **E_FAIL** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Die kritischen Abschnittsobjekt muss zunächst initialisiert werden, durch einen Aufruf der [Init](#init) Methode. Wenn Sie der geschützte Code die Ausführung beendet hat, muss der Thread Aufrufen [Unlock](#unlock) den Besitz der kritischen Abschnitt freigibt.  
  
##  <a name="m_sec"></a>CComCriticalSection::m_sec  
 Enthält einen kritischen Abschnitt-Objekt, das von allen verwendet wird `CComCriticalSection` Methoden.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>CComCriticalSection::Term  
 Ruft die Win32-Funktion [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), die alle von der in enthaltenen kritischen Abschnittsobjekt verwendete Ressourcen frei der [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Einmal `Term` aufgerufen wurde, der kritische Abschnitt kann nicht mehr für die Synchronisierung verwendet werden.  
  
##  <a name="unlock"></a>CComCriticalSection::Unlock  
 Ruft die Win32-Funktion [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), der Besitzer des Objekts kritischen Abschnitt in enthaltenen frei der [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Zuerst letztere der Thread aufrufen, muss die [Sperre](#lock) Methode. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf von `Unlock` den Besitz der kritischen Abschnitt freigibt.  
  
## <a name="see-also"></a>Siehe auch  
 [CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComCritSecLock-Klasse](../../atl/reference/ccomcritseclock-class.md)
