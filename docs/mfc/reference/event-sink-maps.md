---
title: Ordnet die Ereignissenke | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event sink maps
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 33bf66d18b499787a34b2da501bb3e8ead255459
ms.lasthandoff: 02/24/2017

---
# <a name="event-sink-maps"></a>Ereignissenkenzuordnungen
Wenn eingebettetes OLE-Steuerelement ein Ereignis ausgelöst wird, empfängt der Container des Steuerelements das Ereignis mithilfe eines Mechanismus, eine "Event Sink-Zuordnung," von MFC bereitgestellten aufgerufen. Dieses Ereignis Sink-Zuordnung bezeichnet Handlerfunktionen für jedes Ereignis als auch Parameter dieser Ereignisse. Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="event-sink-maps"></a>Ereignissenkenzuordnungen  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Startet die Definition von einem Ereignis Sink-Zuordnung.|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Deklariert eine Ereignis Sink-Zuordnung.|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|Beendet die Definition einer Ereignis-Sink-Zuordnung.|  
|[ON_EVENT](#on_event)|Definiert einen Ereignishandler für ein bestimmtes Ereignis.|  
|[ON_EVENT_RANGE](#on_event_range)|Definiert einen Ereignishandler für ein bestimmtes Ereignis ausgelöst wird, aus einem Satz von OLE-Steuerelemente.|  
|[ON_EVENT_REFLECT](#on_event_reflect)|Empfängt Ereignisse vom Steuerelement ausgelöst wird, bevor sie von der Container des Steuerelements behandelt werden.|  
|[ON_PROPNOTIFY](#on_propnotify)|Definiert einen Handler für die Behandlung von eigenschaftenbenachrichtigungen eines OLE-Steuerelements.|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|Definiert einen Handler für die Behandlung der eigenschaftenbenachrichtigungen aus einem Satz von OLE-Steuerelemente.|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Empfängt eigenschaftenbenachrichtigungen, die vom Steuerelement gesendet wird, bevor sie von der Container des Steuerelements behandelt werden.|  
  
##  <a name="a-namebegineventsinkmapa--begineventsinkmap"></a><a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP  
 Der Beginn der Definition der Zuordnung Ereignissenke.  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Control-Klasse, deren Ereignissenke zuordnen, dies, ist.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse des `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp)-Datei, die Memberfunktionen für die Klasse definiert, die Ereignis-Sink-Zuordnung mit der `BEGIN_EVENTSINK_MAP` -Makro, dann Makro Einträge für jedes Ereignis benachrichtigt werden sollen, und führen Sie die Ereignis-Sink-Zuordnung mit dem `END_EVENTSINK_MAP` Makro.  
  
 Weitere Informationen zu ereignissenkenzuordnungen und OLE-Steuerelement-Container, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-namedeclareeventsinkmapa--declareeventsinkmap"></a><a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP  
 Ein OLE-Container bieten eine Event Sink-Zuordnung zum Angeben von Ereignissen, denen der Container der benachrichtigt werden soll.  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_EVENTSINK_MAP` Makro am Ende der Klassendeklaration. Klicken Sie auf die. CPP-Datei, die das Element definiert für die Klasse funktioniert, verwenden Sie die `BEGIN_EVENTSINK_MAP` -Makro, Makroeinträge für jedes der Ereignisse, benachrichtigt werden und die `END_EVENTSINK_MAP` Makro zum Ende der Liste der Ereignissenke zu deklarieren.  
  
 Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameendeventsinkmapa--endeventsinkmap"></a><a name="end_eventsink_map"></a>END_EVENTSINK_MAP  
 Beendet die Definition der Zuordnung Ereignissenke.  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-nameoneventa--onevent"></a><a name="on_event"></a>ON_EVENT  
 Verwenden der `ON_EVENT` Makro eine Ereignishandlerfunktion für ein Ereignis definieren, die von OLE-Steuerelement ausgelöst.  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 `id`  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müsste ein **BOOL** zurückgeben, Typ und die Parametertypen, die Parameter des Ereignisses übereinstimmen (finden Sie unter `vtsParams`). Die Funktion zurückgeben soll **TRUE** an, dass das Ereignis wurde, andernfalls behandelt **FALSE**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträgen, wie z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit eine kurze ganze Zahl, gefolgt von einer **BOOL**.  
  
 Eine Liste der **VTS_** Konstanten finden Sie unter [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-nameoneventrangea--oneventrange"></a><a name="on_event_range"></a>ON_EVENT_RANGE  
 Verwenden der `ON_EVENT_RANGE` Makros definieren eine Ereignishandlerfunktion für ein Ereignis ausgelöst wird, von jedem OLE-Steuerelement eine Steuerelement-ID auf einen zusammenhängenden Bereich von IDs müssen.  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 `idFirst`  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 `idLast`  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 `dispid`  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müsste ein **BOOL** Rückgabetyp, die als erstes einen Parameter vom Typ **UINT** (für die Steuerelement-ID), und zusätzliche Parametertypen, die Parameter des Ereignisses übereinstimmen (finden Sie unter `vtsParams`). Die Funktion zurückgeben soll **TRUE** an, dass das Ereignis wurde, andernfalls behandelt **FALSE**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Die erste Konstante muss vom Typ **VTS_I4**, für die Steuerelement-ID. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträgen, wie z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit eine kurze ganze Zahl, gefolgt von einer **BOOL**.  
  
 Eine Liste der **VTS_** Konstanten finden Sie unter [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Ereignishandler für das MouseDown-Ereignis für die drei Steuerelemente implementiert ( `IDC_MYCTRL1` über `IDC_MYCTRL3`). Die Ereignishandlerfunktion `OnRangeMouseDown`, in der Headerdatei der Dialogfeldklasse deklariert ist ( `CMyDlg`) als:  
  
 [!code-cpp[NVC_MFCAutomation&#12;](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 Der folgende Code wird in der Implementierungsdatei der Dialogfeldklasse definiert.  
  
 [!code-cpp[NVC_MFCAutomation&#13;](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-nameoneventreflecta--oneventreflect"></a><a name="on_event_reflect"></a>ON_EVENT_REFLECT  
 Die `ON_EVENT_REFLECT` -Makro, wenn im Ereignis Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, verwendet empfängt Ereignisse vom Steuerelement ausgelöst wird, bevor sie von der Container des Steuerelements behandelt werden.  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 DISPID  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müsste ein **BOOL** -Rückgabetyp und Parametertypen, die Parameter des Ereignisses übereinstimmen (finden Sie unter `vtsParams`). Die Funktion zurückgeben soll **TRUE** an, dass das Ereignis wurde, andernfalls behandelt **FALSE**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträgen, wie z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten.  
  
 Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit eine kurze ganze Zahl, gefolgt von einer **BOOL**.  
  
 Eine Liste der **VTS_** Konstanten finden Sie unter [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-nameonpropnotifya--onpropnotify"></a><a name="on_propnotify"></a>ON_PROPNOTIFY  
 Verwenden der `ON_PROPNOTIFY` Makro, um ein Ereignissenke Zuordnungseintrag zum Behandeln von eigenschaftenbenachrichtigungen ein OLE-Steuerelement zu definieren.  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 `id`  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müsste ein **BOOL** Rückgabetyp und ein **BOOL\* ** Parameter. Diese Funktion sollte den Parameter auf festgelegt **TRUE** zu der zu ändernden Eigenschaft und **FALSE** , zu unterbinden. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müsste ein **BOOL** Rückgabetyp und ein **UINT** Parameter. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit eine kurze ganze Zahl, gefolgt von einer **BOOL**.  
  
 Eine Liste der **VTS_** Konstanten finden Sie unter [EVENT_CUSTOM](event-maps.md#event_custom).  
  
##  <a name="a-nameonpropnotifyrangea--onpropnotifyrange"></a><a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE  
 Verwenden der `ON_PROPNOTIFY_RANGE` Makro definiert ein Ereignissenke Zuordnungseintrag für die Behandlung der eigenschaftenbenachrichtigungen von einem OLE-Steuerelement eine Steuerelement-ID auf einen zusammenhängenden Bereich von IDs müssen.  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 `idFirst`  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 `idLast`  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müsste ein **BOOL** Rückgabetyp und **UINT** und **BOOL\* ** Parameter. Die Funktion sollte den Parameter auf festgelegt **TRUE** zu der zu ändernden Eigenschaft und **FALSE** , zu unterbinden. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müsste ein **BOOL** Rückgabetyp und ein **UINT** Parameter. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="a-nameonpropnotifyreflecta--onpropnotifyreflect"></a><a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT  
 Die `ON_PROPNOTIFY_REFLECT` -Makro, wenn im Ereignis Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, verwendet empfängt eigenschaftenbenachrichtigungen, die vom Steuerelement gesendet wird, bevor sie von der Container des Steuerelements behandelt werden.  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignis Sink-Zuordnung gehört.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müsste ein **BOOL** Rückgabetyp und ein **BOOL\* ** Parameter. Diese Funktion sollte den Parameter auf festgelegt **TRUE** zu der zu ändernden Eigenschaft und **FALSE** , zu unterbinden. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müsste ein **BOOL** -Rückgabetyp und keine Parameter. Die Funktion zurückgeben soll **TRUE** an, dass die Benachrichtigung wurde behandelt, andernfalls **FALSE**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

