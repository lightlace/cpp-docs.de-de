---
title: Cdekengroups-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 88096747f45d4a81c873837cdd4975da9d8c24e2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496294"
---
# <a name="ctokengroups-class"></a>Cdekengroups-Klasse

Diese Klasse ist ein Wrapper für die `TOKEN_GROUPS` -Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CTokenGroups
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|Der Konstruktor.|
|[CTokenGroups::~CTokenGroups](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTokenGroups::Add](#add)|Fügt dem `CSid` `TOKEN_GROUPS` -Objekteineodereinevorhandene`CTokenGroups` -Struktur hinzu.|
|[CTokenGroups::Delete](#delete)|Löscht ein `CSid` -Objekt und die zugehörigen Attribute `CTokenGroups` aus dem-Objekt.|
|[CTokenGroups::DeleteAll](#deleteall)|Löscht alle `CSid` -Objekte und ihre zugeordneten Attribute `CTokenGroups` aus dem-Objekt.|
|[CTokenGroups::GetCount](#getcount)|Gibt die Anzahl der `CSid` -Objekte und zugeordneten Attribute zurück `CTokenGroups` , die im-Objekt enthalten sind.|
|[CTokenGroups::GetLength](#getlength)|Gibt die Größe des `CTokenGroups` -Objekts zurück.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Ruft einen Zeiger auf die `TOKEN_GROUPS` -Struktur ab.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Ruft die `CSid` Objekte und Attribute ab, die `CTokenGroups` zum-Objekt gehören.|
|[CTokenGroups::LookupSid](#lookupsid)|Ruft die einem `CSid` -Objekt zugeordneten Attribute ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Cdekengroups:: Operator Konstanten TOKEN_GROUPS *](#operator_const_token_groups__star)|Wandelt das `CTokenGroups` Objekt in einen Zeiger auf die `TOKEN_GROUPS` -Struktur um.|
|[CTokenGroups::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffs Token](/windows/win32/SecAuthZ/access-tokens) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und jedem Benutzer zugeordnet ist, der bei einem Windows-System angemeldet ist.

Die `CTokenGroups` -Klasse ist ein Wrapper für die [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur, die Informationen über die Gruppen Sicherheits-IDs (SIDs) in einem Zugriffs Token enthält.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="add"></a>Cdekengroups:: Add

Fügt dem `CSid` `TOKEN_GROUPS` -Objekteineodereinevorhandene`CTokenGroups` -Struktur hinzu.

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein [CSID](../../atl/reference/csid-class.md) -Objekt.

*dwAttributes*<br/>
Die Attribute, die dem `CSid` -Objekt zugeordnet werden sollen.

*rTokenGroups*<br/>
Eine [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur.

### <a name="remarks"></a>Hinweise

Diese Methoden fügen dem-Objekt `CSid` ein oder mehrere-Objekte und die `CTokenGroups` zugehörigen Attribute hinzu.

##  <a name="ctokengroups"></a>CTO-Gruppen:: cdekengroups

Der Konstruktor.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `CTokenGroups` Objekt-oder [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur, mit der `CTokenGroups` das Objekt erstellt werden soll.

### <a name="remarks"></a>Hinweise

Das `CTokenGroups` Objekt kann optional mithilfe einer `TOKEN_GROUPS` Struktur oder eines zuvor definierten `CTokenGroups` Objekts erstellt werden.

##  <a name="dtor"></a>Cdekengroups:: ~ cdekengroups

Der Destruktor.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle zugeordneten Ressourcen frei.

##  <a name="delete"></a>CTO-Gruppen::D Elete

Löscht ein `CSid` -Objekt und die zugehörigen Attribute `CTokenGroups` aus dem-Objekt.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Das [CSID](../../atl/reference/csid-class.md) -Objekt, für das die Sicherheits-ID (SID) und Attribute entfernt werden sollen.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, `CSid` wenn das entfernt wird, andernfalls false.

##  <a name="deleteall"></a>CTO-Gruppen::D eleteall

Löscht alle `CSid` -Objekte und ihre zugeordneten Attribute `CTokenGroups` aus dem-Objekt.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>CTO-Gruppen:: GetCount

Gibt die Anzahl der `CSid` in `CTokenGroups`enthaltenen-Objekte zurück.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der [CSID](../../atl/reference/csid-class.md) -Objekte und ihre zugeordneten Attribute zurück `CTokenGroups` , die im-Objekt enthalten sind.

##  <a name="getlength"></a>CTO-Gruppen:: GetLength

Gibt die Größe des `CTokenGroup` -Objekts zurück.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt die Gesamtgröße des `CTokenGroup` -Objekts in Bytes zurück.

##  <a name="getptoken_groups"></a>CTO-Gruppen:: GetPTOKEN_GROUPS

Ruft einen Zeiger auf die `TOKEN_GROUPS` -Struktur ab.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Ruft einen Zeiger auf die [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur ab, die `CTokenGroups` zum zugriffstokenobjekt gehört.

##  <a name="getsidsandattributes"></a>CTokenGroups:: getsidsandattribute

Ruft die `CSid` -Objekte und (optional) die Attribute ab `CTokenGroups` , die zum-Objekt gehören.

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSids*<br/>
Zeiger auf ein Array von [CSID](../../atl/reference/csid-class.md) -Objekten.

*pattributes*<br/>
Zeiger auf ein Array von DWORDs. Wenn dieser Parameter ausgelassen wird oder NULL ist, werden die Attribute nicht abgerufen.

### <a name="remarks"></a>Hinweise

Diese Methode listet alle `CSid` Objekte `CTokenGroups` auf, die im-Objekt enthalten sind, und platziert Sie und (optional) die Attributflags in Array-Objekten.

##  <a name="lookupsid"></a>CTO-Gruppen:: lookupsid

Ruft die einem `CSid` -Objekt zugeordneten Attribute ab.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Das [CSID](../../atl/reference/csid-class.md) -Objekt.

*pdwAttributes*<br/>
Zeiger auf ein DWORD, das das- `CSid` Attribut des Objekts akzeptiert. Wenn ausgelassen oder NULL, wird das Attribut nicht abgerufen.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, `CSid` wenn der gefunden wurde, andernfalls false.

### <a name="remarks"></a>Hinweise

Durch das Festlegen von *pdwattributes* auf NULL kann das vorhanden sein von `CSid` bestätigt werden, ohne auf das Attribut zuzugreifen. Beachten Sie, dass diese Methode nicht zum Überprüfen von Zugriffsrechten verwendet werden sollte. Anwendungen sollten stattdessen die [CAccessToken:: checktokenmembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) -Methode verwenden.

##  <a name="operator_eq"></a>Cdekengroups:: Operator =

Zuweisungsoperator.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `CTokenGroups` Objekt-oder [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur, die `CTokenGroups` dem-Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CTokenGroups` Objekt zurück.

##  <a name="operator_const_token_groups__star"></a>Cdekengroups:: Operator Konstanten TOKEN_GROUPS *

Wandelt einen Wert in einen Zeiger auf die `TOKEN_GROUPS` -Struktur um.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Wandelt einen Wert in einen Zeiger auf die [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) -Struktur um.

## <a name="see-also"></a>Siehe auch

[Sicherheits Beispiel](../../overview/visual-cpp-samples.md)<br/>
[CSid-Klasse](../../atl/reference/csid-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
