---
title: CSacl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65375b764c0d8d8673a59fcfb47b4eecaf730cb5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879951"
---
# <a name="csacl-class"></a>CSacl-Klasse
Diese Klasse ist ein Wrapper für eine SACL (System Access Control List)-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Der Konstruktor.|  
|[CSacl::~CSacl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|Fügt einen Überwachungseintrag für Access Control (ACE) die `CSacl` Objekt.|  
|[CSacl::GetAceCount](#getacecount)|Gibt die Anzahl der Access-Control-Einträge (ACEs) in der `CSacl` Objekt.|  
|[CSacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der `CSacl` Objekt.|  
|[CSacl::RemoveAllAces](#removeallaces)|Entfernt alle ACEs innerhalb der `CSacl` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Eine SACL enthält Access-Control-Einträge (ACEs), die die Arten von Zugriffsversuchen angeben, die Überwachungsdatensätze in das Sicherheitsereignisprotokoll von einem Domänencontroller zu generieren. Beachten Sie, dass eine SACL Protokolleinträge, die nur auf dem Domänencontroller generiert, in der Zugriffsversuch aufgetreten ist, nicht auf jedem Domänencontroller, die ein Replikat des Objekts enthält.  
  
 Um festzulegen, oder die SACL in der Sicherheitsbeschreibung des Objekts abzurufen, muss die SE_SECURITY_NAME-Berechtigung im Zugriffstoken des anfordernden Threads aktiviert sein. Die Gruppe "Administratoren" verfügt über diese Berechtigung standardmäßig erteilt werden, und es für andere Benutzer oder Gruppen gewährt werden kann. Die Berechtigung gewährt ist nicht alles, was erforderlich ist: damit der Vorgang, durch die Berechtigung definiert ausgeführt werden kann, muss die Berechtigung in das Sicherheitstoken für den Zugriff aktiviert werden, um wirksam werden. Das Modell kann Berechtigungen nur für bestimmte Systemvorgänge aktiviert, und klicken Sie dann deaktiviert, wenn sie nicht mehr benötigt werden. Finden Sie unter [AtlGetSacl](security-global-functions.md#atlgetsacl) und [AtlSetSacl](security-global-functions.md#atlsetsacl) Beispiele SE_SECURITY_NAME aktivieren.  
  
 Verwenden Sie die Methoden der Klasse bereitgestellt, um das Hinzufügen, entfernen, erstellen und Löschen von ACEs aus dem `SACL` Objekt. Siehe auch [AtlGetSacl](security-global-functions.md#atlgetsacl) und [AtlSetSacl](security-global-functions.md#atlsetsacl).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
 Fügt einen Überwachungseintrag für Access Control (ACE) die `CSacl` Objekt.  
  
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
 *rSid*  
 Die [CSid](../../atl/reference/csid-class.md) Objekt.  
  
 *"AccessMask"*  
 Gibt die Maske von Zugriffsrechten zu überwachenden für den angegebenen `CSid` Objekt.  
  
 *bSuccess*  
 Gibt an, ob zulässigen Zugriffsversuche sollen überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 *bFailure*  
 Gibt an, ob verweigerte Zugriffsversuche sollen überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 *AceFlags*  
 Ein Satz von Bitflags, die Vererbung des ACE steuern.  
  
 *pObjectType*  
 Der Objekttyp.  
  
 *pInheritedObjectType*  
 Den geerbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der ACE hinzugefügt wird die `CSacl` Objekt, "false" bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CSacl` Objekt enthält die Access-Control-Einträge (ACEs), die die Arten von Zugriffsversuchen angeben, die Überwachungsdatensätze in das Sicherheitsereignisprotokoll zu generieren. Diese Methode fügt diese einen ACE, der `CSacl` Objekt.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der *AceFlags* Parameter.  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 Der Konstruktor.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *RS*  
 Eine vorhandene `ACL` (Access Control List)-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSacl` -Objekt kann optional mit einer vorhandenen erstellt werden `ACL` Struktur. Stellen Sie sicher, dass dieser Parameter eine System Access Control List, (Systemzugriffssteuerungsliste SACL) und keiner Liste von Zugriffssteuerungsliste (DACL) ist. Debug-Builds, wenn eine DACL angegeben, wird eine Assertion erfolgt. In Releasebuilds werden alle Einträge aus eine DACL ignoriert.  
  
##  <a name="dtor"></a>  CSacl:: ~ CSacl  
 Der Destruktor.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen, die abgerufen werden, von dem Objekt, einschließlich der Access-Control-Einträge (ACEs) frei.  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 Gibt die Anzahl der Access-Control-Einträge (ACEs) in der `CSacl` Objekt.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACEs innerhalb der `CSacl` Objekt.  
  
##  <a name="operator_eq"></a>  CSacl::operator =  
 Zuweisungsoperator.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *RS*  
 Die `ACL` (Access Control List) auf das vorhandene Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CSacl` Objekt. Sicherstellen, dass die `ACL` Parameter ist tatsächlich eine System Access Control List (SACL) und keiner Liste von Zugriffssteuerungsliste (DACL). In Debugbuilds auf der Behauptung tritt auf, und in Releasebuilds der `ACL` Parameter wird ignoriert.  
  
##  <a name="removeace"></a>  CSacl::RemoveAce  
 Entfernt einen bestimmten ACE (Access Control Entry) aus der `CSacl` Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Index mit dem ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>  CSacl::RemoveAllAces  
 Entfernt alle der Access-Control-Einträge (ACEs) in enthalten die `CSacl` Objekt.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle `ACE` Struktur (falls vorhanden) in der `CSacl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CAcl-Klasse](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
