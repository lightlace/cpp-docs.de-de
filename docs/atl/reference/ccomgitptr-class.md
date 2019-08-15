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
ms.openlocfilehash: 00265cc445191a5a539ab21d6f64b255849495e9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497262"
---
# <a name="ccomgitptr-class"></a>CComGITPtr-Klasse

Diese Klasse stellt Methoden für den Umgang mit Schnittstellen Zeigern und der globalen Schnittstellen Tabelle (git) bereit.

## <a name="syntax"></a>Syntax

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Schnittstellen Zeigers, der im git gespeichert werden soll.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Der Konstruktor.|
|[CComGITPtr::~CComGITPtr](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::Attach](#attach)|Mit dieser Methode wird der Schnittstellen Zeiger in der globalen Schnittstellen Tabelle (git) registriert.|
|[CComGITPtr::CopyTo](#copyto)|Mit dieser Methode wird die-Schnittstelle aus der globalen Schnittstellen Tabelle (git) in den bestandenen Zeiger kopiert.|
|[CComGITPtr::Detach](#detach)|Mit dieser Methode können Sie die Zuordnung der-Schnitt `CComGITPtr` Stelle zum-Objekt aufheben.|
|[CComGITPtr::GetCookie](#getcookie)|Ruft diese Methode auf, um das Cookie aus `CComGITPtr` dem-Objekt zurückzugeben.|
|[CComGITPtr::Revoke](#revoke)|Diese Methode wird aufgerufen, um die-Schnittstelle aus der globalen Schnittstellen Tabelle (git) zu entfernen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr:: Operator DWORD](#operator_dword)|Gibt das Cookie aus dem `CComGITPtr` -Objekt zurück.|
|[CComGITPtr::operator =](#operator_eq)|Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Das Cookie.|

## <a name="remarks"></a>Hinweise

Objekte, die den Free Thread-Mars Haller aggregieren und Schnittstellen Zeiger verwenden müssen, die von anderen Objekten abgerufen werden, müssen zusätzliche Schritte ausführen, um sicherzustellen, dass die Schnittstellen ordnungsgemäß gemarshallt werden. Dies umfasst in der Regel das Speichern der Schnittstellen Zeiger im git und das erhalten des Zeigers aus dem git bei jeder Verwendung. Die- `CComGITPtr` Klasse wird bereitgestellt, um die Verwendung von im git gespeicherten Schnittstellen Zeigern zu erleichtern.

> [!NOTE]
>  Die globale Schnittstellen Tabellen Funktion ist nur unter Windows 95 mit DCOM-Version 1,1 und höher, Windows 98, Windows NT 4,0 mit Service Pack 3 und höher und Windows 2000 verfügbar.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="attach"></a>CComGITPtr:: Attach

Mit dieser Methode wird der Schnittstellen Zeiger in der globalen Schnittstellen Tabelle (git) registriert.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Der Schnittstellen Zeiger, der dem git hinzugefügt werden soll.

*dwCookie*<br/>
Das Cookie, das zum Identifizieren des Schnittstellen Zeigers verwendet wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Fehler auf, wenn das git ungültig ist oder wenn das Cookie gleich NULL ist.

##  <a name="ccomgitptr"></a>CComGITPtr:: CComGITPtr

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
in Ein Schnittstellen Zeiger, der in der globalen Schnittstellen Tabelle (git) gespeichert werden soll.

*git*<br/>
in Ein Verweis auf ein vorhandenes `CComGITPtr` -Objekt.

*dwCookie*<br/>
in Ein Cookie, das zum Identifizieren des Schnittstellen Zeigers verwendet wird.

*rv*<br/>
in Das Quell `CComGITPtr` Objekt, aus dem Daten verschoben werden sollen.

### <a name="remarks"></a>Hinweise

Erstellt ein neues `CComGITPtr` -Objekt und verwendet optional ein `CComGITPtr` vorhandenes-Objekt.

Der Konstruktor, der *RV* nutzt, ist ein bewegungskonstruktor. Die Daten werden aus der Quelle, dem *RV*und dem *RV* gelöscht.

##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr

Der Destruktor.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt die-Schnittstelle aus der globalen Schnittstellen Tabelle (git) mithilfe von [CComGITPtr:: Widerruf](#revoke).

##  <a name="copyto"></a>CComGITPtr:: CopyTo

Mit dieser Methode wird die-Schnittstelle aus der globalen Schnittstellen Tabelle (git) in den bestandenen Zeiger kopiert.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parameter

*pp*<br/>
Der Zeiger, der die-Schnittstelle empfangen soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die-Schnittstelle aus git wird in den bestandenen Zeiger kopiert. Der Zeiger muss vom Aufrufer freigegeben werden, wenn er nicht mehr benötigt wird.

##  <a name="detach"></a>CComGITPtr::D Etach

Mit dieser Methode können Sie die Zuordnung der-Schnitt `CComGITPtr` Stelle zum-Objekt aufheben.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie aus dem `CComGITPtr` -Objekt zurück.

### <a name="remarks"></a>Hinweise

Der Aufrufer muss die Schnittstelle aus dem git entfernen, indem er [CComGITPtr::](#revoke)revoverwendet.

##  <a name="getcookie"></a>CComGITPtr:: GetCookie

Ruft diese Methode auf, um das Cookie aus `CComGITPtr` dem-Objekt zurückzugeben.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie zurück.

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Variable, die zum Identifizieren einer Schnittstelle und ihrer Position verwendet wird.

##  <a name="m_dwcookie"></a>CComGITPtr:: m_dwCookie

Das Cookie.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Element Variable, die zum Identifizieren einer Schnittstelle und ihrer Position verwendet wird.

##  <a name="operator_eq"></a>CComGITPtr:: Operator =

Der Zuweisungs Operator.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parameter

*p*<br/>
in Ein Zeiger auf eine-Schnittstelle.

*git*<br/>
in Ein Verweis auf ein `CComGITPtr` -Objekt.

*dwCookie*<br/>
in Ein Cookie, das zum Identifizieren des Schnittstellen Zeigers verwendet wird.

*rv*<br/>
in Der `CComGITPtr` zum Verschieben von Daten aus.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComGITPtr` Objekt zurück.

### <a name="remarks"></a>Hinweise

Weist einem `CComGITPtr` -Objekt einen neuen Wert zu, entweder aus einem vorhandenen-Objekt oder einem Verweis auf eine globale Schnittstellen Tabelle.

##  <a name="operator_dword"></a>CComGITPtr:: Operator DWORD

Gibt das Cookie zurück, das `CComGITPtr` dem-Objekt zugeordnet ist.

```
operator DWORD() const;
```

### <a name="remarks"></a>Hinweise

Das Cookie ist eine Variable, die zum Identifizieren einer Schnittstelle und ihrer Position verwendet wird.

##  <a name="revoke"></a>CComGITPtr:: Widerruf

Ruft diese Methode auf, um die aktuelle Schnittstelle aus der globalen Schnittstellen Tabelle (git) zu entfernen.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Entfernt die-Schnittstelle aus git.

## <a name="see-also"></a>Siehe auch

[Freethreaded Marshaler](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Zugreifen auf Schnittstellen über mehrere Apartments](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Verwendungszwecke der globalen Schnittstellen Tabelle](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
