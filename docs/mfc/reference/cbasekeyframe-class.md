---
title: CBaseKeyFrame-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3de348131dded63794e818d40c0ac5aeae910b03
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956706"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame-Klasse
Implementiert die grundlegende Funktion eines Keyframe.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Erstellt einen Keyframeobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame:: AddToStoryboard](#addtostoryboard)|Fügt einen Keyframe storyboard hinzu.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Gibt den Wert des zugrunde liegenden Keyframe zurück.|  
|[CBaseKeyFrame::IsAdded](#isadded)|Erfahren Sie, ob ein Keyframe Storyboard hinzugefügt wurde.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Gibt an, ob der Keyframe Offset oder nach der Umstellung Storyboard hinzugefügt werden soll.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|Gibt an, ob ein Storyboard dieser Keyframe hinzugefügt wurde.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Gibt an, ob dieser Keyframe Storyboard mit einem Offset von einem anderen vorhandenen Keyframe oder am Ende des Übergangs hinzugefügt werden soll.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Stellt einen Windows Animation API Keyframe dar. Wenn Keyframe nicht initialisiert wird, die sie auf den vordefinierten Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Kapselt die UI_ANIMATION_KEYFRAME-Variable. Dient als Basisklasse für alle Keyframeimplementierung. Keyframe stellt einen Zeitpunkt in eine Storyboard und kann verwendet werden, um die Start- und Endzeiten von Übergängen angeben. Es gibt zwei Arten von Keyframes - Keyframes am angegebenen Offset (zeitlich) storyboard hinzugefügt oder Keyframes, die nach einem angegebenen Übergang hinzugefügt. Da Dauer einiger Übergänge vor Starten der Animation bekannt sein können, werden die tatsächlichen Werte einiger Keyframes nur zur Laufzeit bestimmt. Da Keyframes möglicherweise von Übergängen, die wiederum von Keyframes abhängen abhängt, ist es wichtig, um unendliche Rekursionen zu verhindern, dass beim Erstellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CBaseKeyFrame:: AddToStoryboard  
 Fügt einen Keyframe storyboard hinzu.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 *pStoryboard*  
 Ein Zeiger auf ein Storyboard.  
  
 *bDeepAdd*  
 Wenn dieser Parameter "true ist", und der Keyframe hinzugefügt wird, abhängig von einem anderen Keyframe oder Übergang, versucht diese Methode diesen Keyframe oder Übergang Storyboard zuerst hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Keyframe storyboard erfolgreich hinzugefügt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, um ein storyboard Keyframe hinzuzufügen.  
  
##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame  
 Erstellt einen Keyframeobjekt.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe  
 Gibt den Wert des zugrunde liegenden Keyframe zurück.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Keyframe. Der Standardwert ist UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor für den zugrunde liegenden Keyframewert.  
  
##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded  
 Erfahren Sie, ob ein Keyframe Storyboard hinzugefügt wurde.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein Storyboard Keyframe hinzugefügt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 In der Basisklasse IsAdded immer gibt "true", aber in abgeleiteten Klassen überschrieben wird.  
  
##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset  
 Gibt an, ob der Keyframe Offset oder nach der Umstellung Storyboard hinzugefügt werden soll.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn der Keyframe Storyboard in einige angegebenen Abstand hinzugefügt werden soll. "False", wenn der Keyframe storyboard nach einem Übergang hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt an, ob der Keyframe Offset Storyboard hinzugefügt werden soll. Der Offset oder die Umstellung muss in einer abgeleiteten Klasse angegeben werden.  
  
##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded  
 Gibt an, ob ein Storyboard dieser Keyframe hinzugefügt wurde.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset  
 Gibt an, ob dieser Keyframe Storyboard mit einem Offset von einem anderen vorhandenen Keyframe oder am Ende des Übergangs hinzugefügt werden soll.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe  
 Stellt einen Windows Animation API Keyframe dar. Wenn Keyframe nicht initialisiert wird, die sie auf den vordefinierten Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
