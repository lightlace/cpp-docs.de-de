---
title: CAnimationController-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
dev_langs:
- C++
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ec93c2d39206bbc0c3076835f55e624d3eef715
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="canimationcontroller-class"></a>CAnimationController-Klasse
Implementiert den Animationscontroller, der eine zentrale Schnittstelle zum Erstellen und Verwalten von Animationen bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Erstellt einen Animationscontroller an.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Der Destruktor. Wird aufgerufen, wenn Animation Controller-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationController:: AddAnimationObject](#addanimationobject)|Eine Gruppe, die den Animationscontroller gehört hinzugefügt ein Animationsobjekt.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Fügt einen Keyframe Gruppe hinzu.|  
|[CAnimationController:: AnimateGroup](#animategroup)|Bereitet eine Gruppe Animation ausgeführt, und plant diesen optional.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Überladen. Wird aufgerufen, durch das Framework zum Bereinigen der Gruppe ", wenn die Animation geplant wurde.|  
|[Aufrufen](#createkeyframe)|Überladen. Erstellt einen Keyframe, der vom Übergang abhängig ist, und fügt ihn der angegebenen Gruppe hinzu.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Legt fest oder gibt einen Handler, der beim Statuswechsel der Animations-Managers aufgerufen.|  
|[CAnimationController:: EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Legt fest oder gibt einen Handler für Ereignisse zu abfrageantwortzeiten und Handler für die zeitliche Steuerung von Updates frei.|  
|[CAnimationController:: EnablePriorityComparisonHandler aktivieren](#enableprioritycomparisonhandler)|Legt fest oder gibt die Priorität Vergleich Handler aufrufen, um festzustellen, ob ein geplante Storyboard abgebrochen, hat ergeben, abgeschnitten oder komprimiert werden kann.|  
|[CAnimationController:: EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Legt fest oder gibt einen Handler für Storyboard-Status und Update-Ereignisse.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Überladen. Sucht nach einer Animationsgruppe durch das Storyboard.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Sucht nach Animationsobjekts, das eine angegebene Animationsvariable enthält.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Gibt einen Keyframe, der Anfang des Storyboards identifiziert.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Bietet Zugriff auf gekapselte IUIAnimationManager-Objekt.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Bietet Zugriff auf gekapselte IUIAnimationTimer-Objekt.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Ein Zeiger auf IUIAnimationTransitionFactory-Schnittstelle oder NULL, wenn Fehler bei der Erstellung der Übergangsbibliothek.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Bietet Zugriff auf gekapselte IUIAnimationTransitionLibrary-Objekt.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|Erfahren Sie, ob mindestens eine Gruppe Animation wiedergegeben wird.|  
|[CAnimationController::IsValid](#isvalid)|Erfahren Sie, ob Animationscontroller gültig ist.|  
|[CAnimationController:: OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Vom Framework aufgerufen, wenn der Ganzzahlwert Animationsvariablen geändert hat.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Vom Framework als Antwort auf StatusChanged-Ereignis von der Animations-Managers aufgerufen.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Vom Framework aufgerufen, nachdem eine Animationsupdate abgeschlossen ist.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Vom Framework aufgerufen, bevor ein Animationsupdate wird gestartet.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Vom Framework aufgerufen, wenn für eine minimale wünschenswert Framerate die Rendering-Framerate für eine Animation unterschritten.|  
|[CAnimationController:: OnAnimationValueChanged](#onanimationvaluechanged)|Vom Framework aufgerufen, wenn der Wert der Animationsvariablen geändert hat.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Vom Framework aufgerufen, rechten, bevor die Animation geplant wird.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Vom Framework aufgerufen, wenn das Storyboardstatus geändert hat.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Vom Framework aufgerufen, wenn ein Storyboard aktualisiert wurde.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Entfernt alle Animationsgruppen aus Animationscontroller.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Entfernt eine Animation Verwaltungsgruppe mit der angegebenen ID aus Animationscontroller.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Entfernen Sie ein Animationsobjekt aus Animationscontroller.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Entfernt Übergänge von Animationsobjekten, die der angegebenen Gruppe gehören.|  
|[CAnimationController:: ScheduleGroup auf](#schedulegroup)|Plant eine Animation.|  
|[CAnimationController:: SetRelatedWnd](#setrelatedwnd)|Legt eine Beziehung zwischen Animationscontroller und ein Fenster.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Leitet die Animations-Manager zum Aktualisieren der Werte aller Variablen der Animation.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Überladen. Ein Hilfsprogramm, das der Gruppe "bereinigt.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Vom Framework aufgerufen, wenn eine Animation für die angegebene Gruppe gerade geplant wurde.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Keyframe, der Anfang des Storyboards darstellt.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Gibt an, ob ein Animationscontroller gültig ist. Dieser Member ist auf "false" festgelegt, wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Eine Liste von Animationsgruppen, die zu diesem Animationscontroller gehören.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Speichert einen Zeiger auf Animations-Manager-COM-Objekt.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Speichert einen Zeiger auf Animation Timer COM-Objekt.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Ein Zeiger auf eine verwandte CWnd-Objekt, das automatisch neu gezeichnet werden kann, wenn der Status eines Animations-Managers geändert wurde oder Post-Update-Ereignis ist aufgetreten. NULL kann sein.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Speichert einen Zeiger auf Transition Factory-COM-Objekt.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Speichert einen Zeiger auf Übergang Bibliothek COM-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationController-Klasse ist die wichtigste Klasse, die Animationen verwaltet. Sie können eine oder mehrere Instanzen eines Animationscontroller in einer Anwendung erstellen und optional können Sie eine Instanz von Animationscontroller mit einem CWnd-Objekt, das mit CAnimationController:: SetRelatedWnd verbinden. Diese Verbindung ist erforderlich, WM_PAINT um Nachrichten zu senden, das zugehörige Fenster automatisch beim Status der Animation-Managers geändert wurde oder Animation Timer aktualisiert wurde. Wenn Sie diese Beziehung nicht aktivieren, müssen Sie ein Fenster neu gezeichnet werden, die eine Animation manuell anzeigt. Zu diesem Zweck können Sie CAnimationController eine Klasse ableiten und OnAnimationManagerStatusChanged und/oder OnAnimationTimerPostUpdate überschreiben und eine oder mehrere Windows bei Bedarf für ungültig zu erklären.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>  CAnimationController:: ~ CAnimationController  
 Der Destruktor. Wird aufgerufen, wenn Animation Controller-Objekt zerstört wird.  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>  CAnimationController:: AddAnimationObject  
 Eine Gruppe, die den Animationscontroller gehört hinzugefügt ein Animationsobjekt.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pObject`  
 Ein Zeiger auf ein Animationsobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den vorhandenen oder neuen Animationsgruppe, in denen pObject hinzugefügt wurde, wenn die Funktion erfolgreich ausgeführt wird; NULL, wenn pObject bereits zu einer Gruppe hinzugefügt wurde, die zu einem anderen Animationscontroller gehört.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Animationscontroller einer Animationsobjekt hinzuzufügen. Ein Objekt wird zu einer Gruppe gemäß des Objekts GroupID hinzugefügt werden (Siehe CAnimationBaseObject:: SetID). Der Animationscontroller, wird eine neue Gruppe erstellen, ist dies das erste Objekt, das der angegebenen GroupID hinzugefügt wird. Ein Animationsobjekt kann nur einem Animationscontroller hinzugefügt werden. Wenn Sie ein Objekt zu einem anderen Controller hinzufügen möchten, rufen Sie zuerst RemoveAnimationObject. Wenn Sie SetID mit einer neuen GroupID für ein Objekt, die bereits zu einer Gruppe hinzugefügt wurde aufrufen, wird das Objekt aus der alten Gruppe entfernt und hinzugefügt werden in eine andere Gruppe mit der angegebenen ID.  
  
##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup  
 Fügt einen Keyframe Gruppe hinzu.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `pKeyframe`  
 Ein Zeiger auf einen Keyframe.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Funktion erfolgreich ausgeführt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie diese Methode aufrufen, verwenden stattdessen aufrufen das erstellt und eine Gruppe automatisch erstellten Keyframe hinzugefügt.  
  
##  <a name="animategroup"></a>  CAnimationController:: AnimateGroup  
 Bereitet eine Gruppe Animation ausgeführt, und plant diesen optional.  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die GroupID an.  
  
 `bScheduleNow`  
 Gibt an, ob die Animation sofort ausgeführt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn die Animation wurde erfolgreich geplant und ausgeführt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt den eigentlichen Storyboard erstellen, Hinzufügen von Animationsvariablen, Übergängen angewendet werden und Keyframes festlegen. Es ist möglich, verzögern, Planung, wenn Sie bScheduleNow auf "false" festgelegt. In diesem Fall wird die angegebene Gruppe ein Storyboard enthalten, die für die Animation eingerichtet wurde. An diesem Punkt können Sie Ereignisse für die Storyboard und Animation Variablen einrichten. Wenn müssen Sie tatsächlich den Aufruf der Animation CAnimationController:: ScheduleGroup auf ausführen.  
  
##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController  
 Erstellt einen Animationscontroller an.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup  
 Wird aufgerufen, durch das Framework zum Bereinigen der Gruppe ", wenn die Animation geplant wurde.  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die GroupID an.  
  
 `pGroup`  
 Ein Zeiger auf die Animationsgruppe zum Bereinigen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt alle Übergänge und Keyframes aus der angegebenen Gruppe, da sie nicht relevant sind, nachdem eine Animation geplant wurde.  
  
##  <a name="createkeyframe"></a>  Aufrufen  
 Erstellt einen Keyframe, der vom Übergang abhängig ist, und fügt ihn der angegebenen Gruppe hinzu.  
  
```  
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseTransition* pTransition);

 
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die ID der Gruppe an, für die der Keyframe erstellt wird.  
  
 `pTransition`  
 Ein Zeiger auf den Übergang. Der Keyframe wird nach diesem Übergang in das Storyboard eingefügt.  
  
 `pKeyframe`  
 Ein Zeiger auf das Basiskeyframe für diesen Keyframe.  
  
 `offset`  
 Offset in Sekunden gegenüber dem vom „pKeyframe“ angegebenen Basiskeyframe.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Keyframe, wenn die Funktion erfolgreich ausgeführt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den zurückgegebenen Zeiger speichern und weitere Keyframes auf dem neu erstellten Keyframe basieren lassen (siehe dazu die zweite Überladung). Es ist möglich, Übergänge an Keyframes zu beginnen – siehe dazu „CBaseTransition::SetKeyframes“. In dieser Weise erstellte Keyframes müssen nicht gelöscht werden, da sie von Animationsgruppen automatisch gelöscht werden. Gehen Sie beim Erstellen von Keyframes auf der Basis anderer Keyframes und Übergänge umsichtig vor, und vermeiden Sie Zirkelbezüge.  
  
##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent  
 Legt fest oder gibt einen Handler, der beim Statuswechsel der Animations-Managers aufgerufen.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob festgelegt oder einen Handler aufgehoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn der Handler festgelegt oder freigegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Ereignishandler (aktiviert) festgelegt ist ruft Windows-Animationen OnAnimationManagerStatusChanged aus, wenn Animations-Managers beobachtet den Statuswechsel.  
  
##  <a name="enableanimationtimereventhandler"></a>  CAnimationController:: EnableAnimationTimerEventHandler  
 Legt fest oder gibt einen Handler für Ereignisse zu abfrageantwortzeiten und Handler für die zeitliche Steuerung von Updates frei.  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob festgelegt oder die Handler aufgehoben werden soll.  
  
 `idleBehavior`  
 Gibt die leerlaufverhalten für Timer-updatehandler an.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Handler festgelegt oder freigegeben wurden. "False", wenn diese Methode wird ein zweites Mal aufgerufen, ohne die Handler zuvor freizugeben, oder wenn ein anderer Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wann werden die Handler (aktiviert) Windows Animation API-Aufrufe OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate OnRenderingTooSlow Methoden festgelegt. In diesem Fall müssen Sie eine Animationszeitgeber Animations-API von Windows Update Storyboards zu aktivieren. Andernfalls müssen Sie CAnimationController::UpdateAnimationManager aufrufen, um die Animation weiterleiten Manager zum Aktualisieren der Werte aller Variablen der Animation.  
  
##  <a name="enableprioritycomparisonhandler"></a>  CAnimationController:: EnablePriorityComparisonHandler aktivieren  
 Legt fest oder gibt die Priorität Vergleich Handler aufrufen, um festzustellen, ob ein geplante Storyboard abgebrochen, hat ergeben, abgeschnitten oder komprimiert werden kann.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Parameter  
 `dwHandlerType`  
 Eine Kombination von UI_ANIMATION_PHT_-flags (siehe "Hinweise"), der angibt, welche Handler festgelegt oder aufgehoben.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn der Handler festgelegt oder freigegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Ereignishandler (aktiviert) festgelegt ist, ruft Windows-Animationen die folgenden virtuellen Methoden je nach dwHandlerType auf: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. DwHandler kann es sich um eine Kombination der folgenden Flags: UI_ANIMATION_PHT_NONE - Version alle Handler UI_ANIMATION_PHT_CANCEL - legen Sie "Abbrechen" Vergleich Handler UI_ANIMATION_PHT_CONCLUDE - set Conclude Vergleich Handler UI_ANIMATION_PHT_COMPRESS - festlegen Komprimieren Vergleich Handler UI_ANIMATION_PHT_TRIM - legen Sie die Trim-Vergleich Ereignishandler UI_ANIMATION_PHT_CANCEL_REMOVE - entfernen Sie "Abbrechen" Vergleich Handler UI_ANIMATION_PHT_CONCLUDE_REMOVE - entfernungshandlers Conclude Vergleich UI_ANIMATION_PHT_COMPRESS_ REMOVE - entfernungshandlers komprimieren Vergleich UI_ANIMATION_PHT_TRIM_REMOVE - Remove Trim Vergleich handler  
  
##  <a name="enablestoryboardeventhandler"></a>  CAnimationController:: EnableStoryboardEventHandler  
 Legt fest oder gibt einen Handler für Storyboard-Status und Update-Ereignisse.  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `bEnable`  
 Gibt an, ob festgelegt oder einen Handler aufgehoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Handler festgelegt oder freigegeben wurde. "False", wenn die angegebene Animationsgruppe sich jetzt befindet oder Animation für die angegebene Gruppe nicht gestartet wurde wurde und seine interne Storyboard NULL ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Ereignishandler festgelegt ist aufruft (aktiviert) Windows Animation API OnStoryboardStatusChanges und OnStoryboardUpdated virtuelle Methoden. Ein Handler muss festgelegt werden, nachdem CAnimationController:: Animate für die Animationsgruppe der angegebenen aufgerufen wurde, weil damit gekapseltes IUIAnimationStoryboard-Objekt erstellt.  
  
##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup  
 Sucht nach einer Animationsgruppe durch seine Gruppen-ID.  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt eine GroupID an.  
  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Animationsgruppe oder NULL, wenn die Gruppe mit der angegebenen ID nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Animationsgruppe zur Laufzeit gefunden werden. Eine Gruppe erstellt und der internen Liste von Animationsgruppen hinzugefügt, wenn eine erste Animationsobjekt mit einer bestimmten GroupID Animationscontroller hinzugefügt wird.  
  
##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject  
 Sucht nach Animationsobjekts, das eine angegebene Animationsvariable enthält.  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `pVariable`  
 Ein Zeiger auf Animationsvariablen.  
  
 `ppObject`  
 Die Ausgabe. Enthält einen Zeiger auf Animationsobjekts oder NULL.  
  
 `ppGroup`  
 Die Ausgabe. Enthält einen Zeiger auf die Animationsgruppe, die die Animationsobjekt, oder NULL enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Objekt gefunden wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Von Ereignishandler aufgerufen, wenn es erforderlich ist, um eine Animationsobjekt aus der eingehenden Animationsvariablen gefunden werden.  
  
##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart  
 Keyframe, der Anfang des Storyboards darstellt.  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart  
 Gibt einen Keyframe, der Anfang des Storyboards identifiziert.  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Basiskeyframe, der den Anfang des Storyboards identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Keyframe alle andere Keyframes und Übergänge Zeitpunkt des Beginns als Grundlage für ein Storyboard beim Starten.  
  
##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager  
 Bietet Zugriff auf gekapselte IUIAnimationManager-Objekt.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf IUIAnimationManager-Schnittstelle oder NULL, wenn Fehler bei der Erstellung der Animations-Managers.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt, gibt diese Methode NULL zurück, und anschließend alle nachfolgenden Methodenaufrufe CAnimationController::IsValid gibt "false". Sie müssen möglicherweise IUIAnimationManager zugreifen, um die Schnittstellenmethoden zu abzurufen, die nicht von Animationscontroller umschlossen werden.  
  
##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer  
 Bietet Zugriff auf gekapselte IUIAnimationTimer-Objekt.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf IUIAnimationTimer-Schnittstelle oder NULL, wenn Fehler bei der Erstellung des Animationszeitgebers für.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt, gibt diese Methode NULL zurück, und anschließend alle nachfolgenden Methodenaufrufe CAnimationController::IsValid gibt "false".  
  
##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory  
 Ein Zeiger auf IUIAnimationTransitionFactory-Schnittstelle oder NULL, wenn Fehler bei der Erstellung der Übergangsbibliothek.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf IUIAnimationTransitionFactory oder NULL, wenn Fehler bei der Erstellung des Übergangsfactory.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt, gibt diese Methode NULL zurück, und anschließend alle nachfolgenden Methodenaufrufe CAnimationController::IsValid gibt "false".  
  
##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary  
 Bietet Zugriff auf gekapselte IUIAnimationTransitionLibrary-Objekt.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf IUIAnimationTransitionLibrary-Schnittstelle oder NULL, wenn Fehler bei der Erstellung der Übergangsbibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt, gibt diese Methode NULL zurück, und anschließend alle nachfolgenden Methodenaufrufe CAnimationController::IsValid gibt "false".  
  
##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress  
 Erfahren Sie, ob mindestens eine Gruppe Animation wiedergegeben wird.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn es eine Animation für diesen Animationscontroller ausgeführt. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Status eines Animations-Manager überprüft, und gibt "true" zurück, wenn der Status UI_ANIMATION_MANAGER_BUSY.  
  
##  <a name="isvalid"></a>  CAnimationController::IsValid  
 Erfahren Sie, ob Animationscontroller gültig ist.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Animationscontroller gültig ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt "false" nur, wenn Windows Animation API nicht unterstützt wird, auf das aktuelle Betriebssystem und Erstellung von der Animations-Managers ist fehlgeschlagen, da es nicht registriert ist. Sie müssen GetUIAnimationManager mindestens einmal nach der Initialisierung von COM-Bibliotheken, die dazu führen, dass bei der Einstellung dieses Flags aufrufen.  
  
##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid  
 Gibt an, ob ein Animationscontroller gültig ist. Dieser Member ist auf "false" festgelegt, wenn das aktuelle Betriebssystem Windows Animation API nicht unterstützt.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups  
 Eine Liste von Animationsgruppen, die zu diesem Animationscontroller gehören.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager  
 Speichert einen Zeiger auf Animations-Manager-COM-Objekt.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer  
 Speichert einen Zeiger auf Animation Timer COM-Objekt.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd  
 Ein Zeiger auf eine verwandte CWnd-Objekt, das automatisch neu gezeichnet werden kann, wenn der Status eines Animations-Managers geändert wurde oder Post-Update-Ereignis ist aufgetreten. NULL kann sein.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory  
 Speichert einen Zeiger auf Transition Factory-COM-Objekt.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary  
 Speichert einen Zeiger auf Übergang Bibliothek COM-Objekt.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule  
 Vom Framework aufgerufen, wenn eine Animation für die angegebene Gruppe gerade geplant wurde.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Animation-Verwaltungsgruppe, die geplant wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung Keyframes aus der angegebenen Gruppe entfernt und Übergang von Animationsvariablen, die der angegebenen Gruppe gehören. Kann in einer abgeleiteten Klasse zusätzliche Aktionen nach Animationszeitplan überschrieben werden.  
  
##  <a name="onanimationintegervaluechanged"></a>  CAnimationController:: OnAnimationIntegerValueChanged  
 Vom Framework aufgerufen, wenn der Ganzzahlwert Animationsvariablen geändert hat.  
  
```  
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    INT32 newValue,  
    INT32 prevValue);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Animationsgruppe, die eine Animationsobjekt, dessen Wert enthält, hat sich geändert.  
  
 `pObject`  
 Ein Zeiger auf eine Animationsobjekt, das eine Animationsvariable enthält, deren Wert geändert wurde.  
  
 `variable`  
 Ein Zeiger auf eine Animationsvariable.  
  
 `newValue`  
 Gibt die neuen Wert.  
  
 `prevValue`  
 Gibt die vorherige Wert an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie mit EnableIntegerValueChangedEvent aufgerufen, die für eine bestimmte Animationsvariable oder Animationsobjekts Animation Variable Ereignisse aktiviert. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged  
 Vom Framework als Antwort auf StatusChanged-Ereignis von der Animations-Managers aufgerufen.  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parameter  
 `newStatus`  
 Neuer Status für die Animation-Manager.  
  
 `previousStatus`  
 Status des vorherigen Animation-Manager.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Animation-Manager-Ereignisse mit EnableAnimationManagerEvent aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Die standardmäßige Implementierung aktualisiert eine zugehörige Fenster aus, wenn er mit SetRelatedWnd festgelegt wurde.  
  
##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate  
 Vom Framework aufgerufen, nachdem eine Animationsupdate abgeschlossen ist.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Timer-Ereignishandler mit EnableAnimationTimerEventHandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate  
 Vom Framework aufgerufen, bevor ein Animationsupdate wird gestartet.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Timer-Ereignishandler mit EnableAnimationTimerEventHandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow  
 Vom Framework aufgerufen, wenn für eine minimale wünschenswert Framerate die Rendering-Framerate für eine Animation unterschritten.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Parameter  
 `fps`  
 Die aktuelle Framerate in Frames pro Sekunde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Timer-Ereignishandler mit EnableAnimationTimerEventHandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Die minimale wünschenswert Framerate wird durch SetFrameRateThreshold angegeben.  
  
##  <a name="onanimationvaluechanged"></a>  CAnimationController:: OnAnimationValueChanged  
 Vom Framework aufgerufen, wenn der Wert der Animationsvariablen geändert hat.  
  
```  
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    DOUBLE newValue,  
    DOUBLE prevValue);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Animationsgruppe, die eine Animationsobjekt, dessen Wert enthält, hat sich geändert.  
  
 `pObject`  
 Ein Zeiger auf eine Animationsobjekt, das eine Animationsvariable enthält, deren Wert geändert wurde.  
  
 `variable`  
 Ein Zeiger auf eine Animationsvariable.  
  
 `newValue`  
 Gibt die neuen Wert.  
  
 `prevValue`  
 Gibt die vorherige Wert an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie mit EnableValueChangedEvent aufgerufen, die für eine bestimmte Animationsvariable oder Animationsobjekts Animation Variable Ereignisse aktiviert. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart  
 Vom Framework aufgerufen, rechten, bevor die Animation geplant wird.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Animationsgruppe, deren Animation wird gestartet.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf wird zum zugehörigen CWnd weitergeleitet und kann überschrieben werden, in einer abgeleiteten Klasse zusätzlichen Aktionen ausführen, bevor die Animation für die angegebene Gruppe gestartet wird.  
  
##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel  
 Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroupScheduled`  
 Die Gruppe, die das aktuell geplante Storyboard besitzt.  
  
 `pGroupNew`  
 Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.  
  
 `priorityEffect`  
 Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_CANCEL angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur Konfliktverwaltung lesen Windows Animation API-Dokumentation (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress  
 Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroupScheduled`  
 Die Gruppe, die das aktuell geplante Storyboard besitzt.  
  
 `pGroupNew`  
 Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.  
  
 `priorityEffect`  
 Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_TRIM angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur Konfliktverwaltung lesen Windows Animation API-Dokumentation (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude  
 Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroupScheduled`  
 Die Gruppe, die das aktuell geplante Storyboard besitzt.  
  
 `pGroupNew`  
 Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.  
  
 `priorityEffect`  
 Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_CONCLUDE angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur Konfliktverwaltung lesen Windows Animation API-Dokumentation (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim  
 Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroupScheduled`  
 Die Gruppe, die das aktuell geplante Storyboard besitzt.  
  
 `pGroupNew`  
 Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.  
  
 `priorityEffect`  
 Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_TRIM angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur Konfliktverwaltung lesen Windows Animation API-Dokumentation (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged  
 Vom Framework aufgerufen, wenn das Storyboardstatus geändert hat.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Animationsgruppe, die das Storyboard, dessen Status besitzt geändert hat.  
  
 `newStatus`  
 Gibt den neuen Status an.  
  
 `previousStatus`  
 Gibt den vorherigen Status.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie mit CAnimationController:: EnableStoryboardEventHandler Storyboardereignisse aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated  
 Vom Framework aufgerufen, wenn ein Storyboard aktualisiert wurde.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Ein Zeiger auf eine Gruppe, die das Storyboard besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie mit CAnimationController:: EnableStoryboardEventHandler Storyboardereignisse aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.  
  
##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups  
 Entfernt alle Animationsgruppen aus Animationscontroller.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle Gruppen werden gelöscht, ihr Zeiger, wenn auf der Anwendungsebene gespeichert muss ungültig gemacht werden. Wenn CAnimationGroup:: M_bautodestroyanimationobjects für eine Gruppe gelöscht wird "true" ist, werden alle Animationsobjekte, die zu dieser Gruppe gehören gelöscht. Andernfalls werden ihre Verweise auf übergeordnete Animationscontroller auf NULL festgelegt werden, und sie zu einem anderen Controller hinzugefügt werden können.  
  
##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup  
 Entfernt eine Animation Verwaltungsgruppe mit der angegebenen ID aus Animationscontroller.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die Animation Gruppen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Animationsgruppe aus der internen Liste von Gruppen und gelöscht werden, daher, wenn Sie einen Zeiger auf diese Animationsgruppe gespeichert, er muss ungültig gemacht. Wenn CAnimationGroup:: M_bautodestroyanimationobjects "true" ist, werden alle Animationsobjekte, die zu dieser Gruppe gehören gelöscht. Andernfalls werden ihre Verweise auf übergeordnete Animationscontroller auf NULL festgelegt werden, und sie zu einem anderen Controller hinzugefügt werden können.  
  
##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject  
 Entfernen Sie ein Animationsobjekt aus Animationscontroller.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `pObject`  
 Ein Zeiger auf ein Animationsobjekt.  
  
 `bNoDelete`  
 Wenn dieser Parameter auf "true" ist werden das Objekt nicht beim Entfernen gelöscht.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt ein Animationsobjekt aus Animationscontroller und Animationsgruppe. Rufen Sie diese Funktion, wenn ein bestimmtes Objekt nicht mehr animiert werden soll, oder wenn Sie das Objekt in einen anderen Animationscontroller verschieben müssen. In den letzten muss die Groß-/Kleinschreibung bNoDelete "true" sein.  
  
##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions  
 Entfernt Übergänge von Animationsobjekten, die der angegebenen Gruppe gehören.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Die Gruppe durchläuft seine Animationsobjekte und ruft ClearTransitions(FALSE) für jedes Animationsobjekt. Diese Methode wird vom Framework aufgerufen, nachdem die Animation geplant wurde.  
  
##  <a name="schedulegroup"></a>  CAnimationController:: ScheduleGroup auf  
 Plant eine Animation.  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die Animation Gruppen-ID zu planen.  
  
 `time`  
 Gibt die Zeit zu planen.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn die Animation erfolgreich geplant wurde. "False", wenn Storyboard nicht erstellt wurde, oder anderer Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen AnimateGroup mit Parameter bScheduleNow legen Sie auf "false" Vorherige ScheduleGroup aufrufen. Sie können angeben, auf die gewünschte Animation Zeit aus IUIAnimationTimer:: GetTime erhaltene abgerufen. Wenn der Parameter "Time" auf 0,0 festgelegt ist, wird die Animation für die aktuelle Uhrzeit geplant.  
  
##  <a name="setrelatedwnd"></a>  CAnimationController:: SetRelatedWnd  
 Legt eine Beziehung zwischen Animationscontroller und ein Fenster.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf Fensterobjekt festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein verknüpftes CWnd-Objekt festgelegt ist, der Animationscontroller kann es automatisch aktualisieren (WM_PAINT-Meldung gesendet) Wenn der Status eines Animations-Managers wurde geändert oder Zeitgeberereignis Post-Update aufgetreten.  
  
##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager  
 Leitet die Animations-Manager zum Aktualisieren der Werte aller Variablen der Animation.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Hinweise  
 Durch das Aufrufen dieser Methode die Animations-Managers auf die aktuelle Zeit verschiebt, Status des Storyboards nach Bedarf ändern und aktualisieren alle Animationsvariablen in entsprechende interpoliert Werte. Intern ruft diese Methode timeNow und IUIAnimationManager. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um dieses Verhalten anzupassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
