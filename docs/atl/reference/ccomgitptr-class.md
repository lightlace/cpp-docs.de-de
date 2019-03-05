---
title: CComGITPtr-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: bf509d027833610e4251c009d4e444dad3fdd5ce
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296032"
---
# <a name="ccomgitptr-class"></a>CComGITPtr-Klasse

Diese Klasse stellt Methoden für den Umgang mit Schnittstellenzeiger und der globale Schnittstellentabelle (GIT).

## <a name="syntax"></a>Syntax

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Schnittstellenzeigers in GIT gespeichert werden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Der Konstruktor.|
|[CComGITPtr::~CComGITPtr](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::Attach](#attach)|Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.|
|[CComGITPtr::CopyTo](#copyto)|Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) in den übergebenen Zeiger zu kopieren.|
|[CComGITPtr::Detach](#detach)|Rufen Sie diese Methode zum Aufheben der Zuordnung der Schnittstelle aus der `CComGITPtr` Objekt.|
|[CComGITPtr::GetCookie](#getcookie)|Rufen Sie diese Methode, um die Rückgabegröße des Cookies aus der `CComGITPtr` Objekt.|
|[CComGITPtr::Revoke](#revoke)|Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) zu entfernen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::operator DWORD](#operator_dword)|Gibt das Cookie aus der `CComGITPtr` Objekt.|
|[CComGITPtr::operator =](#operator_eq)|Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Das Cookie.|

## <a name="remarks"></a>Hinweise

Objekte, die die freethreaded Marshaler aggregiert und müssen Schnittstellenzeiger abgerufen, die von anderen Objekten verwenden müssen zusätzliche Schritte, stellen Sie sicher, dass die Schnittstellen ordnungsgemäß gemarshallt werden. In der Regel umfasst dies den Schnittstellenzeiger in GIT speichern und die Zeiger aus der GIT jedes Mal, wenn er verwendet wird. Die Klasse `CComGITPtr` wird bereitgestellt, um Informationen zur Nutzung von Schnittstellenzeiger in GIT gespeichert.

> [!NOTE]
>  Die globale Schnittstelle Tabelle-Funktion ist nur auf Windows 95 mit DCOM Version 1.1 und höher, Windows 98, Windows NT 4.0 mit Service Pack 3 und höher und Windows 2000 verfügbar.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="attach"></a>  CComGITPtr::Attach

Rufen Sie diese Methode, um den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) zu registrieren.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Der Schnittstellenzeiger GIT hinzugefügt werden.

*dwCookie*<br/>
Das Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Assertionsfehler, wenn GIT nicht gültig ist, oder wenn das Cookie gleich NULL ist.

##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr

Der Konstruktor.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Ein Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) gespeichert werden.

*git*<br/>
[in] Ein Verweis auf einen vorhandenen `CComGITPtr` Objekt.

*dwCookie*<br/>
[in] Ein Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.

*rv*<br/>
[in] Die Quelle `CComGITPtr` Objekt, das Verschieben von Daten aus.

### <a name="remarks"></a>Hinweise

Erstellt ein neues `CComGITPtr` Objekts, das optional verwenden einer vorhandenen `CComGITPtr` Objekt.

Der Konstruktor mit *rv* ein bewegungskonstruktor ist. Beim Verschieben der Daten aus der Quelle *rv*, und klicken Sie dann *rv* deaktiviert ist.

##  <a name="dtor"></a>  CComGITPtr:: ~ CComGITPtr

Der Destruktor.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt die Schnittstelle aus der globalen Schnittstellentabelle (GIT) mit [CComGITPtr::Revoke](#revoke).

##  <a name="copyto"></a>  CComGITPtr::CopyTo

Rufen Sie diese Methode, um die Schnittstelle aus der globalen Schnittstellentabelle (GIT) in den übergebenen Zeiger zu kopieren.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parameter

*pp*<br/>
Der Zeiger handelt es sich um die Schnittstelle zu erhalten.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die Schnittstelle aus der GIT wird in den übergebenen Zeiger kopiert. Der Zeiger muss vom Aufrufer freigegeben werden, wenn es nicht mehr benötigt wird.

##  <a name="detach"></a>  CComGITPtr::Detach

Rufen Sie diese Methode zum Aufheben der Zuordnung der Schnittstelle aus der `CComGITPtr` Objekt.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie aus der `CComGITPtr` Objekt.

### <a name="remarks"></a>Hinweise

Es ist Aufgabe des Aufrufers, entfernen Sie die Schnittstelle aus der GIT mit [CComGITPtr::Revoke](#revoke).

##  <a name="getcookie"></a>  CComGITPtr::GetCookie

Rufen Sie diese Methode, um die Rückgabegröße des Cookies aus der `CComGITPtr` Objekt.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie zurück.

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Variable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.

##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie

Das Cookie.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Member-Variable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.

##  <a name="operator_eq"></a>  CComGITPtr::operator =

Der Zuweisungsoperator.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Ein Zeiger auf eine Schnittstelle.

*git*<br/>
[in] Ein Verweis auf eine `CComGITPtr` Objekt.

*dwCookie*<br/>
[in] Ein Cookie verwendet, um den Schnittstellenzeiger zu identifizieren.

*rv*<br/>
[in] Die `CComGITPtr` zum Verschieben von Daten aus.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CComGITPtr` Objekt.

### <a name="remarks"></a>Hinweise

Weist einen neuen Wert ein `CComGITPtr` Objekt, das entweder von einem vorhandenen Objekt oder aus einem Verweis auf eine globale Schnittstellentabelle.

##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD

Gibt das Cookie für die `CComGITPtr` Objekt.

```
operator DWORD() const;
```

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Variable verwendet, um eine Schnittstelle und den Speicherort zu identifizieren.

##  <a name="revoke"></a>  CComGITPtr::Revoke

Rufen Sie diese Methode, um die aktuelle Schnittstelle aus der globalen Schnittstellentabelle (GIT) zu entfernen.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Entfernt die Schnittstelle aus der GIT.

## <a name="see-also"></a>Siehe auch

[Freethreaded Marshaller](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Zugriff auf Schnittstellen über Apartments hinweg](/windows/desktop/com/accessing-interfaces-across-apartments)<br/>
[Verwenden Sie die globale Schnittstellentabelle](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
