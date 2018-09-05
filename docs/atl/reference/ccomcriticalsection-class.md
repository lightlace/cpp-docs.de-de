---
title: CComCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f6009af2026f10ff25983544e6724385246a42f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755743"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection-Klasse

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts-Objekts.

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
|[CComCriticalSection::Init](#init)|Erstellt und initialisiert ein Objekt des kritischen Abschnitts.|
|[CComCriticalSection::Lock](#lock)|Ruft den Besitz von Objekt des kritischen Abschnitts ab.|
|[CComCriticalSection::Term](#term)|Gibt ein Objekt des kritischen Abschnitts, die Systemressourcen frei.|
|[CComCriticalSection::Unlock](#unlock)|Gibt den Besitz des Objekts kritischen Abschnitt frei.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|Ein Objekt CRITICAL_SECTION.|

## <a name="remarks"></a>Hinweise

`CComCriticalSection` ist vergleichbar mit der Klasse [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), außer dass Sie explizit initialisieren und den kritischen Abschnitt freigeben müssen.

Normalerweise verwenden Sie `CComCriticalSection` über die **Typedef** Namen [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Dieser Name verweist auf `CComCriticalSection` beim [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  

Finden Sie unter [CComCritSecLock-Klasse](../../atl/reference/ccomcritseclock-class.md) für eine sicherere Möglichkeit, diese Klasse als das Aufrufen `Lock` und `Unlock` direkt.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection

Der Konstruktor.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Hinweise

Legt die [M_sec](#m_sec) -Datenmember auf NULL.

##  <a name="init"></a>  CComCriticalSection::Init

Ruft die Win32-Funktion [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), die Objekt des kritischen Abschnitts, die in enthaltenen initialisiert die [M_sec](#m_sec) -Datenmember.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, E_OUTOFMEMORY oder E_FAIL, bei einem Fehler zurück.

##  <a name="lock"></a>  CComCriticalSection::Lock

Ruft die Win32-Funktion [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection), welche wartet, bis der Thread den kritischen Abschnitt-Objekt, das in enthaltenen Besitz kann die [M_sec](#m_sec) -Datenmember.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, E_OUTOFMEMORY oder E_FAIL, bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Objekt des kritischen Abschnitts muss zunächst initialisiert werden, durch einen Aufruf der [Init](#init) Methode. Wenn der geschützte Code die Ausführung beendet hat, muss der Thread Aufrufen [Unlock](#unlock) um den Besitz der des kritischen Abschnitts freizugeben.

##  <a name="m_sec"></a>  CComCriticalSection::m_sec

Enthält einen kritischen Abschnitt-Objekt, das von allen verwendet wird `CComCriticalSection` Methoden.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>  CComCriticalSection::Term

Ruft die Win32-Funktion [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), die alle vom Objekt kritischen Abschnitts, die in enthaltenen verwendete Ressourcen frei der [M_sec](#m_sec) -Datenmember.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Einmal `Term` aufgerufen wurde, der kritische Abschnitt kann nicht mehr für die Synchronisierung verwendet werden.

##  <a name="unlock"></a>  CComCriticalSection::Unlock

Ruft die Win32-Funktion [LeaveCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection), der Besitzer des Objekts in enthaltenen kritischen Abschnitt frei der [M_sec](#m_sec) -Datenmember.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Zuerst den Besitz des Threads muss rufen Sie zum Abrufen der [Sperre](#lock) Methode. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf `Unlock` um den Besitz der des kritischen Abschnitts freizugeben.

## <a name="see-also"></a>Siehe auch

[CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)   
[CComCritSecLock-Klasse](../../atl/reference/ccomcritseclock-class.md)
