---
title: CAnimationBaseObject-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationBaseObject class
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c714c78b7017ed314b30f64df4bfceb587226c15
ms.lasthandoff: 02/24/2017

---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject-Klasse
Die Basisklasse für alle Animationsobjekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Überladen. Erstellt ein Animationsobjekt.|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Der Destruktor. Wird aufgerufen, wenn ein Animationsobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Fügt Übergänge mit gekapselter Animationsvariable Storyboard hinzu.|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Entfernt alle verwandten Übergänge.|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Bestimmt, ob ein Animationsobjekt eine bestimmte Animationsvariable enthält.|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Erstellt ein Animationsobjekt zugeordnete Übergänge.|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Trennt ein Animationsobjekt von übergeordnetem Animationscontroller.|  
|[CAnimationBaseObject](#enableintegervaluechangedevent)|Ereignishandler ganzzahligen Wert geändert wird.|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Ereignishandler Wert geändert wird.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Erfahren Sie, ob verwandter Übergang automatisch zerstört werden.|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Gibt aktuelle Gruppen-ID.|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Gibt aktuelle Objekt-ID.|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|Gibt benutzerdefinierte Daten zurück.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Legt ein Flag, das befiehlt, um Übergänge automatisch zu zerstören.|  
|[CAnimationBaseObject:: SetID](#setid)|Legt neue IDs fest.|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|Legt den benutzerdefinierten Daten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject:: GetAnimationVariableList](#getanimationvariablelist)|Sammelt Zeiger auf enthaltene Animationsvariablen.|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Beziehung zwischen in einem Animationsobjekt und ihrem Container enthaltenen Animationsvariablen hergestellt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob verwandte Übergänge automatisch zerstört werden soll.|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Speichert benutzerdefinierte Daten.|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Gibt die Gruppen-ID des Animationsobjekts an.|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Gibt die Objekt-ID des Animationsobjekts an.|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den übergeordneten Animationscontroller.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert grundlegende Methoden für alle Animationsobjekte. Ein Animationsobjekt kann ein Wert, der Punkt, der Größe, Rechteck darstellen oder Farbe in einer Anwendung als auch eine benutzerdefinierte Entität. Animationsobjekte werden in Animationsgruppen gespeichert (Siehe CAnimationGroup). Jede Gruppe kann getrennt animiert werden und als Entsprechung des Storyboards behandelt werden kann. Ein Animationsobjekt kapselt eine oder mehrere Animationsvariablen (Siehe CAnimationVariable), abhängig von seiner logischen Darstellung. CAnimationRect enthält z. B. vier Animationsvariablen - eine Variable für jede Seite des Rechtecks. Jede Animationsobjektklasse stellt überladene AddTransition-Methode, die verwendet werden sollte, um Übergänge auf gekapselte Animationsvariablen anzuwenden. Ein Animationsobjekt (optional) von Objekt-ID identifiziert werden und von Gruppen-ID. Wenn eine Gruppen-ID nicht angegeben ist, wird ein Objekt in der Standardgruppe mit der ID 0 platziert eine Gruppen-ID ist erforderlich, um ein Animationsobjekt zur richtigen Gruppe zu platzieren. Wenn Sie SetID mit einer anderen GroupID aufrufen, wird ein Animationsobjekt in eine andere Gruppe verschoben werden (eine neue Gruppe wird bei Bedarf erstellt).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: ~ CAnimationBaseObject  
 Der Destruktor. Wird aufgerufen, wenn ein Animationsobjekt zerstört wird.  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>CAnimationBaseObject::ApplyTransitions  
 Fügt Übergänge mit gekapselter Animationsvariable Storyboard hinzu.  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf ein Storyboard.  
  
 `bDependOnKeyframes`  
 Mit FALSE fügt diese Methode nur die Übergänge, die nicht von Keyframes abhängen.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Übergänge erfolgreich hinzugefügt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Fügt verwandte Übergänge, die mit AddTransition (überladene Methoden in abgeleiteten Klassen), um das storyboard hinzugefügt wurden.  
  
##  <a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject  
 Erstellt ein Animationsobjekt.  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nGroupID`  
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Benutzerdefinierte Daten, die Animationsobjekt zugeordnet und später zur Laufzeit abgerufen werden können.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt Animationsobjekte und weist Standard-Objekt-ID (0) und Gruppen-ID (0).  
  
##  <a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions  
 Entfernt alle verwandten Übergänge.  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutodestroy`  
 Gibt an, ob Übergangsobjekte automatisch zerstört, oder entfernen Sie sie einfach in der zugehörigen Liste.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle verwandten Übergänge und zerstört sie, wenn bAutodestroy oder M_bAutodestroyTransitions-Flag TRUE ist. Übergänge sollte automatisch zerstört werden, nur, wenn sie nicht auf dem Stapel zugeordnet werden. Wenn die oben genannten Flags falsch sind, werden die Übergänge nur aus der internen Liste der verwandten Übergänge entfernt.  
  
##  <a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable  
 Bestimmt, ob ein Animationsobjekt eine bestimmte Animationsvariable enthält.  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parameter  
 `pVariable`  
 Ein Zeiger auf eine Animationsvariable.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Animationsvariable im Animationsobjekt enthalten ist. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, um zu bestimmen, ob eine von pVariable angegebene Animationsvariable innerhalb eines Animationsobjekts enthalten ist. Ein Animationsobjekt, abhängig von deren Typ möglicherweise mehrere Animationsvariablen. CAnimationColor enthält z. B. drei Variablen, einen für jede Farbe-Komponente (Rot, Grün und Blau). Wenn der Wert ein Animationsvariablen geändert hat, sendet Windows Animations-API ValueChanged oder IntegerValueChanged-Ereignisse (falls aktiviert), und der Parameter für dieses Ereignis ist ein Zeiger auf IUIAnimationVariable-Schnittstelle der Animationsvariablen. Diese Methode hilft dabei, um einen Zeiger auf Animation von einem Zeiger auf eigenständigen COM-Objekt zu erhalten.  
  
##  <a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions  
 Erstellt ein Animationsobjekt zugeordnete Übergänge.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Übergänge erfolgreich erstellt wurden. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Durchläuft eine Liste von Animationsvariablen, die in einem abgeleiteten Animationsobjekt gekapselt und erstellt Übergänge, die jeder Animationsvariable zugeordnet.  
  
##  <a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController  
 Trennt ein Animationsobjekt von übergeordnetem Animationscontroller.  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern verwendet.  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationBaseObject  
 Ereignishandler ganzzahligen Wert geändert wird.  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `pController`  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 `bEnable`  
 Gibt an, ob aktivieren bzw. deaktivieren Sie die ganze Zahl ValueChanged-Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der ganzzahligen Wert geändert-Ereignishandler aktiviert ist, können Sie dieses Ereignis in der CAnimationController:: OnAnimationIntegerValueChanged-Methode behandeln, die in einer von CAnimationController abgeleiteten Klasse überschrieben werden soll. Diese Methode wird aufgerufen, jedes Mal, wenn der Ganzzahlwert der Animation geändert hat.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent  
 Ereignishandler Wert geändert wird.  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 `pController`  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 `bEnable`  
 Gibt an, ob aktivieren bzw. deaktivieren Sie ValueChanged-Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der ValueChanged-Ereignishandler aktiviert ist, können Sie dieses Ereignis in der CAnimationController:: OnAnimationValueChanged-Methode behandeln, die in einer von CAnimationController abgeleiteten Klasse überschrieben werden soll. Diese Methode wird aufgerufen, jedes Mal, wenn der Animationswert geändert wurde.  
  
##  <a name="getanimationvariablelist"></a>CAnimationBaseObject:: GetAnimationVariableList  
 Sammelt Zeiger auf enthaltene Animationsvariablen.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Eine Liste, die mit in einem Animationsobjekt enthaltenen Animationsvariablen gefüllt werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine rein virtuelle Methode, die in einer abgeleiteten Klasse überschrieben werden muss. Ein Animationsobjekt, abhängig von deren Typ enthält eine oder mehrere Animationsvariablen. CAnimationPoint enthält z. B. zwei Variablen für X- und Y-Koordinaten. Die Basisklasse CAnimationBaseObject implementiert einige generischen Methoden, die eine Liste von Animationsvariablen fungieren: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Diese Methoden rufen GetAnimationVariableList auf, die in einer abgeleiteten Klasse mit tatsächlichen Animationsvariablen aus einem bestimmten Animationsobjekt aufgefüllt wird, und klicken Sie dann die Liste durchlaufen und erforderliche Aktionen ausführen. Wenn Sie ein benutzerdefiniertes Animationsobjekt erstellen, müssen Sie lst alle in diesem Objekt enthaltene Animationsvariablen hinzufügen.  
  
##  <a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions  
 Erfahren Sie, ob verwandter Übergang automatisch zerstört werden.  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn TRUE, werden verknüpfte Übergänge automatisch zerstört; Wenn FALSE, sollten Übergangsobjekte von der aufrufenden Anwendung freigegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist dieses Flag TRUE. Legen Sie dieses Flag nur, wenn Sie die Umstellung auf dem Stapel zugeordnet bzw. Übergänge von der aufrufenden Anwendung aufgehoben werden soll.  
  
##  <a name="getgroupid"></a>CAnimationBaseObject::GetGroupID  
 Gibt aktuelle Gruppen-ID.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Gruppen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Abrufen der Gruppen-ID. Es handelt sich 0 Wenn Gruppen-ID nicht explizit in Konstruktor oder mit SetID festgelegt wurde.  
  
##  <a name="getobjectid"></a>CAnimationBaseObject::GetObjectID  
 Gibt aktuelle Objekt-ID.  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Objekt-ID.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Abrufen der Objekt-ID. Es macht 0, wenn die Objekt-ID nicht explizit in Konstruktor oder mit SetID festgelegt wurde.  
  
##  <a name="getuserdata"></a>CAnimationBaseObject::GetUserData  
 Gibt benutzerdefinierte Daten zurück.  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert von benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die benutzerdefinierten Daten zur Laufzeit abzurufen. Der zurückgegebene Wert ist 0, wenn er nicht explizit in Konstruktor oder mit SetUserData initialisiert wurde.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions  
 Gibt an, ob verwandte Übergänge automatisch zerstört werden soll.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData  
 Speichert benutzerdefinierte Daten.  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID  
 Gibt die Gruppen-ID des Animationsobjekts an.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID  
 Gibt die Objekt-ID des Animationsobjekts an.  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController  
 Ein Zeiger auf den übergeordneten Animationscontroller.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyTransitions  
 Legt ein Flag, das befiehlt, um Übergänge automatisch zu zerstören.  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>Parameter  
 `bValue`  
 Gibt an, das automatische Löschen Flag.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Flag nur, wenn Sie Übergangsobjekte mit dem Operator new zugeordnet. Wenn aus irgendeinem Grund Übergangsobjekte auf dem Stapel zugeordnet sind, automatisch zerstört sollte das Flag "false". Standardmäßig ist dieses Flag TRUE.  
  
##  <a name="setid"></a>CAnimationBaseObject:: SetID  
 Legt neue IDs fest.  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nObjectID`  
 Gibt das neue Objekt-ID an  
  
 `nGroupID`  
 Gibt neue Gruppen-ID an.  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht das Ändern der Objekt-ID und Gruppen-ID Wenn die neue Gruppen-ID von der aktuellen ID unterscheidet, wird ein Animationsobjekt in eine andere Gruppe verschoben (eine neue Gruppe wird, bei Bedarf erstellt werden).  
  
##  <a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects  
 Beziehung zwischen in einem Animationsobjekt und ihrem Container enthaltenen Animationsvariablen hergestellt.  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsklasse, die zum Erstellen der Beziehung zwischen in einem Animationsobjekt und ihrem Container enthaltenen Animationsvariablen verwendet werden kann. Sie durchläuft Animationsvariablen und ein Back-Zeiger auf ein übergeordnetes Animationsobjekt für jede Animationsvariable festgelegt. In der aktuellen Implementierung, die tatsächlichen Beziehung in CAnimationBaseObject::ApplyTransitions hergestellt wird, werden Back Zeiger daher nicht festgelegt, bis Sie CAnimationGroup::Animate aufrufen. Kennen die Beziehung kann hilfreich sein, wenn Sie die Verarbeitung von Ereignissen und Grund, die eine Animation für die übergeordnete über CAnimationVariable (verwenden Sie CAnimationVariable::GetParentAnimationObject) Objekt.  
  
##  <a name="setuserdata"></a>CAnimationBaseObject::SetUserData  
 Legt den benutzerdefinierten Daten.  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>Parameter  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine benutzerdefinierte Daten einem Animationsobjekt zuzuordnen. Diese Daten können später von GetUserData zur Laufzeit abgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

