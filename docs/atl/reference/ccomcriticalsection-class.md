---
title: Ccomcriticalsection-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: ee4ce32ed4ae04bc3b390af5cf104b8a0af599f8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497282"
---
# <a name="ccomcriticalsection-class"></a>Ccomcriticalsection-Klasse

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts Objekts bereit.

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
|[CComCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnitts Objekt.|
|[CComCriticalSection::Lock](#lock)|Ruft den Besitz des kritischen Abschnitts Objekts ab.|
|[CComCriticalSection::Term](#term)|Gibt Systemressourcen frei, die vom Objekt des kritischen Abschnitts verwendet werden.|
|[CComCriticalSection::Unlock](#unlock)|Gibt den Besitz des kritischen Abschnitts Objekts frei.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|Ein CRITICAL_SECTION-Objekt.|

## <a name="remarks"></a>Hinweise

`CComCriticalSection`ähnelt der Klasse [ccomautocriticalsection](../../atl/reference/ccomautocriticalsection-class.md), mit dem Unterschied, dass Sie den kritischen Abschnitt explizit initialisieren und freigeben müssen.

In der Regel verwenden `CComCriticalSection` Sie den **typedef** -Namen [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Dieser Name verweist `CComCriticalSection` auf den Fall, dass [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.

Unter [ccomcritcclock Class](../../atl/reference/ccomcritseclock-class.md) finden Sie eine sicherere Möglichkeit, diese Klasse zu verwenden `Lock` , `Unlock` als direkt aufrufen.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore. h

##  <a name="ccomcriticalsection"></a>Ccomcriticalsection:: ccomcriticalsection

Der Konstruktor.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Hinweise

Legt den [m_sec](#m_sec) -Datenmember auf NULL fest.

##  <a name="init"></a>Ccomcriticalsection:: init

Ruft die Win32-Funktion [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)auf, die das im [m_sec](#m_sec) -Datenmember enthaltene kritische Abschnitts Objekt initialisiert.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, E_OUTOFMEMORY oder E_FAIL bei einem Fehler zurück.

##  <a name="lock"></a>Ccomcriticalsection:: Lock

Ruft die Win32-Funktion " [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)" auf, die wartet, bis der Thread den Besitz des kritischen Abschnitts Objekts übernimmt, das im [m_sec](#m_sec) -Datenmember enthalten ist.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg, E_OUTOFMEMORY oder E_FAIL bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Das Critical Section-Objekt muss zuerst mit einem Rückruf der [Init](#init) -Methode initialisiert werden. Wenn die Ausführung des geschützten Codes abgeschlossen ist, muss der Thread [Unlock](#unlock) aufgerufen werden, um den Besitz des kritischen Abschnitts freizugeben.

##  <a name="m_sec"></a>Ccomcriticalsection:: m_sec

Enthält ein kritisches Abschnitts Objekt, das von allen `CComCriticalSection` -Methoden verwendet wird.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>Ccomcriticalsection:: Term

Ruft die Win32-Funktion [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)auf, die alle Ressourcen freigibt, die vom kritischen Abschnitts Objekt verwendet werden, das im [m_sec](#m_sec) -Datenmember enthalten ist.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Nachdem `Term` aufgerufen wurde, kann der kritische Abschnitt nicht mehr für die Synchronisierung verwendet werden.

##  <a name="unlock"></a>Ccomcriticalsection:: Unlock

Ruft die Win32-Funktion " [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)" auf, die den Besitz des kritischen Abschnitts Objekts freigibt, das im [m_sec](#m_sec) -Datenmember enthalten ist.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zuerst den Besitz zu erhalten, muss der Thread die [Lock](#lock) -Methode aufzurufen. Jeder-Befehl `Unlock` erfordert einen entsprechenden-Befehl, um den Besitz des kritischen Abschnitts freizugeben. `Lock`

## <a name="see-also"></a>Siehe auch

[CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock-Klasse](../../atl/reference/ccomcritseclock-class.md)
