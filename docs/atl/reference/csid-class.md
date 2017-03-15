---
title: CSid Klasse | Microsoft-Dokumentation
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
- ATL::CSid
- ATL.CSid
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ceb0ab95d18e1336584eab45bc00ce769efd7384
ms.lasthandoff: 02/24/2017

---
# <a name="csid-class"></a>CSid-Klasse
Diese Klasse ist ein Wrapper für eine `SID` -Struktur (Sicherheits-ID).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CSid::AccountName](#accountname)|Gibt den Namen des Kontos zugeordnet ist, mit der `CSid` Objekt.|  
|[CSid::Domain](#domain)|Gibt den Namen der Domäne der `CSid` Objekt.|  
|[CSid::EqualPrefix](#equalprefix)|Tests `SID` (Security Identifier)-Präfixe hinsichtlich ihrer Gleichheit.|  
|[CSid::GetLength](#getlength)|Gibt die Länge der `CSid` Objekt.|  
|[CSid::GetPSID](#getpsid)|Gibt einen Zeiger auf eine `SID` Struktur.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Gibt einen Zeiger auf die **SID_IDENTIFIER_AUTHORITY** Struktur.|  
|[CSid::GetSubAuthority](#getsubauthority)|Gibt eine angegebene Teilautoritäten durch in einer **SID** Struktur.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Gibt die Anzahl der Teilautoritäten durch.|  
|[CSid::IsValid](#isvalid)|Tests der `CSid` Objekt Gültigkeit.|  
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
|[Operator\<](#operator_lt_)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|  
|[Operator >](#operator_gt_)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|  
|[Operator\<=](#operator_lt__eq)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|  
|[Operator > =](#operator_gt__eq)|Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `SID` -Struktur ist eine Struktur variabler Länge, die zur eindeutigen Identifizierung von Benutzern oder Gruppen verwendet.  
  
 Clientanwendungen sollten nicht ändern, die `SID` Struktur direkt, sondern stattdessen die in dieser Wrapperklasse bereitgestellten Methoden verwenden. Siehe auch [AtlGetOwnerSid](http://msdn.microsoft.com/library/0e3a2606-74b8-4412-9803-bb437e22da85), [AtlSetGroupSid](http://msdn.microsoft.com/library/83531d32-11ab-4a68-a3c6-1bfa54ab8dfa), [AtlGetGroupSid](http://msdn.microsoft.com/library/8e7ec6b9-15c8-4a8a-977e-1e4c853d0be7), und [AtlSetOwnerSid](http://msdn.microsoft.com/library/3a8abb76-1d2c-465d-a5e8-62a12a3c37f3).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="a-nameaccountnamea--csidaccountname"></a><a name="accountname"></a>CSid::AccountName  
 Gibt den Namen des Kontos zugeordnet ist, mit der `CSid` Objekt.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `LPCTSTR` auf den Namen des Kontos.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht, einen Namen für die angegebene suchen `SID` (Security Identifier). Ausführliche Informationen finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Wenn kein Kontoname für die `SID` gefunden werden kann, `AccountName` eine leere Zeichenfolge zurückgegeben. Dies kann auftreten, wenn ein Netzwerktimeout verhindert, dass diese Methode den Namen gefunden. Es tritt auch für Sicherheits-IDs mit keine entsprechenden Kontonamen, z. B. eine Anmeldung `SID` , die eine Sitzung identifiziert.  
  
##  <a name="a-namecsida--csidcsid"></a><a name="csid"></a>CSid::CSid  
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
 Die Autorität.  
  
 *nSubAuthorityCount*  
 Die Anzahl der Teilautoritäten durch.  
  
 `pszAccountName`  
 Der Kontoname.  
  
 `pszSystem`  
 Der Systemname. Diese Zeichenfolge kann der Name eines Remotecomputers sein. Wenn diese Zeichenfolge NULL ist, wird stattdessen das lokale System verwendet.  
  
 `pSid`  
 Ein Zeiger auf eine `SID` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor initialisiert die `CSid` Objekt, und legen einen interne Datenmember *Ungültiger SID-Typ*, oder kopieren Sie die Einstellungen aus einem vorhandenen `CSid`, `SID`, oder ein vorhandenes Konto.  
  
 Wenn die Initialisierung fehlschlägt, löst der Konstruktor eine [CAtlException Klasse](../../atl/reference/catlexception-class.md).  
  
##  <a name="a-namedtora--csidcsid"></a><a name="dtor"></a>CSid:: ~ CSid  
 Der Destruktor.  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt abgerufen, die vom Objekt Ressourcen frei.  
  
##  <a name="a-namecsidarraya--csidcsidarray"></a><a name="csidarray"></a>CSid::CSidArray  
 Ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition gibt den Arraytyp, der zum Abrufen der Sicherheits-IDs aus einer ACL (Access Control List) verwendet werden kann. Finden Sie unter [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="a-namedomaina--csiddomain"></a><a name="domain"></a>CSid::Domain  
 Gibt den Namen der Domäne der `CSid` Objekt.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `LPCTSTR` auf die Domäne verweisen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht, einen Namen für die angegebene suchen `SID` (Security Identifier). Ausführliche Informationen finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Wenn kein Kontoname für die `SID` gefunden werden kann, **Domäne** gibt die Domäne als eine leere Zeichenfolge zurück. Dies kann auftreten, wenn ein Netzwerktimeout verhindert, dass diese Methode den Namen gefunden. Es tritt auch für Sicherheits-IDs mit keine entsprechenden Kontonamen, z. B. eine Anmeldung `SID` , die eine Sitzung identifiziert.  
  
##  <a name="a-nameequalprefixa--csidequalprefix"></a><a name="equalprefix"></a>CSid::EqualPrefix  
 Tests `SID` (Security Identifier)-Präfixe hinsichtlich ihrer Gleichheit.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `SID` -Struktur (Sicherheits-ID) oder `CSid` zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** bei Erfolg **false** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für weitere Details.  
  
##  <a name="a-namegetlengtha--csidgetlength"></a><a name="getlength"></a>CSid::GetLength  
 Gibt die Länge der `CSid` Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge in Bytes der `CSid` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CSid` Struktur ist nicht gültig, ist des Rückgabewerts nicht definiert. Vor dem Aufruf von `GetLength`, verwenden Sie die [CSid::IsValid](#isvalid) Memberfunktion, um zu überprüfen, ob `CSid` gültig ist.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="a-namegetpsida--csidgetpsid"></a><a name="getpsid"></a>CSid::GetPSID  
 Gibt einen Zeiger auf eine `SID` -Struktur (Sicherheits-ID).  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse der `CSid` Objekt zugrunde liegenden `SID` Struktur.  
  
##  <a name="a-namegetpsididentifierauthoritya--csidgetpsididentifierauthority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Gibt einen Zeiger auf die **SID_IDENTIFIER_AUTHORITY** Struktur.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird die Adresse der **SID_IDENTIFIER_AUTHORITY** Struktur. Wenn dies fehlschlägt, ist der Rückgabewert nicht definiert. Fehler kann auftreten, wenn die `CSid` -Objekt ist ungültig, in diesem Fall die [CSid::IsValid](#isvalid) -Methode gibt **false**. Die Funktion `GetLastError` für erweiterte Fehlerinformationen aufgerufen werden können.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="a-namegetsubauthoritya--csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority  
 Gibt eine angegebene Teilautoritäten durch in einer `SID` Struktur (Sicherheits-ID).  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nSubAuthority*  
 Die Teilautoritäten durch.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Teilautoritäten durch verweist *nSubAuthority.* Der Wert Teilautoritäten durch ist eine relative ID (RID).  
  
### <a name="remarks"></a>Hinweise  
 Die *nSubAuthority* Parameter gibt einen Indexwert identifizieren Teilautoritäten durch Array-Elements gibt die Methode zurück. Die Methode führt keine Validierungstests für diesen Wert. Eine Anwendung kann Aufrufen [CSid::GetSubAuthorityCount](#getsubauthoritycount) den Bereich zulässiger Werte ermittelt.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="a-namegetsubauthoritycounta--csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Gibt die Anzahl der Teilautoritäten durch.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert die Anzahl der Teilautoritäten durch.  
  
 Wenn die Methode fehlschlägt, ist der Rückgabewert nicht definiert. Die Methode schlägt fehl, wenn die `CSid` -Objekt ist ungültig. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
> [!NOTE]
>  Unter Debug-Builds, die die Funktion verursacht eine ASSERTION aus, wenn die `CSid` -Objekt ist ungültig.  
  
##  <a name="a-nameisvalida--csidisvalid"></a><a name="isvalid"></a>CSid::IsValid  
 Tests der `CSid` Objekt Gültigkeit.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das `CSid` -Objekt ist gültig, **false** ist dies nicht. Es gibt keine erweiterten Fehlerinformationen für diese Methode. Rufen Sie `GetLastError`.  
  
### <a name="remarks"></a>Hinweise  
 Die `IsValid` Methode überprüft die `CSid` Objekt, indem Sie überprüfen, dass die Revisionsnummer in einem bekannten Bereich ist und die Anzahl der Subauthorities kleiner als das Maximum ist.  
  
##  <a name="a-nameloadaccounta--csidloadaccount"></a><a name="loadaccount"></a>CSid::LoadAccount  
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
 Gibt **true** bei Erfolg **false** bei einem Fehler. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 `LoadAccount` versucht, eine Sicherheits-ID für den angegebenen Namen zu suchen. Finden Sie unter [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) für weitere Details.  
  
##  <a name="a-nameoperatoreqa--csidoperator-"></a><a name="operator_eq"></a>CSid::operator =  
 Zuweisungsoperator.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` Zuweisen der `CSid` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CSid` Objekt.  
  
##  <a name="a-nameoperatoreqeqa--csidoperator-"></a><a name="operator_eq_eq"></a>CSid::operator ==  
 Testet zwei Security Descriptor-Objekte auf Gleichheit.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` auf der linken Seite des angezeigt wird der Operator ==.  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` auf der rechten Seite des angezeigt wird der Operator ==.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn die Sicherheitsdeskriptoren gleich, andernfalls sind **false**.  
  
##  <a name="a-nameoperatorneqa--csidoperator-"></a><a name="operator_neq"></a>CSid::operator! =  
 Testet zwei Security Descriptor-Objekte auf Ungleichheit.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der linken Seite des der! = (Operator).  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der rechten Seite des der! = (Operator).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die sicherheitsbeschreibungen nicht gleich, andernfalls sind **false**.  
  
##  <a name="a-nameoperatorlta--csidoperator-lt"></a><a name="operator_lt"></a>CSid::operator&lt;  
 Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der linken Seite des der! = (Operator).  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der rechten Seite des der! = (Operator).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn `lhs` ist kleiner als `rhs`, andernfalls **false**.  
  
##  <a name="a-nameoperatorlteqa--csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der linken Seite des der! = (Operator).  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der rechten Seite des der! = (Operator).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn `lhs` ist kleiner als oder gleich `rhs`, andernfalls **false**.  
  
##  <a name="a-nameoperatorgta--csidoperator-gt"></a><a name="operator_gt"></a>CSid::operator&gt;  
 Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der linken Seite des der! = (Operator).  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der rechten Seite des der! = (Operator).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn `lhs` ist größer als `rhs`, andernfalls **false**.  
  
##  <a name="a-nameoperatorgteqa--csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Vergleicht die relativen Wert von zwei Security Descriptor-Objekten.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Parameter  
 `lhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der linken Seite des der! = (Operator).  
  
 `rhs`  
 Die `SID` (Security Identifier) oder `CSid` , die angezeigt wird, klicken Sie auf der rechten Seite des der! = (Operator).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn `lhs` ist größer als oder gleich `rhs`, andernfalls **false**.  
  
##  <a name="a-nameoperatorconstsidstara--csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>Const SID CSid::operator *  
 Wandelt eine `CSid` Objekt in einen Zeiger auf eine `SID` Struktur (Sicherheits-ID).  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Adresse der `SID` Struktur.  
  
##  <a name="a-namesida--csidsid"></a><a name="sid"></a>CSid::Sid  
 Gibt die `SID` -Struktur (Sicherheits-ID) als Zeichenfolge.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `SID` -Struktur als eine Zeichenfolge in ein Format für die Anzeige, Speicherung oder Übertragung geeignet. Entspricht [wurde von ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), obwohl diese Funktion nur verfügbar in Windows 2000 oder höher ist und so für ältere Betriebssysteme emuliert wird.  
  
##  <a name="a-namesidnameusea--csidsidnameuse"></a><a name="sidnameuse"></a>CSid::SidNameUse  
 Gibt eine Beschreibung des Zustands der `CSid` Objekt.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert des Datenmembers, der einen Wert, der den Zustand des speichert die `CSid` Objekt.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SID|Gibt eine `SID` (Security Identifier).|  
|SID|Gibt eine Gruppe an `SID`.|  
|Alias|Gibt eine `SID`.|  
|SID|Zeigt einen Alias `SID`.|  
|SID|Gibt eine `SID` für eine bekannte Gruppe.|  
|Ungültiger SID-Typ|Gibt eine `SID` für gelöschte Konto.|  
|Ungültiger SID-Typ|Zeigt eine ungültige `SID`.|  
|Computer|Gibt einen unbekannten `SID` Typ.|  
|SidTypeComputer|Gibt eine `SID` für einen Computer.|  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CSid::LoadAccount](#loadaccount) zum Aktualisieren der `CSid` Objekt vor dem Aufruf von `SidNameUse` Zustand zurückgegeben. `SidNameUse`Ändert den Zustand des Objekts nicht (durch Aufrufen **LookupAccountName** oder **LookupAccountSid**), jedoch nur der aktuelle Status zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)   
 [Operatoren](../../atl/reference/atl-operators.md)

