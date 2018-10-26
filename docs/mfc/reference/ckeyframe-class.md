---
title: CKeyFrame-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70301284e306a2d207876eead82ad787684809ce
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055527"
---
# <a name="ckeyframe-class"></a>CKeyFrame-Klasse

Stellt einen Animationskeyframe dar.

## <a name="syntax"></a>Syntax

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Überladen. Erstellt einen Keyframe, der von anderen Keyframe abhängig ist.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Fügt einen Keyframe zu einem Storyboard an. (Überschreibt [CBaseKeyFrame:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Fügt nach der Umstellung storyboard einen Keyframe an.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Fügt einen Keyframe an Offset storyboard hinzu.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Gibt einen Zeiger zu einem Keyframe, von denen, dem dieser Keyframe abhängt.|
|[CKeyFrame::GetOffset](#getoffset)|Gibt einen Offset von anderen Keyframe zurück.|
|[CKeyFrame::GetTransition](#gettransition)|Gibt einen Zeiger auf einen Übergang, von denen, dem dieser Keyframe abhängt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|Gibt an, der Offset dieses Keyframes von einem Keyframe in M_pExistingKeyFrame gespeichert.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Speichert einen Zeiger auf einen vorhandenen Keyframe. Diesen Keyframe ist mit M_offset auf den vorhandenen Keyframe storyboard hinzugefügt.|
|[CKeyFrame::m_pTransition](#m_ptransition)|Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.|

## <a name="remarks"></a>Hinweise

Diese Klasse implementiert einen Animationskeyframe. Ein Keyframe stellt einen Zeitpunkt in einem Storyboard dar und kann verwendet werden, um die Start- und Endzeiten der Übergänge angeben. Ein Keyframe basiert möglicherweise auf anderen Keyframe und einen Offset (in Sekunden), oder basiert möglicherweise auf einen Übergang und Darstellen von einem bestimmten Zeitpunkt dieser Übergang endet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard

Fügt einen Keyframe zu einem Storyboard an.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard.

*bDeepAdd*<br/>
Gibt an, ob Keyframe hinzufügen oder rekursiv übertragen werden.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Keyframe erfolgreich hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Diese Methode fügt storyboard einen Keyframe. Wenn es hängt von anderen Keyframe oder Übergang und bDeepAdd TRUE ist, versucht diese Methode ab, sie rekursiv hinzuzufügen.

##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition

Fügt nach der Umstellung storyboard einen Keyframe an.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard.

*bDeepAdd*<br/>
Gibt an, ob ein Übergang rekursiv hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Keyframe erfolgreich hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion wird durch das Framework nach der Umstellung storyboard einen Keyframe hinzufügen aufgerufen.

##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset

Fügt einen Keyframe an Offset storyboard hinzu.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parameter

*pStoryboard*<br/>
Ein Zeiger auf ein Storyboard.

*bDeepAdd*<br/>
Gibt an, ob einen Keyframe hinzufügen diesen Keyframe rekursiv abhängig.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Keyframe erfolgreich hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion wird durch das Framework hinzuzufügende Offset storyboard einen Keyframe aufgerufen.

##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame

Erstellt einen Keyframe, der von einem Übergang abhängig ist.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parameter

*pTransition*<br/>
Ein Zeiger auf einen Übergang.

*pKeyframe*<br/>
Ein Zeiger auf den Keyframe.

*offset*<br/>
Der Offset, in Sekunden, die aus von pKeyframe angegeben.

### <a name="remarks"></a>Hinweise

Der erstellte Keyframe stellt einen Zeitpunkt in einem Storyboard dar, wenn der angegebene Übergang beendet.

##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe

Gibt einen Zeiger zu einem Keyframe, von denen, dem dieser Keyframe abhängt.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger auf den Keyframe oder NULL, wenn es sich bei diesen Keyframe nicht von anderen Keyframe abhängt.

### <a name="remarks"></a>Hinweise

Dies ist ein Accessor zu einem Keyframe, von denen, dem dieser Keyframe abhängt.

##  <a name="getoffset"></a>  CKeyFrame::GetOffset

Gibt einen Offset von anderen Keyframe zurück.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Rückgabewert

Ein Offset in Sekunden, die von anderen Keyframe.

### <a name="remarks"></a>Hinweise

Diese Methode sollte aufgerufen werden, um zu bestimmen, einen Offset in Sekunden, die von anderen Keyframe.

##  <a name="gettransition"></a>  CKeyFrame::GetTransition

Gibt einen Zeiger auf einen Übergang, von denen, dem dieser Keyframe abhängt.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger Zeiger, Übergang oder NULL, wenn es sich bei diesen Keyframe Übergang nicht abhängig ist.

### <a name="remarks"></a>Hinweise

Dies ist ein Accessor für einen Übergang, von denen, dem dieser Keyframe abhängt.

##  <a name="m_offset"></a>  CKeyFrame::m_offset

Gibt an, der Offset dieses Keyframes von einem Keyframe in M_pExistingKeyFrame gespeichert.

```
UI_ANIMATION_SECONDS m_offset;
```

##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame

Speichert einen Zeiger auf einen vorhandenen Keyframe. Diesen Keyframe ist mit M_offset auf den vorhandenen Keyframe storyboard hinzugefügt.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition

Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
