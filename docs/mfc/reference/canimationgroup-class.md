---
title: CAnimationGroup-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationGroup class
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a59d8a86fde68510d48e4a3398b6590b2215cbea
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="canimationgroup-class"></a>CAnimationGroup-Klasse
Implementiert eine Animation-Verwaltungsgruppe, die ein Animationsstoryboard, Animationsobjekte und Übergänge zum Definieren einer Animation kombiniert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Erstellt eine Animationsgruppe.|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|Der Destruktor. Wird aufgerufen, wenn eine Animationsgruppe zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|Animiert eine Gruppe.|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Übernimmt Übergänge für Animationsobjekte.|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Sucht nach einer Animationsobjekt, das die angegebene Animationsvariable enthält.|  
|[CAnimationGroup::GetGroupID](#getgroupid)|Gibt GroupID zurück.|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Entfernt und zerstört optional alle Keyframes, die eine Animationsgruppe angehören.|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.|  
|[CAnimationGroup::Schedule](#schedule)|Plant eine Animation zum angegebenen Zeitpunkt.|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Weist alle Animationsobjekte, die um automatisch gruppieren gehören, Übergänge zu zerstören.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Eine Hilfsklasse, die einem Storyboard Keyframes hinzufügt.|  
|[CAnimationGroup::AddTransitions](#addtransitions)|Eine Hilfsklasse, die einem Storyboard Übergänge hinzufügt.|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|Eine Hilfsklasse, die COM-Übergangsobjekte erstellt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieser Member TRUE ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie Übergänge manuell entfernen.|  
|[CAnimationGroup:: M_bautodestroyanimationobjects](#m_bautodestroyanimationobjects)|Gibt an, wie Animationsobjekte zerstört. Wenn dieser Parameter auf "true" ist, Animationsobjekte automatisch verloren, wenn die Gruppe zerstört wird. Andernfalls müssen Animationsobjekte manuell zerstört werden. Der Standardwert ist FALSE. Legen Sie diesen Wert auf TRUE nur, wenn alle Animationsobjekte, die zur Gruppe gehören, dynamisch mit dem new-Operator zugewiesen werden.|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert TRUE ist, werden alle Keyframes entfernt und zerstört. Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist TRUE.|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Enthält eine Liste von Animationsobjekten.|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Enthält eine Liste von Keyframes.|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Zeigt auf Animationsstoryboard. This-Zeiger ist erst nach Aufruf auf Animate gültig.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Ein eindeutiger Bezeichner der Animationsgruppe.|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den Animationscontroller, der dieser Gruppe angehört.|  
  
## <a name="remarks"></a>Hinweise  
 Animationsgruppen werden automatisch von Animationscontroller (CAnimationController) erstellt, wenn Sie Animationsobjekte AddAnimationObject hinzufügen. Eine Animationsgruppe wird durch GroupID, identifiziert, die in der Regel als Parameter angenommen, um Animationsgruppen bearbeiten. Die GroupID stammt aus dem ersten Animationsobjekt, das eine neue Animationsgruppe hinzugefügt wird. Eine encapsulated Animationsstoryboard wird erstellt, nachdem Sie CAnimationController:: AnimateGroup aufrufen und über die öffentlichen Member M_pStoryboard zugegriffen werden können.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAnimationGroup`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationgroup"></a>CAnimationGroup:: ~ CAnimationGroup  
 Der Destruktor. Wird aufgerufen, wenn eine Animationsgruppe zerstört wird.  
  
```  
~CAnimationGroup();
```  
  
##  <a name="addkeyframes"></a>CAnimationGroup::AddKeyframes  
 Eine Hilfsklasse, die einem Storyboard Keyframes hinzufügt.  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Drehbuch-COM-Objekt.  
  
 `bAddDeep`  
 Gibt an, ob diese Methode in der Storyboardkeyframes hinzufügen sollten, die von anderen Keyframes abhängen.  
  
##  <a name="addtransitions"></a>CAnimationGroup::AddTransitions  
 Eine Hilfsklasse, die einem Storyboard Übergänge hinzufügt.  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Drehbuch-COM-Objekt.  
  
 `bDependOnKeyframes`  
  
##  <a name="animate"></a>CAnimationGroup::Animate  
 Animiert eine Gruppe.  
  
```  
BOOL Animate(
    IUIAnimationManager* pManager,  
    IUIAnimationTimer* pTimer,  
    BOOL bScheduleNow);
```  
  
### <a name="parameters"></a>Parameter  
 `pManager`  
 `pTimer`  
 `bScheduleNow`  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Methode erfolgreich ist. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt ein internes Storyboard, erstellt und wendet Übergänge und plant eine Animation, wenn bScheduleNow TRUE ist. Wenn bScheduleNow FALSE ist, müssen Sie Zeitplan zum Starten der Animation zum angegebenen Zeitpunkt aufrufen.  
  
##  <a name="applytransitions"></a>CAnimationGroup::ApplyTransitions  
 Übernimmt Übergänge für Animationsobjekte.  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode bestätigt im Debugmodus, wenn Storyboard nicht erstellt wurde. Zuerst erstellt alle Übergänge und dann "static" Keyframes (Keyframes, die von Offsets abhängen) hinzugefügt, fügt Übergänge, die nicht von Keyframes abhängen, fügt Keyframes von Übergängen und anderen Keyframes und fügt zuletzt Übergänge, die von Keyframes abhängen.  
  
##  <a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup  
 Erstellt eine Animationsgruppe.  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentController`  
 Ein Zeiger auf den Animationscontroller, der eine Gruppe erstellt.  
  
 `nGroupID`  
 Gibt eine GroupID an.  
  
##  <a name="createtransitions"></a>CAnimationGroup::CreateTransitions  
 Eine Hilfsklasse, die COM-Übergangsobjekte erstellt.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE wird die Methode erfolgreich ist, andernfalls FALSE.  
  
##  <a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject  
 Sucht nach einer Animationsobjekt, das die angegebene Animationsvariable enthält.  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parameter  
 `pVariable`  
 Ein Zeiger auf eine Animationsvariable.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf Animationsobjekt oder NULL, wenn Animationsobjekt nicht gefunden wird.  
  
##  <a name="getgroupid"></a>CAnimationGroup::GetGroupID  
 Gibt GroupID zurück.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Gruppenbezeichner.  
  
##  <a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions  
 Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieser Member TRUE ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie Übergänge manuell entfernen.  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="m_bautodestroyanimationobjects"></a>CAnimationGroup:: M_bautodestroyanimationobjects  
 Gibt an, wie Animationsobjekte zerstört. Wenn dieser Parameter auf "true" ist, Animationsobjekte automatisch verloren, wenn die Gruppe zerstört wird. Andernfalls müssen Animationsobjekte manuell zerstört werden. Der Standardwert ist FALSE. Legen Sie diesen Wert auf TRUE nur, wenn alle Animationsobjekte, die zur Gruppe gehören, dynamisch mit dem new-Operator zugewiesen werden.  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes  
 Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert TRUE ist, werden alle Keyframes entfernt und zerstört. Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist TRUE.  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects  
 Enthält eine Liste von Animationsobjekten.  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames  
 Enthält eine Liste von Keyframes.  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID  
 Ein eindeutiger Bezeichner der Animationsgruppe.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController  
 Ein Zeiger auf den Animationscontroller, der dieser Gruppe angehört.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard  
 Zeigt auf Animationsstoryboard. This-Zeiger ist erst nach Aufruf auf Animate gültig.  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes  
 Entfernt und zerstört optional alle Keyframes, die eine Animationsgruppe angehören.  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der M_bAutodestroyKeyframes-Member TRUE ist, und klicken Sie dann Keyframes entfernt und zerstört, andernfalls werden Keyframes nur aus der internen Liste der Keyframes entfernt.  
  
##  <a name="removetransitions"></a>CAnimationGroup::RemoveTransitions  
 Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das M_bAutoclearTransitions-Flag auf TRUE festgelegt ist, wird diese Methode durchläuft alle Animationsobjekte, die zur Gruppe gehören, und ruft CAnimationObject::ClearTransitions(false) auf.  
  
##  <a name="schedule"></a>CAnimationGroup::Schedule  
 Plant eine Animation zum angegebenen Zeitpunkt.  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>Parameter  
 `pTimer`  
 Ein Zeiger auf die Animationszeitgeber.  
  
 `time`  
 Gibt die Animation zu planen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Methode erfolgreich ist. "False" hat, wenn die Methode fehlschlägt oder wenn Animate nicht mit bScheduleNow auf FALSE festgelegt aufgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um eine Animation zum angegebenen Zeitpunkt zu planen. Sie müssen Animate mit auf "false" festlegen, erster bScheduleNow aufrufen.  
  
##  <a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyTransitions  
 Weist alle Animationsobjekte, die um automatisch gruppieren gehören, Übergänge zu zerstören.  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoDestroy`  
 Gibt an, wie Übergänge zerstört.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf "false" nur dann, wenn Sie Übergänge auf dem Stapel zugeordnet werden. Der Standardwert ist TRUE, es ist daher dringend empfohlen, Übergangsobjekte mit dem Operator new zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

