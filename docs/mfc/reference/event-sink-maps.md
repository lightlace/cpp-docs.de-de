---
title: Ereignissenke Zuordnungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0322d6b304366e598fc3db206d4c2e4b9b9d6315
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336604"
---
# <a name="event-sink-maps"></a>Ereignissenkenzuordnungen
Wenn eingebettete OLE-Steuerelements ein Ereignis ausgelöst wird, erhält der Container des Steuerelements das Ereignis mithilfe von sogenannten, eine "Event-Senke-Zuordnung," von MFC bereitgestellten. Diese Senke ereigniszuordnung kennzeichnet Handlerfunktionen für jedes Ereignis als auch die Parameter dieser Ereignisse. Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="event-sink-maps"></a>Ereignissenkenzuordnungen  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Startet die Definition eine Senke-Event-Zuordnung.|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Deklariert eine Zuordnung der Ereignis-Senke.|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|Beendet die Definition eine Senke-Event-Zuordnung.|  
|[ON_EVENT](#on_event)|Definiert einen Ereignishandler für ein bestimmtes Ereignis.|  
|[ON_EVENT_RANGE](#on_event_range)|Definiert einen Ereignishandler für ein bestimmtes Ereignis ausgelöst wird, aus einer Reihe von OLE-Steuerelemente.|  
|[ON_EVENT_REFLECT](#on_event_reflect)|Empfängt Ereignisse vom Steuerelement ausgelöst wird, bevor sie vom Container des Steuerelements verarbeitet werden.|  
|[ON_PROPNOTIFY](#on_propnotify)|Definiert einen Handler für das Behandeln von eigenschaftsbenachrichtigungen eines OLE-Steuerelements.|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|Definiert einen Handler für die Behandlung von eigenschaftsbenachrichtigungen aus einer Reihe von OLE-Steuerelemente.|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Empfängt eigenschaftsbenachrichtigungen vom Steuerelement gesendet werden, bevor sie vom Container des Steuerelements verarbeitet werden.|  
  
##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP  
 Der Beginn der Definition der Zuordnung Ereignissenke.  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Gibt an, dass der Name der Steuerelement-Klasse, deren Ereignissenke eine Zuordnung, ist.  
  
 *Basisklasse*  
 Gibt den Namen der Basisklasse der *TheClass*.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Member-Funktionen für die Klasse definiert die Senke ereigniszuordnung mit dem BEGIN_EVENTSINK_MAP-Makro, und klicken Sie dann hinzufügen Makroeinträge für jedes Ereignis benachrichtigt werden sollen, und dem Abschließen der Ereignis-Sink-Zuordnung mit dem END_EVENTSINK_MAP-Makro.  
  
 Weitere Informationen zu ereignissenkenzuordnungen und OLE-Control-Container, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP  
 Ein OLE-Container bieten eine Senke ereigniszuordnung zum Angeben von Ereignissen, die, denen der Container, der benachrichtigt werden soll.  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie das DECLARE_EVENTSINK_MAP-Makro, am Ende der Klassendeklaration. Klicken Sie auf der. CPP-Datei, die die Member-Funktionen für die Klasse definiert verwenden die BEGIN_EVENTSINK_MAP-Makro, das Makroeinträge für jedes der Ereignisse benachrichtigt werden sollen, und die END_EVENTSINK_MAP-Makro, um das Ende der Liste der Ereignissenke zu deklarieren.  
  
 Weitere Informationen zu ereignissenkenzuordnungen, finden Sie im Artikel [ActiveX-Steuerelementcontainer](../../mfc/activex-control-containers.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP  
 Beendet die Definition der Zuordnung Ereignissenke.  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event"></a>  ON_EVENT  
 Verwenden Sie die ON_EVENT-Makro, um eine Ereignishandlerfunktion für ein Ereignis ausgelöst wird, von einem OLE-Steuerelement zu definieren.  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 *ID*  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 *DISPID*  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 *pfnHandler*  
 Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen einen booleschen Wert zurückgeben, Typ und die Parametertypen, die die Parameter des Ereignisses entsprechen (siehe *VtsParams*). Die Funktion sollte "true", um anzugeben, dass das Ereignis behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *vtsParams*  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Hierbei handelt es sich um die gleichen Konstanten, die in die Dispatch-Zuordnungseinträge wie z. B. DISP_FUNCTION verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von "bool" enthält.  
  
 Eine Liste mit den **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event_range"></a>  ON_EVENT_RANGE  
 Verwenden Sie die ON_EVENT_RANGE-Makro, um eine Ereignishandlerfunktion für ein Ereignis wird ausgelöst, durch alle OLE-Steuerelements mit einer Steuerelement-ID in einen zusammenhängenden Bereich von-IDs zu definieren.  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 *idFirst*  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 *idLast*  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 *DISPID*  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 *pfnHandler*  
 Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen Rückgabetyp und einen ersten Parameter vom Typ "uint" (für die Steuerelement-ID) und zusätzliche Parametertypen, die die Parameter des Ereignisses entsprechen "bool" (siehe *VtsParams*). Die Funktion sollte "true", um anzugeben, dass das Ereignis behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *vtsParams*  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Das erste Konstante muss vom Typ VTS_I4, für die Steuerelement-ID. Hierbei handelt es sich um die gleichen Konstanten, die in die Dispatch-Zuordnungseinträge wie z. B. DISP_FUNCTION verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von "bool" enthält.  
  
 Eine Liste mit den **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird einen Ereignishandler für das MouseDown-Ereignis, für die drei Steuerelemente implementiert (IDC_MYCTRL1 über IDC_MYCTRL3). Die Ereignishandlerfunktion, `OnRangeMouseDown`, wird in der Headerdatei der Dialogfeldklasse deklariert ( `CMyDlg`) als:  
  
 [!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 Der folgende Code ist in der Implementierungsdatei der Dialogfeldklasse definiert.  
  
 [!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT  
 Die ON_EVENT_REFLECT-Makro, das bei der Verwendung in der ereignismeldung Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, empfängt Ereignisse vom Steuerelement ausgelöst wird, bevor sie vom Container des Steuerelements verarbeitet werden.  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 DISPID  
 Die Dispatch-ID des Ereignisses vom Steuerelement ausgelöst werden soll.  
  
 *pfnHandler*  
 Zeiger auf eine Memberfunktion, die das Ereignis behandelt. Diese Funktion müssen einen booleschen Wert zurückgeben, Typ und die Parametertypen, die die Parameter des Ereignisses entsprechen (siehe *VtsParams*). Die Funktion sollte "true", um anzugeben, dass das Ereignis behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *vtsParams*  
 Eine Sequenz von **VTS_** Konstanten, die die Typen der Parameter für das Ereignis angibt. Hierbei handelt es sich um die gleichen Konstanten, die in die Dispatch-Zuordnungseinträge wie z. B. DISP_FUNCTION verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten.  
  
 Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von "bool" enthält.  
  
 Eine Liste mit den **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_propnotify"></a>  ON_PROPNOTIFY  
 Verwenden Sie die on_propnotifymakro, um einen Eintrag zur Zuordnung von Ereignis-Senke für die Behandlung von eigenschaftsbenachrichtigungen eines OLE-Steuerelements zu definieren.  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 *ID*  
 Die Steuerelement-ID des OLE-Steuerelements.  
  
 *DISPID*  
 Die Dispatch-ID von der Eigenschaft, die in der Benachrichtigung zum.  
  
 *pfnRequest*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnRequestEdit` Benachrichtigung für diese Eigenschaft. Diese Funktion müssen Rückgabetyp "bool" und ein **"bool"\***  Parameter. Diese Funktion sollte der Parameter auf "true", sodass die Eigenschaft geändert und "false", um keine zuzulassen festgelegt. Die Funktion sollte "true", um anzugeben, dass die Benachrichtigung behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *pfnChanged*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnChanged` Benachrichtigung für diese Eigenschaft. Die Funktion muss "bool", Typ und ein UINT-Parameter zurückgegeben haben. Die Funktion sollte "true", um anzugeben, dass Benachrichtigungen behandelt wurde zurückgegeben wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von "bool" enthält.  
  
 Eine Liste mit den **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](event-maps.md#event_custom).  
  
##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE  
 Verwenden Sie die ON_PROPNOTIFY_RANGE-Makro, um einen Eintrag im Ereignissenke-Zuordnung, für die Behandlung von eigenschaftsbenachrichtigungen aus eine Steuerelement-ID in einen zusammenhängenden Bereich von IDs müssen alle OLE-Steuerelements zu definieren.  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 *idFirst*  
 Die Steuerelement-ID des ersten OLE-Steuerelements im Bereich.  
  
 *idLast*  
 Die Steuerelement-ID des letzten OLE-Steuerelements im Bereich.  
  
 *DISPID*  
 Die Dispatch-ID von der Eigenschaft, die in der Benachrichtigung zum.  
  
 *pfnRequest*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnRequestEdit` Benachrichtigung für diese Eigenschaft. Diese Funktion müssen Rückgabetyp "bool" und "uint", und **"bool"\***  Parameter. Die Funktion sollte der Parameter auf "true", sodass die Eigenschaft geändert und "false", um keine zuzulassen festgelegt. Die Funktion sollte "true", um anzugeben, dass Benachrichtigungen behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *pfnChanged*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnChanged` Benachrichtigung für diese Eigenschaft. Die Funktion muss "bool", Typ und ein UINT-Parameter zurückgegeben haben. Die Funktion sollte "true", um anzugeben, dass Benachrichtigungen behandelt wurde zurückgegeben wird. andernfalls "false".  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT  
 Die ON_PROPNOTIFY_REFLECT-Makro, das bei der Verwendung in der ereignismeldung Sink-Zuordnung ein OLE-Steuerelement-Wrapperklasse, empfängt eigenschaftsbenachrichtigungen für das Steuerelement gesendet werden, bevor sie vom Container des Steuerelements verarbeitet werden.  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, zu der diese Senke ereigniszuordnung gehört.  
  
 *DISPID*  
 Die Dispatch-ID von der Eigenschaft, die in der Benachrichtigung zum.  
  
 *pfnRequest*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnRequestEdit` Benachrichtigung für diese Eigenschaft. Diese Funktion müssen Rückgabetyp "bool" und ein **"bool"\***  Parameter. Diese Funktion sollte der Parameter auf "true", sodass die Eigenschaft geändert und "false", um keine zuzulassen festgelegt. Die Funktion sollte "true", um anzugeben, dass die Benachrichtigung behandelt wurde zurückgegeben wird. andernfalls "false".  
  
 *pfnChanged*  
 Zeiger auf eine Memberfunktion, die behandelt die `OnChanged` Benachrichtigung für diese Eigenschaft. Die Funktion sollte einen boolescher Wert, der Typ und keine Parameter haben. Die Funktion sollte "true", um anzugeben, dass die Benachrichtigung behandelt wurde zurückgegeben wird. andernfalls "false".  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
