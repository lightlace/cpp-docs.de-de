---
title: CDacl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
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
ms.openlocfilehash: bb418919c26e3c0054a151b859cdf3f31c5d73a8
ms.lasthandoff: 02/24/2017

---
# <a name="cdacl-class"></a>CDacl-Klasse
Diese Klasse ist ein Wrapper für eine Struktur DACL (discretionary Access Control List).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|Der Konstruktor.|  
|[CDacl:: ~ CDacl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|Fügt einen zulässigen ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) auf den `CDacl` Objekt.|  
|[CDacl::AddDeniedAce](#adddeniedace)|Fügt einen verweigerten ACE, der `CDacl` Objekt.|  
|[CDacl::GetAceCount](#getacecount)|Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.|  
|[CDacl::RemoveAce](#removeace)|Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der `CDacl` Objekt.|  
|[CDacl::RemoveAllAces](#removeallaces)|Entfernt alle ACEs Bestandteil der `CDacl` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Sicherheitsdeskriptor für ein Objekt kann eine DACL enthalten. Eine DACL enthält null oder mehr ACEs (Access Control-Einträge), die die Benutzer und Gruppen, die das Objekt zugreifen können. Wenn eine DACL leer ist (d. h., er enthält keine ACEs), keinen Zugriff ist explizit erteilt, damit der Zugriff implizit verweigert wird. Wenn jedoch Sicherheitsdeskriptor für ein Objekt keine DACL, das Objekt ist nicht geschützt und alle Benutzer über Vollzugriff verfügt.  
  
 Um DACLs eines Objekts abzurufen, müssen Sie den Besitzer des Objekts sein oder READ_CONTROL Zugriff auf das Objekt. Um DACLs eines Objekts zu ändern, müssen Sie WRITE_DAC auf das Objekt zugreifen.  
  
 Die Klasse bereitgestellten Methoden zum Erstellen, hinzufügen, entfernen und Löschen von ACEs aus der `CDacl` Objekt. Siehe auch [AtlGetDacl](http://msdn.microsoft.com/library/a0973648-0d46-4c1a-914f-bda861fe5d19) und [AtlSetDacl](http://msdn.microsoft.com/library/eb88ccb6-1f1b-444d-b0c9-8d5cd0dd6c0b).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
 Fügt einen zulässigen ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) auf den `CDacl` Objekt.  
  
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
 Gibt die Maske der zu gewährenden Zugriffsrechte für den angegebenen `CSid` Objekt.  
  
 `AceFlags`  
 Ein Satz von Bitflags, die Vererbung von ACE steuern.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn ACE hinzugefügt wird die `CDacl` Objekt **false** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CDacl` Objekt enthält null oder mehr ACEs (Access Control-Einträge), die die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, der Zugriff auf die `CDacl` Objekt.  
  
> [!NOTE]
>  Die zweite Form der `AddAllowedAce` ist nur auf Windows 2000 und höher.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden können, in der `AceFlags` Parameter.  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
 Einen verweigerten ACE (Access Control Entry) hinzugefügt der `CDacl` Objekt.  
  
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
 Ein Satz von Bitflags, die Vererbung von ACE steuern. Der Standardwert ist 0, in der ersten Form der Methode.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn ACE hinzugefügt wird die `CDacl` Objekt **false** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CDacl` Objekt enthält null oder mehr ACEs (Access Control-Einträge), die die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, der verweigert den Zugriff auf die `CDacl` Objekt.  
  
> [!NOTE]
>  Die zweite Form der `AddDeniedAce` ist nur auf Windows 2000 und höher.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden können, in der `AceFlags` Parameter.  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 Der Konstruktor.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Eine vorhandene **ACL** Struktur (Access Control List).  
  
### <a name="remarks"></a>Hinweise  
 Die `CDacl` -Objekt kann optional mit einer vorhandenen erstellt werden **ACL** Struktur. Es ist wichtig zu beachten, dass nur eine DACL (discretionary Access Control List), und keine SACL (System Access Control-Liste), als dieser Parameter übergeben werden sollte. In Debugbuilds verursacht eine SACL übergeben einer Assert-Anweisung. In Releasebuilds übergeben eine SACL bewirkt, dass die Zugriffssteuerungseinträge (Access Control-Einträge) in der Zugriffssteuerungsliste ignoriert werden und tritt kein Fehler auf.  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 Der Destruktor.  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt mithilfe von des Objekts, einschließlich aller Zugriffssteuerungseinträge (Access Control-Einträge) erworben Ressourcen frei [CDacl::RemoveAllAces](#removeallaces).  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACEs, die Bestandteil der `CDacl` Objekt.  
  
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
 Sie sollten sicherstellen, dass Sie nur eine DACL (discretionary Access Control List) für diese Funktion übergeben. Übergibt eine SACL (System Access Control List) wird für diese Funktion eine Bestätigung in Debugbuilds jedoch verursacht keine Fehler in Releasebuilds.  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der `CDacl` Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 Entfernt alle ACEs (Access Control-Einträge) Bestandteil der `CDacl` Objekt.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle **ACE** (Access Control Entry)-Struktur (falls vorhanden) in den `CDacl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
 [CAcl-Klasse](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

