---
title: CKeyFrame-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CKeyFrame class
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d8ecff2e36148fb114ee708712b6e8bd0fe558ed
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyframe-class"></a>CKeyFrame-Klasse
Stellt einen Animationskeyframe dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Überladen. Erstellt einen Keyframe, der von anderen Keyframe abhängt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Ein Storyboard hinzugefügt einen Keyframe. (Überschreibt [CBaseKeyFrame:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Fügt einen Keyframe Storyboard nach Übergang.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Fügt storyboard bei Offset einen Keyframe hinzu.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Gibt einen Zeiger auf einen Keyframe, dem dieser Keyframe abhängt.|  
|[CKeyFrame::GetOffset](#getoffset)|Gibt einen Offset von anderem Keyframe zurück.|  
|[CKeyFrame::GetTransition](#gettransition)|Gibt einen Zeiger auf einen Übergang, dem dieser Keyframe abhängt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Gibt Offset dieses Keyframes von einem Keyframe in M_pExistingKeyFrame gespeichert.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Speichert einen Zeiger auf einen vorhandenen Keyframe. Dieser Keyframe wird mit M_offset auf den vorhandenen Keyframe Storyboard hinzugefügt.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert einen Animationskeyframe. Ein Keyframe stellt einen Zeitpunkt in einem Storyboard dar und kann verwendet werden, um die Start- und Endzeiten von Übergängen anzugeben. Ein Keyframe basiert möglicherweise auf andere Keyframes und einen Offset (in Sekunden), oder basiert möglicherweise auf einen Übergang und Darstellen von einem bestimmten Zeitpunkt dieser Übergang endet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard  
 Ein Storyboard hinzugefügt einen Keyframe.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Gibt an, ob hinzufügen Keyframe oder Übergang rekursiv.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt storyboard einen Keyframe. Wenn es auf anderen Keyframe oder Übergang abhängt und bDeepAdd TRUE ist, versucht diese Methode, sie rekursiv hinzuzufügen.  
  
##  <a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition  
 Fügt einen Keyframe Storyboard nach Übergang.  
  
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
 Diese Funktion wird vom Framework storyboard nach Übergang einen Keyframe hinzufügen aufgerufen.  
  
##  <a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset  
 Fügt storyboard bei Offset einen Keyframe hinzu.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDeepAdd`  
 Gibt an, ob einen Keyframe Hinzufügen dieser Keyframe rekursiv abhängt.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Keyframe erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework storyboard bei Offset einen Keyframe hinzufügen aufgerufen.  
  
##  <a name="ckeyframe"></a>CKeyFrame::CKeyFrame  
 Erstellt einen Keyframe, der einen Übergang abhängt.  
  
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
 Ein Zeiger auf den Keyframe.  
  
 `offset`  
 Offset in Sekunden, von pKeyframe angegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Der erstellte Keyframe stellt einen Zeitpunkt in einem Storyboard dar, wenn der angegebene Übergang endet.  
  
##  <a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe  
 Gibt einen Zeiger auf einen Keyframe, dem dieser Keyframe abhängt.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf Keyframe oder NULL, wenn dieser Keyframe nicht von anderem Keyframe abhängt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor für einen Keyframe, dem dieser Keyframe abhängt.  
  
##  <a name="getoffset"></a>CKeyFrame::GetOffset  
 Gibt einen Offset von anderem Keyframe zurück.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Offset in Sekunden von einem anderem Keyframe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte aufgerufen werden, um einen Offset in Sekunden von einem anderem Keyframe zu bestimmen.  
  
##  <a name="gettransition"></a>CKeyFrame::GetTransition  
 Gibt einen Zeiger auf einen Übergang, dem dieser Keyframe abhängt.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf Übergang oder NULL, wenn dieser Keyframe nicht Übergang abhängt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor für einen Übergang, dem dieser Keyframe abhängt.  
  
##  <a name="m_offset"></a>CKeyFrame::m_offset  
 Gibt Offset dieses Keyframes von einem Keyframe in M_pExistingKeyFrame gespeichert.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame  
 Speichert einen Zeiger auf einen vorhandenen Keyframe. Dieser Keyframe wird mit M_offset auf den vorhandenen Keyframe Storyboard hinzugefügt.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>CKeyFrame::m_pTransition  
 Speichert einen Zeiger auf den Übergang, der bei diesem Keyframe beginnt.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

