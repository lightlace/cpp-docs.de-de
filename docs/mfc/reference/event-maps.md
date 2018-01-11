---
title: Ereigniszuordnungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords: event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 130e4ecf7534b16ecabf4c35665a4dabe9eee34e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="event-maps"></a>Ereigniszuordnungen
Wenn möchte, dass ein Steuerelement des Containers zu informieren, die eine Aktion, die (vom Steuerelemententwickler bestimmt). (z. B. eine Tastenkombination, klicken mit der Maus oder eine Änderung an der Zustand des Steuerelements erfolgt ist) wird eine Auslösen von Ereignissen Funktion aufgerufen. Diese Funktion teilt den Steuerelementcontainer, den einige wichtige Aktion aufgetreten ist, durch das zugehörige Ereignis auslösen.  
  
 Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell zum Auslösen von Ereignissen optimiert. In diesem Modell "ereigniszuordnungen" werden verwendet, um festzulegen, welche Funktionen die Ereignisse für ein bestimmtes Steuerelement ausgelöst werden. Ereigniszuordnungen enthalten ein Makro für jedes Ereignis. Eine ereigniszuordnung auslöst, z. B. ein Aktienkurs auf Ereignis wie folgt aussehen kann:  
  
 [!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 Die **EVENT_STOCK_CLICK** Makro gibt an, dass das Steuerelement ausgelöst werden, ein Aktienkurs Ereignis jedes Mal, wenn er erkennt, dass eine Maus klicken. Eine ausführlichere Liste von anderen vordefinierten Ereignissen, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md). Makros sind auch verfügbar, um benutzerdefinierte Ereignisse anzugeben.  
  
 Obwohl die Ereignis-Zuordnungsmakros wichtig sind, Sie in der Regel nicht diese direkt einfügen. Dies ist daran, dass im Eigenschaftenfenster Ereignis-Zuordnungseinträge automatisch in den Quellcodedateien, erstellt Wenn Sie es verwenden, um die Ereignisse auslösen von Ereignissen Funktionen zugeordnet. Jedes Mal, wenn Sie verwenden möchten, bearbeiten oder Hinzufügen eines Eintrags ereigniszuordnung können Sie das Eigenschaftenfenster verwenden.  
  
 Ereigniszuordnungen Unterstützung bietet MFC die folgenden Makros:  
  
### <a name="event-map-declaration-and-demarcation"></a>Ereignis Zuordnung Deklaration und Demarkation  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|Deklariert, dass ein ereigniszuordnung Ereignisse auslösen von Ereignissen Funktionen zuordnen (muss in der Klassendeklaration verwendet werden) in einer Klasse verwendet werden.|  
|[BEGIN_EVENT_MAP](#begin_event_map)|Beginn der Definition einer ereigniszuordnung (muss in der klassenimplementierung verwendet werden).|  
|[END_EVENT_MAP](#end_event_map)|Beendet die Definition einer ereigniszuordnung (muss in der klassenimplementierung verwendet werden).|  
  
### <a name="event-mapping-macros"></a>Ereignis-Mapping-Makros  
  
|||  
|-|-|  
|[EVENT_CUSTOM](#event_custom)|Gibt an, welche Ereignisse auslösen-Funktion das angegebene Ereignis ausgelöst wird.|  
|[EVENT_CUSTOM_ID](#event_custom_id)|Gibt an, welche Funktion Auslösen von Ereignissen ausgelöst werden, das angegebene Ereignis unter einer angegebenen Dispatch-ID|  
  
### <a name="message-mapping-macros"></a>Meldungszuordnungsmakros  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|Gibt ein eigenes Verb behandelt, indem die OLE-Steuerelements an.|  
|[ON_STDOLEVERB](#on_stdoleverb)|Überschreibt eine Standardverb Zuordnung des OLE-Steuerelements an.|  
  
##  <a name="declare_event_map"></a>DECLARE_EVENT_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Ereignis-Karte, um die Ereignisse anzugeben, das Steuerelement ausgelöst wird.  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_EVENT_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Memberfunktionen für die Klasse definiert die `BEGIN_EVENT_MAP` -Makro, Makroeinträge für die einzelnen Ereignisse für das Steuerelement, und die `END_EVENT_MAP` Makro, um das Ende der Ereignisliste zu deklarieren.  
  
 Weitere Informationen zu ereigniszuordnungen, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="begin_event_map"></a>BEGIN_EVENT_MAP  
 Die Definition der ereigniszuordnung beginnt.  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Steuerelementklasse, dessen Ereignis ordnen.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse der `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Memberfunktionen für die Klasse definiert, die ereigniszuordnung mit der `BEGIN_EVENT_MAP` -Makro, dann fügen Sie die Makroeinträge für die einzelnen Ereignisse, und schließen Sie die ereigniszuordnung mit der `END_EVENT_MAP` Makro.  
  
 Weitere Informationen zum Ereignis zugeordnet ist und die `BEGIN_EVENT_MAP` -Makro, finden Sie im Artikel [ActiveX-Steuerelemente: Ereignisse](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="end_event_map"></a>END_EVENT_MAP  
 Verwenden der `END_EVENT_MAP` Makro zum Beenden der Definition der ereigniszuordnung.  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="event_custom"></a>EVENT_CUSTOM  
 Definiert einen Eintrag für die Ereignis-Zuordnung für ein benutzerdefiniertes Ereignis.  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>Parameter  
 `pszName`  
 Der Name des Ereignisses.  
  
 `pfnFire`  
 Der Name des der Funktion Auslösen des Ereignisses.  
  
 `vtsParams`  
 Eine durch Leerzeichen getrennte Liste ein oder mehrere Konstanten, die die Parameterliste der Funktion angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Parameter ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Gibt eine Liste mit der eine 32-Bit-Ganzzahl, die eine RGB darstellt Farbwert, gefolgt von einem Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart OLE-Objekts.  
  
 Die **VTS_** Konstanten und ihre Bedeutungen lauten wie folgt:  
  
|Symbol|Parametertyp|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**WÄHRUNG**|  
|**VTS_DATE**|**DATE**|  
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
|**VTS_PICTURE**|**Lpicturedisp\***|  
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
>  Zusätzliche Variante Konstanten für alle variant-Typen, mit Ausnahme von definiert wurden **VTS_FONT** und **VTS_PICTURE**, die einen Zeiger auf die Konstante variant-Daten bereitstellen. Diese Konstanten sind benannt der **VTS_P** `constantname` Konvention. Beispielsweise **VTS_PCOLOR** ist ein Zeiger auf eine **VTS_COLOR** konstant.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="event_custom_id"></a>EVENT_CUSTOM_ID  
 Definiert eine Funktion für ein benutzerdefiniertes Ereignis zu angegebene Dispatch-ID gehören Auslösen des Ereignisses `dispid`.  
  
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
 Die Dispatch-ID, die vom Steuerelement verwendet wird, wenn das Ereignis ausgelöst.  
  
 `pfnFire`  
 Der Name des der Funktion Auslösen des Ereignisses.  
  
 `vtsParams`  
 Eine Variable Parameterliste an den Steuerelementcontainer übergeben, wenn das Ereignis ausgelöst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen, nicht durch Kommas, gibt die Parameterliste der Funktion an. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Gibt eine Liste mit der eine 32-Bit-Ganzzahl, die eine RGB darstellt Farbwert, gefolgt von einem Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart OLE-Objekts.  
  
 Eine Liste der **VTS_** -Konstanten finden Sie [EVENT_CUSTOM](#event_custom).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="on_oleverb"></a>ON_OLEVERB  
 Dieses Makro definiert einen Nachrichtenzuordnungseintrag, der eine bestimmte Memberfunktion des Steuerelements ein eigenes Verb zuordnet.  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *idsVerbName*  
 Die Zeichenfolgenressource-ID des Namens für das Verb.  
  
 `memberFxn`  
 Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Editor kann verwendet werden, um benutzerdefinierte Verbnamen zu erstellen, die Ihre Zeichenfolgentabelle hinzugefügt werden.  
  
 Der Funktionsprototyp für `memberFxn` ist:  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 Die Werte der `lpMsg`, `hWndParent`, und `lpRect` Parameter stammen aus der entsprechenden Parameter des der **IOleObject** Memberfunktion.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxole.h  
  
##  <a name="on_stdoleverb"></a>ON_STDOLEVERB  
 Verwenden Sie dieses Makro, um das Standardverhalten aus einem Standardverb überschreiben.  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Der Index der Standardverb für das Verb überschrieben wird.  
  
 `memberFxn`  
 Die Funktion, die vom Framework aufgerufen, wenn das Verb aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardverb Index besitzt das Format **OLEIVERB_**, gefolgt von einer Aktion. `OLEIVERB_SHOW`, `OLEIVERB_HIDE`, und `OLEIVERB_UIACTIVATE` sind einige Beispiele für Standardverben.  
  
 Finden Sie unter [ON_OLEVERB](#on_oleverb) eine Beschreibung der Funktionsprototyp als verwendet werden soll die `memberFxn` Parameter.  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxole.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
