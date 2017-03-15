---
title: "Makros für COM-Zuordnung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79658b6ac22719af7172c9d2848675faf2a23a0c
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-macros"></a>Makros für COM-Zuordnung
Diese Makros definieren Zuordnungen von COM-Schnittstelle.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Kennzeichnet den Anfang der Zuordnungseinträge der COM-Schnittstelle.|  
|[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)|Schnittstellen in der COM-schnittstellenzuordnung eingetragen.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Verwenden Sie dieses Makro, um zwei Zweigen der Vererbung zu unterscheiden.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung und die IID angeben.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer wenn `punk` ist **NULL**, wird automatisch erstellt, das Aggregat von beschrieben wird die `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`, und wenn `punk` ist **NULL**automatisch erstellen das Aggregat von beschrieben wird die `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Veranlasst das Programm aufrufen, [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Speichert die Schnittstelle-spezifische Daten für jede Instanz.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Macht die abtrennbare Schnittstellen verfügbar.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Die COM-Zuordnung der Basisklasse verarbeitet, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht wird.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Ein allgemeiner Mechanismus für die Einbindung von ATL `QueryInterface` Logik.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass die Ergebnisse von Abfragen für alle IID in einem Aufruf von `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Gibt **E_NOINTERFACE** und COM-Zuordnung verarbeiten, wenn für die angegebene Schnittstelle abgefragt wird beendet.|  
|[END_COM_MAP](#end_com_map)|Markiert das Ende der Zuordnungseinträge der COM-Schnittstelle.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
   
##  <a name="a-namebegincommapa--begincommap"></a><a name="begin_com_map"></a>BEGIN_COM_MAP  
 Die COM-Zuordnung ist der Mechanismus, der auf ein Objekt an einen Client über Schnittstellen verfügbar macht `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name des Klassenobjekts, den Sie auf Schnittstellen bereitstellen.  
  
### <a name="remarks"></a>Hinweise  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) gibt nur die Zeiger für Schnittstellen in der COM-Zuordnung zurück. Starten Sie die schnittstellenzuordnung mit der `BEGIN_COM_MAP` -Makro, fügen Sie Einträge für jede der Schnittstellen mit der [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) -Makro oder einer seiner Varianten und schließen Sie die Karte mit der [END_COM_MAP](#end_com_map) Makro.  

  
### <a name="example"></a>Beispiel  
 Von ATL [BEEPER](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrymacrosa--cominterfaceentry-macros"></a><a name="com_interface_entry_macros"></a>COM_INTERFACE_ENTRY-Makros  
 Diese Makros Geben Sie die Schnittstellen eines Objekts in die COM-Zuordnung, damit sie von zugegriffen werden kann `QueryInterface`. Die Reihenfolge der Einträge in der COM-Zuordnung ist die Order-Schnittstellen werden nach einer übereinstimmenden überprüft **IID** während `QueryInterface`.  
  
##  <a name="a-namecominterfaceentry2x2a--cominterfaceentry2"></a><a name="com_interface_entry2_x2"></a>COM_INTERFACE_ENTRY2  
 Verwenden Sie dieses Makro, um zwei Zweigen der Vererbung zu unterscheiden.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name der Schnittstelle, die Sie von Ihrem Objekt verfügbar machen möchten.  
  
 `x2`  
 [in] Der Name der Vererbung Verzweigung aus dem *x* verfügbar gemacht wird.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. Wenn Sie Ihr Class-Objekt aus zwei duale Schnittstellen ableiten, Sie verfügbar machen, `IDispatch` mit `COM_INTERFACE_ENTRY2` da `IDispatch` aus einer der Schnittstellen abgerufen werden kann.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryiida--cominterfaceentryiid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 Verwenden Sie dieses Makro, geben die Schnittstelle in der COM-Zuordnung und die IID angeben.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle verfügbar gemacht.  
  
 *x*  
 [in] Der Name der Klasse, deren Vtable verfügbar werden, wie die Schnittstelle identifizierten gemacht wird `iid`.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#117;](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="a-namecominterfaceentry2iida--cominterfaceentry2iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 Identisch mit [COM_INTERFACE_ENTRY2](#com_interface_entry2), außer dass Sie eine andere IID angeben können.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID, die Sie für die Schnittstelle angeben.  
  
 *x*  
 [in] Der Name einer Schnittstelle, die Ihr Class-Objekt direkt von abgeleitet wird.  
  
 `x2`  
 [in] Der Name des eine zweite Schnittstelle, der Ihr Class-Objekt direkt von abgeleitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentry2a--cominterfaceentry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 Verwenden Sie dieses Makro, um zwei Zweigen der Vererbung zu unterscheiden.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name der Schnittstelle, die Sie von Ihrem Objekt verfügbar machen möchten.  
  
 `x2`  
 [in] Der Name der Vererbung Verzweigung aus dem *x* verfügbar gemacht wird.  
  
### <a name="remarks"></a>Hinweise  
 Z. B. Wenn Sie Ihr Class-Objekt aus zwei duale Schnittstellen ableiten, Sie verfügbar machen, `IDispatch` mit `COM_INTERFACE_ENTRY2` da `IDispatch` aus einer der Schnittstellen abgerufen werden kann.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryaggregate2a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate2"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `punk` Parameter wird angenommen, dass der innere unbekannt, der ein Aggregat oder auf **NULL**, in diesem Fall der Eintrag ignoriert wird. In der Regel würden Sie **CoCreate** das Aggregat in `FinalConstruct`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryaggregateblinda--cominterfaceentryaggregateblind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle Abfrage fehlschlägt, wird die Verarbeitung der COM-Zuordnung fortgesetzt.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#113;](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  
##  <a name="a-namecominterfaceentryaggregate3a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate3"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `punk` Parameter wird angenommen, dass der innere unbekannt, der ein Aggregat oder auf **NULL**, in diesem Fall der Eintrag ignoriert wird. In der Regel würden Sie **CoCreate** das Aggregat in `FinalConstruct`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregatea--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer wenn `punk` ist **NULL**, wird automatisch erstellt, das Aggregat von beschrieben wird die `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss Mitglied der Klasse, die die COM-Zuordnung enthält.  
  
 `clsid`  
 [in] Der Bezeichner des Aggregats, die Wenn erstellt werden `punk` ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentryaggregatea--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Wenn die Schnittstelle identifizierten `iid` abgefragt wird, `COM_INTERFACE_ENTRY_AGGREGATE` leitet an `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `punk` Parameter wird angenommen, dass der innere unbekannt, der ein Aggregat oder auf **NULL**, in diesem Fall der Eintrag ignoriert wird. In der Regel würden Sie **CoCreate** das Aggregat in `FinalConstruct`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregateblinda--cominterfaceentryautoaggregateblind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), außer dass die Weiterleitung der Abfrage führt Abfragen für alle IID `punk`, und wenn `punk` ist **NULL**automatisch erstellen das Aggregat von beschrieben wird die `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss Mitglied der Klasse, die die COM-Zuordnung enthält.  
  
 `clsid`  
 [in] Der Bezeichner des Aggregats, die Wenn erstellt werden `punk` ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle Abfrage fehlschlägt, wird die Verarbeitung der COM-Zuordnung fortgesetzt.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#115;](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregate2a--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate2"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 Identisch mit [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), außer wenn `punk` ist **NULL**, wird automatisch erstellt, das Aggregat von beschrieben wird die `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle abgefragt.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss Mitglied der Klasse, die die COM-Zuordnung enthält.  
  
 `clsid`  
 [in] Der Bezeichner des Aggregats, die Wenn erstellt werden `punk` ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentrybreaka--cominterfaceentrybreak"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 Veranlasst das Programm aufrufen, [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) Wenn die angegebene Schnittstelle abgefragt wird.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Text für den Schnittstellenbezeichner erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle, die IID wird durch Anhängen konstruiert *x* auf `IID_`. Zum Beispiel wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentrycachedtearoffa--cominterfaceentrycachedtearoff"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Speichert die Schnittstelle-spezifische Daten für jede Instanz.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Tearoff Schnittstelle.  
  
 *x*  
 [in] Der Name der Klasse, die die Schnittstelle implementiert.  
  
 `punk`  
 [in] Der Name des ein **IUnknown** Zeiger. Muss Mitglied der Klasse, die die COM-Zuordnung enthält. Initialisiert werden soll, um **NULL** im Konstruktor der Klasse des Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schnittstelle nicht verwendet wird, verringert dies die Gesamtgröße der Instanz des Objekts.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#54;](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="a-namecominterfaceentrytearoffa--cominterfaceentrytearoff"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 Macht die abtrennbare Schnittstellen verfügbar.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Tearoff Schnittstelle.  
  
 *x*  
 [in] Der Name der Klasse, die die Schnittstelle implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Als separates Objekt instanziiert wird, jedes Mal, wenn die Schnittstelle dar, die abgefragt werden, ist eine Tearoff Schnittstelle implementiert. In der Regel erstellen Sie die Schnittstelle als eine abtrennbare, wenn die Schnittstelle nur selten verwendet wird, da dies einen Vtable-Zeiger in jeder Instanz des Haupt-Objekts speichert. Die abtrennbare wird gelöscht, wenn der Verweiszähler&0; (null) wird. Die Klasse zur Implementierung der abtrennbare abgeleitet werden sollten `CComTearOffObjectBase` und verfügen über eine eigene COM-Zuordnung.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrychaina--cominterfaceentrychain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 Die COM-Zuordnung der Basisklasse verarbeitet, wenn die Verarbeitung dieser Eintrag in der COM-Zuordnung erreicht wird.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 [in] Eine Basisklasse des aktuellen Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Wenn beispielsweise in den folgenden Code:  
  
 [!code-cpp[NVC_ATL_Windowing Nr.&116;](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Beachten Sie, dass der erste Eintrag in der COM-Zuordnung eine Schnittstelle für das Objekt mit der COM-Zuordnung sein muss. Folglich kann nicht gestartet werden mit die COM-Zuordnungseinträgen `COM_INTERFACE_ENTRY_CHAIN`, wodurch die COM-Zuordnung eines anderen Objekts, an dem Punkt gesucht werden soll, in dem **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** in COM-Zuordnung des Objekts angezeigt wird. Wenn Sie die COM-Zuordnung von einem anderen Objekt zuerst suchen möchten, fügen Sie einen Schnittstelle-Eintrag für **IUnknown** mit COM-Zuordnung, die COM-Zuordnung das andere Objekt dann verkettet. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing&#111;](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentryfunc2a--cominterfaceentryfunc"></a><a name="com_interface_entry_func2"></a>COM_INTERFACE_ENTRY_FUNC  
 Ein allgemeiner Mechanismus für die Einbindung von ATL `QueryInterface` Logik.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle verfügbar gemacht.  
  
 `dw`  
 [in] Ein Parameter übergeben der `func`.  
  
 `func`  
 [in] Der Funktionszeiger, der zurückgegeben wird `iid`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *Iid* entspricht die IID der Schnittstelle abgefragt, und klicken Sie dann auf die angegebene Funktion `func` aufgerufen wird. Die Deklaration für die Funktion sollte sein:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Wenn die Funktion aufgerufen wird, `pv` verweist auf das Klassenobjekt. Die `riid` Parameter bezieht sich auf die Schnittstelle abgefragt wird, `ppv` ist der Zeiger auf den Speicherort, die die Funktion sollte den Zeiger auf die Schnittstelle, und `dw` ist der Parameter, die Sie in den Eintrag angegeben haben. Die Funktion sollte festgelegt \* `ppv` auf **NULL** und zurückgeben **E_NOINTERFACE** oder **S_FALSE** entscheidet es nicht, eine Schnittstelle zurück. Mit **E_NOINTERFACE**, beendet die Verarbeitung der COM-Zuordnung. Mit **S_FALSE**, COM-Zuordnung Verarbeitung wird fortgesetzt, auch wenn keine Schnittstellenzeiger zurückgegeben wurde. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, sollte zurückgegeben `S_OK`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentryfuncblinda--cominterfaceentryfuncblind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 Identisch mit [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), außer dass die Ergebnisse von Abfragen für alle IID in einem Aufruf von `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Parameter  
 `dw`  
 [in] Ein Parameter übergeben der `func`.  
  
 `func`  
 [in] Die Funktion, die aufgerufen wird, wenn dieser Eintrag in der COM-Zuordnung verarbeitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Fehler wird in der COM-Zuordnung Fortsetzung der Verarbeitung führen. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, sollte zurückgegeben `S_OK`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentryfunca--cominterfaceentryfunc"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 Ein allgemeiner Mechanismus für die Einbindung von ATL `QueryInterface` Logik.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle verfügbar gemacht.  
  
 `dw`  
 [in] Ein Parameter übergeben der `func`.  
  
 `func`  
 [in] Der Funktionszeiger, der zurückgegeben wird `iid`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *Iid* entspricht die IID der Schnittstelle abgefragt, und klicken Sie dann auf die angegebene Funktion `func` aufgerufen wird. Die Deklaration für die Funktion sollte sein:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 Wenn die Funktion aufgerufen wird, `pv` verweist auf das Klassenobjekt. Die `riid` Parameter bezieht sich auf die Schnittstelle abgefragt wird, `ppv` ist der Zeiger auf den Speicherort, die die Funktion sollte den Zeiger auf die Schnittstelle, und `dw` ist der Parameter, die Sie in den Eintrag angegeben haben. Die Funktion sollte festgelegt \* `ppv` auf **NULL** und zurückgeben **E_NOINTERFACE** oder **S_FALSE** entscheidet es nicht, eine Schnittstelle zurück. Mit **E_NOINTERFACE**, beendet die Verarbeitung der COM-Zuordnung. Mit **S_FALSE**, COM-Zuordnung Verarbeitung wird fortgesetzt, auch wenn keine Schnittstellenzeiger zurückgegeben wurde. Wenn die Funktion einen Schnittstellenzeiger zurückgibt, sollte zurückgegeben `S_OK`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-namecominterfaceentrynointerfacea--cominterfaceentrynointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 Gibt **E_NOINTERFACE** und COM-Zuordnung verarbeiten, wenn für die angegebene Schnittstelle abgefragt wird beendet.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Text für den Schnittstellenbezeichner erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können dieses Makro verwenden, um zu verhindern, dass eine Schnittstelle in einem bestimmten Fall verwendet wird. Beispielsweise können Sie dieses Makro einfügen, in der COM-Zuordnung direkt vor `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` zu verhindern, dass eine Abfrage für die Schnittstelle, die das Aggregat inneren Unknown weitergeleitet wird.  
  
 Die Schnittstelle, die IID wird durch Anhängen konstruiert *x* auf `IID_`. Zum Beispiel wenn *x* ist `IPersistStorage`, werden die IID `IID_IPersistStorage`.  
  
 Finden Sie unter [COM_INTERFACE_ENTRY-Makros](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) Hinweise zu COM-map-Eingaben.  
  
##  <a name="a-nameendcommapa--endcommap"></a><a name="end_com_map"></a>END_COM_MAP  
 Beendet die Definition der COM-schnittstellenzuordnung.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Globale Funktionen COM-Zuordnung](../../atl/reference/com-map-global-functions.md)

