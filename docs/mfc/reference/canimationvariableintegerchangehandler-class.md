---
title: CAnimationVariableIntegerChangeHandler-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 5348c1cdb665c7b50e4f3bbb504ed9f7d6606ea4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler-Klasse
Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn sich der Wert einer Animationsvariablen ändert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Erstellt ein `CAnimationVariableIntegerChangeHandler`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|Erstellt eine Instanz des `CAnimationVariableIntegerChangeHandler` Rückruf.|  
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde. (Überschreibt `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`.)|  
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Ereignishandler erstellt und beim Aufrufen EnableIntegerValueChangedEvent oder CAnimationBaseObject (wodurch IUIAnimationVariable:: SetVariableIntegerChangeHandler-Methode übergeben Dieses Ereignis für alle in einem Animationsobjekt gekapselten Animationsvariablen).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [MFC-Klassen](../../mfc/reference/mfc-classes.md)  
  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableIntegerChangeHandlerBase`  
  
 `CAnimationVariableIntegerChangeHandler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="canimationvariableintegerchangehandler"></a>CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler  
 Erstellt ein CAnimationVariableIntegerChangeHandler-Objekt.  
  
```  
CAnimationVariableIntegerChangeHandler ();
```  
  
##  <a name="createinstance"></a>CAnimationVariableIntegerChangeHandler::CreateInstance  
 Erstellt eine Instanz des CAnimationVariableIntegerChangeHandler-Rückrufs.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.  
  
 `ppHandler`  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="onintegervaluechanged"></a>CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged  
 Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde.  
  
```  
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```  
  
### <a name="parameters"></a>Parameter  
 `storyboard`  
 Das Storyboard, das die Variable animiert.  
  
 `variable`  
 Die Animationsvariable, die aktualisiert wurde.  
  
 `newValue`  
 Der neue gerundete Wert.  
  
 `previousValue`  
 Der vorherige gerundete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL.  
  
##  <a name="setanimationcontroller"></a>CAnimationVariableIntegerChangeHandler::SetAnimationController  
 Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parameter  
 `pAnimationController`  
 Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

