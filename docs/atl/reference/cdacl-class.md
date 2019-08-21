---
title: CDacl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 2bc962407bac947f475368b43f5039bca3c1da1e
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915816"
---
# <a name="cdacl-class"></a>CDacl-Klasse

Diese Klasse ist ein Wrapper für eine DACL-Struktur (freigegebene Zugriffs Steuerungs Liste).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CDacl : public CAcl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Der Konstruktor.|
|[CDacl::~CDacl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDacl:: addzukomwedace](#addallowedace)|Fügt dem `CDacl` -Objekt einen zulässigen ACE (Zugriffs Steuerungs Eintrag) hinzu.|
|[CDacl::AddDeniedAce](#adddeniedace)|Fügt dem `CDacl` -Objekt einen verweigerten ACE hinzu.|
|[CDacl::GetAceCount](#getacecount)|Gibt die Anzahl der ACEs (Access-Control-Einträge) im `CDacl` -Objekt zurück.|
|[CDacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CDacl` -Objekt.|
|[CDacl::RemoveAllAces](#removeallaces)|Entfernt alle im `CDacl` -Objekt enthaltenen ACEs.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CDacl:: Operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Die Sicherheits Beschreibung eines Objekts kann eine DACL enthalten. Eine DACL enthält NULL oder mehr ACEs (Access-Control-Einträge), mit denen die Benutzer und Gruppen identifiziert werden, die auf das Objekt zugreifen können. Wenn eine DACL leer ist (d. h., Sie enthält NULL-ACEs), wird kein Zugriff explizit erteilt, sodass der Zugriff implizit verweigert wird. Wenn die Sicherheits Beschreibung eines Objekts jedoch nicht über eine DACL verfügt, ist das Objekt nicht geschützt, und jeder Benutzer verfügt über vollständigen Zugriff.

Zum Abrufen der DACL eines Objekts müssen Sie der Besitzer des Objekts sein oder über READ_CONTROL-Zugriff auf das Objekt verfügen. Um die DACL eines Objekts zu ändern, müssen Sie über WRITE_DAC-Zugriff auf das-Objekt verfügen.

Verwenden Sie die-Klassen Methoden zum Erstellen, hinzufügen, entfernen und Löschen von ACEs `CDacl` aus dem-Objekt. Siehe auch [atlgetdacl](security-global-functions.md#atlgetdacl) und [atlsetdacl](security-global-functions.md#atlsetdacl).

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/desktop/SecAuthZ/access-control) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CaCl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="addallowedace"></a>CDacl:: addzukomwedace

Fügt dem `CDacl` -Objekt einen zulässigen ACE (Zugriffs Steuerungs Eintrag) hinzu.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein [CSID](../../atl/reference/csid-class.md) -Objekt.

*AccessMask*<br/>
Gibt die Maske der Zugriffsrechte an, die für das angegebene `CSid` Objekt zulässig sein sollen.

*AceFlags*<br/>
Ein Satz von Bitflags, die die ACE-Vererbung steuern.

*pObjectType*<br/>
Der Objekttyp.

*pInheritedObjectType*<br/>
Der geerbte Objekttyp.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der ACE dem- `CDacl` Objekt hinzugefügt wird, false bei Fehler.

### <a name="remarks"></a>Hinweise

Ein `CDacl` -Objekt enthält NULL oder mehr ACEs (Access-Control-Einträge), die die Benutzer und Gruppen identifizieren, die auf das Objekt zugreifen können. Diese Methode fügt einen ACE hinzu, der den Zugriff `CDacl` auf das-Objekt zulässt.

Eine Beschreibung der verschiedenen Flags, die im `AceFlags`-Parameter festgelegt werden können, finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header).

##  <a name="adddeniedace"></a>CDacl:: adddeniedace

Fügt dem `CDacl` -Objekt einen verweigerten ACE (Zugriffs Steuerungs Eintrag) hinzu.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein `CSid`-Objekt.

*AccessMask*<br/>
Gibt die Maske der Zugriffsrechte an, die für das angegebene `CSid` Objekt verweigert werden sollen.

*AceFlags*<br/>
Ein Satz von Bitflags, die die ACE-Vererbung steuern. Der Standardwert ist 0 (null) in der ersten Form der-Methode.

*pObjectType*<br/>
Der Objekttyp.

*pInheritedObjectType*<br/>
Der geerbte Objekttyp.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der ACE dem- `CDacl` Objekt hinzugefügt wird, false bei Fehler.

### <a name="remarks"></a>Hinweise

Ein `CDacl` -Objekt enthält NULL oder mehr ACEs (Access-Control-Einträge), die die Benutzer und Gruppen identifizieren, die auf das Objekt zugreifen können. Diese Methode fügt einen ACE hinzu, der den Zugriff `CDacl` auf das Objekt verweigert.

Eine Beschreibung der verschiedenen Flags, die im `AceFlags`-Parameter festgelegt werden können, finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header).

##  <a name="cdacl"></a>CDacl:: CDacl

Der Konstruktor.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Eine vorhandene `ACL` Struktur (Zugriffs Steuerungs Liste).

### <a name="remarks"></a>Hinweise

Das `CDacl` -Objekt kann optional mithilfe einer vorhandenen `ACL` -Struktur erstellt werden. Es ist wichtig zu beachten, dass nur eine DACL (freigegebene Zugriffs Steuerungs Liste) und keine SACL (System-Zugriffs Steuerungs Liste) als dieser Parameter übergeben werden sollte. In Debugbuilds führt das Übergeben einer SACL zu einer Bestätigung. In Releasebuilds bewirkt das Übergeben einer SACL, dass die ACEs (Access-Control-Einträge) in der ACL ignoriert werden, und es tritt kein Fehler auf.

##  <a name="dtor"></a>CDacl:: ~ CDacl

Der Destruktor.

```
~CDacl () throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle Ressourcen frei, die vom-Objekt abgerufen werden, einschließlich aller ACEs (Access-Control-Einträge) mithilfe von [CDacl:: removeallaces](#removeallaces).

##  <a name="getacecount"></a>CDacl:: getacecount

Gibt die Anzahl der ACEs (Access-Control-Einträge) im `CDacl` -Objekt zurück.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der im `CDacl` -Objekt enthaltenen ACEs zurück.

##  <a name="operator_eq"></a>CDacl:: Operator =

Zuweisungsoperator.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die ACL (Zugriffs Steuerungs Liste), die dem vorhandenen Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das aktualisierte `CDacl` Objekt zurück.

### <a name="remarks"></a>Hinweise

Stellen Sie sicher, dass Sie nur eine DACL (freigegebene Zugriffs Steuerungs Liste) an diese Funktion übergeben. Wenn eine SACL (System Access-Control List) an diese Funktion übergeben wird, wird eine Assert-Funktion in Debugbuilds ausgelöst, es wird jedoch kein Fehler in Releasebuilds verursacht.

##  <a name="removeace"></a>CDacl:: RemoveAce

Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CDacl` -Objekt.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index für den zu entfern-ACE-Eintrag.

### <a name="remarks"></a>Hinweise

Diese Methode wird von [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat) abgeleitet.

##  <a name="removeallaces"></a>CDacl:: removeallaces

Entfernt alle im `CDacl` -Objekt enthaltenen ACEs (Access-Control-Einträge).

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt jede `ACE` (Zugriffs Steuerungs Eintrag)-Struktur (sofern vorhanden) `CDacl` im-Objekt.

## <a name="see-also"></a>Siehe auch

[Sicherheits Beispiel](../../overview/visual-cpp-samples.md)<br/>
[CAcl-Klasse](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Assen](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
