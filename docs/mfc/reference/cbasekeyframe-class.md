---
title: "CBaseKeyFrame-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBaseKeyFrame"
  - "afxanimationcontroller/CBaseKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseKeyFrame-Klasse"
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CBaseKeyFrame-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die grundlegende Funktion eines Keyframe.  
  
## Syntax  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBaseKeyFrame::CBaseKeyFrame](../Topic/CBaseKeyFrame::CBaseKeyFrame.md)|Erstellt ein Keyframeobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md)|Fügt Keyframes Storyboard hinzu.|  
|[CBaseKeyFrame::GetAnimationKeyframe](../Topic/CBaseKeyFrame::GetAnimationKeyframe.md)|Gibt den zugrunde liegenden Keyframe\-Wert zurück.|  
|[CBaseKeyFrame::IsAdded](../Topic/CBaseKeyFrame::IsAdded.md)|Teilt mit, ob Keyframes zum Storyboard hinzugefügt wurden.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](../Topic/CBaseKeyFrame::IsKeyframeAtOffset.md)|Gibt an, ob die Keyframes Storyboard am Offset hinzugefügt werden sollen, oder nach Übergang an.|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBaseKeyFrame::m\_bAdded](../Topic/CBaseKeyFrame::m_bAdded.md)|Gibt an, ob diese Keyframes zu einem Storyboard hinzugefügt wurden.|  
|[CBaseKeyFrame::m\_bIsKeyframeAtOffset](../Topic/CBaseKeyFrame::m_bIsKeyframeAtOffset.md)|Gibt an, ob diese Keyframes Storyboard bei einem Offset von einen anderen vorhandenen Keyframes hinzugefügt werden sollen, oder am Ende etwas Übergangs an.|  
|[CBaseKeyFrame::m\_keyframe](../Topic/CBaseKeyFrame::m_keyframe.md)|Stellt Keyframes Windows\-Animation API dar.  Wenn Keyframes nicht initialisiert wurde, wird er dem vordefinierten beschränkt UI\_ANIMATION\_KEYFRAME\_STORYBOARD\_START festgelegt.|  
  
## Hinweise  
 Kapselt UI\_ANIMATION\_KEYFRAME\-Variable.  Dient als Basisklasse für eine Keyframeimplementierung.  Keyframes stellen einen Zeitpunkt innerhalb eines Storyboards dar und können verwendet werden, um die Start\- und Endzeiten von Übergängen anzugeben.  Es gibt zwei Typen Keyframe \- Keyframes, die dem Storyboard am angegebenen Offset hinzugefügt werden \(in der Zeit\) oder die Keyframes, die nach dem angegebenen Übergang hinzugefügt werden.  Da Dauer einiger Übergängen nicht bekannt können, bevor Animationsanfänge, die tatsächlichen Werte einiger Keyframes nur zur Laufzeit bestimmt werden.  Da Keyframes möglicherweise von den Übergängen abhängig sind, die in ihrer Drehung von den Keyframe abhängen, ist es wichtig, eine unbegrenzte Rekursionen verhindert, wenn von Keyframes erstellt, verkettet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)