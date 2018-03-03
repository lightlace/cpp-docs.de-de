---
title: COM-Schnittstelle Eintrag Makros | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76352cf2015661bc970b2987b9794f3bf023cc15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY-Makros  
 Diese Makros Geben Sie die Schnittstellen eines Objekts in die COM-Zuordnung, damit diese von zugegriffen werden kann `QueryInterface`. Die Reihenfolge der Einträge in der COM-Zuordnung wird die Order-Schnittstellen für einen übereinstimmenden überprüft **IID** während `QueryInterface`.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|Gibt die schnittstellenzuordnung für den COM-Schnittstellen.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Verwenden Sie dieses Makro, um zwei Verzweigungen der Vererbung zu unterscheiden.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung aus, und geben Sie die IID.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer bei `punk` ist **NULL**, erstellt er automatisch das Aggregat von beschrieben die `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`, und wenn `punk` ist **NULL**, automatisch beim Erstellen der Aggregat von beschrieben die `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Bewirkt, dass das Programm aufrufen ["DebugBreak"](http://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Speichert die Schnittstelle-spezifische Daten für jede Instanz.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Macht die abtrennbare Schnittstellen verfügbar.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Verarbeitet die COM-Zuordnung der Basisklasse an, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Ein allgemeiner Mechanismus für ATLs-Berichterstellungsprozess `QueryInterface` Logik.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass alle IID Abfragen in einem Aufruf führt `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Gibt **E_NOINTERFACE** und COM-Zuordnung Verarbeitung, wenn für die angegebene Schnittstelle abgefragt wird beendet.|  

## <a name="requirements"></a>Anforderungen
**Header:** atlcom.h

## <a name="com_interface_entry"></a>COM_INTERFACE_ENTRY
Gibt die schnittstellenzuordnung für den COM-Schnittstellen.

### <a name="syntax"></a>Syntax

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Parameter

"X" [in] der Name einer Schnittstelle abgeleitet Class-Objekt direkt.

### <a name="remarks"></a>Hinweise
In der Regel ist dies die Art des Eintrags, den Sie am häufigsten verwenden.

### <a name="example"></a>Beispiel
```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```
### <a name="requirements"></a>Anforderungen
**Header:** atlcom.h
  
##  <a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 Verwenden Sie dieses Makro, um zwei Verzweigungen der Vererbung zu unterscheiden.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name einer Schnittstelle, die Sie vom Objekt verfügbar machen möchten.  
  
 `x2`  
 [in] Der Name der Vererbung Verzweigung aus dem *x* verfügbar gemacht wird.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. Wenn Sie Ihre Klassenobjekts aus zwei duale Schnittstellen abgeleitet werden, Sie verfügbar machen `IDispatch` mit `COM_INTERFACE_ENTRY2` da `IDispatch` kann aus einer der Schnittstellen abgerufen werden.  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung aus, und geben Sie die IID.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle verfügbar gemacht werden.  
  
 *w*  
 [in] Der Name der Klasse verfügbar, deren Vtable als Schnittstelle identifizierten gemacht `iid`.  
  
 
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID, die Sie für die Benutzeroberfläche angeben.  
  
 *w*  
 [in] Der Name einer Schnittstelle, die das Klassenobjekt direkt abgeleitet.  
  
 `x2`  
 [in] Der Name des eine zweite Schnittstelle, der das Klassenobjekt direkt abgeleitet.  
  
##  <a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt werden soll.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `punk` Parameter wird davon ausgegangen, dass auf die innere unbekannt, der ein Aggregat oder auf **NULL**, in diesem Fall der Eintrag ignoriert wird. In der Regel würden Sie **CoCreate** das Aggregat in `FinalConstruct`.  
  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle-Abfrage ein Fehler auftritt, setzt die Verarbeitung der COM-Zuordnung fort.  
  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer bei `punk` ist **NULL**, erstellt er automatisch das Aggregat von beschrieben die `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt werden soll.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss ein Member der Klasse, die die COM-Zuordnung enthält.  
  
 `clsid`  
 [in] Der Bezeichner des Aggregats, das Wenn erstellt `punk` ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`, und wenn `punk` ist **NULL**, automatisch beim Erstellen der Aggregat von beschrieben die `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss ein Member der Klasse, die die COM-Zuordnung enthält.  
  
 `clsid`  
 [in] Der Bezeichner des Aggregats, das Wenn erstellt `punk` ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle-Abfrage ein Fehler auftritt, setzt die Verarbeitung der COM-Zuordnung fort.  
  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 Bewirkt, dass das Programm aufrufen ["DebugBreak"](http://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Text, die zum Erstellen des Schnittstellenbezeichner verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle, die IID durch Anfügen erstellt *x* auf `IID_`. Z. B. wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Speichert die Schnittstelle-spezifische Daten für jede Instanz.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abtrennbare.  
  
 *w*  
 [in] Der Name der Klasse, die die Schnittstelle implementiert.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss ein Member der Klasse, die die COM-Zuordnung enthält. Initialisiert werden soll, um **NULL** im Konstruktor der Klasse des Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle nicht verwendet wird, verringert dies die Gesamtgröße der Instanz des Objekts.  
  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 Macht die abtrennbare Schnittstellen verfügbar.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abtrennbare.  
  
 *w*  
 [in] Der Name der Klasse, die die Schnittstelle implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Eine abtrennbare-Schnittstelle wird implementiert, wie ein separates Objekt instanziiert wird, jedes Mal, wenn die Schnittstelle dar, die abgefragt wird. In der Regel erstellen Sie Ihre Schnittstelle als eine abtrennbare, wenn die Schnittstelle nur selten verwendet wird, da dies einen Vtable-Zeiger in jeder Instanz Ihrer Hauptobjekt speichert. Die abtrennbare wird gelöscht, wenn der Verweiszähler auf 0 (null) wird. Die Klasse zur Implementierung der abtrennbare abgeleitet werden sollte `CComTearOffObjectBase` und verfügen über eine eigene COM-Code Map.  
  
  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 Verarbeitet die COM-Zuordnung der Basisklasse an, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Parameter  
 *classname*  
 [in] Eine Basisklasse des aktuellen Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise ist in den folgenden Code:  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Beachten Sie, dass der erste Eintrag in der COM-Zuordnung eine Schnittstelle für das Objekt mit der COM-Zuordnung sein muss. Folglich kann nicht gestartet werden mit der COM-Zuordnungseinträge `COM_INTERFACE_ENTRY_CHAIN`, die bewirkt, dass die COM-Zuordnung eines anderen Objekts, an dem Punkt gesucht werden soll, in denen **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** wird in COM-Zuordnung des Objekts angezeigt. Wenn Sie die COM-Zuordnung von einem anderen Objekt zuerst suchen möchten, fügen Sie einen Schnittstelle-Eintrag für **IUnknown** für COM-Zuordnung, COM-Zuordnung von dem anderen Objekt dann verkettet. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 Ein allgemeiner Mechanismus für ATLs-Berichterstellungsprozess `QueryInterface` Logik.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle verfügbar gemacht werden.  
  
 `dw`  
 [in] Ein Parameter übergeben, um die `func`.  
  
 `func`  
 [in] Der Funktionszeiger, der zurückgegeben wird `iid`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *Iid* entspricht die IID der Schnittstelle abgefragt, und klicken Sie dann auf die Funktion anhand des `func` aufgerufen wird. Die Deklaration für die Funktion sollte sein:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Wenn Ihre Funktion aufgerufen wird, `pv` für Ihr Klassenobjekt verweist. Die `riid` Parameter bezieht sich auf die Schnittstelle, die abgefragt wird, `ppv` ist der Zeiger auf den Speicherort, die die Funktion sollte den Zeiger auf die Schnittstelle und `dw` ist der Parameter, die Sie in den Eintrag angegeben haben. Die Funktion sollte festgelegt \* `ppv` auf **NULL** und zurückgeben **E_NOINTERFACE** oder **"S_FALSE"** entscheidet es nicht, eine Schnittstelle zurück. Mit **E_NOINTERFACE**, COM-Zuordnung Verarbeitung beendet. Mit **"S_FALSE"**, COM-Zuordnung Verarbeitung wird fortgesetzt, obwohl keine Schnittstellenzeiger zurückgegeben wurde. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, sollte zurückgegeben `S_OK`.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass alle IID Abfragen in einem Aufruf führt `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Parameter  
 `dw`  
 [in] Ein Parameter übergeben, um die `func`.  
  
 `func`  
 [in] Die Funktion, die aufgerufen wird, wenn dieser Eintrag in der COM-Zuordnung verarbeitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Fehler bewirkt die Verarbeitung in der COM-Zuordnung fortgesetzt werden kann. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, sollte zurückgegeben `S_OK`.  
  
  
##  <a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 Gibt **E_NOINTERFACE** und COM-Zuordnung Verarbeitung, wenn für die angegebene Schnittstelle abgefragt wird beendet.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Text, die zum Erstellen des Schnittstellenbezeichner verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie können dieses Makro verwenden, um zu verhindern, dass eine Schnittstelle, die in einem bestimmten Fall verwendet wird. Beispielsweise können Sie dieses Makro in den COM-einfügen unmittelbar vor dem zuordnen `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` zu verhindern, dass eine Abfrage für die Schnittstelle, die das Aggregat innere Unknown weitergeleitet wird.  
  
 Die Schnittstelle, die IID durch Anfügen erstellt *x* auf `IID_`. Z. B. wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.  
  
  