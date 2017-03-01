---
title: Klasse &quot;CComCriticalSection&quot; | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComCriticalSection
- CComCriticalSection
- ATL::CComCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 21
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: a7c4fbc87ff06bb09766eb3e4ad0d7c5275eed65
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcriticalsection-class"></a>"CComCriticalSection"-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben der Besitz eines kritischen Abschnitts-Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComCriticalSection::Lock](#lock)|Ruft den Besitz des Objekt des kritischen Abschnitts.|  
|[CComCriticalSection::Term](#term)|Gibt die vom Objekt kritischen Abschnitts verwendete Systemressourcen frei.|  
|[CComCriticalSection::Unlock](#unlock)|Gibt den Besitz des Objekts kritischen Abschnitt frei.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|Ein **CRITICAL_SECTION** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComCriticalSection`Klasse ähnelt [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), allerdings müssen Sie explizit initialisieren und des kritischen Abschnitts freigeben.  
  
 Normalerweise verwenden Sie `CComCriticalSection` über die `typedef` Namen [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Dieser Name verweist auf `CComCriticalSection` Wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  

  
 Finden Sie unter [CComCritSecLock Klasse](../../atl/reference/ccomcritseclock-class.md) für eine sichere Methode dieser Klasse als das Aufrufen `Lock` und `Unlock` direkt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="a-nameccomcriticalsectiona--ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 Der Konstruktor.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die [M_sec](#m_sec) -Datenmember auf NULL **.**  
  
##  <a name="a-nameinita--ccomcriticalsectioninit"></a><a name="init"></a>CComCriticalSection::Init  
 Ruft die Win32-Funktion [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), das Objekt des kritischen Abschnitts in enthaltenen initialisiert die [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg **E_OUTOFMEMORY** oder **E_FAIL** bei einem Fehler.  
  
##  <a name="a-namelocka--ccomcriticalsectionlock"></a><a name="lock"></a>CComCriticalSection::Lock  
 Ruft die Win32-Funktion [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), der wartet, bis der Thread Objekt des kritischen Abschnitts enthalten Besitz kann die [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` bei Erfolg **E_OUTOFMEMORY** oder **E_FAIL** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Objekt des kritischen Abschnitts muss zunächst initialisiert werden, durch einen Aufruf der [Init](#init) Methode. Wenn der geschützte Code die Ausführung beendet hat, muss der Thread Aufrufen [Unlock](#unlock) den Besitz der den kritischen Abschnitt freigibt.  
  
##  <a name="a-namemseca--ccomcriticalsectionmsec"></a><a name="m_sec"></a>CComCriticalSection::m_sec  
 Enthält ein kritisches Abschnittsobjekt, mit dem alle `CComCriticalSection` Methoden.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="a-nameterma--ccomcriticalsectionterm"></a><a name="term"></a>CComCriticalSection::Term  
 Ruft die Win32-Funktion [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), die alle vom Objekt kritischen Abschnitts in enthaltenen verwendete Ressourcen frei der [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Einmal `Term` aufgerufen wurde, der kritische Abschnitt kann nicht mehr für die Synchronisierung verwendet werden.  
  
##  <a name="a-nameunlocka--ccomcriticalsectionunlock"></a><a name="unlock"></a>CComCriticalSection::Unlock  
 Ruft die Win32-Funktion [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), die Besitzrechte Objekt des kritischen Abschnitts in enthaltenen Versionen der [M_sec](#m_sec) -Datenmember.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Zuerst letztere der Thread aufrufen, muss die [Sperren](#lock) Methode. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf `Unlock` den Besitz der den kritischen Abschnitt freigibt.  
  
## <a name="see-also"></a>Siehe auch  
 [CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComCritSecLock-Klasse](../../atl/reference/ccomcritseclock-class.md)

