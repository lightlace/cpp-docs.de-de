---
title: CAnimationManagerEventHandler-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: 6661da55d1091394cff9db4589bc05c721b5ab7c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281069"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler-Klasse

Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn der Status eines Animations-Managers geändert wird.

## <a name="syntax"></a>Syntax

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|Erstellt ein `CAnimationManagerEventHandler`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationManagerEventHandler` Objekt.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|Aufgerufen, wenn der Status der Animations-Manager geändert wurde. (Überschreibt `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.)|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler wird erstellt und an IUIAnimationManager::SetManagerEventHandler Methode übergeben, wenn Sie CAnimationController::EnableAnimationManagerEvent aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler

Visual Studio 2010 SP1 wird benötigt.

Erstellt ein CAnimationManagerEventHandler-Objekt.

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance

Visual Studio 2010 SP1 wird benötigt.

Erstellt eine Instanz eines CAnimationManagerEventHandler-Objekts.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

*ppManagerEventHandler*<br/>
Die Ausgabe. Wenn die Methode erfolgreich, es ist enthält einen Zeiger für COM-Objekt, das statusaktualisierungen an eine Animations-Manager behandelt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged

Visual Studio 2010 SP1 wird benötigt.

Aufgerufen, wenn der Status der Animations-Manager geändert wurde.

```
IFACEMETHOD(OnManagerStatusChanged)(
  UI_ANIMATION_MANAGER_STATUS newStatus,
  UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parameter

*newStatus*<br/>
Neuer Status.

*previousStatus*<br/>
Vorherigen Status.

### <a name="return-value"></a>Rückgabewert

Immer die aktuelle Implementierung gibt S_OK zurück.

##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController

Visual Studio 2010 SP1 wird benötigt.

Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
