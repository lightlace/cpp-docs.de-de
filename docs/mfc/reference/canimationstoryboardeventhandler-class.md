---
title: CAnimationStoryboardEventHandler-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler
dev_langs:
- C++
helpviewer_keywords:
- CAnimationStoryboardEventHandler class
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: bda8b0c941fd833bf821b563f4ca59cab9598cb8
ms.lasthandoff: 02/24/2017

---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler-Klasse
Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn der Status eines Drehbuchs geändert oder ein Storyboard aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Erstellt ein `CAnimationStoryboardEventHandler`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationStoryboardEventHandler` Rückruf.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Behandelt `OnStoryboardStatusChanged` -Ereignisse, die auftreten, wenn der Status eines Storyboards ändert (überschreibt `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Behandelt `OnStoryboardUpdated` Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird (überschreibt `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler wird erstellt und an `IUIAnimationStoryboard::SetStoryboardEventHandler` Methode beim Aufruf von `CAnimationController::EnableStoryboardEventHandler`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namecanimationstoryboardeventhandlera--canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a>CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler  
 Erstellt ein CAnimationStoryboardEventHandler-Objekt.  
  
```  
CAnimationStoryboardEventHandler();
```  
  
##  <a name="a-namecreateinstancea--canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a>CAnimationStoryboardEventHandler::CreateInstance  
 Erstellt eine Instanz des CAnimationStoryboardEventHandler-Rückrufs.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationStoryboardEventHandler** ppHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfangen wird.  
  
 `ppHandler`  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-nameonstoryboardstatuschangeda--canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>CAnimationStoryboardEventHandler::OnStoryboardStatusChanged  
 Behandelt OnStoryboardStatusChanged-Ereignisse, die auftreten, wenn der Status eines Storyboards ändert  
  
```  
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parameter  
 `storyboard`  
 Ein Zeiger auf Storyboard, dessen Status geändert hat.  
  
 `newStatus`  
 Gibt neue Storyboardstatus.  
  
 `previousStatus`  
 Gibt die vorherige Storyboardstatus.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="a-nameonstoryboardupdateda--canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>CAnimationStoryboardEventHandler::OnStoryboardUpdated  
 Behandelt OnStoryboardUpdated-Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird  
  
```  
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```  
  
### <a name="parameters"></a>Parameter  
 `storyboard`  
 Ein Zeiger auf storyboard, das aktualisiert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK zurück, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="a-namesetanimationcontrollera--canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationStoryboardEventHandler::SetAnimationController  
 Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfangen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

