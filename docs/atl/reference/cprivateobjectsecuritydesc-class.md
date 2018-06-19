---
title: CPrivateObjectSecurityDesc Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
dev_langs:
- C++
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f47adc413a0e6d3d9c820b824dec95f55924867
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365203"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc-Klasse
Diese Klasse stellt ein privates Objekt sicherheitsbeschreibungsobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Der Konstruktor.|  
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Rufen Sie diese Methode, um eine Sicherheitsbeschreibung und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, automatische Weitergabe von vererbbare Zugriff-Zugriffssteuerungseinträge (ACEs) unterstützt.|  
|[CPrivateObjectSecurityDesc::Create](#create)|Rufen Sie diese Methode zum Zuweisen und initialisieren eine selbstbezogenen Sicherheitsbeschreibung für das private Objekt, das von der aufrufenden Ressourcen-Manager erstellt.|  
|[CPrivateObjectSecurityDesc::Get](#get)|Rufen Sie diese Methode zum Abrufen von Informationen aus dem Sicherheitsdeskriptor ein privates Objekt.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung für ein privates Objekt zu ändern.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse abgeleitet [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), stellt Methoden zum Erstellen und Verwalten von Sicherheitsbeschreibung des ein privates Objekt bereit.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 Rufen Sie diese Methode, um eine Sicherheitsbeschreibung und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, automatische Weitergabe von vererbbare Zugriff-Zugriffssteuerungseinträge (ACEs) unterstützt.  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt verweisen auf den übergeordneten Container des Objekts. Wenn keine übergeordnete Container vorhanden ist, ist dieser Parameter NULL an.  
  
 `ObjectType`  
 Zeiger auf eine **GUID** Struktur, die den Typ des Objekts mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie `ObjectType` auf NULL, wenn das Objekt keine GUID.  
  
 `bIsDirectoryObject`  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt um einen Container handelt. Der Wert "false" gibt an, dass das neue Objekt nicht um einen Container ist.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) -Struktur, die Zuordnung von jedem der generischen Rechte auf bestimmte Berechtigungen für das Objekt angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht, um festzustellen, ob die ACEs in der Zugriffssteuerungsliste (DACL) auflisten und System Access Control List (SACL) der aktuellen Sicherheitsbeschreibung wurden aus dem Sicherheitsdeskriptor übergeordneten geerbt. Ruft die [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) Funktion.  
  
##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 Der Konstruktor.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CPrivateObjectSecurityDesc` Objekt.  
  
##  <a name="dtor"></a>  CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 Der Destruktor.  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei und löscht die Sicherheitsbeschreibung des Objekts, auf die private.  
  
##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create  
 Rufen Sie diese Methode zum Zuweisen und initialisieren eine selbstbezogenen Sicherheitsbeschreibung für das private Objekt, das von der aufrufenden Ressourcen-Manager erstellt.  
  
```
bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt verweisen auf das übergeordnete Verzeichnis, in dem ein neues Objekt erstellt wird. Auf NULL festgelegt, wenn kein übergeordnetes Verzeichnis vorhanden ist.  
  
 `pCreator`  
 Ein Zeiger auf eine Sicherheitsbeschreibung, die durch den Ersteller des Objekts bereitgestellt. Wenn der Ersteller des Objekts nicht explizit Sicherheitsinformationen für das neue Objekt übergeben, wird dieser Parameter auf NULL festgelegt.  
  
 `bIsDirectoryObject`  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt um einen Container handelt. Der Wert "false" gibt an, dass das neue Objekt nicht um einen Container ist.  
  
 `Token`  
 Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt für den Clientprozess, in dessen Auftrag das Objekt erstellt wird.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) -Struktur, die Zuordnung von jedem der generischen Rechte auf bestimmte Berechtigungen für das Objekt angibt.  
  
 `ObjectType`  
 Zeiger auf eine **GUID** Struktur, die den Typ des Objekts mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie `ObjectType` auf NULL, wenn das Objekt keine GUID.  
  
 *bIsContainerObject*  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt um einen Container handelt. Der Wert "false" gibt an, dass das neue Objekt nicht um einen Container ist.  
  
 `AutoInheritFlags`  
 Ein Satz von Bitflags, die steuern, wie Access-Zugriffssteuerungseinträge (ACEs) geerbt werden `pParent`. Finden Sie unter [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) oder [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581).  
  
 Die zweite Methode ermöglicht das Angeben der GUID des Objekttyp des neuen Objekts oder steuern, wie ACEs geerbt werden.  
  
> [!NOTE]
>  Eine selbstbezogenen Sicherheitsbeschreibung ist eine Sicherheitsbeschreibung, die alle ihre Sicherheitsinformationen in einen zusammenhängenden Block von Arbeitsspeicher speichert.  
  
##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get  
 Rufen Sie diese Methode zum Abrufen von Informationen aus dem Sicherheitsdeskriptor ein privates Objekt.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Ein Satz von Bitflags, die angeben, die Teile der Sicherheitsbeschreibung abgerufen werden soll. Dieser Wert kann eine Kombination der [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Bitflags.  
  
 `pResult`  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das eine Kopie der angeforderten Informationen aus dem angegebenen Sicherheitsdeskriptor empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die Sicherheitsbeschreibung ist eine Struktur und zugehörige Daten, die die Sicherheitsinformationen für ein sicherungsfähiges Objekt enthält.  
  
##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =  
 Zuweisungsoperator.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CPrivateObjectSecurityDesc` -Objekt, mit dem aktuellen Objekt zugewiesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CPrivateObjectSecurityDesc` Objekt.  
  
##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set  
 Rufen Sie diese Methode, um die Sicherheitsbeschreibung für ein privates Objekt zu ändern.  
  
```
bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Ein Satz von Bitflags, die angeben, die Teile der Sicherheitsbeschreibung fest. Dieser Wert kann eine Kombination der [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Bitflags.  
  
 *Änderung*  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt. Die Teile dieses Sicherheitsbeschreibung erkennbar die `si` Parameter auf die Sicherheitsbeschreibung für das Objekt übernommen werden.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) -Struktur, die Zuordnung von jedem der generischen Rechte auf bestimmte Berechtigungen für das Objekt angibt.  
  
 `Token`  
 Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt für den Clientprozess, in dessen Auftrag das Objekt erstellt wird.  
  
 `AutoInheritFlags`  
 Ein Satz von Bitflags, die steuern, wie Access-Zugriffssteuerungseinträge (ACEs) geerbt werden `pParent`. Finden Sie unter [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Methode ermöglicht, die den Objekttyp GUID des Objekts angibt, oder steuern, wie ACEs geerbt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Sicherheit, globale Funktionen](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc-Klasse](../../atl/reference/csecuritydesc-class.md)
