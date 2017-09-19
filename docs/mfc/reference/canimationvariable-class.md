---
title: CAnimationVariable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CAnimationVariable class
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
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
ms.openlocfilehash: 42513c841f6dc891369d7d6640ced1aa37f90e8e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariable-class"></a>CAnimationVariable-Klasse
Stellt eine Animationsvariable dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Erstellt eine Variable Animation-Objekt.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Der Destruktor. Wird aufgerufen, wenn ein CAnimationVariable-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Fügt einen Übergang hinzu.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Fügt Übergänge aus der internen Liste Storyboard hinzu.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Löscht Übergänge.|  
|[CAnimationVariable::Create](#create)|Erstellt das zugrunde liegende Variable Animation COM-Objekt.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Erstellt alle Übergänge, die auf diese Animationsvariable angewendet werden.|  
|[EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Aktiviert oder deaktiviert das IntegerValueChanged-Ereignis.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Aktiviert oder deaktiviert das ValueChanged-Ereignis.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Gibt den Standardwert zurück.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Gibt das übergeordnete Animationsobjekt.|  
|[CAnimationVariable::GetValue](#getvalue)|Überladen. Gibt den aktuellen Wert der Animationsvariablen.|  
|[CAnimationVariable::GetVariable](#getvariable)|Gibt einen Zeiger auf IUIAnimationVariable-COM-Objekt.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Legt Standardwert fest und gibt IUIAnimationVariable-COM-Objekt frei.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Legt die Beziehung zwischen einer Animationsvariable und einem Animationsobjekt fest.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob verwandte Übergangsobjekte gelöscht werden soll.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Gibt den Standardwert an IUIAnimationVariable weitergegeben wird.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Enthält eine Liste der Übergänge, die diese Animationsvariable animieren.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Ein Zeiger auf ein Animationsobjekt, das diese Animationsvariable kapselt.|  
|[CAnimationVariable::m_variable](#m_variable)|Speichert einen Zeiger auf IUIAnimationVariable-COM-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde, oder wenn Fehler bei der Erstellung.|  
  
## <a name="remarks"></a>Hinweise  
 Die CAnimationVariable-Klasse kapselt IUIAnimationVariable-COM-Objekt. Sie enthält auch eine Liste von Übergängen, die auf die Animationsvariable in einem Storyboard angewendet werden. CAnimationVariable-Objekte werden für die Animationsobjekte, eingebettet, die in einer Anwendung einen animierten Wert, Punkt, Größe, Farbe und Rechteck darstellen können.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable  
 Der Destruktor. Wird aufgerufen, wenn ein CAnimationVariable-Objekt zerstört wird.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>CAnimationVariable::AddTransition  
 Fügt einen Übergang hinzu.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pTransition`  
 Ein Zeiger auf einen Übergang hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, um einen Übergang hinzuzufügen, der internen Liste von Übergängen, die auf die Animationsvariable angewendet werden. Diese Liste sollte gelöscht werden, wenn eine Animation geplant wurde.  
  
##  <a name="applytransitions"></a>CAnimationVariable::ApplyTransitions  
 Fügt Übergänge aus der internen Liste Storyboard hinzu.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 `pController`  
 Ein Zeiger auf den übergeordneten Animationscontroller.  
  
 `pStoryboard`  
 Ein Zeiger auf storyboard.  
  
 `bDependOnKeyframes`  
 TRUE, wenn diese Methode Übergänge hinzufügen soll, die von Keyframes abhängen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt Übergänge aus der internen Liste Storyboard. Er vom Code obersten Ebene mehrere Male aufgerufen wird, um Übergänge hinzuzufügen, die nicht von Keyframes abhängen, und fügen Übergänge, die von Keyframes abhängen. Wenn das zugrunde liegende Animationsvariablen-COM-Objekt nicht erstellt wurde, erstellt diese Methode es in dieser Phase.  
  
##  <a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable  
 Erstellt eine Variable Animation-Objekt.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Parameter  
 `dblDefaultValue`  
 Gibt den Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Animationsobjekt Variable und legt seinen Standardwert fest. Ein Standardwert wird verwendet, wenn eine Variable nicht animiert ist oder nicht animiert werden kann.  
  
##  <a name="cleartransitions"></a>CAnimationVariable::ClearTransitions  
 Löscht Übergänge.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutodestroy`  
 Gibt an, ob diese Methode Übergangsobjekte löschen soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt alle Übergänge aus der internen Liste von Übergängen. Wenn bAutodestroy TRUE ist oder M_bAutodestroyTransitions TRUE ist, werden dann Übergänge gelöscht. Andernfalls sollte der Aufrufer die Übergangsobjekte freigeben.  
  
##  <a name="create"></a>CAnimationVariable::Create  
 Erstellt das zugrunde liegende Variable Animation COM-Objekt.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>Parameter  
 `pManager`  
 Ein Zeiger auf Animations-Manager.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Animationsvariable erfolgreich erstellt wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt das zugrunde liegende Animationsvariablen-COM-Objekt und legt seinen Standardwert fest.  
  
##  <a name="createtransitions"></a>CAnimationVariable::CreateTransitions  
 Erstellt alle Übergänge, die auf diese Animationsvariable angewendet werden.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
`pLibrary`  
 Ein Zeiger auf eine [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Übergänge erfolgreich erstellt wurden. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn es benötigt, um Übergänge erstellen, die die Variable internen Liste von Übergängen hinzugefügt wurden.  
  
##  <a name="enableintegervaluechangedevent"></a>EnableIntegerValueChangedEvent  
 Aktiviert oder deaktiviert das IntegerValueChanged-Ereignis.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `pController`  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 `bEnable`  
 TRUE - Ereignis aktivieren, FALSE - Ereignis deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ValueChanged-Ereignis aktiviert ist, ruft das Framework die virtuelle Methode CAnimationController:: OnAnimationIntegerValueChanged auf. Sie müssen es in einer Klasse, um dieses Ereignis verarbeiten von CAnimationController abgeleiteten überschreiben. Diese Methode wird aufgerufen, jedes Mal, wenn der Ganzzahlwert der Animationsvariablen geändert wird.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent  
 Aktiviert oder deaktiviert das ValueChanged-Ereignis.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `pController`  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 `bEnable`  
 TRUE - Ereignis aktivieren, FALSE - Ereignis deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ValueChanged-Ereignis aktiviert ist, ruft das Framework die virtuelle Methode CAnimationController:: OnAnimationValueChanged. Sie müssen es in einer Klasse, um dieses Ereignis verarbeiten von CAnimationController abgeleiteten überschreiben. Diese Methode wird aufgerufen, jedes Mal, wenn der Wert der Animationsvariablen geändert wird.  
  
##  <a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue  
 Gibt den Standardwert zurück.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Standardwert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um den Standardwert der Animationsvariablen zu erhalten. Der Standardwert kann in Konstruktor oder durch SetDefaultValue-Methode festgelegt werden.  
  
##  <a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject  
 Gibt das übergeordnete Animationsobjekt.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf übergeordnetes Animationsobjekt, wenn die Beziehung festgelegt wurde, andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, um einen Zeiger auf ein übergeordnetes Animationsobjekt (einen Container) abzurufen.  
  
##  <a name="getvalue"></a>CAnimationVariable::GetValue  
 Gibt den aktuellen Wert der Animationsvariablen.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dblValue`  
 Der aktuelle Wert der Animationsvariablen.  
  
 `nValue`  
 Der aktuelle Wert der Animationsvariablen.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Wert erfolgreich abgerufen wurde oder die zugrunde liegende Animationsvariable wurde nicht erstellt. Andernfalls HRESULT-Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, um den aktuellen Wert der Animationsvariablen abzurufen. Wenn das zugrunde liegende COM-Objekt nicht erstellt wurde, enthält DblValue einen Standardwert, bei Rückgabe der Funktion.  
  
##  <a name="getvariable"></a>CAnimationVariable::GetVariable  
 Gibt einen Zeiger auf IUIAnimationVariable-COM-Objekt.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf IUIAnimationVariable-COM-Objekt oder NULL, wenn die Animationsvariable nicht erstellt wurde, oder es kann nicht erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Zugriff auf das zugrunde liegende IUIAnimationVariable-COM-Objekt und dessen Methoden bei Bedarf direkt aufzurufen.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationVariable::m_bAutodestroyTransitions  
 Gibt an, ob verwandte Übergangsobjekte gelöscht werden soll.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf "true" Force Löschen von aus, wenn sie aus der internen Liste von Übergängen entfernt werden. Wenn dieser Wert "false" sollte die Übergänge von der aufrufenden Anwendung gelöscht werden. Die Liste der Übergänge wird immer gelöscht, nachdem eine Animation geplant wurde. Der Standardwert ist FALSE.  
  
##  <a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue  
 Gibt den Standardwert an IUIAnimationVariable weitergegeben wird.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions  
 Enthält eine Liste der Übergänge, die diese Animationsvariable animieren.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject  
 Ein Zeiger auf ein Animationsobjekt, das diese Animationsvariable kapselt.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>CAnimationVariable::m_variable  
 Speichert einen Zeiger auf IUIAnimationVariable-COM-Objekt. NULL, wenn das COM-Objekt noch nicht erstellt wurde, oder wenn Fehler bei der Erstellung.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue  
 Legt Standardwert fest und gibt IUIAnimationVariable-COM-Objekt frei.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dblDefaultValue`  
 Gibt den neuen Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Standardwert zurückzusetzen. Diese Methode gibt das interne IUIAnimationVariable-COM-Objekt, daher frei, wenn Animationsvariablen neu erstellt wird, das zugrunde liegende COM-Objekt ruft den neuen Standardwert ab. Der Standardwert wird von GetValue zurückgegeben, wenn das COM-Objekt, das die Animationsvariable darstellt, nicht erstellt wurde, oder wenn die Variable nicht animiert wurde.  
  
##  <a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject  
 Legt die Beziehung zwischen einer Animationsvariable und einem Animationsobjekt fest.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentObject`  
 Ein Zeiger auf ein Animationsobjekt, das diese Variable enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern aufgerufen, um&1;:&1;-Beziehung zwischen einer Animationsvariablen und eines Animationsobjekts, das es kapselt herzustellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

