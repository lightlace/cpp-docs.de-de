---
title: CAnimationGroup-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11b78cf273fd510b8ce224004c759dcc5bbe3bec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355632"
---
# <a name="canimationgroup-class"></a>CAnimationGroup-Klasse
Implementiert eine Animation-Verwaltungsgruppe, die eine Animationsstoryboard Animationsobjekte und Übergänge zum Definieren einer Animation kombiniert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Erstellt eine Animationsgruppe.|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|Der Destruktor. Wird aufgerufen, wenn eine Animationsgruppe zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|Erstellt eine Animation eine Gruppe.|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Animationsobjekte gilt Übergänge.|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Sucht nach einer Animationsobjekt, das die angegebenen Animationsvariablen enthält.|  
|[CAnimationGroup::GetGroupID](#getgroupid)|Gibt GroupID zurück.|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Entfernt und zerstört optional alle Keyframes, die eine Animationsgruppe angehören.|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.|  
|[CAnimationGroup::Schedule](#schedule)|Plant eine Animation zum angegebenen Zeitpunkt.|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Leitet alle Animationsobjekte, die um automatisch gruppieren gehören, Übergänge zu zerstören.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Ein Hilfsprogramm, das ein Storyboard Keyframes hinzufügt.|  
|[CAnimationGroup::AddTransitions](#addtransitions)|Ein Hilfsprogramm, das ein Storyboard Übergänge hinzufügt.|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|Ein Hilfsprogramm, das COM-Objekte erstellt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieses Elements auf "true" ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie Übergänge manuell entfernen.|  
|[CAnimationGroup:: M_bautodestroyanimationobjects](#m_bautodestroyanimationobjects)|Gibt an, wie Animationsobjekte zu zerstören. Wenn dieser Parameter auf "true" ist, werden Animationsobjekte automatisch zerstört werden, wenn die Gruppe zerstört wird. Andernfalls müssen Animationsobjekte manuell zerstört werden. Der Standardwert ist "false". Legen Sie diesen Wert auf "true" nur, wenn alle Animationsobjekte, die zur Gruppe gehören, dynamisch mit new-Operator zugewiesen werden.|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert "true" ist, werden alle Keyframes entfernt und zerstört; Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist "true".|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Enthält eine Liste von Animationsobjekten.|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Enthält eine Liste von Keyframes.|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Verweist auf die Animationsstoryboard. This-Zeiger ist erst nach Aufruf animieren gültig.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Ein eindeutiger Bezeichner der Gruppe "Animation".|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den Animationscontroller, der diese Gruppe angehört.|  
  
## <a name="remarks"></a>Hinweise  
 Animationsgruppen werden automatisch von Animationscontroller (CAnimationController) erstellt, wenn Sie Animationsobjekte AddAnimationObject hinzufügen. Eine Animationsgruppe wird durch GroupID, identifiziert, die in der Regel als Parameter angenommen, um Animationsgruppen zu manipulieren. Das GroupID stammt aus dem ersten Animationsobjekt, das eine neue Animationsgruppe hinzugefügt wird. Ein Animationsstoryboard gekapselten wird erstellt, nachdem Sie CAnimationController:: AnimateGroup aufrufen und über öffentliche Member M_pStoryboard zugegriffen werden können.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAnimationGroup`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationgroup"></a>  CAnimationGroup:: ~ CAnimationGroup  
 Der Destruktor. Wird aufgerufen, wenn eine Animationsgruppe zerstört wird.  
  
```  
~CAnimationGroup();
```  
  
##  <a name="addkeyframes"></a>  CAnimationGroup::AddKeyframes  
 Ein Hilfsprogramm, das ein Storyboard Keyframes hinzufügt.  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard COM-Objekt.  
  
 `bAddDeep`  
 Gibt an, ob diese Methode zur Storyboardkeyframes hinzugefügt werden soll, die von anderen Keyframes abhängen.  
  
##  <a name="addtransitions"></a>  CAnimationGroup::AddTransitions  
 Ein Hilfsprogramm, das ein Storyboard Übergänge hinzufügt.  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard COM-Objekt.  
  
 `bDependOnKeyframes`  
  
##  <a name="animate"></a>  CAnimationGroup::Animate  
 Erstellt eine Animation eine Gruppe.  
  
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
 True, wenn die Methode erfolgreich ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt ein internes Storyboard, erstellt und wendet Übergänge und plant eine Animation, wenn bScheduleNow "true" ist. Wenn bScheduleNow "false" ist, müssen Sie Zeitplan zum Starten der Animation zum angegebenen Zeitpunkt aufrufen.  
  
##  <a name="applytransitions"></a>  CAnimationGroup::ApplyTransitions  
 Animationsobjekte gilt Übergänge.  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ASSERTIONEN im Debugmodus, wenn Storyboard nicht erstellt wurde. Erstellt alle Übergänge zuerst, dann fügt "static" Keyframes (Keyframes, die von Offsets abhängen), fügt Übergänge, die nicht von Keyframes abhängen, fügt Keyframes je nach Übergänge und weitere Keyframes und zumindest fügt Übergänge, die von Keyframes abhängen .  
  
##  <a name="canimationgroup"></a>  CAnimationGroup::CAnimationGroup  
 Erstellt eine Animationsgruppe.  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentController`  
 Ein Zeiger auf den Animationscontroller, der eine Gruppe erstellt.  
  
 `nGroupID`  
 Gibt die GroupID an.  
  
##  <a name="createtransitions"></a>  CAnimationGroup::CreateTransitions  
 Ein Hilfsprogramm, das COM-Objekte erstellt.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 "True" wird die Methode erfolgreich ist, andernfalls "false".  
  
##  <a name="findanimationobject"></a>  CAnimationGroup::FindAnimationObject  
 Sucht nach einer Animationsobjekt, das die angegebenen Animationsvariablen enthält.  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parameter  
 `pVariable`  
 Ein Zeiger auf Animationsvariablen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf Animationsobjekts oder NULL, wenn die Animationsobjekt nicht gefunden wird.  
  
##  <a name="getgroupid"></a>  CAnimationGroup::GetGroupID  
 Gibt GroupID zurück.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner.  
  
##  <a name="m_bautocleartransitions"></a>  CAnimationGroup::m_bAutoclearTransitions  
 Gibt an, wie Übergänge von Animationsobjekte zu löschen, die zur Gruppe gehören. Wenn dieses Elements auf "true" ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde. Andernfalls müssen Sie Übergänge manuell entfernen.  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="m_bautodestroyanimationobjects"></a>  CAnimationGroup:: M_bautodestroyanimationobjects  
 Gibt an, wie Animationsobjekte zu zerstören. Wenn dieser Parameter auf "true" ist, werden Animationsobjekte automatisch zerstört werden, wenn die Gruppe zerstört wird. Andernfalls müssen Animationsobjekte manuell zerstört werden. Der Standardwert ist "false". Legen Sie diesen Wert auf "true" nur, wenn alle Animationsobjekte, die zur Gruppe gehören, dynamisch mit new-Operator zugewiesen werden.  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="m_bautodestroykeyframes"></a>  CAnimationGroup::m_bAutodestroyKeyframes  
 Gibt an, wie Keyframes zu zerstören. Wenn dieser Wert "true" ist, werden alle Keyframes entfernt und zerstört; Andernfalls werden sie nur aus der Liste entfernt. Der Standardwert ist "true".  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="m_lstanimationobjects"></a>  CAnimationGroup::m_lstAnimationObjects  
 Enthält eine Liste von Animationsobjekten.  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="m_lstkeyframes"></a>  CAnimationGroup::m_lstKeyFrames  
 Enthält eine Liste von Keyframes.  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="m_ngroupid"></a>  CAnimationGroup::m_nGroupID  
 Ein eindeutiger Bezeichner der Gruppe "Animation".  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_pparentcontroller"></a>  CAnimationGroup::m_pParentController  
 Ein Zeiger auf den Animationscontroller, der diese Gruppe angehört.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="m_pstoryboard"></a>  CAnimationGroup::m_pStoryboard  
 Verweist auf die Animationsstoryboard. This-Zeiger ist erst nach Aufruf animieren gültig.  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="removekeyframes"></a>  CAnimationGroup::RemoveKeyframes  
 Entfernt und zerstört optional alle Keyframes, die eine Animationsgruppe angehören.  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der M_bAutodestroyKeyframes-Member "true" ist, dann Keyframes entfernt und zerstört wird, andernfalls Keyframes nur aus der internen Liste der Keyframes entfernt werden.  
  
##  <a name="removetransitions"></a>  CAnimationGroup::RemoveTransitions  
 Entfernt Übergänge von Animationsobjekten, die eine Animationsgruppe angehören.  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das M_bAutoclearTransitions-Flag auf "true" festgelegt ist, wird diese Methode durchläuft alle Animationsobjekte, die zur Gruppe gehören, und ruft CAnimationObject::ClearTransitions(false) auf.  
  
##  <a name="schedule"></a>  CAnimationGroup::Schedule  
 Plant eine Animation zum angegebenen Zeitpunkt.  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>Parameter  
 `pTimer`  
 Ein Zeiger auf die Animation Timer.  
  
 `time`  
 Gibt die Zeit die Animation planen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Methode erfolgreich ist. "False" hat, wenn die Methode fehlschlägt oder wenn animieren nicht mit bScheduleNow festlegen auf "false" aufgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um eine Animation zum angegebenen Zeitpunkt zu planen. Rufen Sie animieren mit bScheduleNow zuerst auf "false" festgelegt.  
  
##  <a name="setautodestroytransitions"></a>  CAnimationGroup::SetAutodestroyTransitions  
 Leitet alle Animationsobjekte, die um automatisch gruppieren gehören, Übergänge zu zerstören.  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoDestroy`  
 Gibt an, wie Übergänge zu zerstören.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf "false" nur dann, wenn Sie Übergänge auf dem Stapel zuordnen. Der Standardwert ist "true", es wurde daher dringend empfohlen, den Übergangsobjekte, die mit dem Operator new zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
