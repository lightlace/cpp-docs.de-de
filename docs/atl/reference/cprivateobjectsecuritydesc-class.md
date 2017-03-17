---
title: Klasse CPrivateObjectSecurityDesc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 154a4229f8963d3081e6e0518354d17968ee0e20
ms.lasthandoff: 02/24/2017

---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc-Klasse
Diese Klasse stellt ein privates Objekt Security Descriptor-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Der Konstruktor.|  
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Rufen Sie diese Methode, um einen Sicherheitsdeskriptor und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, die automatische Übertragung von vererbbare Access-Zugriffssteuerungseinträge (ACEs) unterstützt.|  
|[CPrivateObjectSecurityDesc::Create](#create)|Rufen Sie diese Methode zum Zuordnen und initialisieren eine selbstbezogenen Sicherheitsdeskriptor für das private Objekt durch Aufrufen von Ressourcen-Manager erstellt.|  
|[CPrivateObjectSecurityDesc::Get](#get)|Rufen Sie diese Methode zum Abrufen von Informationen aus dem Sicherheitsdeskriptor für ein privates Objekt.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Rufen Sie diese Methode, um ein privates Objekt Sicherheitsdeskriptor zu ändern.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Von dieser Klasse abgeleitete [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), stellt Methoden zum Erstellen und Verwalten des Sicherheitsdeskriptors für ein privates Objekt bereit.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 Rufen Sie diese Methode, um einen Sicherheitsdeskriptor und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, die automatische Übertragung von vererbbare Access-Zugriffssteuerungseinträge (ACEs) unterstützt.  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das den übergeordneten Container des Objekts auf. Wenn keine übergeordnete Container vorhanden ist, ist dieser Parameter NULL an.  
  
 `ObjectType`  
 Zeiger auf eine **GUID** Struktur, die den Typ des Objekts, die mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie `ObjectType` auf NULL, wenn das Objekt nicht über eine GUID verfügt.  
  
 `bIsDirectoryObject`  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert True gibt an, dass das neue Objekt ein Container ist. Der Wert False gibt an, dass das neue Objekt nicht um ein Container ist.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) Struktur, die zum Zuordnen der einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode versucht zu bestimmen, ob die ACEs in der Zugriffssteuerungsliste (DACL) auflisten und System Access Control List (SACL) des aktuellen Sicherheitsdeskriptors wurden aus der übergeordneten Sicherheitsdeskriptor geerbt. Ruft die [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) Funktion.  
  
##  <a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 Der Konstruktor.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das `CPrivateObjectSecurityDesc` Objekt.  
  
##  <a name="dtor"></a>CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 Der Destruktor.  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei und löscht das private Objekt Sicherheitsdeskriptor.  
  
##  <a name="create"></a>CPrivateObjectSecurityDesc::Create  
 Rufen Sie diese Methode zum Zuordnen und initialisieren eine selbstbezogenen Sicherheitsdeskriptor für das private Objekt durch Aufrufen von Ressourcen-Manager erstellt.  
  
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
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das das übergeordnete Verzeichnis, in dem ein neues Objekt erstellt wird. Auf NULL festgelegt, wenn keine übergeordnete Verzeichnis vorhanden ist.  
  
 `pCreator`  
 Zeiger auf den Sicherheitsdeskriptor der Ersteller des Objekts bereitgestellt. Wenn der Ersteller des Objekts Sicherheitsinformationen für das neue Objekt nicht explizit übergeben wird, wird dieser Parameter auf NULL festgelegt.  
  
 `bIsDirectoryObject`  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert True gibt an, dass das neue Objekt ein Container ist. Der Wert False gibt an, dass das neue Objekt nicht um ein Container ist.  
  
 `Token`  
 Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekt für den Prozess auf, deren Namen das Objekt erstellt wird.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) Struktur, die zum Zuordnen der einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.  
  
 `ObjectType`  
 Zeiger auf eine **GUID** Struktur, die den Typ des Objekts, die mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie `ObjectType` auf NULL, wenn das Objekt nicht über eine GUID verfügt.  
  
 *bIsContainerObject*  
 Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert True gibt an, dass das neue Objekt ein Container ist. Der Wert False gibt an, dass das neue Objekt nicht um ein Container ist.  
  
 `AutoInheritFlags`  
 Ein Satz von Bitflags, die steuern, wie Access-Zugriffssteuerungseinträge (ACEs) von geerbt werden `pParent`. Finden Sie unter [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) oder [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581).  
  
 Die zweite Methode, die ermöglicht, das den Objekttyp GUID des neuen Objekts angibt, oder steuern, wie ACEs geerbt werden, ist nur auf Systemen mit Windows 2000 und höher.  
  
> [!NOTE]
>  Ein selbstbezogenen Sicherheitsdeskriptor ist eine Sicherheitsbeschreibung, die alle die Sicherheitsinformationen in einem zusammenhängenden Speicherblock gespeichert.  
  
##  <a name="get"></a>CPrivateObjectSecurityDesc::Get  
 Rufen Sie diese Methode zum Abrufen von Informationen aus dem Sicherheitsdeskriptor für ein privates Objekt.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Ein Satz von Bitflags, die angeben, welcher Teil der Sicherheitsdeskriptor abgerufen werden soll. Dieser Wert kann eine Kombination der [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Bitflags.  
  
 `pResult`  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) -Objekt, das eine Kopie der angeforderten Informationen aus der angegebenen Sicherheitsbeschreibung erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die Sicherheits-ID ist eine Struktur und die zugeordneten Daten, die die Sicherheit für ein sicherungsfähiges Objekt enthält.  
  
##  <a name="operator_eq"></a>CPrivateObjectSecurityDesc::operator =  
 Zuweisungsoperator.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CPrivateObjectSecurityDesc` -Objekt, mit dem aktuellen Objekt zugewiesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CPrivateObjectSecurityDesc` Objekt.  
  
##  <a name="set"></a>CPrivateObjectSecurityDesc::Set  
 Rufen Sie diese Methode, um ein privates Objekt Sicherheitsdeskriptor zu ändern.  
  
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
 Ein Satz von Bitflags, die angeben, die Teile des Sicherheitsdeskriptors festlegen. Dieser Wert kann eine Kombination der [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Bitflags.  
  
 *Änderung*  
 Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt. Die Teile dieser Sicherheitsdeskriptor erkennbar die `si` -Parameters auf den Sicherheitsdeskriptor des Objekts angewendet werden.  
  
 `GenericMapping`  
 Zeiger auf eine [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) Struktur, die zum Zuordnen der einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.  
  
 `Token`  
 Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekt für den Prozess auf, deren Namen das Objekt erstellt wird.  
  
 `AutoInheritFlags`  
 Ein Satz von Bitflags, die steuern, wie Access-Zugriffssteuerungseinträge (ACEs) von geerbt werden `pParent`. Finden Sie unter [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Methode, die ermöglicht, das den Objekttyp GUID des Objekts angibt, oder steuern, wie ACEs geerbt werden, ist nur auf Systemen mit Windows 2000 und höher.  
  
## <a name="see-also"></a>Siehe auch  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc-Klasse](../../atl/reference/csecuritydesc-class.md)

