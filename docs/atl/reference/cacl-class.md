---
title: CAcl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b49d7bf064d65e9a160311d23b304745f4d1b04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cacl-class"></a>CAcl-Klasse
Diese Klasse ist ein Wrapper für ein `ACL` (Access Control List)-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CAcl::GetAceCount](#getacecount)|Gibt die Anzahl von Access Control Entry (ACE)-Objekte zurück.|  
|[CAcl::GetAclEntries](#getaclentries)|Ruft den Access Control (List, ACL) Einträge aus der `CAcl` Objekt.|  
|[CAcl::GetAclEntry](#getaclentry)|Ruft alle Informationen über einen Eintrag in einer `CAcl` Objekt.|  
|[CAcl::GetLength](#getlength)|Gibt die Länge der ACL zurück.|  
|[CAcl::GetPACL](#getpacl)|Gibt eine PACL (Zeiger auf eine Zugriffssteuerungsliste) zurück.|  
|[CAcl::IsEmpty](#isempty)|Tests der `CAcl` Objekt nach Einträgen.|  
|[CAcl::IsNull](#isnull)|Gibt den Status der `CAcl` Objekt.|  
|[CAcl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der `CAcl` Objekt.|  
|[CAcl::RemoveAces](#removeaces)|Entfernt alle Zugriffssteuerungseinträge (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.|  
|[CAcl::SetEmpty](#setempty)|Markiert die `CAcl` als leeres Objekt.|  
|[CAcl::SetNull](#setnull)|Markiert die `CAcl` -Objekts entsprechend der `NULL`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const ACL CAcl::operator *](#operator_const_acl__star)|Wandelt eine `CAcl` -Objekt an eine `ACL` Struktur.|  
|[CAcl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Die **ACL** Struktur ist der Header einer ACL (Access Control List). Eine ACL enthält eine sequenzielle Liste von NULL oder mehr [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868) (Access Control-Einträge). Die einzelne ACEs in einer Zugriffssteuerungsliste werden nummeriert von 0 bis *n-1*, wobei  *n*  ist die Anzahl der ACEs in der ACL. Wenn Sie eine ACL zu bearbeiten, bezieht sich eine Anwendung auf eine Access-Zugriffssteuerungseintrag (ACE) in der ACL über seinen Index.  
  
 Es gibt zwei Typen von ACL:  
  
-   Besitzerverwaltete  
  
-   System  
  
 Eine freigegebene ACL wird gesteuert, indem der Besitzer eines Objekts oder jeder erteilt **WRITE_DAC** Zugriff auf das Objekt. Es gibt an, dass der Zugriff bestimmter Benutzer und Gruppen auf ein Objekt haben können. Beispielsweise können der Besitzer einer Datei eine freigegebene ACL, um zu steuern, welche Benutzer und Gruppen können und kann nicht den Zugriff auf die Datei haben.  
  
 Ein Objekt kann auch auf Systemebene Sicherheitsinformationen zugeordnet, in Form eines Systems ACL gesteuert, die von einem Systemadministrator sein. Ein System-Zugriffssteuerungsliste können den Systemadministrator alle Versuche für den Zugriff auf ein Objekt zu überwachen.  
  
 Weitere Informationen finden Sie unter der [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) Diskussion im Windows SDK.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 Ein Array von ACCESS_MASK-Objekten.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typedef gibt den Arraytyp, der zum Speichern von Zugriffsrechte verwendet in Access-Zugriffssteuerungseinträge (ACEs) verwendet werden kann.  
  
##  <a name="caceflagarray"></a>CAcl::CAceFlagArray  
 Ein Array von BYTEs.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typedef gibt den Arraytyp verwendet, um den Access Control Entry (ACE) typspezifische Steuerungsflags definieren. Finden Sie unter der [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Definition für die vollständige Liste der möglichen Flags.  
  
##  <a name="cacetypearray"></a>CAcl::CAceTypeArray  
 Ein Array von BYTEs.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typedef gibt den Arraytyp verwendet, um die Art der Access Control Entry (ACE) Objekte, z. B. ACCESS_ALLOWED_ACE_TYPE oder ACCESS_DENIED_ACE_TYPE definieren. Finden Sie unter der [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Definition für die vollständige Liste der möglichen Typen.  
  
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
 Die `CAcl` -Objekt kann optional mithilfe eines vorhandenen erstellt werden `CAcl` Objekt.  
  
##  <a name="dtor"></a>CAcl:: ~ CAcl  
 Der Destruktor.  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen, die vom Objekt abgerufen.  
  
##  <a name="getacecount"></a>CAcl::GetAceCount  
 Gibt die Anzahl von Access Control Entry (ACE)-Objekte zurück.  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACE-Einträge in der `CAcl` Objekt.  
  
##  <a name="getaclentries"></a>CAcl::GetAclEntries  
 Ruft den Access Control (List, ACL) Einträge aus der `CAcl` Objekt.  
  
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
 Der Zugriffsmasken.  
  
 *pAceTypes*  
 Der Access-Control-Eintrag ( **ACE**) Typen.  
  
 *pAceFlags*  
 Die **ACE** Flags.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode füllt die Arrayparametern Details zu jeder **ACE** Objekt in der `CAcl` Objekt. Verwenden Sie NULL, wenn die Details für dieses bestimmte Arrays nicht erforderlich sind.  
  
 Der Inhalt jedes Arrays entsprechen zu "other", also das erste Element der der `CAccessMaskArray` das erste Element im Array entspricht der `CSidArray` Array und So weiter.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Weitere Einzelheiten zu ACE-Typen und Flags.  
  
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
 Index für die ACL-Eintrag abgerufen.  
  
 `pSid`  
 Die [CSid](../../atl/reference/csid-class.md) -Objekt, für welche die ACL-Eintrag gilt.  
  
 *pMask*  
 Die Maske, die Berechtigungen zu erteilen oder Verweigern des Zugriffs angibt.  
  
 `pType`  
 Der ACE-Typ.  
  
 `pFlags`  
 Der ACE-Flags.  
  
 `pObjectType`  
 Der Objekttyp. Dies wird auf GUID_NULL festgelegt werden, wenn der Objekttyp in den ACE nicht angegeben ist, oder wenn die ACE kein ACE-Objekt ist.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp. Dies wird auf GUID_NULL festgelegt werden, wenn der vererbten Objekttyp in den ACE nicht angegeben ist, oder wenn die ACE kein ACE-Objekt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft alle Informationen über eine einzelne ACE, bietet mehr Informationen als [CAcl::GetAclEntries](#getaclentries) allein verfügbar macht.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Weitere Einzelheiten zu ACE-Typen und Flags.  
  
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
 Tests der `CAcl` Objekt nach Einträgen.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** Wenn die `CAcl` Objekt ist nicht NULL und enthält keine Einträge. Gibt **"false"** Wenn die `CAcl` Objekt ist entweder NULL oder enthält mindestens einen Eintrag.  
  
##  <a name="isnull"></a>CAcl::IsNull  
 Gibt den Status der `CAcl` Objekt.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die `CAcl` Objekt ist NULL, **"false"** andernfalls.  
  
##  <a name="operator_const_acl__star"></a>Const ACL CAcl::operator *  
 Umwandlungen eine `CAcl` -Objekt an eine **ACL** (Access Control List)-Struktur.  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Adresse des dem **ACL** Struktur.  
  
##  <a name="operator_eq"></a>CAcl::operator =  
 Zuweisungsoperator.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CAcl` das vorhandene Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CAcl` Objekt.  
  
##  <a name="removeace"></a>CAcl::RemoveAce  
 Entfernt einen bestimmten ACE (Access Control Entry) aus der **CAcl** Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleiteten [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeaces"></a>CAcl::RemoveAces  
 Entfernt Alls-ACEs (Access Control-Einträge) aus der `CAcl` gilt für den angegebenen `CSid`.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Ein Verweis auf ein `CSid`-Objekt.  
  
##  <a name="setempty"></a>CAcl::SetEmpty  
 Markiert die `CAcl` als leeres Objekt.  
  
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
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
