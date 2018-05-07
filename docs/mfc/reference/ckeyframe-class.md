---
title: CKeyFrame-Klasse | Microsoft Docs
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
ms.openlocfilehash: 9a9e9ff3d6e3e4bcccf8e9ebd46f791f60f1cc37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CKeyFrame::CKeyFrame](#ckeyframe)|Überladen. Erstellt einen Keyframe, von der andere Keyframe abhängt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Ein Storyboard hinzugefügt Keyframe. (Überschreibt [CBaseKeyFrame:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Fügt nach der Umstellung storyboard einen Keyframe.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Fügt einen Keyframe storyboard-Offset hinzu.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Gibt einen Zeiger auf einen Keyframe, von denen, dem dieser Keyframe abhängt.|  
|[CKeyFrame::GetOffset](#getoffset)|Gibt einen Offset von anderem Keyframe zurück.|  
|[CKeyFrame::GetTransition](#gettransition)|Gibt einen Zeiger auf einen Übergang, von denen, dem dieser Keyframe abhängt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Gibt Offset dieses Keyframes von Keyframe in M_pExistingKeyFrame gespeichert.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Speichert einen Zeiger auf einen vorhandenen Keyframe. Storyboard mit M_offset auf den vorhandenen Keyframe wird dieser Keyframe hinzugefügt.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert einen Animationskeyframe. Keyframe stellt einen Zeitpunkt in eine Storyboard und kann verwendet werden, um die Start- und Endzeiten von Übergängen angeben. Keyframe basiert möglicherweise auf andere Keyframe und einen Offset (in Sekunden) aus, oder basiert möglicherweise auf einen Übergang und einen Zeitpunkt dieser Übergang endet darstellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard  
 Ein Storyboard hinzugefügt Keyframe.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Gibt an, ob Keyframe hinzufügen oder Übergang rekursiv.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt storyboard einen Keyframe. Wenn es anderen Keyframe oder Übergang hängt und bDeepAdd TRUE ist, versucht diese Methode rekursiv hinzufügen.  
  
##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition  
 Fügt nach der Umstellung storyboard einen Keyframe.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Gibt an, ob ein Übergang rekursiv hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird durch das Framework nach der Umstellung storyboard einen Keyframe hinzuzufügende aufgerufen.  
  
##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset  
 Fügt einen Keyframe storyboard-Offset hinzu.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Gibt an, ob ein hinzuzufügende Keyframe dieser Keyframe rekursiv abhängt.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework hinzuzufügende Offset storyboard einen Keyframe aufgerufen.  
  
##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame  
 Erstellt einen Keyframe, der einen Übergang abhängig.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Parameter  
 `pTransition`  
 Ein Zeiger auf einen Übergang.  
  
 `pKeyframe`  
 Ein Zeiger auf Keyframe.  
  
 `offset`  
 Offset in Sekunden, die aus von pKeyframe angegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Der erstellte Keyframe wird einen Zeitpunkt in eine Storyboard darstellen, wenn der angegebene Übergang endet.  
  
##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe  
 Gibt einen Zeiger auf einen Keyframe, von denen, dem dieser Keyframe abhängt.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf Keyframe oder NULL, wenn dieser Keyframe nicht von anderen Keyframe abhängt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor, einen Keyframe, von denen, dem dieser Keyframe abhängt.  
  
##  <a name="getoffset"></a>  CKeyFrame::GetOffset  
 Gibt einen Offset von anderem Keyframe zurück.  
  
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
 Ein gültiger Zeiger auf Übergang oder NULL, wenn dieser Keyframe nicht von Übergang abhängig ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor, einen Übergang, von denen, dem dieser Keyframe abhängt.  
  
##  <a name="m_offset"></a>  CKeyFrame::m_offset  
 Gibt Offset dieses Keyframes von Keyframe in M_pExistingKeyFrame gespeichert.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame  
 Speichert einen Zeiger auf einen vorhandenen Keyframe. Storyboard mit M_offset auf den vorhandenen Keyframe wird dieser Keyframe hinzugefügt.  
  
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
