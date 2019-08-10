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
ms.openlocfilehash: bd13ba4d0dd60f65372b2c1f51d70d338566301e
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916262"
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
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationManagerEventHandler` -Objekts.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|Wird aufgerufen, wenn sich der Status des Animations-Managers geändert hat. (Überschreibt `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.)|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animations Controller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler wird erstellt und an die iuianimationmanager:: setmanagereventhandler-Methode übergeben, wenn Sie canimationcontroller:: enableanimationmanagerevent aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>Canimationmanagereventhandler:: canimationmanagereventhandler

Visual Studio 2010 SP1 wird benötigt.

Erstellt ein canimationmanagereventhandler-Objekt.

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>Canimationmanagereventhandler:: forateinstance

Visual Studio 2010 SP1 wird benötigt.

Erstellt eine Instanz des canimationmanagereventhandler-Objekts.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animations Controller, von dem Ereignisse empfangen werden.

*ppManagerEventHandler*<br/>
Ausgeben. Wenn die Methode erfolgreich ausgeführt wird, enthält Sie einen Zeiger auf ein COM-Objekt, das Statusaktualisierungen für einen Animations-Manager behandelt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Andernfalls wird ein HRESULT-Fehlercode zurückgegeben.

##  <a name="onmanagerstatuschanged"></a>Canimationmanagereventhandler:: onmanagerstatuschangi

Visual Studio 2010 SP1 wird benötigt.

Wird aufgerufen, wenn sich der Status des Animations-Managers geändert hat.

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parameter

*newStatus*<br/>
Neuer Status.

*previousStatus*<br/>
Vorheriger Status.

### <a name="return-value"></a>Rückgabewert

Die aktuelle Implementierung gibt immer S_OK zurück.

##  <a name="setanimationcontroller"></a>Canimationmanagereventhandler:: "abationcontroller"

Visual Studio 2010 SP1 wird benötigt.

Speichert einen Zeiger auf den Animations Controller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animations Controller, von dem Ereignisse empfangen werden.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
