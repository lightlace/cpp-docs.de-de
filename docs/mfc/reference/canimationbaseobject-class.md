---
title: CAnimationBaseObject-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 135bb279daf4c000c025ac6f8fa51a6b023e2d1e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952543"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject-Klasse
Die Basisklasse für alle Animationsobjekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Überladen. Erstellt eine Animationsobjekt.|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Der Destruktor. Wird aufgerufen, wenn eine Animationsobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Fügt Übergänge mit gekapselten Animationsvariablen Storyboard hinzu.|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Entfernt alle zugehörigen Übergänge an.|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Bestimmt, ob eine Animationsobjekt einer bestimmten Animationsvariablen enthält.|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Erstellt eine Animationsobjekt zugeordneten Übergänge.|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Trennt eine Animationsobjekts aus übergeordneten Animationscontroller.|  
|[CAnimationBaseObject](#enableintegervaluechangedevent)|Richtet ein Ereignishandler ganzzahligen Wert geändert.|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Richtet ein Ereignishandler Wert geändert.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Erfahren Sie, ob verwandter Übergang automatisch zerstört wird.|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Gibt aktuelle Gruppen-ID.|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Gibt die vom aktuellen Objekt-ID.|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|Gibt eine benutzerdefinierte Daten zurück.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Setzt ein Flag, das sortiert Übergänge automatisch zerstört.|  
|[CAnimationBaseObject:: SetID](#setid)|Legt neue IDs.|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|Legt benutzerdefinierte Daten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject:: GetAnimationVariableList](#getanimationvariablelist)|Sammelt Zeiger auf enthaltene Animationsvariablen.|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Stellt die Beziehung zwischen Animationsvariablen in ein Animationsobjekt und der Container her.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Gibt an, ob die zugehörigen Übergänge automatisch zerstört werden soll.|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Speichert benutzerdefinierte Daten.|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Gibt die ID des Animationsobjekts an.|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Gibt die Objekt-ID des Animationsobjekts.|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Ein Zeiger auf den übergeordneten Animationscontroller.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert grundlegende Methoden für alle Animationsobjekte. Ein Animationsobjekt kann darstellen, ein Wert, der Punkt, der Größe, Rechteck oder Farbe in eine Anwendung als auch eine benutzerdefinierte Entität. Animationsobjekte werden in Animationsgruppen gespeichert (Siehe CAnimationGroup). Jeder Gruppe separat animiert werden kann und als Entsprechung des Storyboards behandelt werden kann. Ein Animationsobjekt kapselt eine oder mehrere Animationsvariablen (Siehe CAnimationVariable), abhängig von seiner logischen Darstellung. CAnimationRect enthält z. B. vier Animationsvariablen - eine Variable für jede Seite des Rechtecks. Jede Animationsobjektklasse macht überladene AddTransition-Methode, die anzuwendende Übergänge auf gekapselte Animationsvariablen verwendet werden soll. Ein Animationsobjekt kann von Objekt-ID (optional) identifiziert werden und nach Gruppen-ID. Eine Gruppen-ID ist erforderlich, um eine Animationsobjekt zur richtigen Gruppe platzieren, aber wenn eine Gruppen-ID nicht angegeben ist, wird ein Objekt in der Standardgruppe mit der ID 0 platziert. Wenn Sie SetID mit einer anderen GroupID aufrufen, wird ein Animationsobjekt in eine andere Gruppe verschoben werden (eine neue Gruppe wird bei Bedarf erstellt).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject  
 Der Destruktor. Wird aufgerufen, wenn eine Animationsobjekt zerstört wird.  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions  
 Fügt Übergänge mit gekapselten Animationsvariablen Storyboard hinzu.  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parameter  
 *pStoryboard*  
 Ein Zeiger auf ein Storyboard.  
  
 *bDependOnKeyframes*  
 Mit "false" fügt diese Methode nur die Übergänge, die nicht von Keyframes abhängen.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn Übergänge erfolgreich hinzugefügt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Fügt die zugehörigen Übergänge, die mit AddTransition (überladene Methoden in abgeleiteten Klassen) Storyboard hinzugefügt wurden.  
  
##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject  
 Erstellt eine Animationsobjekt.  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *nGroupID*  
 Gibt Gruppen-ID.  
  
 *nObjectID*  
 Gibt die Objekt-ID.  
  
 *dwUserData*  
 Benutzerdefinierte Daten, die Animationsobjekt zugeordnet und später zur Laufzeit abgerufen werden können.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt eine Animationsobjekte, und weist Standard-Objekt-ID (0) und Gruppen-ID (0).  
  
##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions  
 Entfernt alle zugehörigen Übergänge an.  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutodestroy*  
 Gibt an, ob automatisch, Objekte zu zerstören oder entfernen Sie diese einfach aus der verknüpften Liste.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle verwandten Übergänge und zerstört werden, wenn bAutodestroy oder M_bAutodestroyTransitions-Flag auf "true" ist. Übergänge sollte automatisch zerstört werden, nur dann, wenn sie nicht auf dem Stapel zugeordnet sind. Wenn die oben genannten Flags auf "false" sind, werden die Übergänge aus der internen Liste der zugehörigen Übergänge einfach entfernt.  
  
##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable  
 Bestimmt, ob eine Animationsobjekt einer bestimmten Animationsvariablen enthält.  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parameter  
 *pVariable*  
 Ein Zeiger auf Animationsvariablen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Animationsvariablen im Animationsobjekt enthalten ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, um zu bestimmen, ob eine von pVariable angegebene Animationsvariable innerhalb eines Animationsobjekts enthalten ist. Ein Animationsobjekts, abhängig vom Anwendungstyp, möglicherweise mehrere Animationsvariablen enthalten. CAnimationColor enthält z. B. drei Variablen, eine für jede Farbe-Komponente (Rot, Grün und Blau). Wenn der Wert ein Animationsvariablen geändert hat, sendet Windows Animation API ValueChanged oder IntegerValueChanged-Ereignisse (sofern aktiviert), und der Parameter für dieses Ereignis ist ein Zeiger auf IUIAnimationVariable Animationsvariablen-Schnittstelle. Diese Methode hilft, um einen Zeiger auf Animation von einem Zeiger auf eigenständigen COM-Objekt zu erhalten.  
  
##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions  
 Erstellt eine Animationsobjekt zugeordneten Übergänge.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Übergänge erfolgreich erstellt wurden. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Durchläuft eine Liste von Animationsvariablen in einem abgeleiteten Animationsobjekt gekapselt, und jede Animationsvariablen zugeordnete Übergänge erstellt.  
  
##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController  
 Trennt eine Animationsobjekts aus übergeordneten Animationscontroller.  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern verwendet.  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject  
 Richtet ein Ereignishandler ganzzahligen Wert geändert.  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *pController*  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 *bAktivieren*  
 Gibt an, ob aktivieren oder Deaktivieren der ganzzahlige Wert ausgelöstes Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der ganzzahlige Wert geändert Ereignishandler aktiviert ist, können Sie dieses Ereignis in der CAnimationController:: OnAnimationIntegerValueChanged-Methode behandeln, die in einer CAnimationController abgeleiteten Klasse überschrieben werden sollte. Diese Methode wird aufgerufen, jedes Mal, wenn die Animation Integer-Wert geändert wurde.  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent  
 Richtet ein Ereignishandler Wert geändert.  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *pController*  
 Ein Zeiger auf einen übergeordneten Controller.  
  
 *bAktivieren*  
 Gibt an, ob aktivieren oder Deaktivieren von Ereignis Wert geändert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert geändert Ereignishandler aktiviert ist, können Sie dieses Ereignis in der CAnimationController:: OnAnimationValueChanged-Methode behandeln, die in einer CAnimationController abgeleiteten Klasse überschrieben werden sollte. Diese Methode wird aufgerufen, jedes Mal, wenn der Animationswert geändert hat.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject:: GetAnimationVariableList  
 Sammelt Zeiger auf enthaltene Animationsvariablen.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *lst*  
 Eine Liste, die mit in einem Animationsobjekt enthaltenen Animationsvariablen gefüllt werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine rein virtuelle Methode, die in einer abgeleiteten Klasse überschrieben werden muss. Ein Animationsobjekts, abhängig von deren Typ enthält eine oder mehrere Animationsvariablen. CAnimationPoint enthält z. B. zwei Variablen für X- und Y-Koordinaten. Die Basisklasse CAnimationBaseObject implementiert einige generischen Methoden, die sich auf eine Liste der Animationsvariablen: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Diese Methoden rufen GetAnimationVariableList auf, der in einer abgeleiteten Klasse mit tatsächlichen Animationsvariablen in einer bestimmten Animationsobjekts gefüllt ist, und klicken Sie dann Schleife in der Liste und erforderliche Aktionen ausführen. Wenn Sie einen benutzerdefinierten Animation-Objekt erstellen, müssen Sie alle in diesem Objekt enthaltene Animationsvariablen lst hinzufügen.  
  
##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions  
 Erfahren Sie, ob verwandter Übergang automatisch zerstört wird.  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei "true", werden die zugehörigen Übergänge automatisch zerstört; Wenn "false" sollte Übergangsobjekte freigegeben werden, von der aufrufenden Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag ist standardmäßig "Wahr" an. Legen Sie dieses Flag nur, wenn Sie die Umstellung auf dem Stapel zugeordnet und/oder Übergänge von der aufrufenden Anwendung aufgehoben werden soll.  
  
##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID  
 Gibt aktuelle Gruppen-ID.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Gruppen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Abrufen der Gruppen-ID. Es handelt sich um 0 Wenn Gruppen-ID nicht explizit im Konstruktor oder mit SetID festgelegt wurde.  
  
##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID  
 Gibt die vom aktuellen Objekt-ID.  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Objekt-ID.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie Objekt-ID abzurufen. Es handelt sich um 0 Wenn Objekt-ID nicht explizit im Konstruktor oder mit SetID festgelegt wurde.  
  
##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData  
 Gibt eine benutzerdefinierte Daten zurück.  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert von benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der benutzerdefinierten Daten zur Laufzeit. Der zurückgegebene Wert ist 0, wenn sie nicht explizit im Konstruktor oder mit SetUserData initialisiert wurde.  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions  
 Gibt an, ob die zugehörigen Übergänge automatisch zerstört werden soll.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData  
 Speichert benutzerdefinierte Daten.  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID  
 Gibt die ID des Animationsobjekts an.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID  
 Gibt die Objekt-ID des Animationsobjekts.  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController  
 Ein Zeiger auf den übergeordneten Animationscontroller.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions  
 Setzt ein Flag, das sortiert Übergänge automatisch zerstört.  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>Parameter  
 *bValue*  
 Gibt an, die automatische zerstören Flag.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Flag nur, wenn Sie den Übergangsobjekte, die mit dem Operator new zugeordnet. Wenn aus irgendeinem Grund Übergangsobjekte auf dem Stapel zugeordnet sind, automatisch zerstört sollte das Flag "false". Dieses Flag ist standardmäßig "Wahr" an.  
  
##  <a name="setid"></a>  CAnimationBaseObject:: SetID  
 Legt neue IDs.  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *nObjectID*  
 Gibt das neue Objekt-ID an  
  
 *nGroupID*  
 Gibt die neuen Gruppen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht das Ändern von Objekt-ID und Gruppen-ID. Wenn sich die neuen Gruppen-ID aus der aktuellen ID unterscheidet, wird ein Animationsobjekt in eine andere Gruppe verschoben (eine neue Gruppe wird bei Bedarf erstellt, werden).  
  
##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects  
 Stellt die Beziehung zwischen Animationsvariablen in ein Animationsobjekt und der Container her.  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Hilfsprogramm, die zum Herstellen der Beziehung zwischen Animationsvariablen in ein Animationsobjekt und der Container verwendet werden kann. Es durchläuft Animationsvariablen und legt ein rückzeiger auf eine Animation des übergeordneten Objekts für jede Animationsvariable. In der aktuellen Implementierung, die die tatsächlichen Beziehung in CAnimationBaseObject::ApplyTransitions hergestellt wird, werden Back Zeiger aus diesem Grund nicht festgelegt, bis Sie CAnimationGroup::Animate aufrufen. Kennen die Beziehung kann hilfreich sein, wenn Sie die Verarbeitung von Ereignissen und muss eine übergeordnete Animation abrufen aus CAnimationVariable (verwenden Sie CAnimationVariable::GetParentAnimationObject Objekt).  
  
##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData  
 Legt benutzerdefinierte Daten.  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>Parameter  
 *dwUserData*  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um benutzerdefinierten Daten mit einem Animationsobjekt zuzuordnen. Diese Daten können später von GetUserData zur Laufzeit abgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
