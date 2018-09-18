---
title: CAcl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db7903dccfd851bb4bf76f1990424f887686d344
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070105"
---
# <a name="cacl-class"></a>CAcl-Klasse

Diese Klasse ist ein Wrapper für ein `ACL` (Access Control List)-Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAcl
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Ein Array von ACCESS_MASKs.|
|[CAcl::CAceFlagArray](#caceflagarray)|Ein Array von BYTEs.|
|[CAcl::CAceTypeArray](#cacetypearray)|Ein Array von BYTEs.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|Der Konstruktor.|
|[CAcl:: ~ CAcl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|Gibt die Anzahl von Access Control Entry (ACE) Objekte zurück.|
|[CAcl::GetAclEntries](#getaclentries)|Ruft ab, die Access-Control-Zugriffssteuerungsliste (ACL)-Einträge aus der `CAcl` Objekt.|
|[CAcl::GetAclEntry](#getaclentry)|Ruft alle Informationen über einen Eintrag in einer `CAcl` Objekt.|
|[CAcl::GetLength](#getlength)|Die Länge der ACL zurückgegeben.|
|[CAcl::GetPACL](#getpacl)|Gibt eine PACL (Zeiger auf eine Zugriffssteuerungsliste) zurück.|
|[CAcl::IsEmpty](#isempty)|Tests der `CAcl` -Objekt für Einträge.|
|[CAcl::IsNull](#isnull)|Gibt den Status der `CAcl` Objekt.|
|[CAcl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der `CAcl` Objekt.|
|[CAcl::RemoveAces](#removeaces)|Entfernt alle Zugriffssteuerungseinträge (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.|
|[CAcl::SetEmpty](#setempty)|Markiert die `CAcl` als leeres Objekt.|
|[CAcl::SetNull](#setnull)|Markiert die `CAcl` Objekt als NULL.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Const ACL CAcl::operator *](#operator_const_acl__star)|Wandelt eine `CAcl` -Objekt an eine `ACL` Struktur.|
|[CAcl::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Die `ACL` Struktur ist der Header des eine Zugriffssteuerungsliste (Access Control List). Eine ACL enthält eine sequenzielle Liste von NULL oder mehr [ACEs](/windows/desktop/SecAuthZ/access-control-entries) (Access Control-Einträge). Einzelne ACEs in einer ACL sind nummeriert von 0 bis *n-1*, wobei *n* ist die Anzahl der ACEs in der ACL. Wenn Sie eine ACL zu bearbeiten, bezieht sich eine Anwendung auf eine Access Control Entry (ACE), in der ACL aus, nach ihrem Index.

Es gibt zwei ACL-Typen:

- Discretionary

- System

Eine freigegebene ACL wird gesteuert, durch den Besitzer eines Objekts oder jeder Benutzer über WRITE_DAC-Zugriff auf das Objekt gewährt. Es gibt an, dass die Zugriff bestimmter Benutzer und Gruppen auf ein Objekt haben können. Beispielsweise können der Besitzer einer Datei eine discretionary ACL, um zu steuern, welche Benutzer und Gruppen können und Zugriff auf die Datei haben darf nicht.

Ein Objekt kann auch auf Systemebene Sicherheitsinformationen zugeordnet, in der Form eines Systems ACL, die von einem Systemadministrator gesteuert haben. Ein System ACL können den Systemadministrator alle Versuche zum Zugriff auf ein Objekt zu überwachen.

Weitere Informationen finden Sie unter den [ACL](/windows/desktop/SecAuthZ/access-control-lists) Diskussion im Windows SDK.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray

Ein Array von ACCESS_MASK-Objekten.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt an, der Arraytyp, der zum Speichern von Zugriffsrechten verwendet in Access Control-Einträge (ACEs) verwendet werden kann.

##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray

Ein Array von BYTEs.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt den Arraytyp verwendet, um die Access Control Entry (ACE) typspezifische Steuerungsflags definieren. Finden Sie unter den [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Definition für die vollständige Liste der möglichen Flags.

##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray

Ein Array von BYTEs.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt den Arraytyp verwendet, um die Art der Access Control Entry (ACE) Objekte, z. B. ACCESS_ALLOWED_ACE_TYPE oder ACCESS_DENIED_ACE_TYPE definieren. Finden Sie unter den [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Definition für die vollständige Liste der möglichen Typen.

##  <a name="cacl"></a>  CAcl::CAcl

Der Konstruktor.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*<br/>
Ein vorhandenes `CAcl`-Objekt.

### <a name="remarks"></a>Hinweise

Die `CAcl` -Objekt kann optional mit einer vorhandenen erstellt werden `CAcl` Objekt.

##  <a name="dtor"></a>  CAcl:: ~ CAcl

Der Destruktor.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle Ressourcen, die vom Objekt abgerufene frei.

##  <a name="getacecount"></a>  CAcl::GetAceCount

Gibt die Anzahl von Access Control Entry (ACE) Objekte zurück.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der ACE-Einträge in der `CAcl` Objekt.

##  <a name="getaclentries"></a>  CAcl::GetAclEntries

Ruft ab, die Access-Control-Zugriffssteuerungsliste (ACL)-Einträge aus der `CAcl` Objekt.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSids*<br/>
Ein Zeiger auf ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.

*pAccessMasks*<br/>
Die Zugriffsmasken.

*pAceTypes*<br/>
Die Typen des Access Control Entry (ACE).

*pAceFlags*<br/>
Die ACE-Flags.

### <a name="remarks"></a>Hinweise

Diese Methode füllt die Arrayparameter mit den Details eines jeden ACE-Objekts, das innerhalb der `CAcl` Objekt. Verwenden Sie NULL, wenn die Details für dieses bestimmte Array nicht erforderlich sind.

Den Inhalt jedes Arrays entsprechen, d. h. das erste Element des der `CAccessMaskArray` das erste Element im Array entspricht der `CSidArray` Array und So weiter.

Finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) für Weitere Informationen zu den ACE-Typen und Flags.

##  <a name="getaclentry"></a>  CAcl::GetAclEntry

Ruft alle Informationen über einen Eintrag in einer Zugriffssteuerungsliste (ACL) ab.

```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index mit dem ACL-Eintrag zum Abrufen.

*pSid*<br/>
Die [CSid](../../atl/reference/csid-class.md) Objekt, für welche die ACL-Eintrag gilt.

*pMask*<br/>
Die Maske, die Angabe von Berechtigungen zu erteilen oder Verweigern des Zugriffs.

*PGeben*<br/>
Der ACE-Typ.

*pFlags*<br/>
Die ACE-Flags.

*pObjectType*<br/>
Der Objekttyp. Dies wird auf GUID_NULL festgelegt werden, wenn der Objekttyp in der ACE nicht angegeben ist oder wenn der ACE kein ACE-Objekt ist.

*pInheritedObjectType*<br/>
Den geerbten Objekttyp. Dies wird auf GUID_NULL festgelegt werden, wenn in der ACE nicht der geerbten Objekttyp angegeben ist oder der ACE kein ACE-Objekt ist.

### <a name="remarks"></a>Hinweise

Diese Methode ruft alle Informationen über eine einzelne ACE, der Bereitstellung mehr Informationen als [CAcl::GetAclEntries](#getaclentries) allein zur Verfügung.

Finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) für Weitere Informationen zu den ACE-Typen und Flags.

##  <a name="getlength"></a>  CAcl::GetLength

Gibt die Länge der Zugriffssteuerungsliste (ACL) zurück.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die erforderliche Länge in Bytes zurück zum Speichern der `ACL` Struktur.

##  <a name="getpacl"></a>  CAcl::GetPACL

Gibt einen Zeiger auf eine Access Control List (ACL).

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `ACL` Struktur.

##  <a name="isempty"></a>  CAcl::IsEmpty

Tests der `CAcl` -Objekt für Einträge.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" zurück, wenn die `CAcl` Objekt ist nicht NULL und keine Einträge enthält. Gibt "false" zurück, wenn die `CAcl` Objekt ist entweder NULL oder enthält mindestens einen Eintrag.

##  <a name="isnull"></a>  CAcl::IsNull

Gibt den Status der `CAcl` Objekt.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die `CAcl` Objekt ist NULL, sonst FALSE.

##  <a name="operator_const_acl__star"></a>  Const ACL CAcl::operator *

Wandelt eine `CAcl` -Objekt an eine `ACL` (Access Control List)-Struktur.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Gibt die Adresse der `ACL` Struktur.

##  <a name="operator_eq"></a>  CAcl::operator =

Zuweisungsoperator.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*<br/>
Die `CAcl` das vorhandene Objekt zuweisen.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf die aktualisierte `CAcl` Objekt.

##  <a name="removeace"></a>  CAcl::RemoveAce

Entfernt einen bestimmten ACE (Access Control Entry) aus der `CAcl` Objekt.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index mit dem ACE-Eintrag zu entfernen.

### <a name="remarks"></a>Hinweise

Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeaces"></a>  CAcl::RemoveAces

Entfernt Alls ACEs (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein Verweis auf ein `CSid`-Objekt.

##  <a name="setempty"></a>  CAcl::SetEmpty

Markiert die `CAcl` als leeres Objekt.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Hinweise

Die `CAcl` kann leer oder auf NULL festgelegt werden: die beiden Zustände unterscheiden sich.

##  <a name="setnull"></a>  CAcl::SetNull

Markiert die `CAcl` Objekt als NULL.

```
void SetNull() throw();
```

### <a name="remarks"></a>Hinweise

Die `CAcl` kann leer oder auf NULL festgelegt werden: die beiden Zustände unterscheiden sich.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
