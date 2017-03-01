---
title: "Globale Funktionen für Sicherheit | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 368da76305910a0948eb386990a4bcdb84e61396
ms.lasthandoff: 02/24/2017

---
# <a name="security-global-functions"></a>Globale Funktionen für Sicherheit
Diese Funktionen bieten Unterstützung für Sicherheits-ID und ACL-Objekte ändern.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlGetDacl](#atlgetdacl)|Mit dieser Funktion werden die Informationen zur freigegebenen Zugriffssteuerungsliste (DACL, Discretionary Access Control List) eines bestimmten Objekts abgerufen.|  
|[AtlSetDacl](#atlsetdacl)|Mit dieser Funktion werden die Informationen zur freigegebenen Zugriffssteuerungsliste (DACL, Discretionary Access Control List) eines bestimmten Objekts festgelegt.|  
|[AtlGetGroupSid](#atlgetgroupsid)|Mit dieser Funktion wird die Gruppensicherheits-ID (SID) eines Objekts abgerufen.|  
|[AtlSetGroupSid](#atlsetgroupsid)|Mit dieser Funktion wird die Gruppensicherheits-ID (SID) eines Objekts festgelegt.|  
|[AtlGetOwnerSid](#atlgetownersid)|Mit dieser Funktion wird die Sicherheits-ID (SID) des Besitzers eines Objekts abgerufen.|  
|[AtlSetOwnerSid](#atlsetownersid)|Mit dieser Funktion wird die Sicherheits-ID (SID) des Besitzers eines Objekts festgelegt.|  
|[AtlGetSacl](#atlgetsacl)|Mit dieser Funktion werden die Informationen zur Systemzugriffssteuerungsliste (SACL, System Access Control List) eines bestimmten Objekts abgerufen.|  
|[AtlSetSacl](#atlsetsacl)|Mit dieser Funktion werden die Informationen zur Systemzugriffssteuerungsliste (SACL, System Access Control List) eines bestimmten Objekts festgelegt.|  
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Mit dieser Funktion wird die Sicherheitsbeschreibung eines angegebenen Objekts abgerufen.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlgetdacla--atlgetdacl"></a><a name="atlgetdacl"></a>AtlGetDacl  
 Mit dieser Funktion werden die Informationen zur freigegebenen Zugriffssteuerungsliste (DACL, Discretionary Access Control List) eines bestimmten Objekts abgerufen.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt für die Sicherheitsinformationen abzurufen.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `pDacl`  
 Zeiger auf eine DACL-Objekt, das die abgerufenen Sicherheitsinformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler angezeigt, wenn entweder `hObject` oder `pDacl` ist ungültig. *.*  

f

##  <a name="a-nameatlsetdacla--atlsetdacl"></a><a name="atlsetdacl"></a>AtlSetDacl  
 Mit dieser Funktion werden die Informationen zur freigegebenen Zugriffssteuerungsliste (DACL, Discretionary Access Control List) eines bestimmten Objekts festgelegt.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt festgelegt werden soll.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `rDacl`  
 Die DACL, die die neue Sicherheitsinformationen enthält.  
  
 `dwInheritanceFlowControl`  
 Steuerung der Vererbung. Dieser Wert kann 0 (Standard), PROTECTED_DACL_SECURITY_INFORMATION oder UNPROTECTED_DACL_SECURITY_INFORMATION sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn `hObject` ungültig ist, oder wenn `dwInheritanceFlowControl` ist keiner der drei zulässigen Werte.  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlgetgroupsida--atlgetgroupsid"></a><a name="atlgetgroupsid"></a>AtlGetGroupSid  
 Mit dieser Funktion wird die Gruppensicherheits-ID (SID) eines Objekts abgerufen.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt, um Sicherheitsinformationen abzurufen.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `pSid`  
 Zeiger auf ein `CSid` Objekt, das die neue Sicherheitsinformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlsetgroupsida--atlsetgroupsid"></a><a name="atlsetgroupsid"></a>AtlSetGroupSid  
 Mit dieser Funktion wird die Gruppensicherheits-ID (SID) eines Objekts festgelegt.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt festgelegt werden soll.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `rSid`  
 Die `CSid` -Objekt, das die neue Sicherheitsinformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlgetownersida--atlgetownersid"></a><a name="atlgetownersid"></a>AtlGetOwnerSid  
 Mit dieser Funktion wird die Sicherheits-ID (SID) des Besitzers eines Objekts abgerufen.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt, um Sicherheitsinformationen abzurufen.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `pSid`  
 Zeiger auf ein `CSid` Objekt, das die neue Sicherheitsinformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlsetownersida--atlsetownersid"></a><a name="atlsetownersid"></a>AtlSetOwnerSid  
 Mit dieser Funktion wird die Sicherheits-ID (SID) des Besitzers eines Objekts festgelegt.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt festgelegt werden soll.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `rSid`  
 Die `CSid` -Objekt, das die neue Sicherheitsinformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlgetsacla--atlgetsacl"></a><a name="atlgetsacl"></a>AtlGetSacl  
 Mit dieser Funktion werden die Informationen zur Systemzugriffssteuerungsliste (SACL, System Access Control List) eines bestimmten Objekts abgerufen.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt, um die Sicherheitsinformationen abzurufen.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 `pSacl`  
 Zeiger auf eine SACL-Objekt, das die abgerufenen Sicherheitsinformationen enthält.  
  
 `bRequestNeededPrivileges`  
 Bei "true", versucht die Funktion die SE_SECURITY_NAME-Berechtigung aktivieren und auf den Abschluss des Vorgangs wiederhergestellt werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `AtlGetSacl` oft auf viele verschiedene Objekte aufgerufen werden effizienter, die SE_SECURITY_NAME-Berechtigung aktivieren, bevor die Funktion aufgerufen, mit `bRequestNeededPrivileges` auf False festgelegt.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlsetsacla--atlsetsacl"></a><a name="atlsetsacl"></a>AtlSetSacl  
 Mit dieser Funktion werden die Informationen zur Systemzugriffssteuerungsliste (SACL, System Access Control List) eines bestimmten Objekts festgelegt.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Handle für das Objekt festgelegt werden soll.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die `hObject` Parameter.  
  
 *rSacl*  
 Die SACL, das die neue Sicherheitsinformationen enthält.  
  
 `dwInheritanceFlowControl`  
 Steuerung der Vererbung. Dieser Wert kann 0 (Standard), PROTECTED_SACL_SECURITY_INFORMATION oder UNPROTECTED_SACL_SECURITY_INFORMATION sein.  
  
 `bRequestNeededPrivileges`  
 Bei "true", versucht die Funktion die SE_SECURITY_NAME-Berechtigung aktivieren und auf den Abschluss des Vorgangs wiederhergestellt werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn `hObject` ungültig ist, oder wenn `dwInheritanceFlowControl` ist keiner der drei zulässigen Werte.  
  
 Wenn `AtlSetSacl` oft auf viele verschiedene Objekte aufgerufen werden effizienter, die SE_SECURITY_NAME-Berechtigung aktivieren, bevor die Funktion aufgerufen, mit `bRequestNeededPrivileges` auf False festgelegt.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="a-nameatlgetsecuritydescriptora--atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor  
 Mit dieser Funktion wird die Sicherheitsbeschreibung eines angegebenen Objekts abgerufen.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
 bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pszObjectName*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Objekts aus der abzurufenden Sicherheitsinformationen angibt.  
  
 `ObjectType`  
 Gibt einen Wert aus der [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) -Enumeration, die den Typ des-Objekts gibt an, die *PszObjectName* Parameter.  
  
 *pSecurityDescriptor*  
 Das Objekt, das den angeforderten Sicherheitsdeskriptor empfängt.  
  
 *requestedInfo*  
 Eine Reihe von [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Bitflags, die den Typ der abzurufenden Sicherheitsinformationen angeben. Dieser Parameter kann eine Kombination der folgenden Werte sein.  
  
 `bRequestNeededPrivileges`  
 Bei "true", versucht die Funktion die SE_SECURITY_NAME-Berechtigung aktivieren und auf den Abschluss des Vorgangs wiederhergestellt werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `AtlGetSecurityDescriptor` oft auf viele verschiedene Objekte aufgerufen werden effizienter, die SE_SECURITY_NAME-Berechtigung aktivieren, bevor die Funktion aufgerufen, mit `bRequestNeededPrivileges` auf False festgelegt.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 
   
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

