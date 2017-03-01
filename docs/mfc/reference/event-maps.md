---
title: Ereigniszuordnungen | Microsoft-Dokumentation
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
- event maps
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
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
ms.openlocfilehash: 4c4777496ce609d7c2fa20da726f211264095b6e
ms.lasthandoff: 02/24/2017

---
# <a name="event-maps"></a>Ereigniszuordnungen
Wenn möchte, dass ein Steuerelement des Containers zu informieren, die eine Aktion (vom Entwickler Steuerelements bestimmt) (z. B. eine Tastenkombination, klicken mit der Maus oder eine Änderung an den Zustand des Steuerelements) geschehen wird ein Ereignis auslösen-Funktion aufgerufen. Diese Funktion teilt das Steuerelement-Container, das eine wichtige Aktion aufgetreten ist, durch das zugehörige Ereignis auslöst.  
  
 Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, das zum Auslösen von Ereignissen optimiert. In diesem Modell "ereigniszuordnungen" werden verwendet, um festzulegen, welche Funktionen die Ereignisse für ein bestimmtes Steuerelement ausgelöst werden. Ereigniszuordnungen enthalten ein Makro für jedes Ereignis. Eine ereigniszuordnung auslöst, z. B. eine Aktie auf Ereignis wie folgt aussehen kann:  
  
 [!code-cpp[NVC_MFCAxCtl Nr.&16;](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 Die **EVENT_STOCK_CLICK** -Makro gibt an, dass das Steuerelement eine Aktie klicken Sie auf Ereignis jedes Mal, wenn es erkennt, dass eine Maus ausgelöst wird. Eine ausführlichere Liste anderer vordefinierter Ereignisse, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md). Makros sind auch verfügbar, um benutzerdefinierte Ereignisse anzugeben.  
  
 Obwohl die Ereignis-Makros wichtig sind, Sie im Allgemeinen nicht diese direkt eingeben. Dies ist da Eigenschaftenfenster Ereignis Meldungszuordnungseinträge automatisch in den Quelldateien, erstellt Wenn Sie es verwenden, um Ereignisse auslösen – Funktionen mit Ereignissen verknüpfen. Jedes Mal, wenn Sie bearbeiten oder Hinzufügen eines Eintrags Ereignis zuordnen möchten können Sie das Fenster Eigenschaften.  
  
 Um ereigniszuordnungen zu unterstützen, stellt MFC die folgenden Makros:  
  
### <a name="event-map-declaration-and-demarcation"></a>Ereignisdeklaration und Demarkation  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|Deklariert, dass eine Event-Zuordnung in einer Klasse verwendet werden soll, Ereignisse auslösen von Ereignissen Funktionen zuordnen (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_EVENT_MAP](#begin_event_map)|Beginn der Definition eine Event-Zuordnung (muss in der klassenimplementierung verwendet werden).|  
|[END_EVENT_MAP](#end_event_map)|Beendet die Definition einer Event-Zuordnung (muss in der klassenimplementierung verwendet werden).|  
  
### <a name="event-mapping-macros"></a>Ereignis-Mapping-Makros  
  
|||  
|-|-|  
|[EVENT_CUSTOM](#event_custom)|Gibt an, welche Ereignisse auslösen – Funktion das angegebene Ereignis ausgelöst wird.|  
|[EVENT_CUSTOM_ID](#event_custom_id)|Gibt an, welche Ereignisse auslösen –-Funktion mit einer festgelegten Dispatch-ID das angegebene Ereignis auslöst|  
  
### <a name="message-mapping-macros"></a>Meldungszuordnungsmakros  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|Gibt ein benutzerdefiniertes Verb vom OLE-Steuerelements behandelt.|  
|[ON_STDOLEVERB](#on_stdoleverb)|Überschreibt eine standard-Verb Zuordnung des OLE-Steuerelements.|  
  
##  <a name="a-namedeclareeventmapa--declareeventmap"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Event-Zuordnung, um die Ereignisse angeben, wird das Steuerelement ausgelöst.  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_EVENT_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert die `BEGIN_EVENT_MAP` -Makro, Makroeinträge für die einzelnen Ereignisse für das Steuerelement, und die `END_EVENT_MAP` Makro, das Ende der Ereignisliste zu deklarieren.  
  
 Weitere Informationen zu ereigniszuordnungen, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-namebegineventmapa--begineventmap"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP  
 Der Beginn der Definition der ereigniszuordnung.  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt der Namen der Steuerelementklasse, dessen Ereignis zuzuordnen, dies, ist.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse des `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp)-Datei, die Memberfunktionen für die Klasse definiert, die ereigniszuordnung mit der `BEGIN_EVENT_MAP` -Makro, dann fügen Sie die Makroeinträge für jedes der Ereignisse, und schließen Sie die ereigniszuordnung mit den `END_EVENT_MAP` Makro.  
  
 Weitere Informationen zum Ereignis zugeordnet wird und die `BEGIN_EVENT_MAP` -Makro, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameendeventmapa--endeventmap"></a><a name="end_event_map"></a>END_EVENT_MAP  
 Verwenden der `END_EVENT_MAP` Makro zum Beenden der Definition der ereigniszuordnung.  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameeventcustoma--eventcustom"></a><a name="event_custom"></a>EVENT_CUSTOM  
 Definiert einen Ereignis-Eintrag für ein benutzerdefiniertes Ereignis.  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `pszName`  
 Der Name des Ereignisses.  
  
 `pfnFire`  
 Der Name des Ereignisses auslösende Funktion.  
  
 `vtsParams`  
 Eine durch Leerzeichen getrennte Liste von ein oder mehrere Konstanten, die Parameterliste für die Funktion angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Parameter ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Gibt eine Liste mit eine 32-Bit-Ganzzahl, die einen RGB darstellt Farbwert, gefolgt von einem Zeiger auf die **IFontDisp** Schnittstelle eines Schriftart OLE-Objekts.  
  
 Die **VTS_** Konstanten und ihre Bedeutungen lauten wie folgt:  
  
|Symbol|Parametertyp|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**WÄHRUNG**|  
|**VTS_DATE**|**DATUM**|  
|**VTS_BSTR**|**const char\***|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_FONT**|**IFontDispatch\***|  
|**VTS_HANDLE**|`HANDLE`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const-Variante\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE**|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_YSIZE_PIXELS**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_YSIZE_HIMETRIC**|  
  
> [!NOTE]
>  Zusätzliche Variante Konstanten für alle variant-Typen, mit Ausnahme von definiert wurden **VTS_FONT** und **VTS_PICTURE**, die einen Zeiger auf die variant-Daten bereitstellen. Diese Konstanten werden mit dem Namen mit dem **VTS_P** `constantname` Konvention. Beispielsweise **VTS_PCOLOR** ist ein Zeiger auf eine **VTS_COLOR** konstant.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameeventcustomida--eventcustomid"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID  
 Definiert ein Ereignis auslösen-Funktion für ein benutzerdefiniertes Ereignis für die Dispatch-ID, die durch angegebene `dispid`.  
  
```   
EVENT_CUSTOM_ID(
  pszName,   
  dispid,   
  pfnFire,
  vtsParams)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `pszName`  
 Der Name des Ereignisses.  
  
 `dispid`  
 Die Dispatch-ID, die vom Steuerelement verwendet werden, wenn das Ereignis ausgelöst.  
  
 `pfnFire`  
 Der Name des Ereignisses auslösende Funktion.  
  
 `vtsParams`  
 Eine Variable Liste von Parametern an den Steuerelementcontainer übergeben, wenn das Ereignis ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen, nicht durch Kommas, gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Gibt eine Liste mit eine 32-Bit-Ganzzahl, die einen RGB darstellt Farbwert, gefolgt von einem Zeiger auf die **IFontDisp** Schnittstelle eines Schriftart OLE-Objekts.  
  
 Eine Liste der **VTS_** Konstanten finden Sie unter [EVENT_CUSTOM](#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="a-nameonoleverba--onoleverb"></a><a name="on_oleverb"></a>ON_OLEVERB  
 Dieses Makro definiert einen Zuordnungseintrag für Nachricht, der einen bestimmten Member-Funktion des Steuerelements ein benutzerdefiniertes Verb zuordnet.  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *idsVerbName*  
 Die Zeichenfolgenressource-ID des Namens des Verbs.  
  
 `memberFxn`  
 Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Editor kann verwendet werden, um benutzerdefinierte Verbnamen zu erstellen, die der Tabelle hinzugefügt werden.  
  
 Der Funktionsprototyp für `memberFxn` ist:  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 Die Werte der `lpMsg`, `hWndParent`, und `lpRect` Parameter entnommen, die die entsprechenden Parameter von der **IOleObject** Member-Funktion.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxole.h  
  
##  <a name="a-nameonstdoleverba--onstdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB  
 Verwenden Sie dieses Makro, um das Standardverhalten des standard-Verb außer Kraft setzen.  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Der standard Verbindex für das Verb überschrieben wird.  
  
 `memberFxn`  
 Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der standard-Verbindex hat die Form **OLEIVERB_**, gefolgt von einer Aktion. `OLEIVERB_SHOW`, `OLEIVERB_HIDE`, und `OLEIVERB_UIACTIVATE` sind einige Beispiele für standard-Verben.  
  
 Finden Sie unter [ON_OLEVERB](#on_oleverb) eine Beschreibung der Funktionsprototyp als zu verwendenden der `memberFxn` Parameter.  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxole.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

