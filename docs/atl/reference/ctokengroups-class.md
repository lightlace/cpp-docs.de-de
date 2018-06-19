---
title: CTokenGroups Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ccf73cdeac0e7522551c6ddb7bef6b0122297ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365493"
---
# <a name="ctokengroups-class"></a>CTokenGroups-Klasse
Diese Klasse ist ein Wrapper für die **TOKEN_GROUPS** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CTokenGroups::Add](#add)|Fügt eine `CSid` oder vorhandene **TOKEN_GROUPS** -Struktur in der `CTokenGroups` Objekt.|  
|[CTokenGroups::Delete](#delete)|Löscht eine `CSid` und die entsprechenden Attribute aus der `CTokenGroups` Objekt.|  
|[CTokenGroups::DeleteAll](#deleteall)|Löscht alle `CSid` Objekte und die zugehörigen Attribute aus der `CTokenGroups` Objekt.|  
|[CTokenGroups::GetCount](#getcount)|Gibt die Anzahl der `CSid` Objekte und die zugehörigen Attribute in der **CTokenGroups** Objekt.|  
|[CTokenGroups::GetLength](#getlength)|Gibt die Größe der `CTokenGroups` Objekt.|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Ruft einen Zeiger auf die **TOKEN_GROUPS** Struktur.|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Ruft die `CSid` Objekte und Attribute, die zu gehören die `CTokenGroups` Objekt.|  
|[CTokenGroups::LookupSid](#lookupsid)|Ruft die zugeordneten Attribute ab einem `CSid` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const TOKEN_GROUPS CTokenGroups::operator *](#operator_const_token_groups__star)|Wandelt die `CTokenGroups` Objekt in einen Zeiger auf die **TOKEN_GROUPS** Struktur.|  
|[CTokenGroups::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ein Objekt, das den Sicherheitskontext für einen Prozess oder Thread beschreibt und erhält jeder Benutzer auf einem Windows-Betriebssystem angemeldet ist.  
  
 Die **CTokenGroups** Klasse ist ein Wrapper für die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur mit Informationen über die Gruppe Sicherheits-IDs (SIDs) in ein Zugriffstoken.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="add"></a>  CTokenGroups::Add  
 Fügt eine `CSid` oder vorhandene **TOKEN_GROUPS** -Struktur in der `CTokenGroups` Objekt.  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Ein [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 `dwAttributes`  
 Die Attribute zum Zuordnen der `CSid` Objekt.  
  
 *rTokenGroups*  
 Ein [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methoden hinzufügen, eine oder mehrere `CSid` Objekte und die zugehörigen Attribute, die `CTokenGroups` Objekt.  
  
##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups  
 Der Konstruktor.  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CTokenGroups` Objekt oder [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur mit dem Erstellen der `CTokenGroups` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTokenGroups` Objekt kann optional mit erstellt werden ein **TOKEN_GROUPS** Struktur oder eine zuvor definierte `CTokenGroups` Objekt.  
  
##  <a name="dtor"></a>  CTokenGroups:: ~ CTokenGroups  
 Der Destruktor.  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="delete"></a>  CTokenGroups::Delete  
 Löscht eine `CSid` und die entsprechenden Attribute aus der `CTokenGroups` Objekt.  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt für die die Sicherheits-ID (SID) und die Attribute entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die `CSid` entfernt wird, "false" andernfalls.  
  
##  <a name="deleteall"></a>  CTokenGroups::DeleteAll  
 Löscht alle `CSid` Objekte und die zugehörigen Attribute aus der `CTokenGroups` Objekt.  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>  CTokenGroups::GetCount  
 Gibt die Anzahl der `CSid` in enthaltenen Objekte `CTokenGroups`.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der [CSid](../../atl/reference/csid-class.md) Objekte und ihre zugehörigen Attribute in der `CTokenGroups` Objekt.  
  
##  <a name="getlength"></a>  CTokenGroups::GetLength  
 Gibt die Größe der **CTokenGroup** Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Gesamtgröße der **CTokenGroup** -Objekts in Bytes.  
  
##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS  
 Ruft einen Zeiger auf die **TOKEN_GROUPS** Struktur.  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger auf die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur, die zu gehören die `CTokenGroups` Access-token-Objekt.  
  
##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes  
 Ruft die `CSid` Objekte und (optional) die Attribute, die zu gehören die `CTokenGroups` Objekt.  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSids`  
 Zeiger auf ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORDs. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode listet alle die `CSid` enthaltenen Objekte der `CTokenGroups` Objekt, und platzieren Sie sie und (optional) die Attributflags in Array von Objekten.  
  
##  <a name="lookupsid"></a>  CTokenGroups::LookupSid  
 Ruft die zugeordneten Attribute ab einem `CSid` Objekt.  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 `pdwAttributes`  
 Zeiger auf ein DWORD, annehmen, wird, die `CSid` Attribut des Objekts. Wenn nicht angegeben oder NULL, wird das Attribut nicht abgerufen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die `CSid` gefunden wird, wird "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Festlegen von `pdwAttributes` auf NULL bietet eine Möglichkeit, bestätigen Sie das Vorhandensein der `CSid` ohne den Zugriff auf das Attribut. Beachten Sie, dass diese Methode nicht verwendet werden soll, um Zugriffsrechte zu überprüfen. Anwendungen sollte stattdessen verwendet die [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) Methode.  
  
##  <a name="operator_eq"></a>  CTokenGroups::operator =  
 Zuweisungsoperator.  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CTokenGroups` Objekt oder [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur zuweisen der `CTokenGroups` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CTokenGroups` Objekt.  
  
##  <a name="operator_const_token_groups__star"></a>  Const TOKEN_GROUPS CTokenGroups::operator *  
 Wandelt einen Wert in einen Zeiger auf die **TOKEN_GROUPS** Struktur.  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Wandelt einen Wert in einen Zeiger auf die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für nachrichtensicherheit](../../visual-cpp-samples.md)   
 [CSid-Klasse](../../atl/reference/csid-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
