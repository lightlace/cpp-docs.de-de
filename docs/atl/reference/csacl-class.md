---
title: CSacl Klasse | Microsoft-Dokumentation
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 50f10ab765648d4b587a941ccf24726b53f14c88
ms.lasthandoff: 02/24/2017

---
# <a name="csacl-class"></a>CSacl-Klasse
Diese Klasse ist ein Wrapper für eine SACL (System Access Control List)-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CSacl::AddAuditAce](#addauditace)|Fügt einen Audit-Access-Control-Eintrag (ACE) die `CSacl` Objekt.|  
|[CSacl::GetAceCount](#getacecount)|Gibt die Anzahl der Access Control-Einträge (ACEs) in der `CSacl` Objekt.|  
|[CSacl::RemoveAce](#removeace)|Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der **CSacl** Objekt.|  
|[CSacl::RemoveAllAces](#removeallaces)|Entfernt alle ACEs Bestandteil der `CSacl` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Eine SACL enthält Access-Zugriffssteuerungseinträge (ACEs), die die Arten von Zugriffsversuchen angeben, die Überwachungseinträge in das Sicherheitsereignisprotokoll eines Domänencontrollers zu generieren. Beachten Sie, dass eine SACL Protokolleinträge nur auf dem Domänencontroller generiert, der Zugriffsversuch aufgetreten ist, nicht auf jedem Domänencontroller, der ein Replikat des Objekts enthält.  
  
 Festlegen oder Abrufen der SACL in Sicherheitsdeskriptor des Objekts, muss die SE_SECURITY_NAME-Berechtigung im Zugriffstoken des anfordernden Threads aktiviert sein. Die Administratorengruppe ist diese Berechtigung standardmäßig gewährt, und er kann anderen Benutzern oder Gruppen gewährt werden. Die Berechtigung erteilt ist nicht erforderlich ist: vor der durch die Berechtigung definierte Vorgang durchgeführt werden kann, muss die Berechtigung im Sicherheitszugriffstoken aktiviert werden, um wirksam wird. Das Modell kann Berechtigungen nur für bestimmte Systemvorgänge aktiviert und dann deaktiviert, wenn sie nicht mehr benötigt werden. Finden Sie unter [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) und [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547) Beispiele SE_SECURITY_NAME aktivieren.  
  
 Die Klasse bereitgestellten Methoden zum Hinzufügen, entfernen, erstellen und löschen ACEs aus der **SACL** Objekt. Siehe auch [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) und [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547).  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="addauditace"></a>CSacl::AddAuditAce  
 Fügt einen Audit-Access-Control-Eintrag (ACE) die `CSacl` Objekt.  
  
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
 Gibt die Subnetzmaske der Zugriffsrechte, die überwacht werden für den angegebenen `CSid` Objekt.  
  
 `bSuccess`  
 Gibt an, ob zugelassene Zugriffsversuche überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 *bFailure*  
 Gibt an, ob verweigerte Zugriffsversuche überwacht werden. Legen Sie dieses Flag auf "true", aktivieren Sie die Überwachung; Legen Sie sie andernfalls auf "false".  
  
 `AceFlags`  
 Ein Satz von Bitflags, die Vererbung von ACE steuern.  
  
 `pObjectType`  
 Der Objekttyp.  
  
 `pInheritedObjectType`  
 Dem vererbten Objekttyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn ACE hinzugefügt wird die `CSacl` Objekt **false** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CSacl` Objekt enthält Access-Zugriffssteuerungseinträge (ACEs), die die Arten von Zugriffsversuchen angeben, die Audit-Datensätze in das Sicherheitsereignisprotokoll zu generieren. Diese Methode fügt diese einen ACE, der `CSacl` Objekt. Die zweite Form der `AddAuditAce` ist nur auf Windows 2000 und höher.  
  
 Finden Sie unter [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) eine Beschreibung der verschiedenen Flags, die festgelegt werden können, in der `AceFlags` Parameter.  
  
##  <a name="csacl"></a>CSacl::CSacl  
 Der Konstruktor.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Eine vorhandene **ACL** Struktur (Access Control List).  
  
### <a name="remarks"></a>Hinweise  
 Die `CSacl` -Objekt kann optional mit einer vorhandenen erstellt werden **ACL** Struktur. Stellen Sie sicher, dass dieser Parameter eine System Access Control List (SACL) und keiner Liste von Zugriffssteuerungsliste (DACL) ist. Debug-Builds, wenn eine DACL angegeben wird, erfolgt eine Assertion. In Releasebuilds werden alle Einträge aus einem DACL ignoriert.  
  
##  <a name="dtor"></a>CSacl:: ~ CSacl  
 Der Destruktor.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle Ressourcen, die vom Objekt, einschließlich der Access-Control-Einträge (ACEs) erworben frei.  
  
##  <a name="getacecount"></a>CSacl::GetAceCount  
 Gibt die Anzahl der Access Control-Einträge (ACEs) in der `CSacl` Objekt.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der ACEs, die Bestandteil der `CSacl` Objekt.  
  
##  <a name="operator_eq"></a>CSacl::operator =  
 Zuweisungsoperator.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die **ACL** (Access Control List) auf das vorhandene Objekt zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CSacl` Objekt. Sicherstellen, dass die **ACL** Parameter ist tatsächlich eine System Access Control List (SACL) und keiner Liste von Zugriffssteuerungsliste (DACL). Erfolgt eine Assertion Debugbuilds und Releasebuilds die **ACL** -Parameter wird ignoriert.  
  
##  <a name="removeace"></a>CSacl::RemoveAce  
 Entfernt einen bestimmten ZUGRIFFSSTEUERUNGSEINTRAG (Access Control Entry) aus der **CSacl** Objekt.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index für den ACE-Eintrag zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CSacl::RemoveAllAces  
 Entfernt alle der Access Control-Einträge (ACEs), die Bestandteil der `CSacl` Objekt.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle **ACE** -Struktur (falls vorhanden) in den `CSacl` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CAcl-Klasse](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

