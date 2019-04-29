---
title: CAnimationVariableIntegerChangeHandler-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: e1c3dc080c23ba4ac05539674047a66059ce52d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338180"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler-Klasse

Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn sich der Wert einer Animationsvariablen ändert.

## <a name="syntax"></a>Syntax

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Erstellt ein `CAnimationVariableIntegerChangeHandler`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationVariableIntegerChangeHandler` Rückruf.|
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde. (Überschreibt `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`.)|
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler erstellt und an IUIAnimationVariable::SetVariableIntegerChangeHandler Methode übergeben, wenn Sie die EnableIntegerValueChangedEvent oder CAnimationBaseObject (Dies ermöglicht das Aufrufen Dieses Ereignis für alle Animationsvariablen, die in ein Animationsobjekt gekapselt).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[MFC-Klassen](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="canimationvariableintegerchangehandler"></a>  CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler

Erstellt ein CAnimationVariableIntegerChangeHandler-Objekt.

```
CAnimationVariableIntegerChangeHandler ();
```

##  <a name="createinstance"></a>  CAnimationVariableIntegerChangeHandler::CreateInstance

Erstellt eine Instanz des CAnimationVariableIntegerChangeHandler-Rückrufs.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

*ppHandler*

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="onintegervaluechanged"></a>  CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged

Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>Parameter

*storyboard*<br/>
Das Storyboard, das die Variable animiert wird.

*variable*<br/>
Die Animationsvariable, die aktualisiert wurde.

*newValue*<br/>
Der neue gerundeten Wert.

*previousValue*<br/>
Der vorherige gerundeten Wert.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationVariableIntegerChangeHandler::SetAnimationController

Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
