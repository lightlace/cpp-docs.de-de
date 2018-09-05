---
title: CSid-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97c88b73499948db4e8fc0645b2d59f7b92b3cfe
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753177"
---
# <a name="csid-class"></a>CSid-Klasse

Diese Klasse ist ein Wrapper für eine `SID` -Struktur (Sicherheits-ID).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CSid
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CSid::CSidArray](#csidarray)|Ein Array von `CSid`-Objekten.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSid::CSid](#csid)|Der Konstruktor.|
|[CSid::~CSid](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSid::AccountName](#accountname)|Gibt den Namen des Kontos zugeordnet ist, mit der `CSid` Objekt.|
|[CSid::Domain](#domain)|Gibt den Namen der Domäne mit dem `CSid` Objekt.|
|[CSid::EqualPrefix](#equalprefix)|Tests `SID` (Sicherheits-ID)-Präfixe hinsichtlich ihrer Gleichheit.|
|[CSid::GetLength](#getlength)|Gibt die Länge der `CSid` Objekt.|
|[CSid::GetPSID](#getpsid)|Gibt einen Zeiger auf eine `SID` Struktur.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Gibt einen Zeiger auf die `SID_IDENTIFIER_AUTHORITY` Struktur.|
|[CSid::GetSubAuthority](#getsubauthority)|Gibt eine angegebene Teilautoritäten durch in einer `SID` Struktur.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Gibt die Anzahl der Teilautoritäten durch zurück.|
|[CSid::IsValid](#isvalid)|Tests der `CSid` Objekt, dessen Gültigkeit.|
|[CSid::LoadAccount](#loadaccount)|Updates der `CSid` Objekts, dem den Kontonamen und die Domäne oder eine vorhandene `SID` Struktur.|
|[CSid::Sid](#sid)|Gibt die ID-Zeichenfolge zurück.|
|[CSid::SidNameUse](#sidnameuse)|Gibt eine Beschreibung des Zustands der `CSid` Objekt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Zuweisungsoperator.|
|[Operator const SID *](#operator_const_sid__star)|Wandelt eine `CSid` Objekt in einen Zeiger auf eine `SID` Struktur.|

### <a name="global-operators"></a>Globale Operatoren

|||
|-|-|
|[operator ==](#operator_eq_eq)|Testet zwei Security Descriptor Objekte auf Gleichheit|
|[Operator! =](#operator_neq)|Testet zwei Security Descriptor-Objekte auf Ungleichheit|
|[Operator \<](#operator_lt_)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|
|[operator >](#operator_gt_)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|
|[Operator \<=](#operator_lt__eq)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|
|[operator >=](#operator_gt__eq)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|

## <a name="remarks"></a>Hinweise

Die `SID` Struktur ist eine Struktur variabler Länge, die zur eindeutigen Identifizierung von Benutzern oder Gruppen.

Anwendungen sollten nicht ändern, die `SID` Struktur direkt, sondern stattdessen verwenden Sie die Methoden, die in diese Wrapperklasse bereitgestellt. Siehe auch [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), und [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="accountname"></a>  CSid::AccountName

Gibt den Namen des Kontos zugeordnet ist, mit der `CSid` Objekt.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt die LPCTSTR verweist auf den Namen des Kontos an.

### <a name="remarks"></a>Hinweise

Diese Methode versucht, einen Namen für den angegebenen finden `SID` (Sicherheits-ID). Ausführliche Informationen finden Sie unter [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Wenn kein Kontoname für den `SID` gefunden werden kann, `AccountName` eine leere Zeichenfolge zurückgegeben. Dies kann auftreten, wenn eine Zeitüberschreitung im Netzwerk verhindert, dass diese Methode suchen nach dem Namen. Sie kommt auch für die Sicherheits-IDs ohne entsprechenden Konto-Namen, z. B. eine Anmeldung `SID` , eine anmeldesitzung identifiziert.

##  <a name="csid"></a>  CSid::CSid

Der Konstruktor.

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*  
Eine vorhandene `CSid` Objekt oder `SID` -Struktur (Sicherheits-ID).

*IdentifierAuthority*  
Die Autorität.

*nSubAuthorityCount*  
Die Anzahl der Teilautoritäten durch.

*pszAccountName*  
Der Kontoname.

*pszSystem*  
Der Systemname. Diese Zeichenfolge kann der Name eines Remotecomputers sein. Wenn diese Zeichenfolge NULL ist, wird stattdessen das lokale System verwendet.

*pSid*  
Ein Zeiger auf eine `SID` Struktur.

### <a name="remarks"></a>Hinweise

Der Konstruktor initialisiert die `CSid` Objekt, und legen einen internen Datenmember auf *Ungültiger SID-Typ*, oder kopieren die Einstellungen aus einer vorhandenen `CSid`, `SID`, oder ein vorhandenes Konto.

Wenn die Initialisierung fehlschlägt, löst der Konstruktor eine [CAtlException-Klasse](../../atl/reference/catlexception-class.md).

##  <a name="dtor"></a>  CSid:: ~ CSid

Der Destruktor.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle Ressourcen, die vom Objekt abgerufene frei.

##  <a name="csidarray"></a>  CSid::CSidArray

Ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition gibt an, der Arraytyp, der zum Abrufen der Sicherheits-IDs aus einer ACL (Access Control List) verwendet werden kann. Finden Sie unter [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).

##  <a name="domain"></a>  CSid::Domain

Gibt den Namen der Domäne mit dem `CSid` Objekt.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt die `LPCTSTR` auf die Domäne verweisen.

### <a name="remarks"></a>Hinweise

Diese Methode versucht, einen Namen für den angegebenen finden `SID` (Sicherheits-ID). Ausführliche Informationen finden Sie unter [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Wenn kein Kontoname für den `SID` gefunden werden kann, `Domain` gibt die Domäne als leere Zeichenfolge zurück. Dies kann auftreten, wenn eine Zeitüberschreitung im Netzwerk verhindert, dass diese Methode suchen nach dem Namen. Sie kommt auch für die Sicherheits-IDs ohne entsprechenden Konto-Namen, z. B. eine Anmeldung `SID` , eine anmeldesitzung identifiziert.

##  <a name="equalprefix"></a>  CSid::EqualPrefix

Tests `SID` (Sicherheits-ID)-Präfixe hinsichtlich ihrer Gleichheit.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Parameter

*RS*  
Die `SID` -Struktur (Sicherheits-ID) oder `CSid` zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Finden Sie unter [EqualPrefixSid](https://msdn.microsoft.com/library/windows/desktop/aa446621) im Windows SDK für weitere Details.

##  <a name="getlength"></a>  CSid::GetLength

Gibt die Länge der `CSid` Objekt.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge in Bytes zurück. die `CSid` Objekt.

### <a name="remarks"></a>Hinweise

Wenn die `CSid` Struktur ist nicht gültig, ist des Rückgabewerts nicht definiert. Vor dem Aufruf `GetLength`, verwenden Sie die [CSid::IsValid](#isvalid) Memberfunktion, um zu überprüfen, ob `CSid` gültig ist.

> [!NOTE]
>  In der Debug-Builds, die die Funktion eine ASSERTION verursacht, wenn die `CSid` -Objekt ist ungültig.

##  <a name="getpsid"></a>  CSid::GetPSID

Gibt einen Zeiger auf eine `SID` -Struktur (Sicherheits-ID).

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse der `CSid` Objekt zugrunde liegenden `SID` Struktur.

##  <a name="getpsid_identifier_authority"></a>  CSid::GetPSID_IDENTIFIER_AUTHORITY

Gibt einen Zeiger auf die `SID_IDENTIFIER_AUTHORITY` Struktur.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, gibt die Adresse der `SID_IDENTIFIER_AUTHORITY` Struktur. Wenn ein Fehler auftritt, ist der Rückgabewert nicht definiert. Fehler kann auftreten, wenn die `CSid` Objekt ist ungültig, in diesem Fall die [CSid::IsValid](#isvalid) Methode gibt FALSE zurück. Die Funktion `GetLastError` kann für erweiterte Fehlerinformationen aufgerufen werden.

> [!NOTE]
>  In der Debug-Builds, die die Funktion eine ASSERTION verursacht, wenn die `CSid` -Objekt ist ungültig.

##  <a name="getsubauthority"></a>  CSid::GetSubAuthority

Gibt eine angegebene Teilautoritäten durch in einer `SID` -Struktur (Sicherheits-ID).

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Parameter

*nSubAuthority*  
Die Teilautoritäten durch.

### <a name="return-value"></a>Rückgabewert

Gibt die Teilautoritäten durch verweist *nSubAuthority.* Teilautoritäten durch Wert ist eine relative ID (RID).

### <a name="remarks"></a>Hinweise

Die *nSubAuthority* Parameter gibt einen Indexwert identifizieren Teilautoritäten durch Array-Elements, das die Methode zurück. Die Methode führt keine Validierungstests für diesen Wert an. Kann eine Anwendung aufrufen [CSid::GetSubAuthorityCount](#getsubauthoritycount) Bereich zulässiger Werte ermittelt.

> [!NOTE]
>  In der Debug-Builds, die die Funktion eine ASSERTION verursacht, wenn die `CSid` -Objekt ist ungültig.

##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount

Gibt die Anzahl der Teilautoritäten durch zurück.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert die Anzahl der Teilautoritäten durch.

Wenn die Methode fehlschlägt, ist der Rückgabewert nicht definiert. Die Methode schlägt fehl, wenn die `CSid` Objekt ist ungültig. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.

> [!NOTE]
>  In der Debug-Builds, die die Funktion eine ASSERTION verursacht, wenn die `CSid` -Objekt ist ungültig.

##  <a name="isvalid"></a>  CSid::IsValid

Tests der `CSid` Objekt, dessen Gültigkeit.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die `CSid` -Objekt ist "false" gültig, wenn nicht. Es gibt keine erweiterten Fehlerinformationen für diese Methode ein. Rufen Sie keine `GetLastError`.

### <a name="remarks"></a>Hinweise

Die `IsValid` Methode überprüft die `CSid` Objekt, indem Sie überprüfen, ob die Revisionsnummer in einem bekannten Bereich ist und die Anzahl der Subauthorities kleiner als der Maximalwert ist.

##  <a name="loadaccount"></a>  CSid::LoadAccount

Aktualisiert das `CSid`-Objekt, das den Kontonamen und die Domäne oder eine vorhandene SID-Struktur (Sicherheits-ID) erhalten hat.

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*pszAccountName*  
Der Kontoname.

*pszSystem*  
Der Systemname. Diese Zeichenfolge kann der Name eines Remotecomputers sein. Wenn diese Zeichenfolge NULL ist, wird stattdessen das lokale System verwendet.

*pSid*  
Ein Zeiger auf eine [SID](/windows/desktop/api/winnt/ns-winnt-_sid) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false". Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.

### <a name="remarks"></a>Hinweise

`LoadAccount` versucht, eine Sicherheits-ID für den angegebenen Namen zu suchen. Finden Sie unter [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida) Weitere Details.

##  <a name="operator_eq"></a>  CSid::operator =

Zuweisungsoperator.

```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` Zuweisen der `CSid` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf die aktualisierte `CSid` Objekt.

##  <a name="operator_eq_eq"></a>  CSid::operator ==

Testet zwei Security Descriptor Objekte auf Gleichheit.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von den Operator ==-Operator.

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, klicken Sie auf der rechten Seite der den Operator ==-Operator.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die sicherheitsbeschreibungen gleich, andernfalls "false sind".

##  <a name="operator_neq"></a>  CSid::operator! =

Testet zwei Security Descriptor-Objekte auf Ungleichheit.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von der! = (Operator).

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite von der! = (Operator).

### <a name="return-value"></a>Rückgabewert

True, wenn die sicherheitsbeschreibungen nicht gleich, andernfalls "false".

##  <a name="operator_lt"></a>  CSid::operator &lt;

Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von der! = (Operator).

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite von der! = (Operator).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *Lhs* ist kleiner als *RS*, andernfalls "false".

##  <a name="operator_lt__eq"></a>  CSid::operator &lt;=

Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von der! = (Operator).

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite von der! = (Operator).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *Lhs* ist kleiner als oder gleich *RS*, andernfalls "false".

##  <a name="operator_gt"></a>  CSid::operator &gt;

Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von der! = (Operator).

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite von der! = (Operator).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *Lhs* ist größer als *RS*, andernfalls "false".

##  <a name="operator_gt__eq"></a>  CSid::operator &gt;=

Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Parameter

*LHS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite von der! = (Operator).

*RS*  
Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite von der! = (Operator).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *Lhs* ist größer als oder gleich *RS*, andernfalls "false".

##  <a name="operator_const_sid__star"></a>  CSid::operator const-SID \*

Wandelt eine `CSid` Objekt in einen Zeiger auf eine `SID` -Struktur (Sicherheits-ID).

```  
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Hinweise

Gibt die Adresse der `SID` Struktur.

##  <a name="sid"></a>  CSid::Sid

Gibt die `SID` (Sicherheits-ID) der Struktur als Zeichenfolge.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt die `SID` Struktur als Zeichenfolge in ein Format für die Anzeige, Speicher oder Übertragung geeignet ist. Äquivalent zu [wurde von ConvertSidToStringSid](/windows/desktop/api/sddl/nf-sddl-convertsidtostringsida).

##  <a name="sidnameuse"></a>  CSid::SidNameUse

Gibt eine Beschreibung des Zustands der `CSid` Objekt.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des Datenmembers, der ein Wert, der beschreibt den Zustand speichert die `CSid` Objekt.

|Wert|Beschreibung|
|-----------|-----------------|
|SidTypeUser|Gibt einen Benutzer `SID` (Sicherheits-ID).|
|SidTypeGroup|Gibt eine Gruppe an `SID`.|
|SidTypeDomain|Gibt an, eine Domäne `SID`.|
|SidTypeAlias|Zeigt einen Alias `SID`.|
|SidTypeWellKnownGroup|Gibt eine `SID` für eine bekannte Gruppe.|
|SidTypeDeletedAccount|Gibt eine `SID` für ein gelöschtes Konto.|
|SidTypeInvalid|Kennzeichnet eine ungültige `SID`.|
|SidTypeUnknown|Gibt einen unbekannten `SID` Typ.|
|SidTypeComputer|Gibt eine `SID` für einen Computer.|

### <a name="remarks"></a>Hinweise

Rufen Sie [CSid::LoadAccount](#loadaccount) zum Aktualisieren der `CSid` Objekt vor dem Aufruf `SidNameUse` seinen Zustand zurückgeben. `SidNameUse` ändert sich nicht auf den Zustand des Objekts (durch den Aufruf von `LookupAccountName` oder `LookupAccountSid`), jedoch nur den aktuellen Status zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)   
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)   
[Operatoren](../../atl/reference/atl-operators.md)
