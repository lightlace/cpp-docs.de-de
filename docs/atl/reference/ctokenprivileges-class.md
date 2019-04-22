---
title: CTokenPrivileges-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 8bca3e1d45d0a85d1d4ceac4ffdf7b11091020f6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769315"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges-Klasse

Diese Klasse ist ein Wrapper für die `TOKEN_PRIVILEGES` Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CTokenPrivileges
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Der Konstruktor.|
|[CTokenPrivileges::~CTokenPrivileges](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|Fügt einen oder mehrere Berechtigungen, um die `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::Delete](#delete)|Löscht eine Berechtigung aus dem `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::DeleteAll](#deleteall)|Löscht alle Berechtigungen aus der `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetCount](#getcount)|Gibt die Anzahl der Berechtigungen von Einträgen in der `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Ruft den Anzeigenamen für die Berechtigungen, die innerhalb der `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetLength](#getlength)|Gibt die Größe des Puffers in Bytes erforderlich ist, enthalten die `TOKEN_PRIVILEGES` Struktur dargestellt werden, indem die `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Ruft die lokal eindeutige Bezeichner (LUIDs) und die Attributflags aus der `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ruft ab, die Berechtigung-Namen und das von Attributflags aus der `CTokenPrivileges` Objekt.|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Gibt einen Zeiger auf die `TOKEN_PRIVILEGES` Struktur.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Ruft das Attribut verknüpft ist, mit dem Namen der Berechtigung ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Const TOKEN_PRIVILEGES CTokenPrivileges::operator *](#operator_const_token_privileges__star)|Wandelt einen Wert in einen Zeiger auf die `TOKEN_PRIVILEGES` Struktur.|
|[CTokenPrivileges::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffstoken](/windows/desktop/SecAuthZ/access-tokens) ist ein Objekt, das beschreibt den Sicherheitskontext eines Prozesses oder Threads. zudem ist jeder Benutzer, die auf einem Windows-System protokolliert zugeordnet ist.

Das Zugriffstoken wird verwendet, um die verschiedenen Sicherheitsprivilegien gewährt jedem Benutzer zu beschreiben. Eine Berechtigung besteht aus einer 64-Bit-Zahl, die eine lokal eindeutige Kennung aufgerufen ( [LUID](/windows/desktop/api/winnt/ns-winnt-_luid)) und eine sicherheitsbeschreibungs-Zeichenfolge.

Die `CTokenPrivileges` Klasse ist ein Wrapper für die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) strukturieren und enthält 0 oder mehr Berechtigungen. Berechtigungen können hinzugefügt, gelöscht wird oder mithilfe der angegebenen Klassenmethoden abgefragt werden.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="add"></a>  CTokenPrivileges::Add

Fügt einen oder mehrere Berechtigungen, um die `CTokenPrivileges` Access-token-Objekt.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei.

*bEnable*<br/>
True gibt an, dass die Berechtigung aktiviert ist. Wenn "false" ist die Berechtigung deaktiviert.

*rPrivileges*<br/>
Ein Verweis auf eine [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) Struktur. Die Berechtigungen und die Attribute von dieser Struktur kopiert und hinzugefügt werden, um die `CTokenPrivileges` Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Form der diese Methode gibt "true", wenn die Berechtigungen erfolgreich hinzugefügt werden, "false" andernfalls zurück.

##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges

Der Konstruktor.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `CTokenPrivileges` -Objekt, mit dem neuen Objekt zugewiesen.

*rPrivileges*<br/>
Die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) Struktur, die dem neuen Server `CTokenPrivileges` Objekt.

### <a name="remarks"></a>Hinweise

Die `CTokenPrivileges` Objekt kann optional mit erstellt eine `TOKEN_PRIVILEGES` Struktur oder eine zuvor definierte `CTokenPrivileges` Objekt.

##  <a name="dtor"></a>  CTokenPrivileges:: ~ CTokenPrivileges

Der Destruktor.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle zugeordnete Ressourcen frei.

##  <a name="delete"></a>  CTokenPrivileges::Delete

Löscht eine Berechtigung aus dem `CTokenPrivileges` Access-token-Objekt.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter der SE_SECURITY_NAME-Konstante oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Berechtigung wurde erfolgreich gelöscht, andernfalls false wurde.

### <a name="remarks"></a>Hinweise

Diese Methode eignet sich als Tool zum Erstellen von eingeschränkter Tokens.

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

Löscht alle Berechtigungen aus der `CTokenPrivileges` Access-token-Objekt.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Hinweise

Löscht alle Berechtigungen, die innerhalb der `CTokenPrivileges` Access-token-Objekt.

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

Ruft den Anzeigenamen für die Berechtigungen, die innerhalb der `CTokenPrivileges` Access-token-Objekt.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDisplayNames*<br/>
Ein Zeiger auf ein Array von `CString`-Objekten. `CNames` wird definiert als Typedef: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Hinweise

Der Parameter `pDisplayNames` ist ein Zeiger auf ein Array von `CString` Objekte, die die Anzeigenamen für die Berechtigungen, die in enthaltenen erhält die `CTokenPrivileges` Objekt. Diese Methode ruft die Anzeigenamen sind nur für die Berechtigungen, die im Abschnitt definiert Berechtigungen WINNT angegeben ab. H.

Diese Methode ruft einen anzeigbaren Namen ab: z. B. der Attributnamen SE_REMOTE_SHUTDOWN_NAME der anzeigbare Namen ist, "Über ein Remotesystem Herunterfahren erzwingen". Verwenden Sie zum Abrufen der Systemname [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

Gibt die Anzahl der Berechtigungen von Einträgen in der `CTokenPrivileges` Objekt.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Berechtigungen, die innerhalb der `CTokenPrivileges` Objekt.

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

Gibt die Länge der `CTokenPrivileges` Objekt.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Bytes, die zum Speichern erforderlichen eine `TOKEN_PRIVILEGES` Struktur dargestellt werden, indem Sie die `CTokenPrivileges` -Objekts, einschließlich alle Berechtigungen-Einträge, die sie enthält.

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

Ruft die lokal eindeutige Bezeichner (LUIDs) und die Attributflags aus der `CTokenPrivileges` Objekt.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pPrivileges*<br/>
Zeiger auf ein Array von [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) Objekte. `CLUIDArray` ist eine Typedef, die als definiert `CAtlArray<LUID> CLUIDArray`.

*pAttributes*<br/>
Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. `CAttributes` ist eine Typedef, die als definiert `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Hinweise

Diese Methode listet alle Berechtigungen, die innerhalb der `CTokenPrivileges` Tokenobjekt zugreifen, und platzieren Sie die einzelnen LUIDs und (optional) die Attributflags der in Arrayobjekte.

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

Ruft die Namen und Attribut Flags aus der `CTokenPrivileges` Objekt.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pNames*<br/>
Zeiger auf ein Array von `CString` Objekte. `CNames` ist eine Typedef, die als definiert `CAtlArray <CString> CNames`.

*pAttributes*<br/>
Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. `CAttributes` ist eine Typedef, die als definiert `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Hinweise

Diese Methode listet alle Berechtigungen, die innerhalb der `CTokenPrivileges` Objekt, das den Namen und (optional) die Attributflags der in Array von Objekten zu platzieren.

Diese Methode ruft ab, der Attributname, anstatt den anzeigbaren Namen: z. B. der Attributnamen SE_REMOTE_SHUTDOWN_NAME der Systemname ist, "SeRemoteShutdownPrivilege." Um den anzeigbaren Namen zu erhalten, verwenden Sie die Methode [CTokenPrivileges::GetDisplayNames](#getdisplaynames).

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

Gibt einen Zeiger auf die `TOKEN_PRIVILEGES` Struktur.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) Struktur.

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

Ruft das Attribut verknüpft ist, mit dem Namen der Berechtigung ab.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter der SE_SECURITY_NAME-Konstante oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben

*pdwAttributes*<br/>
Zeiger auf eine Variable, die Attribute empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn das Attribut wurde erfolgreich abgerufen, andernfalls false ist.

##  <a name="operator_eq"></a>  CTokenPrivileges::operator =

Zuweisungsoperator.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rPrivileges*<br/>
Die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) Struktur zuweisen der `CTokenPrivileges` Objekt.

*rhs*<br/>
Die `CTokenPrivileges` Objekt, das das Objekt zugewiesen.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CTokenPrivileges` Objekt.

##  <a name="operator_const_token_privileges__star"></a>  Const TOKEN_PRIVILEGES CTokenPrivileges::operator \*

Wandelt einen Wert in einen Zeiger auf die `TOKEN_PRIVILEGES` Struktur.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Wandelt einen Wert in einen Zeiger auf die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) Struktur.

## <a name="see-also"></a>Siehe auch

[Beispiel für die Sicherheit](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-_luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
