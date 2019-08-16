---
title: CAnimationController-Klasse
ms.date: 03/27/2019
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
ms.openlocfilehash: 9039d44d9ef36a47c11b3ecaddf232ad427727c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507648"
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
|[CAnimationController::CAnimationController](#canimationcontroller)|Erstellt einen Animations Controller.|
|[CAnimationController::~CAnimationController](#_dtorcanimationcontroller)|Der Destruktor. Wird aufgerufen, wenn das Animations Controller Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationController::AddAnimationObject](#addanimationobject)|Fügt einer Gruppe, die zum Animations Controller gehört, ein Animations Objekt hinzu.|
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Fügt der Gruppe einen Keyframe hinzu.|
|[CAnimationController::AnimateGroup](#animategroup)|Bereitet eine Gruppe auf die Ausführung von Animationen vor und plant optional die Planung.|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Überladen. Wird von Framework aufgerufen, um die Gruppe zu bereinigen, wenn die Animation geplant wurde.|
|[CAnimationController::CreateKeyframe](#createkeyframe)|Überladen. Erstellt einen Keyframe, der vom Übergang abhängig ist, und fügt ihn der angegebenen Gruppe hinzu.|
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Legt einen Handler fest, der aufgerufen werden soll, wenn der Status des Animations-Managers geändert wird.|
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Legt einen Handler für Zeit Steuerungs Ereignisse und Handler für Zeit Steuerungs Updates fest oder gibt diesen frei.|
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Legt den Prioritäts Vergleichs Handler fest, der aufgerufen werden soll, um zu bestimmen, ob ein geplantes Storyboard abgebrochen, geschlossen, gekürzt oder komprimiert werden kann.|
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Legt einen Handler für Storyboard-Status-und Update Ereignisse fest oder gibt diesen frei.|
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Überladen. Findet eine Animations Gruppe nach dem Storyboard.|
|[CAnimationController::FindAnimationObject](#findanimationobject)|Sucht das Animations Objekt, das eine angegebene Animations Variable enthält.|
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Gibt einen Keyframe zurück, der den Start des Storyboards identifiziert.|
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Bietet Zugriff auf das gekapselte iuianimationmanager-Objekt.|
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Bietet Zugriff auf das gekapselte iuianimationtimer-Objekt.|
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Ein Zeiger auf die iuianimationtransitionfactory-Schnittstelle oder NULL, wenn beim Erstellen der Übergangs Bibliothek ein Fehler aufgetreten ist.|
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Ermöglicht den Zugriff auf das gekapselte iuianimationtransitionlibrary-Objekt.|
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|Gibt an, ob mindestens eine Gruppe eine Animation abspielt.|
|[CAnimationController::IsValid](#isvalid)|Gibt an, ob der Animations Controller gültig ist.|
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Wird von Framework aufgerufen, wenn sich der ganzzahlige Wert der Animations Variablen geändert hat.|
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Wird vom Framework als Reaktion auf das Status Page-Ereignis vom Animations-Manager aufgerufen.|
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Wird von Framework aufgerufen, nachdem ein Animations Update abgeschlossen wurde.|
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Wird von Framework aufgerufen, bevor ein Animations Update beginnt.|
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Wird von Framework aufgerufen, wenn die renderingframerate für eine Animation unter eine minimale gewünschte Framerate fällt.|
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Wird von Framework aufgerufen, wenn sich der Wert der Animations Variablen geändert hat.|
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Wird von Framework aufgerufen, unmittelbar bevor die Animation geplant wird.|
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.|
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Wird von Framework aufgerufen, wenn sich der storyboardstatus geändert hat.|
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Wird von Framework aufgerufen, wenn das Storyboard aktualisiert wurde.|
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Entfernt alle Animations Gruppen aus dem Animations Controller.|
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Entfernt eine Animations Gruppe mit der angegebenen ID aus dem Animations Controller.|
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Entfernen Sie ein Animations Objekt aus dem Animations Controller.|
|[CAnimationController::RemoveTransitions](#removetransitions)|Entfernt Übergänge von Animations Objekten, die zur angegebenen Gruppe gehören.|
|[CAnimationController::ScheduleGroup](#schedulegroup)|Plant eine Animation.|
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Stellt eine Beziehung zwischen dem Animations Controller und einem Fenster her.|
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Weist den Animations-Manager an, die Werte aller Animations Variablen zu aktualisieren.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Überladen. Ein Hilfsprogramm, das die Gruppe bereinigt.|
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Wird von Framework aufgerufen, wenn eine Animation für die angegebene Gruppe soeben geplant wurde.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Ein Keyframe, der den Anfang des Storyboards darstellt.|
|[CAnimationController::m_bIsValid](#m_bisvalid)|Gibt an, ob ein Animations Controller gültig ist. Dieser Member ist auf false festgelegt, wenn das aktuelle Betriebssystem keine Windows-Animations-API unterstützt.|
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Eine Liste von Animations Gruppen, die zu diesem Animations Controller gehören.|
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Speichert einen Zeiger auf das COM-Objekt des Animations-Managers.|
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Speichert einen Zeiger auf ein COM-Objekt des Animations Timers.|
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Ein Zeiger auf ein verknüpftes CWnd-Objekt, das automatisch neu gezeichnet werden kann, wenn sich der Status des Animations-Managers geändert hat oder nach dem Update ein Ereignis aufgetreten ist. Kann NULL sein.|
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Speichert einen Zeiger auf ein COM-Objekt der Übergangs Factory.|
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Speichert einen Zeiger auf das COM-Objekt der Übergangs Bibliothek.|

## <a name="remarks"></a>Hinweise

Die canimationcontroller-Klasse ist die Schlüssel Klasse, mit der Animationen verwaltet werden. Sie können eine oder mehrere Instanzen des Animations Controllers in einer Anwendung erstellen und optional eine Instanz des Animations Controllers mithilfe von canimationcontroller:: setrelatedwnd mit einem CWnd-Objekt verbinden. Diese Verbindung ist erforderlich, um WM_PAINT-Nachrichten automatisch an das zugehörige Fenster zu senden, wenn sich der Status des Animations-Managers geändert hat oder der Animations Timer aktualisiert wurde Wenn Sie diese Beziehung nicht aktivieren, müssen Sie ein Fenster neu zeichnen, in dem eine Animation manuell angezeigt wird. Zu diesem Zweck können Sie eine Klasse von canimationcontroller ableiten und onanimationmanagerstatuschangiund/oder onanimationtimerpostupdate überschreiben und bei Bedarf ein oder mehrere Fenster für ungültig erklären.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="_dtorcanimationcontroller"></a>Canimationcontroller:: ~ canimationcontroller

Der Destruktor. Wird aufgerufen, wenn das Animations Controller Objekt zerstört wird.

```
virtual ~CAnimationController(void);
```

##  <a name="addanimationobject"></a>Canimationcontroller:: addanimationobject

Fügt einer Gruppe, die zum Animations Controller gehört, ein Animations Objekt hinzu.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>Parameter

*pObject*<br/>
Ein Zeiger auf ein Animations Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine vorhandene oder neue Animations Gruppe, in der pObject hinzugefügt wurde, wenn die Funktion erfolgreich ausgeführt wurde. NULL, wenn pObject bereits einer Gruppe hinzugefügt wurde, die zu einem anderen Animations Controller gehört.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, um dem Animations Controller ein Animations Objekt hinzuzufügen. Ein Objekt wird einer Gruppe entsprechend der groupid des Objekts hinzugefügt (siehe canimationbaseobject:: setID). Der Animations Controller erstellt eine neue Gruppe, wenn dies das erste Objekt ist, das mit der angegebenen GroupID hinzugefügt wird. Ein Animations Objekt kann nur einem Animations Controller hinzugefügt werden. Wenn Sie ein Objekt einem anderen Controller hinzufügen müssen, müssen Sie zuerst removeanimationobject abrufen. Wenn Sie für ein Objekt, das einer Gruppe bereits hinzugefügt wurde, setID mit neuer GroupID aufzurufen, wird das Objekt aus der alten Gruppe entfernt und einer anderen Gruppe mit der angegebenen ID hinzugefügt.

##  <a name="addkeyframetogroup"></a>Canimationcontroller:: addkeyframeumgroup

Fügt der Gruppe einen Keyframe hinzu.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die Gruppen-ID an.

*pKeyframe*<br/>
Ein Zeiger auf einen Keyframe.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Funktion erfolgreich ausgeführt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

In der Regel müssen Sie diese Methode nicht aufrufen, sondern stattdessen canimationcontroller:: foratekeyframe verwenden. Dadurch wird der erstellte Keyframe automatisch zu einer Gruppe hinzugefügt und zu einer Gruppe hinzugefügt.

##  <a name="animategroup"></a>Canimationcontroller:: animategroup

Bereitet eine Gruppe auf die Ausführung von Animationen vor und plant optional die Planung.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt GroupID an.

*bScheduleNow*<br/>
Gibt an, ob Animation sofort ausgeführt werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Animation erfolgreich geplant und ausgeführt wurde.

### <a name="remarks"></a>Hinweise

Diese Methode führt die eigentliche Arbeit aus, die das Storyboard erstellt, Animations Variablen hinzufügt, Übergänge anwendet und Keyframes festlegt. Die Planung kann verzögert werden, wenn bschedulenow auf false festgelegt ist. In diesem Fall enthält die angegebene Gruppe ein Storyboard, das für die Animation eingerichtet wurde. An diesem Punkt können Sie Ereignisse für die Storyboard-und Animations Variablen einrichten. Wenn Sie tatsächlich den Animations Aufruf "canimationcontroller:: ScheduleGroup" ausführen müssen.

##  <a name="canimationcontroller"></a>Canimationcontroller:: canimationcontroller

Erstellt einen Animations Controller.

```
CAnimationController(void);
```

##  <a name="cleanupgroup"></a>Canimationcontroller:: cleanupgroup

Wird von Framework aufgerufen, um die Gruppe zu bereinigen, wenn die Animation geplant wurde.

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt GroupID an.

*pGroup*<br/>
Ein Zeiger auf eine zu bereine Animations Gruppe.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt alle Übergänge und Keyframes aus der angegebenen Gruppe, da Sie nach dem Planen einer Animation nicht relevant sind.

##  <a name="createkeyframe"></a>Canimationcontroller:: foratekeyframe

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

*nGroupID*<br/>
Gibt die ID der Gruppe an, für die der Keyframe erstellt wird.

*pTransition*<br/>
Ein Zeiger auf den Übergang. Der Keyframe wird nach diesem Übergang in das Storyboard eingefügt.

*pKeyframe*<br/>
Ein Zeiger auf das Basiskeyframe für diesen Keyframe.

*offset*<br/>
Offset in Sekunden gegenüber dem vom „pKeyframe“ angegebenen Basiskeyframe.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neu erstellte Keyframe, wenn die Funktion erfolgreich ausgeführt wurde.

### <a name="remarks"></a>Hinweise

Sie können den zurückgegebenen Zeiger speichern und weitere Keyframes auf dem neu erstellten Keyframe basieren lassen (siehe dazu die zweite Überladung). Es ist möglich, Übergänge an Keyframes zu beginnen – siehe dazu „CBaseTransition::SetKeyframes“. In dieser Weise erstellte Keyframes müssen nicht gelöscht werden, da sie von Animationsgruppen automatisch gelöscht werden. Gehen Sie beim Erstellen von Keyframes auf der Basis anderer Keyframes und Übergänge umsichtig vor, und vermeiden Sie Zirkelbezüge.

##  <a name="enableanimationmanagerevent"></a>Canimationcontroller:: enableanimationmanagerevent

Legt einen Handler fest, der aufgerufen werden soll, wenn der Status des Animations-Managers geändert wird.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
Gibt an, ob ein Handler festgelegt oder freigegeben werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Handler erfolgreich festgelegt oder freigegeben wurde.

### <a name="remarks"></a>Hinweise

Wenn ein Handler festgelegt wird (aktiviert), ruft die Windows-Animation onanimationmanagerstatuschge auf, wenn der Status des Animations-Managers geändert wird.

##  <a name="enableanimationtimereventhandler"></a>Canimationcontroller:: enableanimationtimereventhandler

Legt einen Handler für Zeit Steuerungs Ereignisse und Handler für Zeit Steuerungs Updates fest oder gibt diesen frei.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
Gibt an, ob die Handler festgelegt oder freigegeben werden sollen.

*idleBehavior*<br/>
Gibt das Leerlauf Verhalten für den Timer-Update Handler an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Handler erfolgreich festgelegt oder freigegeben wurden. FALSE, wenn diese Methode ein zweites Mal aufgerufen wird, ohne die Handler zuerst zu veröffentlichen, oder wenn ein anderer Fehler auftritt.

### <a name="remarks"></a>Hinweise

Wenn die Handler festgelegt sind (aktiviert), ruft die Windows-Animations-API onanimationtimerpreupdate, onanimationtimerpostupdate, onrenderingtooslow-Methoden auf. Sie müssen Animations Timer aktivieren, um Storyboards für Windows Animation-API-Updates zuzulassen. Andernfalls müssen Sie canimationcontroller:: updateanimationmanager aufrufen, um den Animations-Manager zum Aktualisieren der Werte aller Animations Variablen zu leiten.

##  <a name="enableprioritycomparisonhandler"></a>Canimationcontroller:: enableprioritycomparisonhandler

Legt den Prioritäts Vergleichs Handler fest, der aufgerufen werden soll, um zu bestimmen, ob ein geplantes Storyboard abgebrochen, geschlossen, gekürzt oder komprimiert werden kann.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>Parameter

*dwHandlerType*<br/>
Eine Kombination aus UI_ANIMATION_PHT_-Flags (siehe Hinweise), die angibt, welche Handler festgelegt oder freigegeben werden.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Handler erfolgreich festgelegt oder freigegeben wurde.

### <a name="remarks"></a>Hinweise

Wenn ein Handler festgelegt wird (aktiviert), ruft die Windows-Animation abhängig von dwhandlertype die folgenden virtuellen Methoden auf: Onhasprioritycancel, onhaspriorityend, onhasprioritytrim, onhasprioritycompress. dwhandler kann eine Kombination der folgenden Flags sein: UI_ANIMATION_PHT_NONE-alle Handler freigeben UI_ANIMATION_PHT_CANCEL-Satz Vergleichs Handler für Abbruch festlegen UI_ANIMATION_PHT_CONCLUDE-Festlegen des Vergleichs Handler UI_ANIMATION_PHT_COMPRESS-Set komprimieren Vergleichs Handler UI_ANIMATION_PHT_TRIM-Set Vergleichs Handler kürzen UI_ANIMATION_PHT_CANCEL_REMOVE-entfernen Vergleichs Handler Abbrechen UI_ANIMATION_PHT_CONCLUDE_REMOVE-Schluss enden Vergleichs Handler entfernen UI_ANIMATION_PHT_COMPRESS_REMOVE-Remove Vergleichs Handler für komprimieren UI_ANIMATION_PHT _TRIM_REMOVE-Entfernungs Vergleichs Handler entfernen

##  <a name="enablestoryboardeventhandler"></a>Canimationcontroller:: enablestoryboarde venthandler

Legt einen Handler für Storyboard-Status-und Update Ereignisse fest oder gibt diesen frei.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die Gruppen-ID an.

*bEnable*<br/>
Gibt an, ob ein Handler festgelegt oder freigegeben werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Handler erfolgreich festgelegt oder freigegeben wurde. FALSE, wenn die angegebene Animations Gruppe nun gefunden wurde oder die Animation für die angegebene Gruppe nicht initiiert wurde und das interne Storyboard NULL ist.

### <a name="remarks"></a>Hinweise

Wenn ein Handler festgelegt ist (aktiviert), ruft die Windows-Animations-API die virtuellen Methoden onstoryboardstatuschanges und onstoryboardupdatiert auf. Ein Handler muss festgelegt werden, nachdem canimationcontroller:: Animieren für die angegebene Animations Gruppe aufgerufen wurde, da er ein gekapseltes iuianimationstoryboard-Objekt erstellt.

##  <a name="findanimationgroup"></a>Canimationcontroller:: findanimationgroup

Sucht eine Animations Gruppe anhand ihrer Gruppen-ID.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt eine GroupID an.

*pstoryboard*<br/>
Ein Zeiger auf ein Storyboard.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Animations Gruppe oder NULL, wenn die Gruppe mit der angegebenen ID nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um zur Laufzeit eine Animations Gruppe zu suchen. Eine Gruppe wird erstellt und der internen Liste der Animations Gruppen hinzugefügt, wenn dem Animations Controller ein erstes Animations Objekt mit bestimmter GroupID hinzugefügt wird.

##  <a name="findanimationobject"></a>Canimationcontroller:: findanimationobject

Sucht das Animations Objekt, das eine angegebene Animations Variable enthält.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>Parameter

*pVariable*<br/>
Ein Zeiger auf eine Animations Variable.

*ppObject*<br/>
Ausgeben. Enthält einen Zeiger auf das Animations Objekt oder NULL.

*ppGroup*<br/>
Ausgeben. Enthält einen Zeiger auf eine Animations Gruppe, die das Animations Objekt enthält, oder NULL.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Objekt gefunden wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Wird von Ereignis Handlern aufgerufen, wenn es erforderlich ist, ein Animations Objekt von der eingehenden Animations Variablen zu finden.

##  <a name="g_keyframestoryboardstart"></a>Canimationcontroller:: gkeyframestoryboardstart

Ein Keyframe, der den Anfang des Storyboards darstellt.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

##  <a name="getkeyframestoryboardstart"></a>Canimationcontroller:: getkeyframestoryboardstart

Gibt einen Keyframe zurück, der den Start des Storyboards identifiziert.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Basis-Keyframe, der den Start des Storyboards identifiziert.

### <a name="remarks"></a>Hinweise

Rufen Sie diesen Keyframe ab, um beim Start eines Storyboards alle anderen Keyframes oder Übergänge zu einem Zeitpunkt zu basieren.

##  <a name="getuianimationmanager"></a>Canimationcontroller:: getuianimationmanager

Bietet Zugriff auf das gekapselte iuianimationmanager-Objekt.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die iuianimationmanager-Schnittstelle oder NULL, wenn die Erstellung des Animations-Managers fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Wenn das aktuelle Betriebssystem die Windows-Animations-API nicht unterstützt, gibt diese Methode NULL zurück, und danach geben alle nachfolgenden Aufrufe von canimationcontroller:: IsValid den Wert false zurück. Möglicherweise müssen Sie auf iuianimationmanager zugreifen, um die Schnittstellen Methoden aufzurufen, die nicht vom Animations Controller umschließt werden.

##  <a name="getuianimationtimer"></a>Canimationcontroller:: getuianimationtimer

Bietet Zugriff auf das gekapselte iuianimationtimer-Objekt.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die iuianimationtimer-Schnittstelle oder NULL, wenn die Erstellung des Animations Timers fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Wenn das aktuelle Betriebssystem die Windows-Animations-API nicht unterstützt, gibt diese Methode NULL zurück, und danach geben alle nachfolgenden Aufrufe von canimationcontroller:: IsValid den Wert false zurück.

##  <a name="getuitransitionfactory"></a>Canimationcontroller:: getuitransitionfactory

Ein Zeiger auf die iuianimationtransitionfactory-Schnittstelle oder NULL, wenn beim Erstellen der Übergangs Bibliothek ein Fehler aufgetreten ist.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf iuianimationtransitionfactory oder NULL, wenn beim Erstellen der Übergangs Factory ein Fehler aufgetreten ist.

### <a name="remarks"></a>Hinweise

Wenn das aktuelle Betriebssystem die Windows-Animations-API nicht unterstützt, gibt diese Methode NULL zurück, und danach geben alle nachfolgenden Aufrufe von canimationcontroller:: IsValid den Wert false zurück.

##  <a name="getuitransitionlibrary"></a>Canimationcontroller:: getuitransitionlibrary

Ermöglicht den Zugriff auf das gekapselte iuianimationtransitionlibrary-Objekt.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die iuianimationtransitionlibrary-Schnittstelle oder NULL, wenn beim Erstellen der Übergangs Bibliothek ein Fehler aufgetreten ist.

### <a name="remarks"></a>Hinweise

Wenn das aktuelle Betriebssystem die Windows-Animations-API nicht unterstützt, gibt diese Methode NULL zurück, und danach geben alle nachfolgenden Aufrufe von canimationcontroller:: IsValid den Wert false zurück.

##  <a name="isanimationinprogress"></a>Canimationcontroller:: isanimationinprogress

Gibt an, ob mindestens eine Gruppe eine Animation abspielt.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn für diesen Animations Controller eine Animation ausgeführt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

Überprüft den Status des Animations-Managers und gibt true zurück, wenn der Status UI_ANIMATION_MANAGER_BUSY lautet.

##  <a name="isvalid"></a>Canimationcontroller:: IsValid

Gibt an, ob der Animations Controller gültig ist.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Animations Controller gültig ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode gibt nur dann false zurück, wenn die Windows-Animations-API vom aktuellen Betriebssystem nicht unterstützt wird und der Animations-Manager nicht erstellt werden konnte, weil Sie nicht registriert ist Sie müssen getuianimationmanager nach der Initialisierung von com-Bibliotheken mindestens einmal aufrufen, um die Einstellung dieses Flags zu verursachen.

##  <a name="m_bisvalid"></a>Canimationcontroller:: m_bIsValid

Gibt an, ob ein Animations Controller gültig ist. Dieser Member ist auf false festgelegt, wenn das aktuelle Betriebssystem keine Windows-Animations-API unterstützt.

```
BOOL m_bIsValid;
```

##  <a name="m_lstanimationgroups"></a>Canimationcontroller:: m_lstAnimationGroups

Eine Liste von Animations Gruppen, die zu diesem Animations Controller gehören.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

##  <a name="m_panimationmanager"></a>Canimationcontroller:: m_pAnimationManager

Speichert einen Zeiger auf das COM-Objekt des Animations-Managers.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

##  <a name="m_panimationtimer"></a>Canimationcontroller:: m_pAnimationTimer

Speichert einen Zeiger auf ein COM-Objekt des Animations Timers.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

##  <a name="m_prelatedwnd"></a>Canimationcontroller:: m_pRelatedWnd

Ein Zeiger auf ein verknüpftes CWnd-Objekt, das automatisch neu gezeichnet werden kann, wenn sich der Status des Animations-Managers geändert hat oder nach dem Update ein Ereignis aufgetreten ist. Kann NULL sein.

```
CWnd* m_pRelatedWnd;
```

##  <a name="m_ptransitionfactory"></a>Canimationcontroller:: m_pTransitionFactory

Speichert einen Zeiger auf ein COM-Objekt der Übergangs Factory.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

##  <a name="m_ptransitionlibrary"></a>Canimationcontroller:: m_pTransitionLibrary

Speichert einen Zeiger auf das COM-Objekt der Übergangs Bibliothek.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

##  <a name="onafterschedule"></a>Canimationcontroller:: onafterschedule

Wird von Framework aufgerufen, wenn eine Animation für die angegebene Gruppe soeben geplant wurde.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Animations Gruppe, die geplant wurde.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung entfernt Keyframes aus der angegebenen Gruppe und geht von Animations Variablen aus, die zur angegebenen Gruppe gehören. Kann in einer abgeleiteten Klasse überschrieben werden, um zusätzliche Aktionen nach dem Animations Zeitplan auszuführen.

##  <a name="onanimationintegervaluechanged"></a>Canimationcontroller:: onanimationintegervaluechanged

Wird von Framework aufgerufen, wenn sich der ganzzahlige Wert der Animations Variablen geändert hat.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Animations Gruppe, die ein Animations Objekt enthält, dessen Wert geändert wurde.

*pObject*<br/>
Ein Zeiger auf ein Animations Objekt, das eine Animations Variable enthält, deren Wert geändert wurde.

*veränder*<br/>
Ein Zeiger auf eine Animations Variable.

*newValue*<br/>
Gibt den neuen Wert an.

*prevValue*<br/>
Gibt den vorherigen Wert an.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Animations Variablen Ereignisse mit enableintegervaluechangedevent aktivieren, die für eine bestimmte Animations Variable oder ein Animations Objekt aufgerufen werden. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="onanimationmanagerstatuschanged"></a>Canimationcontroller:: onanimationmanagerstatuschangi

Wird vom Framework als Reaktion auf das Status Page-Ereignis vom Animations-Manager aufgerufen.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parameter

*newStatus*<br/>
Neuer Status des Animations-Managers.

*previousStatus*<br/>
Vorheriger Status des Animations-Managers.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Animations-Manager-Ereignisse mit enableanimationmanagerevent aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Die Standard Implementierung aktualisiert ein verwandtes Fenster, wenn es mit setrelatedwnd festgelegt wurde.

##  <a name="onanimationtimerpostupdate"></a>Canimationcontroller:: onanimationtimerpostupdate

Wird von Framework aufgerufen, nachdem ein Animations Update abgeschlossen wurde.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Timer-Ereignishandler mithilfe von enableanimationtimereventhandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="onanimationtimerpreupdate"></a>Canimationcontroller:: onanimationtimerpreupdate

Wird von Framework aufgerufen, bevor ein Animations Update beginnt.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Timer-Ereignishandler mithilfe von enableanimationtimereventhandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="onanimationtimerrenderingtooslow"></a>Canimationcontroller:: onanimationtimerrenderingto oslow

Wird von Framework aufgerufen, wenn die renderingframerate für eine Animation unter eine minimale gewünschte Framerate fällt.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>Parameter

*FPS*<br/>
Die aktuelle Framerate in Frames pro Sekunde.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Timer-Ereignishandler mithilfe von enableanimationtimereventhandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Die minimale gewünschte Framerate wird durch Aufrufen von iuianimationtimer:: setframeratethreshold angegeben.

##  <a name="onanimationvaluechanged"></a>Canimationcontroller:: onanimationvaluechanged

Wird von Framework aufgerufen, wenn sich der Wert der Animations Variablen geändert hat.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Animations Gruppe, die ein Animations Objekt enthält, dessen Wert geändert wurde.

*pObject*<br/>
Ein Zeiger auf ein Animations Objekt, das eine Animations Variable enthält, deren Wert geändert wurde.

*veränder*<br/>
Ein Zeiger auf eine Animations Variable.

*newValue*<br/>
Gibt den neuen Wert an.

*prevValue*<br/>
Gibt den vorherigen Wert an.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Animations Variablen Ereignisse mit enablevaluechangedevent aktivieren, die für eine bestimmte Animations Variable oder ein Animations Objekt aufgerufen werden. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="onbeforeanimationstart"></a>Canimationcontroller:: onbeforeanimationstart

Wird von Framework aufgerufen, unmittelbar bevor die Animation geplant wird.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Animations Gruppe, deren Animation gerade gestartet wird.

### <a name="remarks"></a>Hinweise

Dieser-Befehl wird an das zugehörige CWnd weitergeleitet und kann in einer abgeleiteten Klasse überschrieben werden, um zusätzliche Aktionen auszuführen, bevor die Animation für die angegebene Gruppe gestartet wird.

##  <a name="onhasprioritycancel"></a>Canimationcontroller:: onhasprioritycancel

Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parameter

*pGroupScheduled*<br/>
Die Gruppe, die das aktuell geplante Storyboard besitzt.

*pGroupNew*<br/>
Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.

*priorityEffect*<br/>
Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.

### <a name="return-value"></a>Rückgabewert

Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_CANCEL angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur [Konflikt Verwaltung](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)finden Sie in der Dokumentation zur Windows-Animations-API.

##  <a name="onhasprioritycompress"></a>Canimationcontroller:: onhasprioritycompress

Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parameter

*pGroupScheduled*<br/>
Die Gruppe, die das aktuell geplante Storyboard besitzt.

*pGroupNew*<br/>
Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.

*priorityEffect*<br/>
Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.

### <a name="return-value"></a>Rückgabewert

Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_TRIM angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur [Konflikt Verwaltung](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)finden Sie in der Dokumentation zur Windows-Animations-API.

##  <a name="onhaspriorityconclude"></a>Canimationcontroller:: onhaspriorityschluss

Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parameter

*pGroupScheduled*<br/>
Die Gruppe, die das aktuell geplante Storyboard besitzt.

*pGroupNew*<br/>
Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.

*priorityEffect*<br/>
Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.

### <a name="return-value"></a>Rückgabewert

Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_CONCLUDE angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur [Konflikt Verwaltung](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)finden Sie in der Dokumentation zur Windows-Animations-API.

##  <a name="onhasprioritytrim"></a>Canimationcontroller:: onhasprioritytrim

Wird vom Framework aufgerufen, um Konflikte bei der Planung zu beheben.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parameter

*pGroupScheduled*<br/>
Die Gruppe, die das aktuell geplante Storyboard besitzt.

*pGroupNew*<br/>
Die Gruppe, die das neue Storyboard besitzt, für das ein Planungskonflikt mit dem geplanten Storyboard im Besitz von pGroupScheduled besteht.

*priorityEffect*<br/>
Die möglichen Auswirkungen auf pGroupNew, wenn pGroupScheduled eine höhere Priorität hat.

### <a name="return-value"></a>Rückgabewert

Muss „true“ zurückgeben, wenn das Storyboard im Besitz von pGroupNew Priorität hat. Muss „false“ zurückgeben, wenn das Storyboard im Besitz von pGroupScheduled Priorität hat.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Prioritätsvergleichsereignisse mit CAnimationController::EnablePriorityComparisonHandler aktivieren und UI_ANIMATION_PHT_TRIM angeben. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden. Weitere Informationen zur [Konflikt Verwaltung](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)finden Sie in der Dokumentation zur Windows-Animations-API.

##  <a name="onstoryboardstatuschanged"></a>Canimationcontroller:: onstoryboardstatuschangi

Wird von Framework aufgerufen, wenn sich der storyboardstatus geändert hat.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Animations Gruppe, die das Storyboard besitzt, dessen Status sich geändert hat.

*newStatus*<br/>
Gibt den neuen Status an.

*previousStatus*<br/>
Gibt den vorherigen Status an.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Storyboard-Ereignisse mithilfe von canimationcontroller:: enablestoryboardeventhandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="onstoryboardupdated"></a>Canimationcontroller:: onstoryboardupveraltet

Wird von Framework aufgerufen, wenn das Storyboard aktualisiert wurde.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parameter

*pGroup*<br/>
Ein Zeiger auf eine Gruppe, die das Storyboard besitzt.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn Sie Storyboard-Ereignisse mithilfe von canimationcontroller:: enablestoryboardeventhandler aktivieren. Sie kann in einer abgeleiteten Klasse überschrieben werden, um anwendungsspezifische Aktionen zu verwenden.

##  <a name="removeallanimationgroups"></a>Canimationcontroller:: removeallanimationgroups

Entfernt alle Animations Gruppen aus dem Animations Controller.

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>Hinweise

Alle Gruppen werden gelöscht. der Zeiger, wenn er auf Anwendungsebene gespeichert wird, muss ungültig werden. Wenn canimationgroup:: m_bAutodestroyAnimationObjects für eine Gruppe, die gelöscht wird, den Wert true hat, werden alle Animations Objekte gelöscht, die zu dieser Gruppe gehören. Andernfalls werden die Verweise auf den übergeordneten Animations Controller auf NULL festgelegt, und Sie können einem anderen Controller hinzugefügt werden.

##  <a name="removeanimationgroup"></a>Canimationcontroller:: removeanimationgroup

Entfernt eine Animations Gruppe mit der angegebenen ID aus dem Animations Controller.

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die Animations Gruppen-ID an.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird eine Animations Gruppe aus der internen Liste der Gruppen entfernt und gelöscht. Wenn Sie also einen Zeiger auf diese Animations Gruppe gespeichert haben, muss diese ungültig gemacht werden. Wenn canimationgroup:: m_bAutodestroyAnimationObjects den Wert true hat, werden alle Animations Objekte gelöscht, die zu dieser Gruppe gehören. Andernfalls werden die Verweise auf den übergeordneten Animations Controller auf NULL festgelegt, und Sie können einem anderen Controller hinzugefügt werden.

##  <a name="removeanimationobject"></a>Canimationcontroller:: removeanimationobject

Entfernen Sie ein Animations Objekt aus dem Animations Controller.

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>Parameter

*pObject*<br/>
Ein Zeiger auf ein Animations Objekt.

*bNoDelete*<br/>
Wenn dieser Parameter true ist, wird das Objekt beim Entfernen nicht gelöscht.

### <a name="remarks"></a>Hinweise

Entfernt ein Animations Objekt aus dem Animations Controller und der Animations Gruppe. Diese Funktion wird aufgerufen, wenn ein bestimmtes Objekt nicht mehr animiert werden soll, oder wenn Sie das Objekt auf einen anderen Animations Controller verschieben müssen. Im letzten Fall muss bnodelete den Wert "true" aufweisen.

##  <a name="removetransitions"></a>Canimationcontroller:: removeübergänge

Entfernt Übergänge von Animations Objekten, die zur angegebenen Gruppe gehören.

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die Gruppen-ID an.

### <a name="remarks"></a>Hinweise

Die Gruppe durchläuft Ihre Animations Objekte und ruft clearübergänge (false) für jedes Animations Objekt auf. Diese Methode wird vom Framework aufgerufen, nachdem die Animation geplant wurde.

##  <a name="schedulegroup"></a>Canimationcontroller:: ScheduleGroup

Plant eine Animation.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>Parameter

*nGroupID*<br/>
Gibt die zu planfeste Animations Gruppen-ID an.

*time*<br/>
Gibt die Zeit für die Planung an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Animation erfolgreich geplant wurde. FALSE, wenn das Storyboard nicht erstellt wurde, oder ein anderer Fehler auftritt.

### <a name="remarks"></a>Hinweise

Sie müssen animategroup mit dem Parameter bschedulenow aufrufen, der vor ScheduleGroup auf false festgelegt ist. Sie können die gewünschte Animations Zeit angeben, die von iuianimationtimer:: getTime abgerufen wird. Wenn der Zeitparameter 0,0 ist, wird die Animation für die aktuelle Uhrzeit geplant.

##  <a name="setrelatedwnd"></a>Canimationcontroller:: abtrelatedwnd

Stellt eine Beziehung zwischen dem Animations Controller und einem Fenster her.

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Ein Zeiger auf ein Fenster Objekt, das festgelegt wird.

### <a name="remarks"></a>Hinweise

Wenn ein verknüpftes CWnd-Objekt festgelegt ist, kann der Animations Controller es automatisch aktualisieren (Send WM_PAINT Message), wenn sich der Status des Animations-Managers geändert hat oder das Ereignis "Timer nach Update" aufgetreten ist.

##  <a name="updateanimationmanager"></a>Canimationcontroller:: updateanimationmanager

Weist den Animations-Manager an, die Werte aller Animations Variablen zu aktualisieren.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>Hinweise

Durch Aufrufen dieser Methode wird der Animations-Manager auf die aktuelle Zeit erweitert, die Status von Storyboards bei Bedarf geändert und alle Animations Variablen auf entsprechende interinterpolierte Werte aktualisiert. Intern ruft diese Methode iuianimationtimer:: getTime (TimeNow) und iuianimationmanager:: Update (TimeNow) auf. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um dieses Verhalten anzupassen.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
