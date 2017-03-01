---
title: CBaseTransition-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- afxanimationcontroller/CBaseTransition
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition class
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
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
ms.openlocfilehash: b979d03587ada42486d0462733dfe6fd22f9f7cc
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetransition-class"></a>CBaseTransition-Klasse
Stellt einen einfachen Übergang dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-enumerations"></a>Öffentliche Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION_TYPE-Enumeration](#transition_type_enumeration)|Definiert die Transition-Typen, die derzeit von der MFC-Implementierung der Windows-Animations-API unterstützt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|Erstellt ein Objekt Basis Übergang.|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Der Destruktor. Wird aufgerufen, wenn ein Übergangsobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Fügt einen Übergang zu einem Storyboard.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Fügt einen Übergang zu einem Storyboard.|  
|[CBaseTransition::Clear](#clear)|Gibt gekapseltes IUIAnimationTransitions-COM-Objekt.|  
|[CBaseTransition:: Create](#create)|Erstellt einen COM-Übergang.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Gibt Anfangs-Keyframe.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Gibt einen Zeiger auf Verwandte Variable zurück.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Gibt Anfangs-Keyframe.|  
|[CBaseTransition::GetTransition](#gettransition)|Überladen. Gibt einen Zeiger auf zugrunde liegende COM-Übergang-Objekt.|  
|[CBaseTransition::GetType](#gettype)|Gibt Übergangstyp zurück.|  
|[CBaseTransition::IsAdded](#isadded)|Erfahren Sie, ob ein Storyboard ein Übergang hinzugefügt wurde.|  
|[CBaseTransition:: SetKeyframes](#setkeyframes)|Legt Keyframes für einen Übergang fest.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Legt eine Beziehung zwischen Animationsvariable und Übergang.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|Gibt an, ob ein Storyboard ein Übergang hinzugefügt wurde.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Speichert einen Zeiger auf den Keyframe, der das Ende des Übergangs angibt.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Ein Zeiger auf eine Animationsvariable, die mit dem in M_transition gespeicherten Übergang animiert wird.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Speichert einen Zeiger auf den Keyframe, der den Anfang des Übergangs angibt.|  
|[CBaseTransition::m_transition](#m_transition)|Speichert einen Zeiger auf IUIAnimationTransition. NULL, wenn ein COM-Übergang-Objekt nicht erstellt wurde.|  
|[CBaseTransition::m_type](#m_type)|Speichert den Übergangstyp.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse kapselt die IUIAnimationTransitions-Schnittstelle und dient als Basisklasse für alle Übergänge.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namedtorcbasetransitiona--cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>CBaseTransition:: ~ CBaseTransition  
 Der Destruktor. Wird aufgerufen, wenn ein Übergangsobjekt zerstört wird.  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="a-nameaddtostoryboarda--cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 Fügt einen Übergang zu einem Storyboard.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf storyboard, der verwandte Variable animiert.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Übergang zu einem Storyboard erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Übernimmt den Übergang für die verwandte Variable im Storyboard. Wenn dies auf den ersten Übergang auf diese Variable in diesem Storyboard angewendet ist, beginnt der Übergang am Anfang des Storyboards. Andernfalls wird der Übergang zum Übergang auf die Variable zuletzt hinzugefügt wurde angefügt.  
  
##  <a name="a-nameaddtostoryboardatkeyframesa--cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 Fügt einen Übergang zu einem Storyboard.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parameter  
 `pStoryboard`  
 Ein Zeiger auf storyboard, der verwandte Variable animiert.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der Übergang zu einem Storyboard erfolgreich hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Übernimmt den Übergang für die verwandte Variable im Storyboard. Wenn der Startkeyframe angegeben wurde, beginnt der Übergang bei diesem Keyframe. Wenn der Ende Keyframe angegeben wurde, beginnt der Übergang am Startkeyframe und und endet am Ende Keyframe. Wenn der Übergang mit einem Dauerparameter erstellt wurde, wird dieser Dauer mit der Dauer der Zeit zwischen den Start- und End-Keyframes überschrieben. Wenn kein Keyframe angegeben wurde, wird der Übergang zum Übergang auf die Variable zuletzt hinzugefügt wurde angefügt.  
  
##  <a name="a-namecbasetransitiona--cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 Erstellt ein Objekt Basis Übergang.  
  
```  
CBaseTransition();
```  
  
##  <a name="a-namecleara--cbasetransitionclear"></a><a name="clear"></a>CBaseTransition::Clear  
 Gibt gekapseltes IUIAnimationTransitions-COM-Objekt.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte von der Create-Methode einer abgeleiteten Klasse aufgerufen werden, um Speicherverluste der IUITransitions-Schnittstelle zu vermeiden.  
  
##  <a name="a-namecreatea--cbasetransitioncreate"></a><a name="create"></a>CBaseTransition:: Create  
 Erstellt einen COM-Übergang.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pLibrary`  
 Ein Zeiger auf Übergangsbibliothek, die standard-Übergänge erstellt. Für benutzerdefinierte Übergänge kann NULL sein.  
  
 `pFactory`  
 Ein Zeiger auf Übergang-Klassenfactory, die benutzerdefinierte Übergänge erstellt. Standard-Übergänge kann NULL sein.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein COM-Übergangsobjekt erfolgreich erstellt wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine rein virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben werden muss. Sie wird vom Framework zum Instanziieren des zugrunde liegenden COM-Übergang-Objekts aufgerufen.  
  
##  <a name="a-namegetendkeyframea--cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 Gibt Anfangs-Keyframe.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf einen Keyframe oder NULL, wenn ein Übergang zwischen Keyframes nicht eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, auf einem Keyframe-Objekt, das zuvor mit SetKeyframes festgelegt wurde. Sie wird von Top Level-Code aufgerufen, wenn Übergänge Storyboard hinzugefügt wird.  
  
##  <a name="a-namegetrelatedvariablea--cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 Gibt einen Zeiger auf Verwandte Variable zurück.  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf Animationsvariablen oder NULL, wenn eine Animationsvariable nicht vom SetRelatedVariable festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein Accessor für die zugehörige Animationsvariable.  
  
##  <a name="a-namegetstartkeyframea--cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 Gibt Anfangs-Keyframe.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf einen Keyframe oder NULL, wenn ein Übergang nicht nach einem Keyframe starten sollte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, auf einem Keyframe-Objekt, das zuvor mit SetKeyframes festgelegt wurde. Sie wird von Top Level-Code aufgerufen, wenn Übergänge Storyboard hinzugefügt wird.  
  
##  <a name="a-namegettransitiona--cbasetransitiongettransition"></a><a name="gettransition"></a>CBaseTransition::GetTransition  
 Gibt einen Zeiger auf zugrunde liegende COM-Übergang-Objekt.  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>Parameter  
 `pLibrary`  
 Ein Zeiger auf Übergangsbibliothek, die standard-Übergänge erstellt. Für benutzerdefinierte Übergänge kann NULL sein.  
  
 `pFactory`  
 Ein Zeiger auf Übergang-Klassenfactory, die benutzerdefinierte Übergänge erstellt. Standard-Übergänge kann NULL sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf IUIAnimationTransition oder NULL, wenn das zugrunde liegende Übergang erstellt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Zeiger auf die zugrunde liegende COM-Übergang-Objekt und erstellt diese bei Bedarf.  
  
##  <a name="a-namegettypea--cbasetransitiongettype"></a><a name="gettype"></a>CBaseTransition::GetType  
 Gibt Übergangstyp zurück.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der TRANSITION_TYPE-Enumerationswerte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann zum Identifizieren eines Übergangs-Objekts anhand des Typs verwendet werden. Der Typ ist in einem Konstruktor einer abgeleiteten Klasse festgelegt.  
  
##  <a name="a-nameisaddeda--cbasetransitionisadded"></a><a name="isadded"></a>CBaseTransition::IsAdded  
 Erfahren Sie, ob ein Storyboard ein Übergang hinzugefügt wurde.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn ein Übergang zu einem Storyboard, andernfalls "false" hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag wird intern festgelegt, wenn der Code der obersten Ebene storyboard Übergänge hinzufügt.  
  
##  <a name="a-namembaddeda--cbasetransitionmbadded"></a><a name="m_badded"></a>CBaseTransition::m_bAdded  
 Gibt an, ob ein Storyboard ein Übergang hinzugefügt wurde.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="a-namempendkeyframea--cbasetransitionmpendkeyframe"></a><a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 Speichert einen Zeiger auf den Keyframe, der das Ende des Übergangs angibt.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="a-namemprelatedvariablea--cbasetransitionmprelatedvariable"></a><a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 Ein Zeiger auf eine Animationsvariable, die mit dem in M_transition gespeicherten Übergang animiert wird.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="a-namempstartkeyframea--cbasetransitionmpstartkeyframe"></a><a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 Speichert einen Zeiger auf den Keyframe, der den Anfang des Übergangs angibt.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="a-namemtransitiona--cbasetransitionmtransition"></a><a name="m_transition"></a>CBaseTransition::m_transition  
 Speichert einen Zeiger auf IUIAnimationTransition. NULL, wenn ein COM-Übergang-Objekt nicht erstellt wurde.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="a-namemtypea--cbasetransitionmtype"></a><a name="m_type"></a>CBaseTransition::m_type  
 Speichert den Übergangstyp.  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="a-namesetkeyframesa--cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>CBaseTransition:: SetKeyframes  
 Legt Keyframes für einen Übergang fest.  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pStart`  
 Ein Keyframe, der den Anfang des Übergangs angibt.  
  
 `pEnd`  
 Ein Keyframe, der das Ende des Übergangs angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode teilt den Übergang zu starten, nachdem die angegebenen Keyframe und, optional, wenn ausgesetzt nicht NULL ist, am Ende vor der angegebenen Keyframe. Wenn der Übergang mit einem Dauerparameter erstellt wurde, wird dieser Dauer mit der Dauer der Zeit zwischen den Start- und End-Keyframes überschrieben.  
  
##  <a name="a-namesetrelatedvariablea--cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 Legt eine Beziehung zwischen Animationsvariable und Übergang.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parameter  
 `pVariable`  
 Ein Zeiger auf die zugehörige Animationsvariable.  
  
### <a name="remarks"></a>Hinweise  
 Legt eine Beziehung zwischen Animationsvariable und Übergang. Ein Übergang kann nur auf eine Variable angewendet werden.  
  
##  <a name="a-nametransitiontypeenumerationa--cbasetransitiontransitiontype-enumeration"></a><a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE-Enumeration  
 Definiert die Transition-Typen, die derzeit von der MFC-Implementierung der Windows-Animations-API unterstützt.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Übergangstyp wird im Konstruktor des bestimmten Übergangs festgelegt. CSinusoidalTransitionFromRange legt z. B. seinen Typ auf SINUSOIDAL_FROM_RANGE fest.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

