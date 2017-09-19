---
title: CAnimationValue-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CAnimationValue class
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
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
ms.openlocfilehash: 083c8be9a0d9d518d5353b6d02c0050944312805
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvalue-class"></a>CAnimationValue-Klasse
Implementiert die Funktion eines Animationsobjekts, das über einen Wert verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|Überladen. Erstellt ein CAnimationValue-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|Fügt einen Übergang zu einem Wert zugewiesen werden.|  
|[CAnimationValue::GetValue](#getvalue)|Überladen. Ruft den aktuellen Wert.|  
|[CAnimationValue::GetVariable](#getvariable)|Bietet Zugriff auf gekapselte Animationsvariable.|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Fügt die gekapselte Animationsvariable in eine Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::operator DOUBLE](#operator_double)|Stellt die Konvertierung in CAnimationValue und DOUBLE.|  
|[CAnimationValue::operator INT32](#operator_int32)|Stellt die Konvertierung in CAnimationValue und INT32.|  
|[CAnimationValue::operator =](#operator_eq)|Überladen. CAnimationValue einen INT32-Wert zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|Die gekapselte Animationsvariable, die Animationswert darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationValue-Klasse kapselt ein einzelnes CAnimationVariable-Objekt und kann in Clientanwendungen einen einzelnen animierten Wert darstellen. Beispielsweise können Sie diese Klasse für animierte Transparenz (Ausblendeffekt), Winkel (zum Drehen von Objekten), oder für alle anderen Fälle eine Animation abhängig von einem einzelnen animierten Wert erstellt werden sollen. Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse zu, Animationscontroller AddAnimationObject fügen Sie hinzu und rufen Sie AddTransition für jeden Übergang auf den Wert angewendet werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationValue::AddTransition  
 Fügt einen Übergang zu einem Wert zugewiesen werden.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pTransition`  
 Ein Zeiger auf Übergangsobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Hinzufügen eines Übergangs internen Liste von Übergängen, die auf eine Animationsvariable angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (einem Storyboard für einen bestimmten Wert hinzugefügt) Wenn Sie CAnimationController:: AnimateGroup aufrufen.  
  
##  <a name="canimationvalue"></a>CAnimationValue::CAnimationValue  
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
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt CAnimationValue-Objekt mit Standardeigenschaften: Standardwert, Gruppen-ID und Objekt-ID werden auf 0 festgelegt.  
  
##  <a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList  
 Fügt die gekapselte Animationsvariable in eine Liste.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Bei Rückgabe der Funktion enthält einen Zeiger auf CAnimationVariable, die den animierten Wert darstellt.  
  
##  <a name="getvalue"></a>CAnimationValue::GetValue  
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
 True, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen des aktuellen Werts. Diese Implementierung ruft das gekapselte COM-Objekt, und wenn der Aufruf fehlschlägt, gibt diese Methode den Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvariable"></a>CAnimationValue::GetVariable  
 Bietet Zugriff auf gekapselte Animationsvariable.  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte Animationsvariable.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die gekapselte Animationsvariable zuzugreifen. In CAnimationVariable haben Sie Zugriff auf die zugrunde liegende IUIAnimationVariable-Objekt, dessen Zeiger NULL sein kann, wenn die Animationsvariable nicht erstellt wurde.  
  
##  <a name="m_value"></a>CAnimationValue::m_value  
 Die gekapselte Animationsvariable, die Animationswert darstellt.  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>CAnimationValue::operator DOUBLE  
 Stellt die Konvertierung in CAnimationValue und DOUBLE.  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuellen Wert von Animations-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Stellt die Konvertierung in CAnimationValue und DOUBLE. Diese Methode wird intern "GetValue" aufruft und überprüft nicht auf Fehler. Wenn GetValue fehlschlägt, enthält der zurückgegebene Wert einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt.  
  
##  <a name="operator_int32"></a>CAnimationValue::operator INT32  
 Stellt die Konvertierung in CAnimationValue und INT32.  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuellen Wert von Animations-Wert als ganze Zahl.  
  
### <a name="remarks"></a>Hinweise  
 Stellt die Konvertierung in CAnimationValue und INT32. Diese Methode wird intern "GetValue" aufruft und überprüft nicht auf Fehler. Wenn GetValue fehlschlägt, enthält der zurückgegebene Wert einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt.  
  
##  <a name="operator_eq"></a>CAnimationValue::operator =  
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
 CAnimationValue einen DOUBLE-Wert zugewiesen. Dieser Wert wird als Standardwert für gekapselte Animationsvariable festgelegt. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parameter  
 `dblDefaultValue`  
 Gibt den Standardwert an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Standardwert festzulegen. Ein Standardwert wird an die Anwendung zurückgegeben, wenn Animation nicht gestartet wurde bzw. das zugrunde liegende COM-Objekt wurde nicht erstellt. Wenn die zugrunde liegende COM-Objekt in CAnimationVarible bereits erstellt wurde, diese Methode neu erstellt, daher müssen möglicherweise erneut EnableValueChanged/EnableIntegerValueChanged-Methoden aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

