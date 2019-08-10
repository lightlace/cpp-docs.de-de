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
ms.openlocfilehash: 5f8379d20d8c8d525cd645e1d4aa0c751e16f531
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915534"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges-Klasse

Diese Klasse ist ein Wrapper für die `TOKEN_PRIVILEGES` -Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

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
|[CTokenPrivileges::Add](#add)|Fügt dem `CTokenPrivileges` -Objekt mindestens eine Berechtigung hinzu.|
|[CTokenPrivileges::Delete](#delete)|Löscht eine Berechtigung aus dem `CTokenPrivileges` -Objekt.|
|[CTokenPrivileges::DeleteAll](#deleteall)|Löscht alle Berechtigungen aus dem `CTokenPrivileges` -Objekt.|
|[CTokenPrivileges::GetCount](#getcount)|Gibt die Anzahl der Berechtigungs Einträge im `CTokenPrivileges` -Objekt zurück.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Ruft die anzeigen Amen für die im `CTokenPrivileges` -Objekt enthaltenen Berechtigungen ab.|
|[CTokenPrivileges::GetLength](#getlength)|Gibt die Puffergröße in Bytes zurück, die zum `TOKEN_PRIVILEGES` Speichern der durch das `CTokenPrivileges` -Objekt dargestellten Struktur erforderlich ist.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Ruft die lokalen eindeutigen Bezeichner (LUIDs) und Attributflags aus dem `CTokenPrivileges` -Objekt ab.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ruft die Berechtigungs Namen und Attributflags aus `CTokenPrivileges` dem-Objekt ab.|
|[CTokenPrivileges:: GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Gibt einen Zeiger auf die `TOKEN_PRIVILEGES` -Struktur zurück.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Ruft das Attribut ab, das einem angegebenen Berechtigungs Namen zugeordnet ist.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CTokenPrivileges:: Operator Konstanten TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Wandelt einen Wert in einen Zeiger auf die `TOKEN_PRIVILEGES` -Struktur um.|
|[CTokenPrivileges:: Operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffs Token](/windows/desktop/SecAuthZ/access-tokens) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und jedem Benutzer zugeordnet ist, der bei einem Windows-System angemeldet ist.

Das Zugriffs Token wird verwendet, um die verschiedenen Sicherheits Privilegien zu beschreiben, die den einzelnen Benutzern gewährt werden. Ein-Privileg besteht aus einer 64-Bit-Nummer, die als lokale eindeutige Kennung ( [LUID](/windows/desktop/api/winnt/ns-winnt-luid)) und einer Deskriptorzeichenfolge bezeichnet wird.

Die `CTokenPrivileges` -Klasse ist ein Wrapper für die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur und enthält 0 oder mehr Berechtigungen. Berechtigungen können mithilfe der angegebenen Klassen Methoden hinzugefügt, gelöscht oder abgefragt werden.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/desktop/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="add"></a>CTokenPrivileges:: Add

Fügt dem `CTokenPrivileges` zugriffstokenobjekt mindestens eine Berechtigung hinzu.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen der Berechtigung angibt, wie in WinNT definiert. H-Header Datei.

*bEnable*<br/>
True gibt an, dass die Berechtigung aktiviert ist. Der Wert false gibt an, dass die Berechtigung deaktiviert ist.

*rprivileges*<br/>
Verweis auf eine [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur. Die Berechtigungen und Attribute werden aus dieser Struktur kopiert und dem `CTokenPrivileges` -Objekt hinzugefügt.

### <a name="return-value"></a>Rückgabewert

Die erste Form dieser Methode gibt true zurück, wenn die Berechtigungen erfolgreich hinzugefügt wurden, andernfalls false.

##  <a name="ctokenprivileges"></a>CTokenPrivileges:: CTokenPrivileges

Der Konstruktor.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Das `CTokenPrivileges` -Objekt, das dem neuen-Objekt zugewiesen werden soll.

*rprivileges*<br/>
Die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur, die dem neuen `CTokenPrivileges` -Objekt zugewiesen werden soll.

### <a name="remarks"></a>Hinweise

Das `CTokenPrivileges` Objekt kann optional mithilfe einer `TOKEN_PRIVILEGES` Struktur oder eines zuvor definierten `CTokenPrivileges` Objekts erstellt werden.

##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges

Der Destruktor.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle zugeordneten Ressourcen frei.

##  <a name="delete"></a>CTokenPrivileges::D Elete

Löscht eine Berechtigung aus dem `CTokenPrivileges` zugriffstokenobjekt.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen der Berechtigung angibt, wie in WinNT definiert. H-Header Datei. Mit diesem Parameter kann beispielsweise die Konstante SE_SECURITY_NAME oder die zugehörige Zeichenfolge "SeSecurityPrivilege" angegeben werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Berechtigung erfolgreich gelöscht wurde, andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode ist als Tool zum Erstellen von eingeschränkten Token nützlich.

##  <a name="deleteall"></a>CTokenPrivileges::D eleteall

Löscht alle Berechtigungen aus dem `CTokenPrivileges` zugriffstokenobjekt.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Hinweise

Löscht alle im `CTokenPrivileges` zugriffstokenobjekt enthaltenen Berechtigungen.

##  <a name="getdisplaynames"></a>CTokenPrivileges:: getdisplaynames

Ruft die anzeigen Amen für die im `CTokenPrivileges` zugriffstokenobjekt enthaltenen Berechtigungen ab.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDisplayNames*<br/>
Ein Zeiger auf ein Array von `CString`-Objekten. `CNames`ist als typedef: `CTokenPrivileges::CAtlArray<CString>`definiert.

### <a name="remarks"></a>Hinweise

Der- `pDisplayNames` Parameter ist ein Zeiger auf ein Array `CString` von-Objekten, das die anzeigen Amen erhält, die `CTokenPrivileges` den im-Objekt enthaltenen Berechtigungen entsprechen. Diese Methode ruft nur anzeigen Amen für die Berechtigungen ab, die im Abschnitt "definierte Privilegien" von Winnt angegeben sind. Micha.

Diese Methode ruft einen anzeigbaren Namen ab. wenn der Attribut Name beispielsweise "SE_REMOTE_SHUTDOWN_NAME" lautet, lautet der anzeigbare Name "das Herunterfahren von einem Remote System aus". Verwenden Sie zum Abrufen des System namens [CTokenPrivileges:: getnamesandattributs](#getnamesandattributes).

##  <a name="getcount"></a>CTokenPrivileges:: GetCount

Gibt die Anzahl der Berechtigungs Einträge im `CTokenPrivileges` -Objekt zurück.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der im `CTokenPrivileges` -Objekt enthaltenen Berechtigungen zurück.

##  <a name="getlength"></a>CTokenPrivileges:: GetLength

Gibt die Länge des `CTokenPrivileges` -Objekts zurück.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Bytes zurück, die für `TOKEN_PRIVILEGES` eine durch das `CTokenPrivileges` -Objekt dargestellte Struktur erforderlich sind, einschließlich aller darin enthaltenen Berechtigungs Einträge.

##  <a name="getluidsandattributes"></a>CTokenPrivileges:: getluidsandattribute

Ruft die lokalen eindeutigen Bezeichner (LUIDs) und Attributflags aus dem `CTokenPrivileges` -Objekt ab.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pprivileges*<br/>
Zeiger auf ein Array von [LUID](/windows/desktop/api/winnt/ns-winnt-luid) -Objekten. `CLUIDArray`ist eine typedef, die `CAtlArray<LUID> CLUIDArray`als definiert ist.

*pattributes*<br/>
Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter ausgelassen wird oder NULL ist, werden die Attribute nicht abgerufen. `CAttributes`ist eine typedef, die `CAtlArray <DWORD> CAttributes`als definiert ist.

### <a name="remarks"></a>Hinweise

Diese Methode listet alle im `CTokenPrivileges` zugriffstokenobjekt enthaltenen Berechtigungen auf und platziert die einzelnen LUIDs und (optional) die Attributflags in Array Objekten.

##  <a name="getnamesandattributes"></a>CTokenPrivileges:: getnamesandattribute

Ruft die Namen-und Attributflags aus `CTokenPrivileges` dem-Objekt ab.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pNames*<br/>
Zeiger auf ein Array von `CString` -Objekten. `CNames`ist eine typedef, die `CAtlArray <CString> CNames`als definiert ist.

*pattributes*<br/>
Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter ausgelassen wird oder NULL ist, werden die Attribute nicht abgerufen. `CAttributes`ist eine typedef, die `CAtlArray <DWORD> CAttributes`als definiert ist.

### <a name="remarks"></a>Hinweise

Diese Methode listet alle im- `CTokenPrivileges` Objekt enthaltenen Berechtigungen auf, wobei der Name und (optional) die Attributflags in Array Objekten abgelegt werden.

Diese Methode ruft den Attributnamen anstelle des anzeigbaren namens ab. wenn der Attribut Name beispielsweise SE_REMOTE_SHUTDOWN_NAME lautet, lautet der Systemname "SeRemoteShutdownPrivilege". Verwenden Sie zum Abrufen des anzeigbaren namens die Methode [CTokenPrivileges:: getdisplaynames](#getdisplaynames).

##  <a name="getptoken_privileges"></a>CTokenPrivileges:: GetPTOKEN_PRIVILEGES

Gibt einen Zeiger auf die `TOKEN_PRIVILEGES` -Struktur zurück.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur zurück.

##  <a name="lookupprivilege"></a>CTokenPrivileges:: lookupprivilege

Ruft das Attribut ab, das einem angegebenen Berechtigungs Namen zugeordnet ist.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen der Berechtigung angibt, wie in WinNT definiert. H-Header Datei. Mit diesem Parameter kann beispielsweise die Konstante SE_SECURITY_NAME oder die zugehörige Zeichenfolge "SeSecurityPrivilege" angegeben werden.

*pdwAttributes*<br/>
Ein Zeiger auf eine Variable, die die Attribute empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Attribut erfolgreich abgerufen wurde, andernfalls false.

##  <a name="operator_eq"></a>CTokenPrivileges:: Operator =

Zuweisungsoperator.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rprivileges*<br/>
Die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur, die dem `CTokenPrivileges` -Objekt zugewiesen werden soll.

*rhs*<br/>
Das `CTokenPrivileges` -Objekt, das dem-Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CTokenPrivileges` Objekt zurück.

##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges:: Operator Konstanten TOKEN_PRIVILEGES\*

Wandelt einen Wert in einen Zeiger auf die `TOKEN_PRIVILEGES` -Struktur um.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Wandelt einen Wert in einen Zeiger auf die [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) -Struktur um.

## <a name="see-also"></a>Siehe auch

[Sicherheits Beispiel](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
