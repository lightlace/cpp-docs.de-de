---
title: CAnimationTimerEventHandler-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CAnimationTimerEventHandler
- CAnimationTimerEventHandler
dev_langs:
- C++
helpviewer_keywords:
- CAnimationTimerEventHandler class
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 5412c215caf85440e923e8a083ed310f8960849a
ms.lasthandoff: 02/24/2017

---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler-Klasse
Implementiert einen Rückruf, der von der Animations-API beim Auftreten von Zeitsteuerungsereignissen aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationTimerEventHandler` Rückruf.|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Behandelt Ereignisse, die auftreten, nachdem eine Animationsupdate abgeschlossen ist. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.)|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Behandelt Ereignisse, die auftreten, bevor ein Animationsupdate beginnt. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Behandelt Ereignisse, die auftreten, wenn die Rendering-Framerate für eine Animation unter die minimale erwünschte Framerate fällt. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.)|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler wird erstellt und an SetTimerEventHandler übergeben übergeben werden, wenn Sie CAnimationController:: EnableAnimationTimerEventHandler aufrufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namecreateinstancea--canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 Erstellt eine Instanz der CAnimationTimerEventHandler-Rückrufs.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfangen wird.  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-nameonpostupdatea--canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 Behandelt Ereignisse, die auftreten, nachdem eine Animationsupdate abgeschlossen ist.  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="a-nameonpreupdatea--canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 Behandelt Ereignisse, die auftreten, bevor ein Animationsupdate beginnt.  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="a-nameonrenderingtooslowa--canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 Behandelt Ereignisse, die auftreten, wenn die Rendering-Framerate für eine Animation unter die minimale erwünschte Framerate fällt.  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>Parameter  
 `fps`  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="a-namesetanimationcontrollera--canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfangen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

