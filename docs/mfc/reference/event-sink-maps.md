---
title: Ereignissenke Zuordnungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords: event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 309474220f081a0eca67d0f83ead21c59eb649e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="event-sink-maps"></a>Ereignissenkenzuordnungen
Bei einem eingebetteten OLE-Steuerelements ein Ereignis ausgelöst wird, erhält der Container des Steuerelements das Ereignis mit einem Mechanismus, der eine "Senke ereigniszuordnung," von MFC bereitgestellten aufgerufen. Dieses Ereignissenke Zuordnung kennzeichnet Handlerfunktionen für jedes Ereignis als auch Parameter dieser Ereignisse. Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="event-sink-maps"></a>Ereignissenkenzuordnungen  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Startet die Definition einer Senke ereigniszuordnung an.|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Deklariert eine Ereignis Sink-Zuordnung.|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|Beendet die Definition einer Senke ereigniszuordnung an.|  
|[ON_EVENT](#on_event)|Definiert einen Ereignishandler für ein bestimmtes Ereignis.|  
|[ON_EVENT_RANGE](#on_event_range)|Definiert einen Ereignishandler für ein bestimmtes Ereignis ausgelöst wird, aus einem Satz von OLE-Steuerelemente.|  
|[ON_EVENT_REFLECT](#on_event_reflect)|Empfängt Ereignisse vom Steuerelement ausgelöst werden, bevor sie von der Container des Steuerelements behandelt werden.|  
|[ON_PROPNOTIFY](#on_propnotify)|Definiert einen Handler für handlingbenachrichtigungen-Eigenschaft eines OLE-Steuerelements an.|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|Definiert einen Handler für die Eigenschaft handlingbenachrichtigungen aus einem Satz von OLE-Steuerelemente.|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Empfängt Eigenschaft Benachrichtigungen, die vom Steuerelement gesendet wird, bevor sie von der Container des Steuerelements behandelt werden.|  
  
##  <a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP  
 Die Definition von der Senke ereigniszuordnung beginnt.  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Steuerelementklasse, deren-Ereignissenke ordnen.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse der `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Memberfunktionen für die Klasse definiert, die Senke ereigniszuordnung mit der `BEGIN_EVENTSINK_MAP` -Makro, dann fügen Sie Makroeinträge für jedes Ereignis benachrichtigt zu werden, und schließen Sie die Senke ereigniszuordnung mit der `END_EVENTSINK_MAP` Makro.  
  
 Weitere Informationen zu ereignissenkenzuordnungen und OLE-Steuerelement-Container, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP  
 Ein OLE-Container bieten eine ereigniszuordnung Senke, um die Ereignisse anzugeben, denen der Container der benachrichtigt wird.  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_EVENTSINK_MAP` Makro am Ende der Klassendeklaration. Klicken Sie auf die. CPP-Datei, die das Element definiert Funktionen für die Klasse, verwenden Sie die `BEGIN_EVENTSINK_MAP` -Makro, Makroeinträge für jedes der Ereignisse, benachrichtigt zu werden und die `END_EVENTSINK_MAP` Makro, um das Ende der Senke Ereignisliste zu deklarieren.  
  
 Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="end_eventsink_map"></a>END_EVENTSINK_MAP  
 Beendet die Definition der Zuordnung Ereignissenke.  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event"></a>ON_EVENT  
 Verwenden der `ON_EVENT` Makro eine Ereignishandlerfunktion für ein Ereignis definieren, die von einer OLE-Steuerelements ausgelöst werden.  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 `id`  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID des Ereignisses, die vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen ein **BOOL** zurückgeben, Typ und die Parametertypen, die die Parameter des Ereignisses entsprechen (finden Sie unter `vtsParams`). Die Funktion zurückgeben sollte **"true"** an, dass das Ereignis behandelt wurde andernfalls **"false"**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträge, z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit einer kurzen ganzen Zahl, gefolgt von einem **BOOL**.  
  
 Eine Liste der **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event_range"></a>ON_EVENT_RANGE  
 Verwenden der `ON_EVENT_RANGE` Makro eine Ereignishandlerfunktion für ein Ereignis definieren, die von jeder OLE-Steuerelements müssen eine Steuerelement-ID in einem zusammenhängenden Bereich von IDs ausgelöst werden.  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 `idFirst`  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 `idLast`  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 `dispid`  
 Die Dispatch-ID des Ereignisses, die vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen eine **BOOL** Rückgabetyp, die einen ersten Parameter vom Typ **"uint"** (für die Steuerelement-ID), und zusätzliche Parametertypen, die die Parameter des Ereignisses entsprechen (finden Sie unter `vtsParams`). Die Funktion zurückgeben sollte **"true"** an, dass das Ereignis behandelt wurde andernfalls **"false"**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Das erste Konstante muss vom Typ **VTS_I4**, für die Steuerelement-ID. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträge, z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit einer kurzen ganzen Zahl, gefolgt von einem **BOOL**.  
  
 Eine Liste der **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht einen Ereignishandler für das MouseDown-Ereignis, das für die drei Steuerelemente implementiert ( `IDC_MYCTRL1` über `IDC_MYCTRL3`). Die Ereignishandlerfunktion `OnRangeMouseDown`, wird in der Headerdatei der Dialogklasse deklariert ( `CMyDlg`) als:  
  
 [!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 Der folgende Code ist in der Implementierungsdatei der Dialogklasse definiert.  
  
 [!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event_reflect"></a>ON_EVENT_REFLECT  
 Die `ON_EVENT_REFLECT` -Makro, bei Verwendung der Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, empfängt die Ereignisse, die vom Steuerelement ausgelöst werden, bevor sie von der Container des Steuerelements behandelt werden.  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 DISPID  
 Die Dispatch-ID des Ereignisses, die vom Steuerelement ausgelöst werden soll.  
  
 `pfnHandler`  
 Ein Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen ein **BOOL** -Rückgabetyp und Parametertypen, die die Parameter des Ereignisses entsprechen (finden Sie unter `vtsParams`). Die Funktion zurückgeben sollte **"true"** an, dass das Ereignis behandelt wurde andernfalls **"false"**.  
  
 `vtsParams`  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Dies sind die gleichen Konstanten, die in Dispatch-Zuordnungseinträge, z. B. verwendet werden `DISP_FUNCTION`.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten.  
  
 Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit einer kurzen ganzen Zahl, gefolgt von einem **BOOL**.  
  
 Eine Liste der **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_propnotify"></a>ON_PROPNOTIFY  
 Verwenden der `ON_PROPNOTIFY` Makro, um ein Ereignissenke-Zuordnungseintrag für handlingbenachrichtigungen Eigenschaft eines OLE-Steuerelements zu definieren.  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 `id`  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müssen ein **BOOL** Rückgabetyp und ein **BOOL\***  Parameter. Diese Funktion sollte den Parameter auf festgelegt **"true"** zum Zulassen der zu ändernden Eigenschaft und **"false"** , zu unterbinden. Die Funktion zurückgeben sollte **"true"** an, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müssen ein **BOOL** Rückgabetyp und ein **"uint"** Parameter. Die Funktion zurückgeben sollte **"true"** um anzugeben, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste mit einer kurzen ganzen Zahl, gefolgt von einem **BOOL**.  
  
 Eine Liste der **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
##  <a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE  
 Verwenden der `ON_PROPNOTIFY_RANGE` Makro auf einen Ereignissenke Map-Eintrag für die Eigenschaft handlingbenachrichtigungen aus jedem OLE-Steuerelement mit einem Steuerelement-ID in einem zusammenhängenden Bereich von-IDs zu definieren.  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 `idFirst`  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 `idLast`  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müssen ein **BOOL** Rückgabetyp und **"uint"** und **BOOL\***  Parameter. Die Funktion sollte den Parameter auf festgelegt **"true"** zum Zulassen der zu ändernden Eigenschaft und **"false"** , zu unterbinden. Die Funktion zurückgeben sollte **"true"** um anzugeben, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müssen ein **BOOL** Rückgabetyp und ein **"uint"** Parameter. Die Funktion zurückgeben sollte **"true"** um anzugeben, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT  
 Die `ON_PROPNOTIFY_REFLECT` -Makro, bei Verwendung der Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, empfängt Eigenschaft Benachrichtigungen, die vom Steuerelement gesendet wird, bevor sie von der Container des Steuerelements behandelt werden.  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, zu der dieses Ereignissenke Zuordnung gehört.  
  
 `dispid`  
 Die Dispatch-ID der Eigenschaft, die die Benachrichtigung beteiligt.  
  
 `pfnRequest`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnRequestEdit** Benachrichtigung für diese Eigenschaft. Diese Funktion müssen ein **BOOL** Rückgabetyp und ein **BOOL\***  Parameter. Diese Funktion sollte den Parameter auf festgelegt **"true"** zum Zulassen der zu ändernden Eigenschaft und **"false"** , zu unterbinden. Die Funktion zurückgeben sollte **"true"** an, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
 `pfnChanged`  
 Zeiger auf eine Memberfunktion, die behandelt die **OnChanged** Benachrichtigung für diese Eigenschaft. Die Funktion müssen ein **BOOL** -Rückgabetyp und keine Parameter. Die Funktion zurückgeben sollte **"true"** an, dass die Benachrichtigung wurde verarbeitet andernfalls **"false"**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
