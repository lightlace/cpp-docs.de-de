---
title: CAcl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
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
ms.openlocfilehash: 52de083664c2e9ca00a140450cb43372aff28428
ms.lasthandoff: 02/24/2017

---
# <a name="cacl-class"></a>CAcl-Klasse
Diese Klasse ist ein Wrapper für eine `ACL` Struktur (Access Control List).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAcl
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Ein Array von `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](#caceflagarray)|Ein Array von `BYTE`s.|  
|[CAcl::CAceTypeArray](#cacetypearray)|Ein Array von `BYTE`s.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|Der Konstruktor.|  
|[CAcl:: ~ CAcl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|Gibt die Anzahl der Access Control Entry (ACE)-Objekte zurück.|  
|[CAcl::GetAclEntries](#getaclentries)|Ruft die Access Control List (ACL) Einträge aus der `CAcl` Objekt.|  
|[CAcl::GetAclEntry](#getaclentry)|Ruft alle Informationen über einen Eintrag in einer `CAcl` Objekt.|  
|[CAcl::GetLength](#getlength)|Gibt die Länge der Zugriffssteuerungsliste zurück.|  
|[CAcl::GetPACL](#getpacl)|Gibt eine PACL (Zeiger auf eine Zugriffssteuerungsliste) zurück.|  
|[CAcl::IsEmpty](#isempty)|Tests der `CAcl` Objekt Einträge.|  
|[CAcl::IsNull](#isnull)|Gibt den Status der `CAcl` Objekt.|  
|[CAcl::RemoveAce](#removeace)|Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der `CAcl` Objekt.|  
|[CAcl::RemoveAces](#removeaces)|Entfernt alle Zugriffssteuerungseinträge (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.|  
|[CAcl::SetEmpty](#setempty)|Markiert die `CAcl` -Objekt als leer.|  
|[CAcl::SetNull](#setnull)|Markiert die `CAcl` -Objekt als `NULL`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|Wandelt eine `CAcl` -Objekt an eine `ACL` Struktur.|  
|[CAcl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Die **ACL** Struktur ist der Header einer ACL (Access Control List). Eine ACL enthält eine sequenzielle Liste von NULL oder mehr [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868) (Access Control-Einträge). Einzelne ACEs in einer Zugriffssteuerungsliste werden nummeriert von 0 bis *n-1*, wobei *n* ist die Anzahl der ACEs in der ACL. Bei der Bearbeitung einer ACL bezieht sich eine Anwendung auf eine Access-Zugriffssteuerungseintrag (ACE) in der ACL über seinen Index.  
  
 Es gibt zwei Typen von Zugriffssteuerungslisten:  
  
-   Discretionary  
  
-   System  
  
 Eine freigegebene ACL wird gesteuert, indem der Besitzer eines Objekts oder jeder erteilt **WRITE_DAC** Zugriff auf das Objekt. Es gibt an, dass der Zugriff bestimmter Benutzer und Gruppen zu einem Objekt können. Beispielsweise können der Besitzer einer Datei eine freigegebene ACL zu steuern, welche Benutzer und Gruppen kann und keinen Zugriff auf die Datei.  
  
 Ein Objekt kann auch auf Systemebene Sicherheitsinformationen zugeordnet, in Form eines Systems ACL, die von einem Systemadministrator gesteuert werden. Ein System ACL können den Systemadministrator alle Versuche, den Zugriff auf ein Objekt überwacht.  
  
 Weitere Informationen finden Sie unter der [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) Diskussion in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 Ein Array von ACCESS_MASK-Objekten.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition gibt den Arraytyp, der zum Speichern der Zugriffsrechte verwendet in Access-Zugriffssteuerungseinträge (ACEs) verwendet werden kann.  
  
##  <a name="caceflagarray"></a>CAcl::CAceFlagArray  
 Ein Array von BYTEs.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition gibt den Arraytyp verwendet, um die Access Control Entry (ACE)-spezifische Steuerungsflags definieren. Finden Sie unter der [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Definition für eine vollständige Liste der möglichen-Flags.  
  
##  <a name="cacetypearray"></a>CAcl::CAceTypeArray  
 Ein Array von BYTEs.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition gibt den Arraytyp verwendet, um die Art der Access Control Entry (ACE) Objekte, z. B. ACCESS_ALLOWED_ACE_TYPE oder ACCESS_DENIED_ACE_TYPE definieren. Finden Sie unter der [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Definition für eine vollständige Liste möglicher Typen.  
  
##  <a name="cacl"></a>CAcl::CAcl  
 Der Konstruktor.  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Ein vorhandenes `CAcl`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CAcl` -Objekt kann optional mit einer vorhandenen erstellt werden `CAcl` Objekt.  
  
##  <a name="dtor"></a>CAcl:: ~ CAcl  
 Der Destruktor.  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt abgerufen, die vom Objekt Ressourcen frei.  
  
##  <a name="getacecount"></a>CAcl::GetAceCount  
 Gibt die Anzahl der Access Control Entry (ACE)-Objekte zurück.  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACE-Einträge in der `CAcl` Objekt.  
  
##  <a name="getaclentries"></a>CAcl::GetAclEntries  
 Ruft die Access Control List (ACL) Einträge aus der `CAcl` Objekt.  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSids`  
 Ein Zeiger auf ein Array von [CSid](../../atl/reference/csid-class.md) Objekte.  
  
 *pAccessMasks*  
 Die Access-Masken.  
  
 *pAceTypes*  
 Die Access Control Entry ( **ACE**) Typen.  
  
 *pAceFlags*  
 Die **ACE** Flags.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode füllt die Arrayparameter mit den Details jeder **ACE** -Objekt in die `CAcl` Objekt. Verwenden Sie NULL, wenn die Details für dieses bestimmte Array nicht erforderlich sind.  
  
 Den Inhalt der einzelnen Arrays entsprechen, d. h. das erste Element der der `CAccessMaskArray` das erste Element im Array entspricht der `CSidArray` Array und So weiter.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Weitere Informationen zu ACE-Typen und Flags.  
  
##  <a name="getaclentry"></a>CAcl::GetAclEntry  
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
 `nIndex`  
 Index für die ACL-Eintrag abrufen.  
  
 `pSid`  
 Die [CSid](../../atl/reference/csid-class.md) -Objekt für die ACL-Eintrag gilt.  
  
 *pMask*  
 Die Maske, die Festlegung von Berechtigungen zu erteilen oder Verweigern des Zugriffs.  
  
 `pType`  
 Der ACE-Typ.  
  
 `pFlags`  
 Die ACE-Flags.  
  
 `pObjectType`  
 Der Objekttyp. Diese wird auf GUID_NULL festgelegt werden, wenn der Objekttyp in der ACE-Eintrag nicht angegeben ist, oder wenn der ACE kein ACE-Objekt ist.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp. Diese wird auf GUID_NULL festgelegt werden, wenn der vererbten Objekttyp in der ACE-Eintrag nicht angegeben ist, oder wenn der ACE kein ACE-Objekt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft alle Informationen über eine einzelne ACE, der mit weiteren Informationen als [CAcl::GetAclEntries](#getaclentries) allein zur Verfügung.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Weitere Informationen zu ACE-Typen und Flags.  
  
##  <a name="getlength"></a>CAcl::GetLength  
 Gibt die Länge der Zugriffssteuerungsliste (ACL) zurück.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erforderliche Länge in Bytes zurück zum Speichern der **ACL** Struktur.  
  
##  <a name="getpacl"></a>CAcl::GetPACL  
 Gibt einen Zeiger auf eine Zugriffssteuerungsliste (ACL).  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die **ACL** Struktur.  
  
##  <a name="isempty"></a>CAcl::IsEmpty  
 Tests der `CAcl` Objekt Einträge.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **true** Wenn das `CAcl` Objekt ist nicht NULL und keine Einträge enthält. Gibt **false** Wenn das `CAcl` Objekt ist entweder NULL oder mindestens einen Eintrag enthält.  
  
##  <a name="isnull"></a>CAcl::IsNull  
 Gibt den Status der `CAcl` Objekt.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das `CAcl` Objekt ist NULL, **false** andernfalls.  
  
##  <a name="operator_const_acl__star"></a>CAcl::operator const ACL *  
 Wandelt eine `CAcl` -Objekt an ein **ACL** Struktur (Access Control List).  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Adresse der **ACL** Struktur.  
  
##  <a name="operator_eq"></a>CAcl::operator =  
 Zuweisungsoperator.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CAcl` im vorhandenen Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CAcl` Objekt.  
  
##  <a name="removeace"></a>CAcl::RemoveAce  
 Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der **CAcl** Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeaces"></a>CAcl::RemoveAces  
 Entfernt Alls ACEs (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Ein Verweis auf ein `CSid`-Objekt.  
  
##  <a name="setempty"></a>CAcl::SetEmpty  
 Markiert die `CAcl` -Objekt als leer.  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CAcl` kann leer oder auf NULL festgelegt werden: die beiden Zustände unterscheiden.  
  
##  <a name="setnull"></a>CAcl::SetNull  
 Markiert die `CAcl` Objekt als NULL.  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CAcl` kann leer oder auf NULL festgelegt werden: die beiden Zustände unterscheiden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

