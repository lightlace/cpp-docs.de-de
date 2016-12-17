---
title: "CKeyFrame-Klasse"
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
  - "afxanimationcontroller/CKeyFrame"
  - "CKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyFrame-Klasse"
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CKeyFrame-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Animationskeyframe dar.  
  
## Syntax  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](../Topic/CKeyFrame::CKeyFrame.md)|Überladen.  Erstellt einen Keyframe, der von einem anderem Keyframe abhängt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](../Topic/CKeyFrame::AddToStoryboard.md)|Fügt einem Storyboard einen Keyframe hinzu.  \(Überschreibt [CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md).\)|  
|[CKeyFrame::AddToStoryboardAfterTransition](../Topic/CKeyFrame::AddToStoryboardAfterTransition.md)|Fügt Storyboard nach Übergang einen Keyframe hinzu.|  
|[CKeyFrame::AddToStoryboardAtOffset](../Topic/CKeyFrame::AddToStoryboardAtOffset.md)|Fügt Storyboard bei Offset einen Keyframe hinzu.|  
|[CKeyFrame::GetExistingKeyframe](../Topic/CKeyFrame::GetExistingKeyframe.md)|Gibt einen Zeiger auf einen Keyframe zurück, von dem dieser Keyframe abhängt.|  
|[CKeyFrame::GetOffset](../Topic/CKeyFrame::GetOffset.md)|Gibt einen Offset von anderem Keyframe zurück.|  
|[CKeyFrame::GetTransition](../Topic/CKeyFrame::GetTransition.md)|Gibt einen Zeiger auf einen Übergang zurück, von dem dieser Keyframe abhängt.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::m\_offset](../Topic/CKeyFrame::m_offset.md)|Gibt Offset dieses Keyframes von einem in m\_pExistingKeyFrame gespeicherten Keyframe an.|  
|[CKeyFrame::m\_pExistingKeyFrame](../Topic/CKeyFrame::m_pExistingKeyFrame.md)|Speichert einen Zeiger auf einen vorhandenen Keyframe.  Dieser Keyframe wird dem Storyboard mit m\_offset zum vorhandenen Keyframe hinzugefügt.|  
|[CKeyFrame::m\_pTransition](../Topic/CKeyFrame::m_pTransition.md)|Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.|  
  
## Hinweise  
 Diese Klasse implementiert einen Animationskeyframe.  Ein Keyframe stellt einen Zeitpunkt in einem Storyboard dar und kann verwendet werden, um die Start\- und Endzeiten von Übergängen anzugeben.  Ein Keyframe kann auf einem anderem Keyframe basieren und einen Offset \(in Sekunden\) von diesem haben, oder er kann auf einem Übergang basieren und den Zeitpunkt darstellen, an dem dieser Übergang endet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)