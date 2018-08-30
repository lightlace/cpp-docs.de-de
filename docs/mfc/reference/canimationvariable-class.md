---
title: CAnimationVariable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 964d5691baf47adc51663d2de19c58ee6dfe0cc8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216909"
---
# <a name="canimationvariable-class"></a>CAnimationVariable-Klasse
Stellt eine Animationsvariable dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Erstellt eine Animation-Variable-Objekt.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Der Destruktor. Wird aufgerufen, wenn ein CAnimationVariable-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Fügt einen Übergang.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Fügt die Übergänge aus der internen Liste Storyboard hinzu.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Löscht die Übergänge.|  
|[CAnimationVariable::Create](#create)|Erstellt das zugrunde liegende Animation Variable-COM-Objekt.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Erstellt alle Übergänge, die auf diese Animationsvariable angewendet werden.|  
|[EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Aktiviert oder deaktiviert das IntegerValueChanged-Ereignis.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Aktiviert oder deaktiviert das ValueChanged-Ereignis.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Gibt den Standardwert zurück.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Gibt das übergeordnete Animationsobjekt.|  
|[CAnimationVariable::GetValue](#getvalue)|Überladen. Gibt den aktuellen Wert der Animationsvariablen zurück.|  
|[CAnimationVariable::GetVariable](#getvariable)|Gibt einen Zeiger auf IUIAnimationVariable COM-Objekt.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Legt Standardwert fest, und gibt Sie IUIAnimationVariable COM-Objekt frei.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Legt die Beziehung zwischen einer Animationsvariablen und ein Animationsobjekt fest.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob verwandte Übergangsobjekte gelöscht werden soll.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Gibt den Standardwert, der an IUIAnimationVariable weitergegeben wird.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Enthält eine Liste der Übergänge, die diese Animationsvariable animieren.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Ein Zeiger auf eine Animationsobjekt, das diese Animationsvariable kapselt.|  
|[CAnimationVariable::m_variable](#m_variable)|Speichert einen Zeiger auf IUIAnimationVariable COM-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde oder wenn der Fehler bei der Erstellung.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationVariable-Klasse kapselt IUIAnimationVariable COM-Objekt. Sie enthält auch eine Liste der Übergänge, die auf die Animationsvariable in einem Storyboard angewendet werden. CAnimationVariable-Objekte werden für Animationsobjekte, eingebettet, die in eine Anwendung einen animierten Wert, Punkt, Größe, Farbe und Rechteck darstellen kann.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable:: ~ CAnimationVariable  
 Der Destruktor. Wird aufgerufen, wenn ein CAnimationVariable-Objekt zerstört wird.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>  CAnimationVariable::AddTransition  
 Fügt einen Übergang.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parameter  
 *pTransition*  
 Ein Zeiger auf einen Übergang hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, um einen Übergang hinzuzufügen, das der internen Liste von Übergängen, die auf die Animationsvariable angewendet werden. Diese Liste sollte gelöscht werden, wenn eine Animation geplant wurde.  
  
##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions  
 Fügt die Übergänge aus der internen Liste Storyboard hinzu.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 *pController*  
 Ein Zeiger auf den übergeordneten Animationscontroller.  
  
 *pStoryboard*  
 Ein Zeiger auf das storyboard.  
  
 *bDependOnKeyframes*  
 TRUE, wenn diese Methode sollte Übergänge hinzugefügt werden, die von Keyframes abhängen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt Übergänge, aus der internen Liste Storyboard. Es aus der obersten Ebene Code mehrmals aufgerufen wird, um Übergänge hinzuzufügen, die nicht abhängig von Keyframes und Übergänge hinzufügen, die von Keyframes abhängen. Wenn das zugrunde liegende Animationsvariablen COM-Objekt nicht erstellt wurde, erstellt diese Methode es in dieser Phase an.  
  
##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable  
 Erstellt eine Animation-Variable-Objekt.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Parameter  
 *dblDefaultValue*  
 Gibt den Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Animationsobjekt Variable und legt seinen Standardwert fest. Wenn eine Variable nicht animiert ist, oder kann nicht animiert werden, wird ein Standardwert verwendet.  
  
##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions  
 Löscht die Übergänge.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutodestroy*  
 Gibt an, ob es sich bei dieser Methode sollten Übergangsobjekte löschen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt alle Übergänge aus der internen Liste von Übergängen an. Wenn bAutodestroy "true ist" oder M_bAutodestroyTransitions TRUE ist, sind Übergänge gelöscht. Andernfalls muss der Aufrufer die Übergangsobjekte freigeben.  
  
##  <a name="create"></a>  CAnimationVariable::Create  
 Erstellt das zugrunde liegende Animation Variable-COM-Objekt.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>Parameter  
 *pManager*  
 Ein Zeiger auf die Animations-Manager.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Animationsvariablen erfolgreich erstellt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt das zugrunde liegende Animationsvariablen COM-Objekt und legt seinen Standardwert fest.  
  
##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions  
 Erstellt alle Übergänge, die auf diese Animationsvariable angewendet werden.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
*pLibrary*  
 Ein Zeiger auf ein [IUIAnimationTransitionLibrary Schnittstelle](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), das eine Bibliothek mit standard-Übergänge definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Übergänge erfolgreich erstellt wurden. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn es benötigt, um Übergänge erstellen, die den Wert der Variablen internen Liste von Übergängen hinzugefügt wurden.  
  
##  <a name="enableintegervaluechangedevent"></a>  EnableIntegerValueChangedEvent  
 Aktiviert oder deaktiviert das IntegerValueChanged-Ereignis.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *pController*  
 Ein Zeiger auf den übergeordneten Controller.  
  
 *bAktivieren*  
 Deaktivieren Sie "true" - Ereignis "aktivieren", "false" - Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ValueChanged-Ereignis aktiviert ist, ruft das Framework virtuelle Methode CAnimationController:: OnAnimationIntegerValueChanged an. Sie müssen es in einer Klasse, die von CAnimationController abgeleitet werden, um die Verarbeitung dieses Ereignisses zu überschreiben. Diese Methode wird aufgerufen, jedes Mal, wenn der ganzzahlige Wert der Animationsvariablen geändert wird.  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent  
 Aktiviert oder deaktiviert das ValueChanged-Ereignis.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *pController*  
 Ein Zeiger auf den übergeordneten Controller.  
  
 *bAktivieren*  
 Deaktivieren Sie "true" - Ereignis "aktivieren", "false" - Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ValueChanged-Ereignis aktiviert ist, ruft das Framework virtuelle Methode CAnimationController:: OnAnimationValueChanged an. Sie müssen es in einer Klasse, die von CAnimationController abgeleitet werden, um die Verarbeitung dieses Ereignisses zu überschreiben. Diese Methode wird aufgerufen, jedes Mal, wenn der Wert der Animationsvariablen geändert wird.  
  
##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue  
 Gibt den Standardwert zurück.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Standardwert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Abrufen der Standardwert der Animationsvariablen an. Standardmäßig ist der Wert kann im Konstruktor oder durch SetDefaultValue-Methode festgelegt werden.  
  
##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject  
 Gibt das übergeordnete Animationsobjekt.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Animation-Objekt, wenn die Beziehung hergestellt wurde, andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, um einen Zeiger auf ein übergeordnetes Animation-Objekt (einen Container) abzurufen.  
  
##  <a name="getvalue"></a>  CAnimationVariable::GetValue  
 Gibt den aktuellen Wert der Animationsvariablen zurück.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Parameter  
 *dblValue*  
 Der aktuelle Wert der Animationsvariablen.  
  
 *nWert*  
 Der aktuelle Wert der Animationsvariablen.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Wert erfolgreich abgerufen wurde, oder zugrunde liegenden Animationsvariablen nicht erstellt wurde noch. Andernfalls HRESULT-Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, um den aktuellen Wert der Animationsvariablen abzurufen. Wenn das zugrunde liegende COM-Objekt nicht erstellt wurde, enthält DblValue bei Rückgabe der Funktion einen Standardwert.  
  
##  <a name="getvariable"></a>  CAnimationVariable::GetVariable  
 Gibt einen Zeiger auf IUIAnimationVariable COM-Objekt.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf IUIAnimationVariable-COM-Objekt oder NULL, wenn der Animationsvariablen nicht erstellt wurde, oder kann nicht erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um Zugriff auf das zugrunde liegende IUIAnimationVariable-COM-Objekt und dessen Methoden direkt aufzurufen, wenn erforderlich.  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions  
 Gibt an, ob verwandte Übergangsobjekte gelöscht werden soll.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf "true"-Force Übergangsobjekte löschen, wenn sie aus der internen Liste von Übergängen entfernt werden. Wenn dieser Wert "false" sollte die Übergänge von der aufrufenden Anwendung gelöscht werden. Die Liste der Übergänge ist immer deaktiviert, wenn es sich bei eine Animation geplant wurde. Der Standardwert ist "false".  
  
##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue  
 Gibt den Standardwert, der an IUIAnimationVariable weitergegeben wird.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions  
 Enthält eine Liste der Übergänge, die diese Animationsvariable animieren.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject  
 Ein Zeiger auf eine Animationsobjekt, das diese Animationsvariable kapselt.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>  CAnimationVariable::m_variable  
 Speichert einen Zeiger auf IUIAnimationVariable COM-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde oder wenn der Fehler bei der Erstellung.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue  
 Legt Standardwert fest, und gibt Sie IUIAnimationVariable COM-Objekt frei.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parameter  
 *dblDefaultValue*  
 Gibt den neuen Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Standardwert zurückzusetzen. Diese Methode gibt das interne IUIAnimationVariable-COM-Objekt, aus diesem Grund frei, wenn Animationsvariablen neu erstellt wird, ruft das zugrunde liegende COM-Objekt ab, den neuen Standardwert. Der Standardwert wird von "GetValue" zurückgegeben, wenn das COM-Objekt, das die Animationsvariable darstellt, nicht erstellt wurde, oder wenn die Variable nicht animiert wurde.  
  
##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject  
 Legt die Beziehung zwischen einer Animationsvariablen und ein Animationsobjekt fest.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentObject*  
 Ein Zeiger auf eine Animationsobjekt, das diese Variable enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern aufgerufen, um 1: 1-Beziehung zwischen einer Animationsvariablen und eines Animationsobjekts, das diese kapselt herstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
