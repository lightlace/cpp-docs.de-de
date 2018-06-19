---
title: CAnimationValue-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs:
- C++
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 923b1b74a50fd13a57c1d9c7696f81acb28453e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356537"
---
# <a name="canimationvalue-class"></a>CAnimationValue-Klasse
Implementiert die Funktion eines Animationsobjekts, das über einen Wert verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|Überladen. Erstellt ein CAnimationValue-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|Fügt einen Übergang zu einem Wert angewendet werden.|  
|[CAnimationValue::GetValue](#getvalue)|Überladen. Ruft den aktuellen Wert.|  
|[CAnimationValue::GetVariable](#getvariable)|Bietet Zugriff auf gekapselte Animationsvariablen.|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselte Animationsvariable in einer Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::operator DOUBLE](#operator_double)|Stellt die Konvertierung zwischen CAnimationValue und DOUBLE.|  
|[CAnimationValue::operator INT32](#operator_int32)|Stellt die Konvertierung in CAnimationValue und INT32 bereit.|  
|[CAnimationValue::operator =](#operator_eq)|Überladen. CAnimationValue einen INT32-Wert zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|Die gekapselte Animationsvariable, die Animationswert darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationValue-Klasse kapselt ein einzelnes CAnimationVariable-Objekt und kann in Anwendungen einen Einzelwert animierten darstellen. Beispielsweise können Sie diese Klasse für animierte Transparenz (Ausblendeffekt), Winkel (zum Drehen von Objekten), oder für andere Fall, wenn eine Animation je nach einem einzelnen animierten Wert erstellt werden müssen. Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf den Wert angewendet werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationValue::AddTransition  
 Fügt einen Übergang zu einem Wert angewendet werden.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pTransition`  
 Ein Zeiger auf den Übergangsobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Hinzufügen eines Übergangs interne Liste der Übergänge, die auf eine Animationsvariable angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (ein Storyboard für einen bestimmten Wert hinzugefügt) beim CAnimationController:: AnimateGroup aufrufen.  
  
##  <a name="canimationvalue"></a>  CAnimationValue::CAnimationValue  
 Erstellt ein CAnimationValue-Objekt.  
  
```  
CAnimationValue();

 
CAnimationValue(
    DOUBLE dblDefaultValue,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dblDefaultValue`  
 Gibt den Standardwert an.  
  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 CAnimationValue-Objekt mit Standardeigenschaften erstellt: Standardwert, Gruppen-ID und Objekt-ID werden auf 0 festgelegt.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationValue::GetAnimationVariableList  
 Legt die gekapselte Animationsvariable in einer Liste.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält es einen Zeiger auf CAnimationVariable, die den Wert der animierten darstellt.  
  
##  <a name="getvalue"></a>  CAnimationValue::GetValue  
 Ruft den aktuellen Wert.  
  
```  
BOOL GetValue(DOUBLE& dblValue);  
BOOL GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dblValue`  
 Die Ausgabe. Bei Rückgabe der Funktion enthält einen aktuellen Wert der Animationsvariablen.  
  
 `nValue`  
 Die Ausgabe. Bei Rückgabe der Funktion enthält einen aktuellen Wert der Animationsvariablen.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des aktuellen Werts. Diese Implementierung ruft das gekapselte COM-Objekt, und wenn der Aufruf fehlschlägt, gibt diese Methode den Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvariable"></a>  CAnimationValue::GetVariable  
 Bietet Zugriff auf gekapselte Animationsvariablen.  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte Animationsvariablen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode auf die gekapselte Animationsvariable zuzugreifen. CAnimationVariable bekommen Sie den Zugriff auf zugrunde liegende IUIAnimationVariable-Objekt, dessen Zeiger NULL sein kann, wenn Animationsvariablen nicht erstellt wurde.  
  
##  <a name="m_value"></a>  CAnimationValue::m_value  
 Die gekapselte Animationsvariable, die Animationswert darstellt.  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>  CAnimationValue::operator DOUBLE  
 Stellt die Konvertierung zwischen CAnimationValue und DOUBLE.  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der Animation-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Stellt die Konvertierung zwischen CAnimationValue und DOUBLE. Diese Methode intern GetValue aufruft und nicht auf Fehler überprüft. Wenn GetValue fehlschlägt, enthält der zurückgegebene Wert den Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt.  
  
##  <a name="operator_int32"></a>  CAnimationValue::operator INT32  
 Stellt die Konvertierung in CAnimationValue und INT32 bereit.  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der Animationswert als ganze Zahl.  
  
### <a name="remarks"></a>Hinweise  
 Stellt die Konvertierung in CAnimationValue und INT32 bereit. Diese Methode intern GetValue aufruft und nicht auf Fehler überprüft. Wenn GetValue fehlschlägt, enthält der zurückgegebene Wert den Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt.  
  
##  <a name="operator_eq"></a>  CAnimationValue::operator =  
 CAnimationValue einen DOUBLE-Wert zugewiesen.  
  
```  
void operator=(DOUBLE dblVal);  
void operator=(INT32 nVal);
```  
  
### <a name="parameters"></a>Parameter  
 `dblVal`  
 Gibt den Wert der Animationswert zugewiesen werden.  
  
 `nVal`  
 Gibt den Wert der Animationswert zugewiesen werden.  
  
### <a name="remarks"></a>Hinweise  
 CAnimationValue einen DOUBLE-Wert zugewiesen. Dieser Wert wird als Standardwert für den gekapselten Animationsvariablen festgelegt. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
##  <a name="setdefaultvalue"></a>  CAnimationValue::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dblDefaultValue`  
 Gibt den Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein Standardwert festgelegt. Ein Default-Wert wird an die Anwendung zurückgegeben, wenn Animation nicht gestartet wurde, und/oder zugrunde liegenden COM-Objekt wurde nicht erstellt. Wenn das zugrunde liegende COM-Objekt, das in den CAnimationVarible gekapselt ist bereits erstellt wurde, diese Methode neu erstellt, sind daher möglicherweise EnableValueChanged/EnableIntegerValueChanged Methoden erneut aufzurufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
