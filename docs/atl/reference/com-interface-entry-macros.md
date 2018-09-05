---
title: Einstiegsmakros für COM-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 914619c2790a904530f6efe2324549402d9b6785
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758156"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY-Makros  

Diese Makros Geben Sie die Schnittstellen eines Objekts in die COM-Zuordnung, damit darauf zugreifen können `QueryInterface`. Die Reihenfolge der Einträge in der COM-Zuordnung ist die Order-Schnittstellen für eine übereinstimmende IID während überprüft `QueryInterface`.  

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Gibt ein in die schnittstellenzuordnung für die COM-Schnittstellen.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Verwenden Sie dieses Makro, um zwei Verzweigungen der Vererbung zu unterscheiden.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung, und geben Sie die IID.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Wenn die Schnittstelle identifizierte *Iid* wird abgefragt, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Abfrage, Weiterleitung führt Abfragen für alle IID *Punk*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer bei *Punk* NULL ist, erstellt es automatisch das Aggregat von beschrieben die *Clsid*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Abfrage, Weiterleitung führt Abfragen für alle IID *Punk*, und wenn *Punk* NULL ist, automatisch erstellen das Aggregat von beschrieben die *Clsid*.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Bewirkt, dass das Programm aufrufen ["DebugBreak"](https://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Speichert die Schnittstelle-spezifische Daten für jede Instanz.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Macht Ihre abtrennbare Schnittstellen verfügbar.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Verarbeitet die COM-Zuordnung der Basisklasse an, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Ein allgemeiner Mechanismus für die Einbindung in die ATL `QueryInterface` Logik.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass die Ergebnisse von Abfragen für alle IID in einem Aufruf von *Func*.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Wird E_NOINTERFACE zurückgegeben, und wird beendet, COM-Zuordnung verarbeitet, wenn für die angegebene Schnittstelle abgefragt wird.|  

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

Gibt ein in die schnittstellenzuordnung für die COM-Schnittstellen.

### <a name="syntax"></a>Syntax

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Parameter

X [in] der Name einer Schnittstelle leitet das Klassenobjekt direkt aus.

### <a name="remarks"></a>Hinweise

In der Regel ist dies die Art des Eintrags, die Sie am häufigsten verwenden.

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

##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2

Verwenden Sie dieses Makro, um zwei Verzweigungen der Vererbung zu unterscheiden.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Parameter

*w*  
[in] Der Name einer Schnittstelle, die Sie von Ihrem Objekt verfügbar machen möchten.

*x2*  
[in] Der Name des branchs Vererbung aus dem *x* verfügbar gemacht wird.

### <a name="remarks"></a>Hinweise

Z. B. Wenn Sie Ihre Klassenobjekt aus zwei duale Schnittstellen abgeleitet werden, Sie verfügbar machen `IDispatch` mit COM_INTERFACE_ENTRY2 seit `IDispatch` aus einer der Schnittstellen abgerufen werden kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID

Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung, und geben Sie die IID.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle verfügbar gemacht werden.

*w*  
[in] Der Name der Klasse, deren Vtable verfügbar werden, wie die Schnittstelle identifizierte gemacht wird *Iid*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID

Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID, die Sie für die Schnittstelle angegeben werden.

*w*  
[in] Der Name einer Schnittstelle, die das Klassenobjekt direkt von abgeleitet ist.

*x2*  
[in] Der Name des eine zweite Schnittstelle, der das Klassenobjekt direkt von abgeleitet ist.

##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE

Wenn die Schnittstelle identifizierte *Iid* abgefragt wird, für die COM_INTERFACE_ENTRY_AGGREGATE weiterleitet *Punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle abgefragt.

*pUnk*  
[in] Der Name des ein `IUnknown` Zeiger.

### <a name="remarks"></a>Hinweise

Die *Punk* Parameter wird davon ausgegangen, auf die innere unbekannte eines Aggregats oder für NULL-Werte in diesem Fall der Einstiegspunkt werden ignoriert. In der Regel würden Sie `CoCreate` das Aggregat in `FinalConstruct`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND

Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Abfrage, Weiterleitung führt Abfragen für alle IID *Punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Parameter

*pUnk*  
[in] Der Name des ein `IUnknown` Zeiger.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstelle-Abfrage schlägt fehl, setzt die Verarbeitung der COM-Zuordnung fort.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE

Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer bei *Punk* NULL ist, erstellt es automatisch das Aggregat von beschrieben die *Clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle abgefragt.

*pUnk*  
[in] Der Name des ein `IUnknown` Zeiger. Sie muss ein Member der Klasse, die die COM-Zuordnung enthält.

*clsid*  
[in] Der Bezeichner des Aggregats, das Wenn erstellt *Punk* ist NULL.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Abfrage, Weiterleitung führt Abfragen für alle IID *Punk*, und wenn *Punk* NULL ist, automatisch erstellen das Aggregat von beschrieben die *Clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Parameter

*pUnk*  
[in] Der Name des ein `IUnknown` Zeiger. Sie muss ein Member der Klasse, die die COM-Zuordnung enthält.

*clsid*  
[in] Der Bezeichner des Aggregats, das Wenn erstellt *Punk* ist NULL.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstelle-Abfrage schlägt fehl, setzt die Verarbeitung der COM-Zuordnung fort.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK

Bewirkt, dass das Programm aufrufen ["DebugBreak"](https://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Parameter

*w*  
[in] Text verwendet, um den Schnittstellenbezeichner zu erstellen.

### <a name="remarks"></a>Hinweise

Die Schnittstelle, die IID durch Anfügen erstellt *x* zu `IID_`. Z. B. wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.

##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Speichert die Schnittstelle-spezifische Daten für jede Instanz.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle abtrennbare.

*w*  
[in] Der Name der Klasse, die die Schnittstelle implementiert.

*pUnk*  
[in] Der Name des ein `IUnknown` Zeiger. Sie muss ein Member der Klasse, die die COM-Zuordnung enthält. Sollte auf NULL im Konstruktor der Klasse des Objekts initialisiert werden.

### <a name="remarks"></a>Hinweise

Wenn die Schnittstelle nicht verwendet wird, verringert dies die Gesamtgröße der Instanz des Objekts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF

Macht Ihre abtrennbare Schnittstellen verfügbar.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle abtrennbare.

*w*  
[in] Der Name der Klasse, die die Schnittstelle implementiert.

### <a name="remarks"></a>Hinweise

Eine Tearoff Schnittstelle wird implementiert, wie ein separates Objekt instanziiert wird, jedes Mal, wenn die Schnittstelle, die es darstellt, die abgefragt werden. In der Regel erstellen Sie Ihre Schnittstelle als eine abtrennbare, wenn die Schnittstelle nur selten verwendet wird, da dadurch einen Vtable-Zeiger in jeder Instanz des Objekts main. Die abtrennbare wird gelöscht, wenn dessen Verweiszähler auf 0 (null) ist. Die Klasse implementiert die abtrennbare abgeleitet werden sollte `CComTearOffObjectBase` und verfügen über einen eigenen COM-Code Map.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN

Verarbeitet die COM-Zuordnung der Basisklasse an, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Parameter

*classname*  
[in] Eine Basisklasse des aktuellen Objekts.

### <a name="remarks"></a>Hinweise

Z. B. in den folgenden Code:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

Beachten Sie, dass der erste Eintrag in der COM-Zuordnung eine Schnittstelle für das Objekt, das mit der COM-Zuordnung sein muss. Daher können keine beginnen Sie Ihre COM-Zuordnungseinträgen mit COM_INTERFACE_ENTRY_CHAIN, wodurch die COM-Zuordnung eines anderen Objekts, an dem Punkt gesucht werden soll, in denen **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** in COM-Zuordnung des Objekts angezeigt. Falls die COM-Zuordnung eines anderen Objekts zu suchen, zuerst werden sollen, fügen Sie einen Schnittstelle-Eintrag für `IUnknown` mit COM-Zuordnung, verkettet Sie dann COM-Zuordnung das andere Objekt. Zum Beispiel:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC

Ein allgemeiner Mechanismus für die Einbindung in die ATL `QueryInterface` Logik.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Parameter

*IID*  
[in] Die GUID der Schnittstelle verfügbar gemacht werden.

*Data Warehouse*  
[in] Ein Parameter übergeben die *Func*.

*func*  
[in] Der Funktionszeiger, der zurückgegeben wird *Iid*.

### <a name="remarks"></a>Hinweise

Wenn *Iid* entspricht die IID der Schnittstelle abgefragt, und klicken Sie dann auf die Funktion anhand des *Func* aufgerufen wird. Die Deklaration für die Funktion sollte sein:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

Wenn die Funktion aufgerufen wird, `pv` verweist auf das Klassenobjekt. Die *Riid* Parameter verweist auf die Schnittstelle, die abgefragt wird, `ppv` der Zeiger auf den Speicherort, in dem die Funktion sollte den Zeiger auf die Schnittstelle, speichern, und *dw* ist der Parameter Sie in den Eintrag angegeben. Legen Sie die Funktion sollte \* `ppv` auf NULL und return E_NOINTERFACE oder S_FALSE, wenn es nicht entscheidet, eine Schnittstelle zurück. Mit E_NOINTERFACE beendet die Verarbeitung von COM-Zuordnung. Mit S_FALSE COM-Zuordnung wird die Verarbeitung fortgesetzt, auch wenn keine Schnittstellenzeiger zurückgegeben wurde. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, muss er S_OK zurückgeben.

##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND

Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass die Ergebnisse von Abfragen für alle IID in einem Aufruf von *Func*.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Parameter

*Data Warehouse*  
[in] Ein Parameter übergeben die *Func*.

*func*  
[in] Die Funktion, die aufgerufen wird, wenn dieser Eintrag in der COM-Zuordnung verarbeitet wird.

### <a name="remarks"></a>Hinweise

Jeder Fehler bewirkt die Verarbeitung fortgesetzt werden auf der COM-Zuordnung. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, muss er S_OK zurückgeben.

##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE

Wird E_NOINTERFACE zurückgegeben, und wird beendet, COM-Zuordnung verarbeitet, wenn für die angegebene Schnittstelle abgefragt wird.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Parameter

*w*  
[in] Text verwendet, um den Schnittstellenbezeichner zu erstellen.

### <a name="remarks"></a>Hinweise

Sie können dieses Makro verwenden, um zu verhindern, dass eine Schnittstelle, die in einem bestimmten Fall verwendet wird. Beispielsweise können Sie dieses Makro in der COM-Zuordnung direkt vor COM_INTERFACE_ENTRY_AGGREGATE_BLIND, um zu verhindern, dass eine Abfrage für die Schnittstelle des Aggregats innere Unknown weitergeleitet einfügen.

Die Schnittstelle, die IID durch Anfügen erstellt *x* zu `IID_`. Z. B. wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.

  