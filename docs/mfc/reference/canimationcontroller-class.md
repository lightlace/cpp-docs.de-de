---
title: "CAnimationController-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CAnimationController"
  - "afxanimationcontroller/CAnimationController"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationController-Klasse"
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationController-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert den Animationscontroller, der eine zentrale Schnittstelle zum Erstellen und Verwalten von Animationen bereitstellt.  
  
## Syntax  
  
```  
class CAnimationController : public CObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](../Topic/CAnimationController::CAnimationController.md)|Erstellt einen Animationscontroller.|  
|[CAnimationController::~CAnimationController](../Topic/CAnimationController::~CAnimationController.md)|Der Destruktor.  Wird aufgerufen, wenn ein Animationscontrollerobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](../Topic/CAnimationController::AddAnimationObject.md)|Fügt einer Gruppe, die zum Animationscontroller gehört, ein Animationsobjekt hinzu.|  
|[CAnimationController::AddKeyframeToGroup](../Topic/CAnimationController::AddKeyframeToGroup.md)|Fügt einer Gruppe einen Keyframe hinzu.|  
|[CAnimationController::AnimateGroup](../Topic/CAnimationController::AnimateGroup.md)|Bereitet eine Gruppe vor, Animation auszuführen, und plant sie optional.|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Überladen.  Wird vom Framework aufgerufen, um die Gruppe zu bereinigen, wenn Animation geplant wurde.|  
|[CAnimationController::CreateKeyframe](../Topic/CAnimationController::CreateKeyframe.md)|Überladen.  Erstellt einen Keyframe, der vom Übergang abhängt und zur angegebenen Gruppe hinzugefügt wird.|  
|[CAnimationController::EnableAnimationManagerEvent](../Topic/CAnimationController::EnableAnimationManagerEvent.md)|Legt fest oder gibt einen Handler frei, der bei Statusänderungen von Animations\-Manager aufzurufen ist.|  
|[CAnimationController::EnableAnimationTimerEventHandler](../Topic/CAnimationController::EnableAnimationTimerEventHandler.md)|Legt fest oder gibt einen Handler für die Zeitsteuerung von Ereignissen und Aktualisierungen frei.|  
|[CAnimationController::EnablePriorityComparisonHandler](../Topic/CAnimationController::EnablePriorityComparisonHandler.md)|Setzt oder gib den Prioritätsvergleichshandler frei, der aufgerufen werden soll, um zu bestimmen, ob ein geplantes Storyboard abgebrochen, abgeschlossen, abgeschnitten oder komprimiert werden kann.|  
|[CAnimationController::EnableStoryboardEventHandler](../Topic/CAnimationController::EnableStoryboardEventHandler.md)|Legt fest oder gibt einen Handler für Storyboardstatus\- und \-aktualisierungsereignisse frei.|  
|[CAnimationController::FindAnimationGroup](../Topic/CAnimationController::FindAnimationGroup.md)|Überladen.  Sucht eine Animationsgruppe über sein Storyboard.|  
|[CAnimationController::FindAnimationObject](../Topic/CAnimationController::FindAnimationObject.md)|Sucht ein Animationsobjekt, das eine angegebene Animationsvariable enthält.|  
|[CAnimationController::GetKeyframeStoryboardStart](../Topic/CAnimationController::GetKeyframeStoryboardStart.md)|Gibt einen Keyframe zurück, der den Anfang des Storyboards identifiziert.|  
|[CAnimationController::GetUIAnimationManager](../Topic/CAnimationController::GetUIAnimationManager.md)|Bietet Zugriff auf gekapseltes IUIAnimationManager\-Objekt.|  
|[CAnimationController::GetUIAnimationTimer](../Topic/CAnimationController::GetUIAnimationTimer.md)|Bietet Zugriff auf gekapseltes IUIAnimationTimer\-Objekt.|  
|[CAnimationController::GetUITransitionFactory](../Topic/CAnimationController::GetUITransitionFactory.md)|Ein Zeiger auf IUIAnimationTransitionFactory\-Schnittstelle oder NULL, wenn die Erstellung der Übergangsbibliothek fehlschlug.|  
|[CAnimationController::GetUITransitionLibrary](../Topic/CAnimationController::GetUITransitionLibrary.md)|Bietet Zugriff auf gekapseltes IUIAnimationTransitionLibrary\-Objekt.|  
|[CAnimationController::IsAnimationInProgress](../Topic/CAnimationController::IsAnimationInProgress.md)|Gibt an, ob mindestens eine Gruppe Animation wiedergibt.|  
|[CAnimationController::IsValid](../Topic/CAnimationController::IsValid.md)|Gibt an, ob Animationscontroller gültig ist.|  
|[CAnimationController::OnAnimationIntegerValueChanged](../Topic/CAnimationController::OnAnimationIntegerValueChanged.md)|Wird vom Framework aufgerufen, wenn sich ganzzahliger Wert der Animationsvariable geändert hat.|  
|[CAnimationController::OnAnimationManagerStatusChanged](../Topic/CAnimationController::OnAnimationManagerStatusChanged.md)|Wird vom Framework als Reaktion auf StatusChanged\-Ereignis von Animations\-Manager aufgerufen.|  
|[CAnimationController::OnAnimationTimerPostUpdate](../Topic/CAnimationController::OnAnimationTimerPostUpdate.md)|Wird vom Framework aufgerufen, nachdem ein Animationsupdate beendet wurde.|  
|[CAnimationController::OnAnimationTimerPreUpdate](../Topic/CAnimationController::OnAnimationTimerPreUpdate.md)|Wird vom Framework aufgerufen, bevor ein Animationsupdate beginnt.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](../Topic/CAnimationController::OnAnimationTimerRenderingTooSlow.md)|Wird vom Framework aufgerufen, wenn die Renderingframerate für eine Animation unter eine minimale gewünschte Framerate fällt.|  
|[CAnimationController::OnAnimationValueChanged](../Topic/CAnimationController::OnAnimationValueChanged.md)|Wird vom Framework aufgerufen, wenn sich der Wert der Animationsvariable geändert hat.|  
|[CAnimationController::OnBeforeAnimationStart](../Topic/CAnimationController::OnBeforeAnimationStart.md)|Wird vom Framework aufgerufen, unmittelbar bevor die Animation geplant wird.|  
|[CAnimationController::OnHasPriorityCancel](../Topic/CAnimationController::OnHasPriorityCancel.md)|Wird vom Framework aufgerufen, um Planungskonflikte zu lösen.|  
|[CAnimationController::OnHasPriorityCompress](../Topic/CAnimationController::OnHasPriorityCompress.md)|Wird vom Framework aufgerufen, um Planungskonflikte zu lösen.|  
|[CAnimationController::OnHasPriorityConclude](../Topic/CAnimationController::OnHasPriorityConclude.md)|Wird vom Framework aufgerufen, um Planungskonflikte zu lösen.|  
|[CAnimationController::OnHasPriorityTrim](../Topic/CAnimationController::OnHasPriorityTrim.md)|Wird vom Framework aufgerufen, um Planungskonflikte zu lösen.|  
|[CAnimationController::OnStoryboardStatusChanged](../Topic/CAnimationController::OnStoryboardStatusChanged.md)|Wird vom Framework aufgerufen, wenn sich Storyboardstatus geändert hat.|  
|[CAnimationController::OnStoryboardUpdated](../Topic/CAnimationController::OnStoryboardUpdated.md)|Wird vom Framework aufgerufen, wenn Storyboard aktualisiert wurde.|  
|[CAnimationController::RemoveAllAnimationGroups](../Topic/CAnimationController::RemoveAllAnimationGroups.md)|Entfernt alle Animationsgruppen aus Animationscontroller.|  
|[CAnimationController::RemoveAnimationGroup](../Topic/CAnimationController::RemoveAnimationGroup.md)|Entfernt eine Animationsgruppe mit angegebener ID aus Animationscontroller.|  
|[CAnimationController::RemoveAnimationObject](../Topic/CAnimationController::RemoveAnimationObject.md)|Entfernen Sie ein Animationsobjekt aus Animationscontroller.|  
|[CAnimationController::RemoveTransitions](../Topic/CAnimationController::RemoveTransitions.md)|Entfernt Übergänge aus Animationsobjekten, die zur angegebenen Gruppe gehören.|  
|[CAnimationController::ScheduleGroup](../Topic/CAnimationController::ScheduleGroup.md)|Plant eine Animation.|  
|[CAnimationController::SetRelatedWnd](../Topic/CAnimationController::SetRelatedWnd.md)|Legt eine Beziehung zwischen Animationscontroller und einem Fenster fest.|  
|[CAnimationController::UpdateAnimationManager](../Topic/CAnimationController::UpdateAnimationManager.md)|Weist den Animations\-Manager an, die Werte aller Animationsvariablen zu aktualisieren.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Überladen.  Eine Hilfe, die die Gruppe bereinigt.|  
|[CAnimationController::OnAfterSchedule](../Topic/CAnimationController::OnAfterSchedule.md)|Wird vom Framework aufgerufen, wenn eine Animation für die angegebene Gruppe gerade geplant wurde.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationController::g\_KeyframeStoryboardStart](../Topic/CAnimationController::g_KeyframeStoryboardStart.md)|Ein Keyframe, der den Anfang des Storyboards darstellt.|  
|[CAnimationController::m\_bIsValid](../Topic/CAnimationController::m_bIsValid.md)|Gibt an, ob ein Animationscontroller gültig ist, oder nicht.  Dieser Member wird auf FALSE festgelegt, wenn das aktuelle Betriebssystem die Windows\-Animations\-API nicht unterstützt.|  
|[CAnimationController::m\_lstAnimationGroups](../Topic/CAnimationController::m_lstAnimationGroups.md)|Eine Liste von Animationsgruppen, die zu diesem Animationscontroller gehören.|  
|[CAnimationController::m\_pAnimationManager](../Topic/CAnimationController::m_pAnimationManager.md)|Speichert einen Zeiger auf Animations\-Manager\-COM\-Objekt.|  
|[CAnimationController::m\_pAnimationTimer](../Topic/CAnimationController::m_pAnimationTimer.md)|Speichert einen Zeiger auf Animationszeitgeber\-COM\-Objekt.|  
|[CAnimationController::m\_pRelatedWnd](../Topic/CAnimationController::m_pRelatedWnd.md)|Ein Zeiger auf ein zugehöriges CWnd\-Objekt, das automatisch neu gezeichnet werden kann, wenn sich der Status des Animations\-Managers ändert oder ein Ereignis nach dem Update aufgetreten ist.  Kann NULL sein.|  
|[CAnimationController::m\_pTransitionFactory](../Topic/CAnimationController::m_pTransitionFactory.md)|Speichert einen Zeiger auf Transition Factory\-COM\-Objekt.|  
|[CAnimationController::m\_pTransitionLibrary](../Topic/CAnimationController::m_pTransitionLibrary.md)|Speichert einen Zeiger auf Transition Library\-COM\-Objekt.|  
  
## Hinweise  
 Die CAnimationController\-Klasse ist die Hauptklasse, die Animationen verwaltet.  Sie können eine oder mehrere Instanzen des Animationscontrollers in einer Anwendung erstellen und optional eine Instanz des Animationscontrollers mithilfe von CAnimationController::SetRelatedWnd mit einem CWnd\-Objekt verbinden.  Diese Verbindung ist erforderlich, um automatisch WM\_PAINT\-Meldungen an das zugehörige Fenster zu senden, wenn sich der Status des Animations\-Managers ändert oder der Animationszeitgeber aktualisiert wurde.  Wenn Sie diese Beziehung nicht aktivieren, müssen Sie ein Fenster, das manuell eine Animation anzeigt, neu zeichnen.  Zu diesem Zweck können Sie eine Klasse von CAnimationController ableiten und OnAnimationManagerStatusChanged und\/oder OnAnimationTimerPostUpdate überschreiben und eines oder mehrere Fenster bei Bedarf für ungültig erklären.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationController](../../mfc/reference/canimationcontroller-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)