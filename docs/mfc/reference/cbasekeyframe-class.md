---
title: CBaseKeyFrame-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame class
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cfbaac379097c89b5dcb52fa36c0cd1f6e3d2c7f
ms.lasthandoff: 02/24/2017

---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame-Klasse
Implementiert die grundlegende Funktion eines Keyframe.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Erstellt ein Keyframeobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame:: AddToStoryboard](#addtostoryboard)|Fügt storyboard einen Keyframe hinzu.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Gibt den Wert des zugrunde liegenden Keyframe zurück.|  
|[CBaseKeyFrame::IsAdded](#isadded)|Erfahren Sie, ob Storyboard ein Keyframe hinzugefügt wurde.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Gibt an, ob der Keyframe bei Offset, oder nach Übergang Storyboard hinzugefügt werden soll.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|Gibt an, ob ein Storyboard dieser Keyframe hinzugefügt wurde.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Gibt an, ob dieser Keyframe bei einem Offset von einem anderen vorhandenen Keyframe oder am Ende des Übergangs storyboard hinzugefügt werden soll.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Stellt einen Windows Animation API Keyframe dar. Wenn ein Keyframe nicht initialisiert wird, die es zu den vordefinierten Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Kapselt die UI_ANIMATION_KEYFRAME-Variable. Dient als Basisklasse für alle Keyframeimplementierung. Ein Keyframe stellt einen Zeitpunkt in einem Storyboard dar und kann verwendet werden, um die Start- und Endzeiten von Übergängen anzugeben. Es gibt zwei Typen von Keyframes: Keyframes, die am angegebenen Offset (in Time) storyboard hinzugefügt oder Keyframes, die nach einem angegebenen Übergang hinzugefügt. Da die Dauer einiger Übergänge, bevor die Animation startet bekannt sein können, werden die tatsächlichen Werte einiger Keyframes nur zur Laufzeit bestimmt. Da Keyframes möglicherweise von Übergängen, die wiederum von Keyframes abhängig sind abhängt, ist es wichtig, unbegrenzte Rekursionen zu verhindern, dass beim Erstellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CBaseKeyFrame:: AddToStoryboard  
 Fügt storyboard einen Keyframe hinzu.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Wenn dieser Parameter TRUE ist, und der Keyframe hinzugefügt wird, hängt von einem anderen Keyframe oder Übergang, versucht diese Methode diesen Keyframe oder Übergang Storyboard zuerst hinzuzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Keyframe storyboard erfolgreich hinzugefügt wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, um einen Keyframe storyboard hinzuzufügen.  
  
##  <a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame  
 Erstellt ein Keyframeobjekt.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe  
 Gibt den Wert des zugrunde liegenden Keyframe zurück.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Keyframe. Der Standardwert ist UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor für den zugrunde liegenden Keyframewert.  
  
##  <a name="isadded"></a>CBaseKeyFrame::IsAdded  
 Erfahren Sie, ob Storyboard ein Keyframe hinzugefügt wurde.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein Storyboard ein Keyframe hinzugefügt wird. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 In der Basisklasse gibt IsAdded immer TRUE zurück, aber in abgeleiteten Klassen überschrieben wird.  
  
##  <a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeAtOffset  
 Gibt an, ob der Keyframe bei Offset, oder nach Übergang Storyboard hinzugefügt werden soll.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe an einigen angegebenen Offset Storyboard hinzugefügt werden soll. FALSE, wenn der Keyframe storyboard nach einem Übergang hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt an, ob der Keyframe bei Offset Storyboard hinzugefügt werden soll. Der Offset oder der Übergang muss in einer abgeleiteten Klasse angegeben werden.  
  
##  <a name="m_badded"></a>CBaseKeyFrame::m_bAdded  
 Gibt an, ob ein Storyboard dieser Keyframe hinzugefügt wurde.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset  
 Gibt an, ob dieser Keyframe bei einem Offset von einem anderen vorhandenen Keyframe oder am Ende des Übergangs storyboard hinzugefügt werden soll.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>CBaseKeyFrame::m_keyframe  
 Stellt einen Windows Animation API Keyframe dar. Wenn ein Keyframe nicht initialisiert wird, die es zu den vordefinierten Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

