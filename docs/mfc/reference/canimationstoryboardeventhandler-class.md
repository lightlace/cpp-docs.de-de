---
title: CAnimationStoryboardEventHandler-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1235ff529a39f84923b1bf08880c72c94f53abc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389008"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler-Klasse

Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn der Status eines Drehbuchs geändert oder ein Storyboard aktualisiert wird.

## <a name="syntax"></a>Syntax

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Erstellt ein `CAnimationStoryboardEventHandler`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationStoryboardEventHandler` Rückruf.|
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Behandelt `OnStoryboardStatusChanged` Ereignisse, die auftreten, wenn sich der Status eines Storyboards ändert (überschreibt `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Behandelt `OnStoryboardUpdated` Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird (überschreibt `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler erstellt und übergeben `IUIAnimationStoryboard::SetStoryboardEventHandler` Methode, die beim Aufrufen `CAnimationController::EnableStoryboardEventHandler`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="canimationstoryboardeventhandler"></a>  CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler

Erstellt ein CAnimationStoryboardEventHandler-Objekt.

```
CAnimationStoryboardEventHandler();
```

##  <a name="createinstance"></a>  CAnimationStoryboardEventHandler::CreateInstance

Erstellt eine Instanz des CAnimationStoryboardEventHandler-Rückrufs.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

*ppHandler*

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="onstoryboardstatuschanged"></a>  CAnimationStoryboardEventHandler::OnStoryboardStatusChanged

Behandelt OnStoryboardStatusChanged-Ereignisse, die auftreten, wenn der Status eines Storyboards ändert

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parameter

*Storyboard*<br/>
Ein Zeiger auf das Storyboard, deren Status geändert hat.

*newStatus*<br/>
Gibt neue Storyboardstatus an.

*previousStatus*<br/>
Gibt die vorherige Storyboardstatus an.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="onstoryboardupdated"></a>  CAnimationStoryboardEventHandler::OnStoryboardUpdated

Handles OnStoryboardUpdated-Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>Parameter

*Storyboard*<br/>
Ein Zeiger auf storyboard, das aktualisiert wurde.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationStoryboardEventHandler::SetAnimationController

Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
