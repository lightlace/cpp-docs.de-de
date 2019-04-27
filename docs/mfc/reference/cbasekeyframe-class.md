---
title: CBaseKeyFrame-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: d36c924d30bd728fcd54b6cdf6805ade25e20b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218401"
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
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Erstellt ein Keyframeobjekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Fügt einen Keyframe storyboard hinzu.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Gibt den zugrunde liegenden Keyframewert zurück.|
|[CBaseKeyFrame::IsAdded](#isadded)|Erfahren Sie, ob ein Keyframe Storyboard hinzugefügt wurde.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Gibt an, ob es sich bei der Keyframe an Offset oder nach der Umstellung Storyboard hinzugefügt werden soll.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|Gibt an, ob es sich bei diesen Keyframe auf ein Storyboard hinzugefügt wurde.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Gibt an, ob es sich bei diesen Keyframe bei einem Offset von einem anderen vorhandenen Keyframe oder am Ende eines Übergangs Storyboard hinzugefügt werden soll.|
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Stellt einen Keyframe Windows Animations-API dar. Wenn Sie ein Keyframe nicht initialisiert ist, die es der vordefinierte Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.|

## <a name="remarks"></a>Hinweise

Encapsulates UI_ANIMATION_KEYFRAME variable. Dient als Basisklasse für eine Keyframeimplementierung. Ein Keyframe stellt einen Zeitpunkt in einem Storyboard dar und kann verwendet werden, um die Start- und Endzeiten der Übergänge angeben. Es gibt zwei Arten von Keyframes - Keyframes, die mit dem angegebenen Offset (in-Time) storyboard hinzugefügt oder Keyframes, die nach einem angegebenen Übergang hinzugefügt. Da die Dauer einiger Übergänge darf nicht vor dem Starten der Animation bekannt sind, werden die tatsächlichen Werte des einige Keyframes nur zur Laufzeit bestimmt. Da Keyframes möglicherweise von Übergängen,, die wiederum von Keyframes abhängen abhängt, ist es wichtig, um unbegrenzte Rekursionen zu verhindern, dass beim Erstellen.

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

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard.

*bDeepAdd*<br/>
Wenn dieser Parameter "true ist", und der Keyframe, der hinzugefügt wird, hängt von einem anderen Keyframe oder Übergangs, versucht diese Methode, um diesen Keyframe oder Übergang Storyboard zuerst hinzuzufügen.

### <a name="return-value"></a>Rückgabewert

True, wenn ein Keyframe für die storyboard-erfolgreich hinzugefügt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, um einen Keyframe storyboard hinzuzufügen.

##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame

Erstellt ein Keyframeobjekt.

```
CBaseKeyFrame();
```

##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe

Gibt den zugrunde liegenden Keyframewert zurück.

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

True, wenn ein Keyframe auf ein Storyboard hinzugefügt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

In der Basisklasse IsAdded immer TRUE zurück, aber es wird in abgeleiteten Klassen überschrieben.

##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset

Gibt an, ob es sich bei der Keyframe an Offset oder nach der Umstellung Storyboard hinzugefügt werden soll.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Sie der Keyframe an einigen angegebenen Offset Storyboard hinzugefügt werden soll. FALSE, wenn Sie der Keyframe storyboard nach einem Übergang hinzugefügt werden soll.

### <a name="remarks"></a>Hinweise

Gibt an, ob es sich bei der Keyframe an Offset Storyboard hinzugefügt werden soll. Der Offset oder Übergangs muss in einer abgeleiteten Klasse angegeben werden.

##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded

Gibt an, ob es sich bei diesen Keyframe auf ein Storyboard hinzugefügt wurde.

```
BOOL m_bAdded;
```

##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset

Gibt an, ob es sich bei diesen Keyframe bei einem Offset von einem anderen vorhandenen Keyframe oder am Ende eines Übergangs Storyboard hinzugefügt werden soll.

```
BOOL m_bIsKeyframeAtOffset;
```

##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe

Stellt einen Keyframe Windows Animations-API dar. Wenn Sie ein Keyframe nicht initialisiert ist, die es der vordefinierte Wert UI_ANIMATION_KEYFRAME_STORYBOARD_START festgelegt ist.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
