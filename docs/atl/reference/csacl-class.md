---
title: CSacl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: c4bbdfccb2d6d8b167c537b7ae4df57c89438479
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496516"
---
# <a name="csacl-class"></a>CSacl-Klasse

Diese Klasse ist ein Wrapper für eine SACL-Struktur (Systemzugriffssteuerungsliste).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CSacl : public CAcl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|Der Konstruktor.|
|[CSacl::~CSacl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|Fügt dem `CSacl` -Objekt einen Überwachungs Zugriffs Steuerungs Eintrag (ACE) hinzu.|
|[CSacl::GetAceCount](#getacecount)|Gibt die Anzahl der Zugriffs Steuerungs Einträge (ACEs) im `CSacl` -Objekt zurück.|
|[CSacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CSacl` -Objekt.|
|[CSacl::RemoveAllAces](#removeallaces)|Entfernt alle im `CSacl` -Objekt enthaltenen ACEs.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSacl:: Operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Eine SACL enthält Zugriffs Steuerungs Einträge (Access Control Entries, ACEs), die die Typen der Zugriffsversuche angeben, mit denen Überwachungsdaten Sätze im Sicherheits Ereignisprotokoll eines Domänen Controllers generiert werden. Beachten Sie, dass eine SACL Protokolleinträge nur auf dem Domänen Controller generiert, in dem der Zugriffs Versuch aufgetreten ist, nicht auf allen Domänen Controllern, die ein Replikat des Objekts enthalten.

Um die SACL in der Sicherheits Beschreibung eines Objekts festzulegen oder abzurufen, muss das SE_SECURITY_NAME-Privileg im Zugriffs Token des anfordernden Threads aktiviert werden. Der Gruppe "Administratoren" wird diese Berechtigung standardmäßig erteilt und kann anderen Benutzern oder Gruppen gewährt werden. Das erteilen der gewährten Berechtigungen ist nicht alles erforderlich: bevor der durch die Berechtigung definierte Vorgang durchgeführt werden kann, muss die Berechtigung im Sicherheits Zugriffs Token aktiviert werden, damit Sie wirksam werden. Das Modell ermöglicht das Aktivieren von Berechtigungen nur für bestimmte System Vorgänge und wird dann deaktiviert, wenn Sie nicht mehr benötigt werden. Weitere Beispiele für die Aktivierung von SE_SECURITY_NAME finden Sie unter [AtlGetSacl](security-global-functions.md#atlgetsacl) und [AtlSetSacl](security-global-functions.md#atlsetsacl).

Verwenden Sie die zum Hinzufügen, entfernen, erstellen und Löschen von ACEs aus dem `SACL` -Objekt bereitgestellten Klassen Methoden. Weitere Informationen finden Sie unter [atlgesiacl](security-global-functions.md#atlgetsacl) und [atlanll](security-global-functions.md#atlsetsacl).

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CaCl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="addauditace"></a>CSacl:: addauditace

Fügt dem `CSacl` -Objekt einen Überwachungs Zugriffs Steuerungs Eintrag (ACE) hinzu.

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Das [CSID](../../atl/reference/csid-class.md) -Objekt.

*AccessMask*<br/>
Gibt die Maske der Zugriffsrechte an, die für das angegebene `CSid` Objekt überwacht werden sollen.

*bSuccess*<br/>
Gibt an, ob zulässige Zugriffsversuche überwacht werden sollen. Legen Sie dieses Flag auf true fest, um die Überwachung zu aktivieren. andernfalls legen Sie diese Einstellung auf "false" fest.

*bFailure*<br/>
Gibt an, ob verweigerte Zugriffsversuche überwacht werden sollen. Legen Sie dieses Flag auf true fest, um die Überwachung zu aktivieren. andernfalls legen Sie diese Einstellung auf "false" fest.

*AceFlags*<br/>
Ein Satz von Bitflags, die die ACE-Vererbung steuern.

*pObjectType*<br/>
Der Objekttyp.

*pInheritedObjectType*<br/>
Der geerbte Objekttyp.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der ACE dem- `CSacl` Objekt hinzugefügt wird, false bei Fehler.

### <a name="remarks"></a>Hinweise

Ein `CSacl` -Objekt enthält Zugriffs Steuerungs Einträge (Access Control Entries, ACEs), die die Typen der Zugriffsversuche angeben, mit denen Überwachungsdaten Sätze im Sicherheits Ereignisprotokoll generiert werden. Diese Methode fügt dem `CSacl` -Objekt einen solchen ACE hinzu.

Eine Beschreibung der verschiedenen Flags, die im *AceFlags* -Parameter festgelegt werden können, finden Sie unter [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="csacl"></a>CSacl:: CSacl

Der Konstruktor.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Eine vorhandene `ACL` Struktur (Zugriffs Steuerungs Liste).

### <a name="remarks"></a>Hinweise

Das `CSacl` -Objekt kann optional mithilfe einer vorhandenen `ACL` -Struktur erstellt werden. Stellen Sie sicher, dass dieser Parameter eine System Zugriffs Steuerungs Liste (SACL) und keine freigegebene Zugriffs Steuerungs Liste (DACL) ist. In Debugbuilds wird eine-Assertion ausgelöst, wenn eine DACL bereitgestellt wird. In Release werden alle Einträge aus einer DACL ignoriert.

##  <a name="dtor"></a>CSacl:: ~ CSacl

Der Destruktor.

```
~CSacl() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle Ressourcen frei, die vom-Objekt abgerufen werden, einschließlich aller Zugriffs Steuerungs Einträge (ACEs).

##  <a name="getacecount"></a>CSacl:: getacecount

Gibt die Anzahl der Zugriffs Steuerungs Einträge (ACEs) im `CSacl` -Objekt zurück.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der im `CSacl` -Objekt enthaltenen ACEs zurück.

##  <a name="operator_eq"></a>CSacl:: Operator =

Zuweisungsoperator.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `ACL` (Zugriffs Steuerungs Liste), die dem vorhandenen Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das aktualisierte `CSacl` Objekt zurück. Stellen Sie sicher `ACL` , dass der Parameter tatsächlich eine System Zugriffs Steuerungs Liste (SACL) und keine freigegebene Zugriffs Steuerungs Liste (DACL) ist. In Debug-Builds findet eine-Assertion statt, und in `ACL` Releasebuilds wird der-Parameter ignoriert.

##  <a name="removeace"></a>CSacl:: RemoveAce

Entfernt einen bestimmten ACE (Zugriffs Steuerungs Eintrag) aus dem `CSacl` -Objekt.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index für den zu entfern-ACE-Eintrag.

### <a name="remarks"></a>Hinweise

Diese Methode wird von [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat) abgeleitet.

##  <a name="removeallaces"></a>CSacl:: removeallaces

Entfernt alle im `CSacl` -Objekt enthaltenen Zugriffs Steuerungs Einträge (ACEs).

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt alle `ACE` -Strukturen (sofern vorhanden) `CSacl` im-Objekt.

## <a name="see-also"></a>Siehe auch

[CAcl-Klasse](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Assen](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
