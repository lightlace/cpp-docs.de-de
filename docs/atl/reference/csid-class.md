---
title: CSid Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: f1e731c82892c5622dcb437498d2d318086f66d8
ms.lasthandoff: 03/31/2017

---
# <a name="csid-class"></a>CSid-Klasse
Diese Klasse ist ein Wrapper für eine `SID` Struktur (Sicherheits-ID).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CSid
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|Ein Array von `CSid`-Objekten.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSid::CSid](#csid)|Der Konstruktor.|  
|[CSid:: ~ CSid](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|Gibt den Namen der dem Konto zugeordnet ist, mit der `CSid` Objekt.|  
|[CSid::Domain](#domain)|Gibt den Namen der Domäne mit dem `CSid` Objekt.|  
|[CSid::EqualPrefix](#equalprefix)|Tests `SID` (Sicherheits-ID) Präfixe auf Gleichheit.|  
|[CSid::GetLength](#getlength)|Gibt die Länge der `CSid` Objekt.|  
|[CSid::GetPSID](#getpsid)|Gibt einen Zeiger auf eine `SID` Struktur.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Gibt einen Zeiger auf die **SID_IDENTIFIER_AUTHORITY** Struktur.|  
|[CSid::GetSubAuthority](#getsubauthority)|Gibt eine angegebene Subauthority in einem **SID** Struktur.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Gibt die Anzahl der Subauthority zurück.|  
|[CSid::IsValid](#isvalid)|Tests der `CSid` Objekt auf seine Gültigkeit.|  
|[CSid::LoadAccount](#loadaccount)|Updates der `CSid` erhält, den Kontonamen und die Domäne oder ein vorhandenes Objekt `SID` Struktur.|  
|[CSid::Sid](#sid)|Gibt die ID-Zeichenfolge zurück.|  
|[CSid::SidNameUse](#sidnameuse)|Gibt eine Beschreibung des Zustands der `CSid` Objekt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Zuweisungsoperator.|  
|[Operator const SID *](#operator_const_sid__star)|Wandelt eine `CSid` Objekt in einen Zeiger auf eine `SID` Struktur.|  
  
### <a name="global-operators"></a>Globale Operatoren  
  
|||  
|-|-|  
|[Operator ==](#operator_eq_eq)|Testet zwei Security Descriptor-Objekte auf Gleichheit|  
|[Operator! =](#operator_neq)|Testet zwei Security Descriptor-Objekte auf Ungleichheit|  
|[Operator\<](#operator_lt_)|Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.|  
|[Operator >](#operator_gt_)|Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.|  
|[Operator\<=](#operator_lt__eq)|Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.|  
|[Operator > =](#operator_gt__eq)|Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.|  
  
## <a name="remarks"></a>Hinweise  
 Die `SID` Struktur ist eine Struktur variabler Länge verwendet, um die Identifizierung von Benutzern oder Gruppen.  
  
 Anwendungen sollten nicht ändern, die `SID` Struktur direkt, sondern stattdessen die in diese Wrapperklasse bereitgestellten Methoden verwenden. Siehe auch [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), und [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="accountname"></a>CSid::AccountName  
 Gibt den Namen der dem Konto zugeordnet ist, mit der `CSid` Objekt.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `LPCTSTR` auf den Namen des Kontos verweist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht, beim Ermitteln eines Namens für den angegebenen `SID` (Sicherheits-ID). Alle Details finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Wenn kein Kontoname für den `SID` gefunden werden kann, `AccountName` eine leere Zeichenfolge zurückgegeben. Dies kann auftreten, wenn eine Netzwerktimeout verhindert, dass diese Methode suchen nach dem Namen. Sie kommt auch für die Sicherheits-IDs mit keine entsprechenden Kontonamen wie eine Anmeldung `SID` , die eine Sitzung identifiziert.  
  
##  <a name="csid"></a>CSid::CSid  
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
 `rhs`  
 Eine vorhandene `CSid` Objekt oder `SID` Struktur (Sicherheits-ID).  
  
 *IdentifierAuthority*  
 Die Stelle.  
  
 *nSubAuthorityCount*  
 Die Anzahl der Subauthority.  
  
 `pszAccountName`  
 Der Kontoname.  
  
 `pszSystem`  
 Der Systemname. Diese Zeichenfolge kann der Name eines Remotecomputers sein. Wenn diese Zeichenfolge NULL ist, wird stattdessen das lokale System verwendet.  
  
 `pSid`  
 Ein Zeiger auf eine `SID` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor initialisiert die `CSid` Objekt, und legen einen internen Datenmember auf *Ungültiger SID-Typ*, oder kopieren die Einstellungen aus einem vorhandenen `CSid`, `SID`, oder ein vorhandenes Konto.  
  
 Wenn die Initialisierung fehlschlägt, löst der Konstruktor eine [CAtlException Klasse](../../atl/reference/catlexception-class.md).  
  
##  <a name="dtor"></a>CSid:: ~ CSid  
 Der Destruktor.  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen, die vom Objekt abgerufen.  
  
##  <a name="csidarray"></a>CSid::CSidArray  
 Ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typedef gibt den Arraytyp, der zum Abrufen der Sicherheits-IDs aus eine Zugriffssteuerungsliste (Access Control List) verwendet werden kann. Finden Sie unter [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="domain"></a>CSid::Domain  
 Gibt den Namen der Domäne mit dem `CSid` Objekt.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `LPCTSTR` auf die Domäne verweist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht, beim Ermitteln eines Namens für den angegebenen `SID` (Sicherheits-ID). Alle Details finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Wenn kein Kontoname für den `SID` gefunden werden kann, **Domäne** gibt die Domäne als eine leere Zeichenfolge zurück. Dies kann auftreten, wenn eine Netzwerktimeout verhindert, dass diese Methode suchen nach dem Namen. Sie kommt auch für die Sicherheits-IDs mit keine entsprechenden Kontonamen wie eine Anmeldung `SID` , die eine Sitzung identifiziert.  
  
##  <a name="equalprefix"></a>CSid::EqualPrefix  
 Tests `SID` (Sicherheits-ID) Präfixe auf Gleichheit.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `SID` Struktur (Sicherheits-ID) oder `CSid` zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) in die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Details.  
  
##  <a name="getlength"></a>CSid::GetLength  
 Gibt die Länge der `CSid` Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge in Byte der `CSid` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CSid` Struktur ist nicht gültig, ist des Rückgabewerts nicht definiert. Vor dem Aufruf `GetLength`, verwenden Sie die [CSid::IsValid](#isvalid) Memberfunktion, um zu überprüfen, ob `CSid` gültig ist.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="getpsid"></a>CSid::GetPSID  
 Gibt einen Zeiger auf eine `SID` Struktur (Sicherheits-ID).  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des dem `CSid` Objekt zugrunde liegenden `SID` Struktur.  
  
##  <a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Gibt einen Zeiger auf die **SID_IDENTIFIER_AUTHORITY** Struktur.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, gibt er die Adresse des dem **SID_IDENTIFIER_AUTHORITY** Struktur. Falls dies fehlschlägt, ist der Rückgabewert nicht definiert. Fehler kann auftreten, wenn die `CSid` -Objekt ist ungültig, in diesem Fall die [CSid::IsValid](#isvalid) -Methode zurückkehrt **"false"**. Die Funktion `GetLastError` kann aufgerufen werden, um erweiterte Fehlerinformationen anzuzeigen.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="getsubauthority"></a>CSid::GetSubAuthority  
 Gibt eine angegebene Subauthority in einer `SID` Struktur (Sicherheits-ID).  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nSubAuthority*  
 Die Subauthority.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Subauthority verweist *nSubAuthority.* Der Subauthority-Wert ist eine relative ID (RID).  
  
### <a name="remarks"></a>Hinweise  
 Die *nSubAuthority* Parameter gibt einen Indexwert der Methodenrückgabewert Subauthority Arrayelement identifizieren. Die Methode führt keine Validierungstests für diesen Wert. Eine Anwendung kann Aufrufen [CSid::GetSubAuthorityCount](#getsubauthoritycount) des Bereichs zulässiger Werte ermittelt.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Gibt die Anzahl der Subauthority zurück.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert die Anzahl der Subauthority an.  
  
 Wenn die Methode fehlschlägt, ist der Rückgabewert nicht definiert. Die Methode fehlschlägt, wenn die `CSid` Objekt ist ungültig. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="isvalid"></a>CSid::IsValid  
 Tests der `CSid` Objekt auf seine Gültigkeit.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die `CSid` Objekt gültig ist, **"false"** Wenn dies nicht. Es gibt keine erweiterten Fehlerinformationen für diese Methode. Rufen Sie nicht `GetLastError`.  
  
### <a name="remarks"></a>Hinweise  
 Die `IsValid` Methode überprüft die `CSid` Objekt, indem Sie überprüfen, dass die Revisionsnummer in einem bekannten Bereich und die Anzahl der Subauthorities kleiner als das Maximum ist.  
  
##  <a name="loadaccount"></a>CSid::LoadAccount  
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
 `pszAccountName`  
 Der Kontoname.  
  
 `pszSystem`  
 Der Systemname. Diese Zeichenfolge kann der Name eines Remotecomputers sein. Wenn diese Zeichenfolge NULL ist, wird stattdessen das lokale System verwendet.  
  
 `pSid`  
 Ein Zeiger auf eine [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 `LoadAccount` versucht, eine Sicherheits-ID für den angegebenen Namen zu suchen. Finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) Weitere Details.  
  
##  <a name="operator_eq"></a>CSid::operator =  
 Zuweisungsoperator.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` Zuweisen der `CSid` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CSid` Objekt.  
  
##  <a name="operator_eq_eq"></a>CSid::operator ==  
 Testet zwei Security Descriptor-Objekte auf Gleichheit.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite der den Operator ==-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der rechten Seite der den Operator ==-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** , wenn die sicherheitsbeschreibungen gleich, andernfalls sind **"false"**.  
  
##  <a name="operator_neq"></a>CSid::operator! =  
 Testet zwei Security Descriptor-Objekte auf Ungleichheit.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite des der! =-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf die rechts neben der! =-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** , wenn die sicherheitsbeschreibungen nicht gleich, andernfalls sind **"false"**.  
  
##  <a name="operator_lt"></a>CSid::operator&lt;  
 Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite des der! =-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf die rechts neben der! =-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn `lhs` ist kleiner als `rhs`, da andernfalls **"false"**.  
  
##  <a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite des der! =-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf die rechts neben der! =-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn `lhs` ist kleiner als oder gleich `rhs`, da andernfalls **"false"**.  
  
##  <a name="operator_gt"></a>CSid::operator&gt;  
 Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite des der! =-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf die rechts neben der! =-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn `lhs` ist größer als `rhs`, da andernfalls **"false"**.  
  
##  <a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Vergleicht zwei Sicherheitsobjekte Deskriptor relative Wert.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf der linken Seite des der! =-Operator.  
  
 `rhs`  
 Die `SID` (Sicherheits-ID) oder `CSid` , angezeigt wird, auf die rechts neben der! =-Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn `lhs` ist größer als oder gleich `rhs`, da andernfalls **"false"**.  
  
##  <a name="operator_const_sid__star"></a>Const SID CSid::operator *  
 Wandelt eine `CSid` Objekt in einen Zeiger auf eine `SID` Struktur (Sicherheits-ID).  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Adresse des dem `SID` Struktur.  
  
##  <a name="sid"></a>CSid::Sid  
 Gibt die `SID` (Sicherheits-ID) der Struktur als Zeichenfolge.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `SID` Struktur als eine Zeichenfolge in ein Format für die Anzeige, Speicher oder Übertragung geeignet ist. Entspricht [ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), obwohl diese Funktion nur auf Windows 2000 oder höher ausgeführt wird und daher für ältere Betriebssysteme emuliert wird.  
  
##  <a name="sidnameuse"></a>CSid::SidNameUse  
 Gibt eine Beschreibung des Zustands der `CSid` Objekt.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert des Datenmembers, der ein Wert, der Status der beschreiben speichert die `CSid` Objekt.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SID|Gibt eine `SID` (Sicherheits-ID).|  
|SID|Gibt eine Gruppe an `SID`.|  
|Alias|Zeigt eine Domäne an `SID`.|  
|SID|Zeigt einen Alias `SID`.|  
|SID|Gibt eine `SID` für eine bekannte Gruppe.|  
|Ungültiger SID-Typ|Gibt eine `SID` für gelöschte Konto.|  
|Ungültiger SID-Typ|Kennzeichnet eine ungültige `SID`.|  
|Computer|Gibt einen unbekannten `SID` Typ.|  
|SidTypeComputer|Gibt eine `SID` für einen Computer.|  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CSid::LoadAccount](#loadaccount) zum Aktualisieren der `CSid` Objekt vor dem Aufruf `SidNameUse` Zustand zurückgegeben. `SidNameUse`ändert nicht den Zustand des Objekts (durch Aufrufen **"LookupAccountName" wurde** oder **LookupAccountSid**), jedoch nur den aktuellen Status zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für nachrichtensicherheit](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Sicherheit, globale Funktionen](../../atl/reference/security-global-functions.md)   
 [Operatoren](../../atl/reference/atl-operators.md)

