---
title: DHTML-Ereigniszuordnungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros
- DHTML, event map macros
- macros, DHTML event map
- DHTML events, event map
- DHTML events
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
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
ms.openlocfilehash: 8be59b52e06241651a2f605ab949efffd0e010d3
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-event-maps"></a>DHTML-Ereigniszuordnungen
Die folgenden Makros können zum Behandeln von DHTML-Ereignissen verwendet werden.  
  
## <a name="dhtml-event-map-macros"></a>DHTML Ereigniszuordnungs-Makros  
 Die folgenden Makros können zum Behandeln von DHTML-Ereignissen in [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleitete Klassen.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Kennzeichnet den Beginn der Zuordnung DHTML-Ereignis.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Kennzeichnet den Beginn der Zuordnung DHTML-Ereignis.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Deklariert die Zuordnung der DHTML-Ereignis.|  
|[DHTML_EVENT](#dhtml_event)|Behandeln eines Ereignisses auf der Ebene für ein einzelnes HTML-Element verwendet.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Behandeln eines Ereignisses, das ausgelöst wird, indem ein ActiveX-Steuerelement verwendet.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Behandeln eines Ereignisses auf der Ebene für alle HTML-Elemente mit einer bestimmten CSS-Klasse verwendet.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Behandeln eines Ereignisses auf Elementebene verwendet.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Zum Behandeln der **Onafterupdate** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Zum Behandeln der **Onbeforeupdate** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Zum Behandeln der **Onblur** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Zum Behandeln der `onchange` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Zum Behandeln der **Onclick** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Zum Behandeln der **Ondataavailable** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Zum Behandeln der **Ondatasetchanged** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Zum Behandeln der **Ondatasetcomplete** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Zum Behandeln der **Ondblclick** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Zum Behandeln der **Ondragstart** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Zum Behandeln der **Onerrorupdate** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Zum Behandeln der **Onfilterchange** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Zum Behandeln der **Onfocus** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Zum Behandeln der `onhelp` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Zum Behandeln der **Onkeydown** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Zum Behandeln der **Onkeypress** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Zum Behandeln der **Onkeyup** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Zum Behandeln der **Onmousedown** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Zum Behandeln der `onmousemove` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Zum Behandeln der **Onmouseout** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Zum Behandeln der **Onmouseover** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Zum Behandeln der **Onmouseup** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Zum Behandeln der **Onresize** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Zum Behandeln der **Onrowenter** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Zum Behandeln der **Onrowexit** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Zum Behandeln der **Onselectstart** Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Behandeln eines Ereignisses auf der Ebene für alle Elemente mit einer bestimmten HTML-Tags verwendet.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Markiert das Ende der Zuordnung DHTML-Ereignis.|  
  
## <a name="url-event-map-macros"></a>URL Ereigniszuordnungs-Makros  
 Die folgenden Makros können zum Behandeln von DHTML-Ereignissen in [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klassen.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Kennzeichnet den Beginn der Zuordnung mehrseitigen DHTML und URL-Ereignis.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Markiert den Anfang einer eingebetteten DHTML-ereigniszuordnung.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Kennzeichnet den Beginn einer URL Ereignis Eintrag Zuordnung.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Deklariert die mehrseitige DHTML und URL-Event-Zuordnung.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Markiert das Ende der Zuordnung mehrseitigen DHTML und URL-Ereignis.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Markiert das Ende einer eingebetteten DHTML-ereigniszuordnung.|  
|[END_URL_ENTRIES](#end_url_entries)|Markiert das Ende einer URL Ereignis Eintrag Zuordnung.|  
|[URL_EVENT_ENTRY](#url_event_entry)|Ordnet eine URL oder HTML-Ressource auf eine Seite in ein mehrseitiges Dialogfeld.|  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapa--begindhtmleventmap"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP  
 Markiert den Anfang der DHTML-ereigniszuordnung in der Quelldatei für die Klasse identifizierten platziert `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse, die die Zuordnung der DHTML-Ereignis enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzufügen **CDHtmlDialog** , die verwendet werden kann, um Ereignisse weiterzuleiten, die von HTML-Elementen oder ActiveX-Steuerelemente auf einer Webseite mit Handlerfunktionen in der Klasse ausgelöst werden.  
  
 Ort der `BEGIN_DHTML_EVENT_MAP` -Makro in der Implementierungsdatei (.cpp) der Klasse, gefolgt von `DHTML_EVENT` Makros für die Ereignisse die Klasse behandelt wird (z. B. `DHTML_EVENT_ONMOUSEOVER` für Mouseover-Ereignisse). Verwenden der [END_DHTML_EVENT_MAP](#end_dhtml_event_map) Makro, um das Ende der ereigniszuordnung markieren. Diese Makros implementieren Sie die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapinlinea--begindhtmleventmapinline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE  
 Markiert den Anfang der Zuordnung des DHTML-Ereignis innerhalb der Klassendefinition für `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse, die die Zuordnung der DHTML-Ereignis enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzufügen **CDHtmlDialog** , die verwendet werden kann, um Ereignisse weiterzuleiten, die von HTML-Elementen oder ActiveX-Steuerelemente auf einer Webseite mit Handlerfunktionen in der Klasse ausgelöst werden.  
  
 Ort der `BEGIN_DHTML_EVENT_MAP` Makro in der Klasse-Definitionsdatei (. h), gefolgt von `DHTML_EVENT` Makros für die Ereignisse die Klasse behandelt wird (z. B. `DHTML_EVENT_ONMOUSEOVER` für Mouseover-Ereignisse). Verwenden der [END_DHTML_EVENT_MAP_INLINE](http://msdn.microsoft.com/library/0cfec092-20ee-49f3-bc38-56d6a5572db2) Makro, um das Ende der ereigniszuordnung markieren. Diese Makros implementieren Sie die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  

  
##  <a name="a-namedeclaredhtmleventmapa--declaredhtmleventmap"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP  
 Deklariert eine Zuordnung des DHTML-Ereignis in einer Klassendefinition.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in die Definition des zu verwendenden [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleitete Klassen.  
  
 Verwendung [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) oder [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) die Zuordnung zu implementieren.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) deklariert die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventa--dhtmlevent"></a><a name="dhtml_event"></a>DHTML_EVENT  
 (Auf der Ebene) ein Ereignis verarbeitet `dispid` stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die DispID DARSTELLT, der das Ereignis behandelt werden.  
  
 `elemName`  
 Ein `LPCWSTR` halten die ID des HTML-Elements, das als Quelle des Ereignisses oder **NULL** Dokumentereignisse behandeln.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventaxcontrola--dhtmleventaxcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL  
 Behandelt das Ereignis identifizierten `dispid` ausgelöst wird, durch das ActiveX-Steuerelement identifizierten `controlName`.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID des Ereignisses, das verarbeitet werden.  
  
 `controlName`  
 Ein `LPCWSTR` mit der HTML-ID des Steuerelements, das das Ereignis auslöst.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventclassa--dhtmleventclass"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS  
 (Auf der Ebene) ein Ereignis verarbeitet `dispid` stammt von HTML-Element mit der CSS-Klasse, die durch identifizierte `elemName`.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID des Ereignisses, das verarbeitet werden.  
  
 `elemName`  
 Ein `LPCWSTR` halten die CSS-Klasse, die HTML-Elemente, die als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventelementa--dhtmleventelement"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT  
 Behandelt (identifizierten Element `elemName`) ein identifizierte Ereignis `dispid`.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID des Ereignisses, das verarbeitet werden.  
  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
 Wenn Sie dieses Makro zur Ereignisbehandlung nonbubbling verwendet wird, werden die Quelle des Ereignisses durch identifizierte `elemName`.  
  
 Wenn dieses Makro zum Behandeln von bubbling von Ereignissen verwendet wird, identifiziert das Element durch `elemName` möglicherweise nicht die Quelle des Ereignisses (die Quelle kann ein Element enthalten `elemName`).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonafterupdatea--dhtmleventonafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE  
 (Auf der Ebene) behandelt die **Onafterupdate** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonbeforeupdatea--dhtmleventonbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE  
 (Auf der Ebene) behandelt die **Onbeforeupdate** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonblura--dhtmleventonblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR  
 (Auf der Elementebene) behandelt die **Onblur** Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonchangea--dhtmleventonchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE  
 (Auf der Elementebene) behandelt die `onchange` Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonclicka--dhtmleventonclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK  
 (Auf der Ebene) behandelt die **Onclick** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventondataavailablea--dhtmleventondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE  
 (Auf der Ebene) behandelt die **Ondataavailable** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetchangeda--dhtmleventondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED  
 (Auf der Ebene) behandelt die **Ondatasetchanged** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetcompletea--dhtmleventondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE  
 (Auf der Ebene) behandelt die **Ondatasetcomplete** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventondblclicka--dhtmleventondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK  
 (Auf der Ebene) behandelt die **Ondblclick** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventondragstarta--dhtmleventondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART  
 (Auf der Ebene) behandelt die **Ondragstart** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonerrorupdatea--dhtmleventonerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE  
 (Auf der Ebene) behandelt die **Onerrorupdate** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfilterchangea--dhtmleventonfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE  
 (Auf der Ebene) behandelt die **Onfilterchange** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfocusa--dhtmleventonfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS  
 (Auf der Elementebene) behandelt die **Onfocus** Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonhelpa--dhtmleventonhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP  
 (Auf der Ebene) behandelt die `onhelp` Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeydowna--dhtmleventonkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN  
 (Auf der Ebene) behandelt die **Onkeydown** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeypressa--dhtmleventonkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS  
 (Auf der Ebene) behandelt die **Onkeypress** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeyupa--dhtmleventonkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP  
 (Auf der Ebene) behandelt die **Onkeyup** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousedowna--dhtmleventonmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN  
 (Auf der Ebene) behandelt die **Onmousedown** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousemovea--dhtmleventonmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE  
 (Auf der Ebene) behandelt die `onmousemove` Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseouta--dhtmleventonmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT  
 (Auf der Ebene) behandelt die **Onmouseout** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseovera--dhtmleventonmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER  
 (Auf der Ebene) behandelt die **Onmouseover** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseupa--dhtmleventonmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP  
 (Auf der Ebene) behandelt die **Onmouseup** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonresizea--dhtmleventonresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE  
 (Auf der Elementebene) behandelt die **Onresize** Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowentera--dhtmleventonrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER  
 (Auf der Ebene) behandelt die **Onrowenter** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowexita--dhtmleventonrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT  
 (Auf der Ebene) behandelt die **Onrowexit** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventonselectstarta--dhtmleventonselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART  
 (Auf der Ebene) behandelt die **Onselectstart** Ereignis stammt vom HTML-Element identifizierten `elemName`.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `elemName`  
 Ein `LPCWSTR` enthält die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedhtmleventtaga--dhtmleventtag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG  
 (Auf der Ebene) ein Ereignis verarbeitet `dispid` stammt von HTML-Element mit dem HTML-Tag identifizierte `elemName`.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Die Dispatch-ID des Ereignisses, das verarbeitet werden.  
  
 `elemName`  
 Die HTML-Tags, HTML-Elemente, die als Quelle des Ereignisses.  
  
 `memberFxn`  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags zu den [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-nameenddhtmleventmapa--enddhtmleventmap"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP  
 Markiert das Ende der Zuordnung DHTML-Ereignis.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Muss verwendet werden, zusammen mit [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namebegindhtmlurleventmapa--begindhtmlurleventmap"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP  
 Wird die Definition einer Zuordnung mit DHTML und URL-Ereignis in ein mehrseitiges Dialogfeld gestartet.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Hinweise  
 Put `BEGIN_DHTML_URL_EVENT_MAP` in der Implementierungsdatei der Ihre [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleiteten Klasse. Führen Sie es mit [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [-URL-Einträge](#begin_url_entries), und schließen Sie sie mit [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Enthalten die [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#196;](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namebeginembeddhtmleventmapa--beginembeddhtmleventmap"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP  
 Wird die Definition einer eingebetteten DHTML-ereigniszuordnung in ein mehrseitiges Dialogfeld gestartet.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse mit der ereigniszuordnung. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die eingebettete DHTML-ereigniszuordnung muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
 *mapName*  
 Gibt an, dass die Seite, dessen Ereignis zuzuordnen, dies, ist. Dies entspricht *MapName* in der [URL_EVENT_ENTRY](#url_event_entry) Makro tatsächlich definieren die URL oder HTML-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Daran ein mehrseitiges DHTML-Dialogfeld mehrere HTML-Seiten, von denen jede DHTML-Ereignis auslösen kann, werden eingebettete ereigniszuordnungen zum Ereignisse Handler pro Seite zuordnen.  
  
 Eingebettete ereigniszuordnungen innerhalb einer DHTML und URL-Ereignis-Zuordnung bestehen aus einer `BEGIN_EMBED_DHTML_EVENT_MAP` Makro gefolgt von [DHTML_EVENT](dhtml-event-maps.md#dhtml_event) Makros und [END_EMBED_DHTML_EVENT_MAP](dhtml-event-maps.md#end_embed_dhtml_event_map) Makro.  
  
 Jede ereigniszuordnung eingebettete erfordert eine entsprechende [URL Ereigniseintrag](#url_event_entry) zuordnen *MapName* (im `BEGIN_EMBED_DHTML_EVENT_MAP`) auf eine URL oder HTML-Ressource.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namebeginurlentriesa--beginurlentries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES  
 Wird die Definition einer URL Ereignis Eintrag Zuordnung in ein mehrseitiges Dialogfeld gestartet.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse, die die URL-Ereignis Eintrag Zuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-Eintrag ereigniszuordnung muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>Hinweise  
 Da ein mehrseitiges DHTML-Dialogfeld mehrere HTML-Seiten umfasst, URL Einträge werden zum Zuordnen von URLs oder HTML-Ressourcen, die entsprechenden [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map). Put `URL_EVENT_ENTRY` Makros zwischen `BEGIN_URL_ENTRIES` und [END_URL_ENTRIES](#end_url_entries) Makros.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-namedeclaredhtmlurleventmapa--declaredhtmlurleventmap"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP  
 Deklariert eine DHTML und URL-Zuordnung in einer Klassendefinition Ereignis.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in die Definition des zu verwendenden [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klassen.  
  
 Eine Zuordnung mit DHTML und URL-Ereignis enthält [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [URL Ereigniseinträge](#begin_url_entries) Handler pro Seite DHTML-Ereignis zuordnen. Verwendung [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) die Zuordnung zu implementieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-nameenddhtmlurleventmapa--enddhtmlurleventmap"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP  
 Markiert das Ende einer Zuordnung mit DHTML und URL-Ereignis.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse mit der ereigniszuordnung. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Dieser sollte übereinstimmen, `className` in den entsprechenden [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-nameendembeddhtmleventmapa--endembeddhtmleventmap"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP  
 Markiert das Ende einer eingebetteten DHTML-ereigniszuordnung.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-nameendurlentriesa--endurlentries"></a><a name="end_url_entries"></a>END_URL_ENTRIES  
 Markiert das Ende einer URL Ereignis Eintrag Zuordnung.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="a-nameurlevententrya--urlevententry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY  
 Ordnet eine URL oder HTML-Ressource auf eine Seite in ein mehrseitiges Dialogfeld.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse, die die URL-Ereignis Eintrag Zuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-Eintrag ereigniszuordnung muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
 *URL*  
 Die URL oder HTML-Ressource für die Seite.  
  
 *mapName*  
 Gibt die Seite an, deren URL ist *Url*. Dies entspricht *MapName* in der [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) Makro, das Ereignisse auf dieser Seite.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Seite eine HTML-Ressource ist *Url* muss die Darstellung der Ressourcen-ID-Nummer (d. h. "123", nicht 123 oder ID_HTMLRES1).  
  
 Der Bezeichner, *MapName*, ein beliebiges Symbol verknüpft DHTML-ereigniszuordnungen zu URL-Eintrag ereigniszuordnungen eingebettet ist. Es wird im Bereich für die DHTML und URL-Event-Zuordnung beschränkt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

