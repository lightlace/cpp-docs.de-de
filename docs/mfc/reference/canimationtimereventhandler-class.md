---
title: CAnimationTimerEventHandler-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: c94cb3849d4101365d137733c08135b86db23801
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518663"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler-Klasse

Implementiert einen Rückruf, der von der Animations-API beim Auftreten von Zeitsteuerungsereignissen aufgerufen wird.

## <a name="syntax"></a>Syntax

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationTimerEventHandler` Rückruf.|
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Behandelt Ereignisse, die auftreten, nachdem ein Animationsupdate abgeschlossen ist. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.)|
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Behandelt Ereignisse, die auftreten, bevor ein Animationsupdate beginnt. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.)|
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Behandelt Ereignisse, die auftreten, wenn die minimale wünschenswert Framerate die Rendering-Framerate für eine Animation unterschreitet. (Überschreibt `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.)|
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler wird erstellt und an SetTimerEventHandler übergeben übergeben wird, wenn Sie mit CAnimationController:: EnableAnimationTimerEventHandler aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="createinstance"></a>  CAnimationTimerEventHandler::CreateInstance

Erstellt eine Instanz der CAnimationTimerEventHandler-Rückrufs.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

*ppTimerEventHandler*

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="onpostupdate"></a>  CAnimationTimerEventHandler::OnPostUpdate

Behandelt Ereignisse, die auftreten, nachdem ein Animationsupdate abgeschlossen ist.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="onpreupdate"></a>  CAnimationTimerEventHandler::OnPreUpdate

Behandelt Ereignisse, die auftreten, bevor ein Animationsupdate beginnt.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="onrenderingtooslow"></a>  CAnimationTimerEventHandler::OnRenderingTooSlow

Behandelt Ereignisse, die auftreten, wenn die minimale wünschenswert Framerate die Rendering-Framerate für eine Animation unterschreitet.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>Parameter

*f/s*

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationTimerEventHandler::SetAnimationController

Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
