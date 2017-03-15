---
title: CTokenGroups Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CTokenGroups
- ATL.CTokenGroups
- CTokenGroups
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
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
ms.openlocfilehash: 41b93e1c0a2e55013e280023a7f47610d38ddc10
ms.lasthandoff: 02/24/2017

---
# <a name="ctokengroups-class"></a>CTokenGroups-Klasse
Diese Klasse ist ein Wrapper für die **TOKEN_GROUPS** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|Der Konstruktor.|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|Fügt eine `CSid` oder vorhandene **TOKEN_GROUPS** Struktur auf der `CTokenGroups` Objekt.|  
|[CTokenGroups::Delete](#delete)|Löscht eine `CSid` und die zugehörigen Attribute aus der `CTokenGroups` Objekt.|  
|[CTokenGroups::DeleteAll](#deleteall)|Löscht alle `CSid` Objekte und die zugehörigen Attribute aus der `CTokenGroups` Objekt.|  
|[CTokenGroups::GetCount](#getcount)|Gibt die Anzahl der `CSid` Objekte und die zugehörigen Attribute in der **CTokenGroups** Objekt.|  
|[CTokenGroups::GetLength](#getlength)|Gibt die Größe der `CTokenGroups` Objekt.|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Ruft einen Zeiger auf die **TOKEN_GROUPS** Struktur.|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Ruft die `CSid` Objekte und Attribute, die für die `CTokenGroups` Objekt.|  
|[CTokenGroups::LookupSid](#lookupsid)|Ruft die zugeordneten Attribute ein `CSid` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const TOKEN_GROUPS CTokenGroups::operator *](#operator_const_token_groups__star)|Wandelt die `CTokenGroups` Objekt in einen Zeiger auf die **TOKEN_GROUPS** Struktur.|  
|[CTokenGroups::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das beschreibt den Sicherheitskontext für einen Prozess oder Thread, und jeder Benutzer ein Windows NT oder Windows 2000-System angemeldet zugeordnet ist.  
  
 Die **CTokenGroups** ist ein Wrapper für die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur mit Informationen über die Gruppe Sicherheits-IDs (SIDs) im Zugriffstoken.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="a-nameadda--ctokengroupsadd"></a><a name="add"></a>CTokenGroups::Add  
 Fügt eine `CSid` oder vorhandene **TOKEN_GROUPS** Struktur auf der `CTokenGroups` Objekt.  
  
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
 Diese Methoden fügen Sie ein oder mehr `CSid` Objekte und die zugehörigen Attribute, die `CTokenGroups` Objekt.  
  
##  <a name="a-namectokengroupsa--ctokengroupsctokengroups"></a><a name="ctokengroups"></a>CTokenGroups::CTokenGroups  
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
 Die `CTokenGroups` -Objekt kann optional mit erstellt werden ein **TOKEN_GROUPS** Struktur oder eine zuvor definierte `CTokenGroups` Objekt.  
  
##  <a name="a-namedtora--ctokengroupsctokengroups"></a><a name="dtor"></a>CTokenGroups:: ~ CTokenGroups  
 Der Destruktor.  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-namedeletea--ctokengroupsdelete"></a><a name="delete"></a>CTokenGroups::Delete  
 Löscht eine `CSid` und die zugehörigen Attribute aus der `CTokenGroups` Objekt.  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt für die die Sicherheits-ID (SID) und die Attribute entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der `CSid` entfernt wurde, false andernfalls.  
  
##  <a name="a-namedeletealla--ctokengroupsdeleteall"></a><a name="deleteall"></a>CTokenGroups::DeleteAll  
 Löscht alle `CSid` Objekte und die zugehörigen Attribute aus der `CTokenGroups` Objekt.  
  
```
void DeleteAll() throw();
```  
  
##  <a name="a-namegetcounta--ctokengroupsgetcount"></a><a name="getcount"></a>CTokenGroups::GetCount  
 Gibt die Anzahl der `CSid` Objekte in `CTokenGroups`.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der [CSid](../../atl/reference/csid-class.md) Objekte und die zugehörigen Attribute, die Bestandteil der `CTokenGroups` Objekt.  
  
##  <a name="a-namegetlengtha--ctokengroupsgetlength"></a><a name="getlength"></a>CTokenGroups::GetLength  
 Gibt die Größe der **CTokenGroup** Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Gesamtgröße der **CTokenGroup** -Objekts in Bytes.  
  
##  <a name="a-namegetptokengroupsa--ctokengroupsgetptokengroups"></a><a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS  
 Ruft einen Zeiger auf die **TOKEN_GROUPS** Struktur.  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger auf die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) zur Struktur der `CTokenGroups` Access token-Objekt.  
  
##  <a name="a-namegetsidsandattributesa--ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes  
 Ruft die `CSid` Objekte und (optional) die Attribute für die `CTokenGroups` Objekt.  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSids`  
 Zeiger auf ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORD. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode werden alle aufgelistet der `CSid` Objekte in der `CTokenGroups` Objekt, und platzieren sie und (optional) die Attributflags in Arrayobjekte.  
  
##  <a name="a-namelookupsida--ctokengroupslookupsid"></a><a name="lookupsid"></a>CTokenGroups::LookupSid  
 Ruft die zugeordneten Attribute ein `CSid` Objekt.  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 `pdwAttributes`  
 Zeiger auf ein DWORD zulässt, wird das `CSid` -Attribut des Objekts. Wenn nicht angegeben oder NULL, wird das Attribut nicht abgerufen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die `CSid` gefunden wird, wird "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Festlegen von `pdwAttributes` auf NULL bietet eine Möglichkeit, bestätigen das Vorhandensein der `CSid` ohne Zugriff auf das Attribut. Beachten Sie, dass diese Methode nicht verwendet werden soll, um Zugriffsrechte zu überprüfen, wie unter Windows 2000 falsche Ergebnisse auftreten können. Anwendungen sollte stattdessen verwendet die [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) Methode.  
  
##  <a name="a-nameoperatoreqa--ctokengroupsoperator-"></a><a name="operator_eq"></a>CTokenGroups::operator =  
 Zuweisungsoperator.  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CTokenGroups` Objekt oder [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur zuweisen der `CTokenGroups` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CTokenGroups` Objekt.  
  
##  <a name="a-nameoperatorconsttokengroupsstara--ctokengroupsoperator-const-tokengroups-"></a><a name="operator_const_token_groups__star"></a>Const TOKEN_GROUPS CTokenGroups::operator *  
 Wandelt einen Wert in einen Zeiger auf die **TOKEN_GROUPS** Struktur.  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Wandelt einen Wert in einen Zeiger auf die [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
 [CSid-Klasse](../../atl/reference/csid-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

