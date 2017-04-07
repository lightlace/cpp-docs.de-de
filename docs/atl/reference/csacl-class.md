---
title: CSacl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
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
ms.openlocfilehash: bd9ef9932938cfe5ec65965b3a40116da7f43b90
ms.lasthandoff: 03/31/2017

---
# <a name="csacl-class"></a>CSacl-Klasse
Diese Klasse ist ein Wrapper für eine Struktur SACL (System Access Control List).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Der Konstruktor.|  
|[CSacl:: ~ CSacl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|Wird ein Eintrag für Audit-Zugriffssteuerung (ACE) in der `CSacl` Objekt.|  
|[CSacl::GetAceCount](#getacecount)|Gibt die Anzahl der Access-Zugriffssteuerungseinträge (ACEs) in der `CSacl` Objekt.|  
|[CSacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der **CSacl** Objekt.|  
|[CSacl::RemoveAllAces](#removeallaces)|Entfernt alle der in enthaltenen ACEs der `CSacl` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Eine SACL enthält Access-Zugriffssteuerungseinträge (ACEs), die die Typen von Zugriffsversuchen angeben, die Überwachungsdatensätze in das Sicherheitsereignisprotokoll von einem Domänencontroller zu generieren. Beachten Sie, dass eine SACL Protokolleinträge nur auf dem Domänencontroller generiert, auf dem der Zugriffsversuch aufgetreten ist, nicht auf jedem Domänencontroller, die ein Replikat des Objekts enthält.  
  
 Um die SACL in Sicherheitsbeschreibung eines Objekts abgerufen oder festgelegt, muss die Berechtigung SE_SECURITY_NAME im Zugriffstoken des anfordernden Threads aktiviert sein. Die Gruppe "Administratoren" verfügt über dieses Recht gewährt wird, wird standardmäßig, und an andere Benutzer oder Gruppen erteilt werden. Über die Berechtigung erteilt ist nicht erforderlich: Bevor Sie der Vorgang, durch die Berechtigung definierten ausgeführt werden kann, muss die Berechtigung in das Zugriffstoken für die Sicherheit aktiviert werden, um wirksam wird. Das Modell kann Berechtigungen nur für bestimmte Systemvorgänge aktiviert, und klicken Sie dann deaktiviert, wenn sie nicht mehr benötigt werden. Finden Sie unter [AtlGetSacl](security-global-functions.md#atlgetsacl) und [AtlSetSacl](security-global-functions.md#atlsetsacl) Beispiele SE_SECURITY_NAME aktivieren.  
  
 Die Klasse bereitgestellten Methoden zum Hinzufügen, entfernen, erstellen und Löschen von ACEs aus dem **SACL** Objekt. Siehe auch [AtlGetSacl](security-global-functions.md#atlgetsacl) und [AtlSetSacl](security-global-functions.md#atlsetsacl).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="addauditace"></a>CSacl::AddAuditAce  
 Wird ein Eintrag für Audit-Zugriffssteuerung (ACE) in der `CSacl` Objekt.  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 `AccessMask`  
 Gibt die Subnetzmaske des zu überwachenden Zugriffsrechte für den angegebenen `CSid` Objekt.  
  
 `bSuccess`  
 Gibt an, ob zulässigen Zugriffsversuche überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 *bFailure*  
 Gibt an, ob verweigerten Zugriffsversuche überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 `AceFlags`  
 Ein Satz von Bitflags, die ACE-Vererbung zu steuern.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn ACE hinzugefügt wird die `CSacl` Objekt **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CSacl` Objekt enthält die Access-Zugriffssteuerungseinträge (ACEs), die die Typen von Zugriffsversuchen angeben, die Überwachungsdatensätze in das Sicherheitsereignisprotokoll generieren. Diese Methode fügt diese einen ACE zum die `CSacl` Objekt. Die zweite Form der `AddAuditAce` ist nur auf Windows 2000 und höher verfügbar.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der `AceFlags` Parameter.  
  
##  <a name="csacl"></a>CSacl::CSacl  
 Der Konstruktor.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Eine vorhandene **ACL** (Access Control List)-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSacl` -Objekt kann optional mithilfe eines vorhandenen erstellt werden **ACL** Struktur. Stellen Sie sicher, dass dieser Parameter eine System Access Control List (SACL) und keiner Liste von Zugriffssteuerungsliste (DACL) ist. Debug-Builds, wenn eine DACL angegeben, wird eine Assertion erfolgt. In Releasebuilds werden alle Einträge aus einer DACL ignoriert.  
  
##  <a name="dtor"></a>CSacl:: ~ CSacl  
 Der Destruktor.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen, die von dem Objekt, einschließlich der Access-Control-Einträge (ACEs) abgerufen.  
  
##  <a name="getacecount"></a>CSacl::GetAceCount  
 Gibt die Anzahl der Access-Zugriffssteuerungseinträge (ACEs) in der `CSacl` Objekt.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACEs im enthalten die `CSacl` Objekt.  
  
##  <a name="operator_eq"></a>CSacl::operator =  
 Zuweisungsoperator.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die **ACL** (Access Control List) auf das vorhandene Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CSacl` Objekt. Sicherstellen, dass die **ACL** Parameter ist tatsächlich eine System Access Control List (SACL) und keiner Liste von Zugriffssteuerungsliste (DACL). Debug-Builds, die eine Assertion tritt auf, und klicken Sie in Releasebuilds die **ACL** -Parameter wird ignoriert.  
  
##  <a name="removeace"></a>CSacl::RemoveAce  
 Entfernt einen bestimmten ACE (Access Control Entry) aus der **CSacl** Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleiteten [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CSacl::RemoveAllAces  
 Entfernt alle von der Access-Zugriffssteuerungseinträge (ACEs) in enthalten die `CSacl` Objekt.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle **ACE** -Struktur (falls vorhanden) in der `CSacl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CAcl-Klasse](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)

