---
title: CDacl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs: C++
helpviewer_keywords: CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f57fc1bdd641fbc8e770ddc9b37480530034ba1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdacl-class"></a>CDacl-Klasse
Diese Klasse ist ein Wrapper für eine Struktur DACL (discretionary Access Control List).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|Der Konstruktor.|  
|[CDacl:: ~ CDacl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|Fügt einen zulässigen ACE (Access Control Entry) auf die `CDacl` Objekt.|  
|[CDacl::AddDeniedAce](#adddeniedace)|Fügt einen verweigerten ACE, die `CDacl` Objekt.|  
|[CDacl::GetAceCount](#getacecount)|Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.|  
|[CDacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der `CDacl` Objekt.|  
|[CDacl::RemoveAllAces](#removeallaces)|Entfernt alle der in enthaltenen ACEs der `CDacl` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Sicherheitsbeschreibung für ein Objekt kann es sich um eine DACL enthalten. Eine DACL enthält 0 (null) oder mehreren Zugriffssteuerungseinträgen (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Wenn eine DACL leer ist (d. h., er enthält 0 (null) ACEs), keine Zugriff explizit erteilt, daher implizit Zugriff verweigert wird. Wenn die Sicherheitsbeschreibung für ein Objekt keine DACL, das Objekt ist nicht geschützt und "Jeder" über Vollzugriff verfügt.  
  
 Um DACL eines Objekts abzurufen, müssen Sie den Besitzer des Objekts sein oder haben READ_CONTROL Zugriff auf das Objekt. Um die DACL eines Objekts zu ändern, benötigen Sie WRITE_DAC Zugriff auf das Objekt.  
  
 Die Klasse bereitgestellten Methoden zum Erstellen, hinzufügen, entfernen und Löschen von ACEs aus der `CDacl` Objekt. Siehe auch [AtlGetDacl](security-global-functions.md#atlgetdacl) und [AtlSetDacl](security-global-functions.md#atlsetdacl).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
 Fügt einen zulässigen ACE (Access Control Entry) auf die `CDacl` Objekt.  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Ein [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 `AccessMask`  
 Gibt die Subnetzmaske von Zugriffsrechten dürfen für den angegebenen `CSid` Objekt.  
  
 `AceFlags`  
 Ein Satz von Bitflags, die ACE-Vererbung zu steuern.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn ACE hinzugefügt wird die `CDacl` Objekt **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CDacl` Objekt enthält 0 (null) oder mehreren Zugriffssteuerungseinträgen (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, durch den Zugriff auf die `CDacl` Objekt.  
  
> [!NOTE]
>  Die zweite Form der `AddAllowedAce` ist nur auf Windows 2000 und höher verfügbar.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der `AceFlags` Parameter.  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
 Fügt einen verweigerten ACE (Access Control Entry) auf die `CDacl` Objekt.  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Ein `CSid`-Objekt.  
  
 `AccessMask`  
 Gibt die Subnetzmaske der Zugriffsrechte verweigert werden für den angegebenen `CSid` Objekt.  
  
 `AceFlags`  
 Ein Satz von Bitflags, die ACE-Vererbung zu steuern. Der Standardwert ist 0, in der ersten Form der Methode.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn ACE hinzugefügt wird die `CDacl` Objekt **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CDacl` Objekt enthält 0 (null) oder mehreren Zugriffssteuerungseinträgen (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, durch den verweigert den Zugriff auf die `CDacl` Objekt.  
  
> [!NOTE]
>  Die zweite Form der `AddDeniedAce` ist nur auf Windows 2000 und höher verfügbar.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der `AceFlags` Parameter.  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 Der Konstruktor.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Eine vorhandene **ACL** (Access Control List)-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `CDacl` -Objekt kann optional mithilfe eines vorhandenen erstellt werden **ACL** Struktur. Es ist wichtig zu beachten, dass nur eine DACL (discretionary Access Control List), und keine SACL (System Access Control List), sollten als diesen Parameter übergeben werden. Debug-Builds bewirkt und übergeben einer SACL ASSERT. In Releasebuilds übergeben einer SACL wird dazu führen, dass die Zugriffssteuerungseinträge (Access Control-Einträge) in der ACL, ignoriert werden sollen, und tritt kein Fehler auf.  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 Der Destruktor.  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen abgerufen, von dem Objekt, einschließlich aller ACEs (Access Control-Einträge), die mit frei [CDacl::RemoveAllAces](#removeallaces).  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACEs im enthalten die `CDacl` Objekt.  
  
##  <a name="operator_eq"></a>CDacl::operator =  
 Zuweisungsoperator.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die ACL (Access Control List) auf das vorhandene Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CDacl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten sicherstellen, dass Sie nur eine DACL (discretionary Access Control List) für diese Funktion übergeben. Übergeben einer SACL (System Access Control List) für diese Funktion verursacht eine ASSERTION in Debugbuilds jedoch verursacht keine Fehler in Releasebuilds.  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 Entfernt einen bestimmten ACE (Access Control Entry) aus der `CDacl` Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleiteten [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 Entfernt alle der in enthaltenen ACEs (Access Control-Einträge) die `CDacl` Objekt.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle **ACE** (Access Control Entry)-Struktur (falls vorhanden) in der `CDacl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für nachrichtensicherheit](../../visual-cpp-samples.md)   
 [CAcl-Klasse](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
