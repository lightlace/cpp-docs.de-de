---
title: DHTML-Ereigniszuordnungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8a888cfdf8d83f3628bf4ad80b26db6ac51ad72
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123096"
---
# <a name="dhtml-event-maps"></a>DHTML-Ereigniszuordnungen
DHTML-Ereignis zu behandeln, können die folgenden Makros verwendet werden.  
  
## <a name="dhtml-event-map-macros"></a>DHTML Ereigniszuordnungs-Makros  
 Die folgenden Makros können zum Behandeln von DHTML-Ereignis im [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleitete Klassen.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Kennzeichnet den Anfang der DHTML-ereigniszuordnung an.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Kennzeichnet den Anfang der DHTML-ereigniszuordnung an.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Deklariert den DHTML-ereigniszuordnung an.|  
|[DHTML_EVENT](#dhtml_event)|Zum Behandeln eines Ereignisses auf Dokumentenebene für eine einzelnes HTML-Element verwendet.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Zum Behandeln eines Ereignisses, das ausgelöst wird, indem Sie ein ActiveX-Steuerelement verwendet.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Verwendet für die Ereignisbehandlung auf Dokumentenebene für alle HTML-Elemente mit einer bestimmten CSS-Klasse.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Zum Behandeln eines Ereignisses auf Elementebene verwendet.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Zum Behandeln der `onafterupdate` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Zum Behandeln der `onbeforeupdate` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Zum Behandeln der `onblur` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Zum Behandeln der `onchange` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Zum Behandeln der `onclick` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Zum Behandeln der `ondataavailable` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Zum Behandeln der `ondatasetchanged` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Zum Behandeln der `ondatasetcomplete` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Zum Behandeln der `ondblclick` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Zum Behandeln der `ondragstart` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Zum Behandeln der `onerrorupdate` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Zum Behandeln der `onfilterchange` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Zum Behandeln der `onfocus` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Zum Behandeln der `onhelp` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Zum Behandeln der `onkeydown` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Zum Behandeln der `onkeypress` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Zum Behandeln der `onkeyup` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Zum Behandeln der `onmousedown` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Zum Behandeln der `onmousemove` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Zum Behandeln der `onmouseout` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Zum Behandeln der `onmouseover` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Zum Behandeln der `onmouseup` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Zum Behandeln der `onresize` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Zum Behandeln der `onrowenter` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Zum Behandeln der `onrowexit` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Zum Behandeln der `onselectstart` Ereignis von einem HTML-Element.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Zum Behandeln eines Ereignisses auf Dokumentenebene für alle Elemente mit einem bestimmten HTML-Tag verwendet.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Markiert das Ende der Zuordnung DHTML-Ereignis.|  
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Markiert das Ende der Zuordnung DHTML-Ereignis. |
  
## <a name="url-event-map-macros"></a>URL Ereigniszuordnungs-Makros  
 Die folgenden Makros können zum Behandeln von DHTML-Ereignis im [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klassen.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Kennzeichnet den Anfang der Zuordnung mehrseitigen DHTML- und URL-Ereignis.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Kennzeichnet den Anfang einer eingebetteten DHTML-ereigniszuordnung an.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Kennzeichnet den Anfang einer URL-ereigniszuordnung Eintrag an.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Deklariert die mehrseitigen DHTML- und URL-ereigniszuordnung an.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Markiert das Ende der Zuordnung mehrseitigen DHTML- und URL-Ereignis.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Markiert das Ende des eingebetteten DHTML-ereigniszuordnung.|  
|[END_URL_ENTRIES](#end_url_entries)|Markiert das Ende einer URL-Ereignis-Eintrag-Zuordnung.|  
|[URL_EVENT_ENTRY](#url_event_entry)|Ordnet eine URL oder HTML-Ressource auf eine Seite in ein mehrseitiges Dialogfeld an.|  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP  
 Kennzeichnet den Anfang der DHTML-ereigniszuordnung, wenn in der Quelldatei für die Klasse identifizierte platziert `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die DHTML-ereigniszuordnung enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und enthalten die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzufügen `CDHtmlDialog` , die verwendet werden kann, um Ereignisse weiterzuleiten, die von HTML-Elementen oder ActiveX-Steuerelemente auf einer Webseite mit Handlerfunktionen in Ihrer Klasse ausgelöst werden.  
  
 Platzieren Sie das BEGIN_DHTML_EVENT_MAP-Makro in der Klasse Implementierungsdatei (.cpp) gefolgt von DHTML_EVENT-Makros für die Ereignisse an, die die Klasse behandeln (z. B. DHTML_EVENT_ONMOUSEOVER für Mouseover-Ereignisse). Verwenden der [END_DHTML_EVENT_MAP](#end_dhtml_event_map) Makro auf das Ende der ereigniszuordnung zu markieren. Diese Makros implementieren Sie die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE  
 Kennzeichnet den Anfang der DHTML-ereigniszuordnung innerhalb der Klassendefinition für *ClassName*.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die DHTML-ereigniszuordnung enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und enthalten die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzufügen `CDHtmlDialog` , die verwendet werden kann, um Ereignisse weiterzuleiten, die von HTML-Elementen oder ActiveX-Steuerelemente auf einer Webseite mit Handlerfunktionen in Ihrer Klasse ausgelöst werden.  
  
 BEGIN_DHTML_EVENT_MAP-Makro wird in der Klasse Definition (. h)-Datei gefolgt von DHTML_EVENT-Makros für die Ereignisse an, die die Klasse behandeln (z. B. DHTML_EVENT_ONMOUSEOVER für Mouseover-Ereignisse) platzieren. Verwenden der [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) Makro auf das Ende der ereigniszuordnung zu markieren. Diese Makros implementieren Sie die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  

  
##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP  
 Deklariert eine DHTML-ereigniszuordnung in einer Klassendefinition.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in der Definition der zu verwendende [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleitete Klassen.  
  
 Verwendung [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) oder [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) die Zuordnung zu implementieren.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) deklariert die folgende Funktion:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event"></a>  DHTML_EVENT  
 (Auf Dokumentebene) ein identifizierte Ereignis behandelt *Dispid* stammt vom HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die DISPID des Ereignisses behandelt werden.  
  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses oder NULL, wenn Dokumentereignisse behandeln.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL  
 Behandelt das Ereignis identifizierten *Dispid* ausgelöst wird, vom ActiveX-Steuerelement identifizierten *Steuerelementname*.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die Dispatch-ID des Ereignisses behandelt werden.  
  
 *Steuerelementname*  
 Ein LPCWSTR halten die HTML-ID des Steuerelements, das das Ereignis ausgelöst wird.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS  
 (Auf Dokumentebene) ein identifizierte Ereignis behandelt *Dispid* stammt von HTML-Element mit der CSS-Klasse, die identifizierte *ElemName*.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die Dispatch-ID des Ereignisses behandelt werden.  
  
 *elemName*  
 Ein LPCWSTR, halten die CSS-Klasse, die HTML-Elemente, die als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT  
 Verarbeitet (bei dem Element identifizierte *ElemName*) ein identifizierte Ereignis *Dispid*.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die Dispatch-ID des Ereignisses behandelt werden.  
  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
 Wenn dieses Makro zum nonbubbling aufgeladenen verwendet wird, werden die Quelle des Ereignisses durch identifizierte *ElemName*.  
  
 Wenn Sie dieses Makro zum Behandeln von bubbling-Ereignisse verwendet wird, wird das Element durch identifiziert *ElemName* möglicherweise nicht die Quelle des Ereignisses (die Quelle ist möglicherweise ein Element enthaltenen *ElemName*).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE  
 (Auf Dokumentebene) behandelt die `onafterupdate` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE  
 (Auf Dokumentebene) behandelt die `onbeforeupdate` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR  
 (Auf der Elementebene) behandelt die `onblur` Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE  
 (Auf der Elementebene) behandelt die `onchange` Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK  
 (Auf Dokumentebene) behandelt die `onclick` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE  
 (Auf Dokumentebene) behandelt die `ondataavailable` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED  
 (Auf Dokumentebene) behandelt die `ondatasetchanged` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE  
 (Auf Dokumentebene) behandelt die `ondatasetcomplete` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK  
 (Auf Dokumentebene) behandelt die `ondblclick` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART  
 (Auf Dokumentebene) behandelt die `ondragstart` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE  
 (Auf Dokumentebene) behandelt die `onerrorupdate` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE  
 (Auf Dokumentebene) behandelt die `onfilterchange` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS  
 (Auf der Elementebene) behandelt die `onfocus` Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP  
 (Auf Dokumentebene) behandelt die `onhelp` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN  
 (Auf Dokumentebene) behandelt die `onkeydown` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS  
 (Auf Dokumentebene) behandelt die `onkeypress` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP  
 (Auf Dokumentebene) behandelt die `onkeyup` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN  
 (Auf Dokumentebene) behandelt die `onmousedown` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE  
 (Auf Dokumentebene) behandelt die `onmousemove` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT  
 (Auf Dokumentebene) behandelt die `onmouseout` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER  
 (Auf Dokumentebene) behandelt die `onmouseover` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP  
 (Auf Dokumentebene) behandelt die `onmouseup` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE  
 (Auf der Elementebene) behandelt die `onresize` Ereignis. Dies ist ein nonbubbling-Ereignis.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER  
 (Auf Dokumentebene) behandelt die `onrowenter` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT  
 (Auf Dokumentebene) behandelt die `onrowexit` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART  
 (Auf Dokumentebene) behandelt die `onselectstart` Ereignis ausgelöst wurde, indem Sie das HTML-Element identifizierte *ElemName*.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *elemName*  
 Ein LPCWSTR, halten die ID des HTML-Elements, das als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG  
 (Auf Dokumentebene) ein identifizierte Ereignis behandelt `dispid` stammt von HTML-Element mit dem HTML-Tag identifizierte *ElemName*.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Die Dispatch-ID des Ereignisses behandelt werden.  
  
 *elemName*  
 Die HTML-Tags, HTML-Elemente, die als Quelle des Ereignisses.  
  
 *memberFxn*  
 Die Handlerfunktion für das Ereignis.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP  
 Markiert das Ende der Zuordnung DHTML-Ereignis.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Muss verwendet werden, zusammen mit [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP  
 Startet die Definition einer DHTML- und URL-Ereignis-Zuordnung in ein mehrseitiges Dialogfeld an.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Hinweise  
 Versetzen in der Implementierungsdatei des BEGIN_DHTML_URL_EVENT_MAP Ihrer [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klasse. Führen Sie ihn mit [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [URL-Einträgen](#begin_url_entries), und schließen Sie sie mit [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Enthalten die [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) Makro innerhalb der Klassendefinition.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP  
 Startet die Definition einer eingebetteten DHTML-ereigniszuordnung in ein mehrseitiges Dialogfeld an.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die ereigniszuordnung enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die eingebettete DHTML-ereigniszuordnung muss innerhalb einer [DHTML- und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
 *mapName*  
 Gibt an, dass die Seite, dessen Ereignis ordnen, ist. Dies entspricht *MapName* in der [URL_EVENT_ENTRY](#url_event_entry) Makro tatsächlich definieren die URL oder HTML-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Weil ein mehrseitiges DHTML-Dialogfeld mehrere HTML-Seiten besteht, von denen jede DHTML-Ereignis auslösen kann, werden eingebettete ereigniszuordnungen verwendet, um Handler pro Seite Ereignisse zuzuordnen.  
  
 Eingebettete ereigniszuordnungen innerhalb einer DHTML- und URL-ereigniszuordnung bestehen aus einem BEGIN_EMBED_DHTML_EVENT_MAP-Makro, gefolgt von [DHTML_EVENT](#dhtml_event) Makros und ein [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) Makro.  
  
 Jedes eingebettete ereigniszuordnung erfordert eine entsprechende [URL Ereigniseintrag](#url_event_entry) abzubildenden *MapName* (angegeben in BEGIN_EMBED_DHTML_EVENT_MAP) auf eine URL oder HTML-Ressource.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES  
 Startet die Definition einer URL-ereigniszuordnung Eintrag in ein mehrseitiges Dialogfeld an.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die URL-ereigniszuordnung Eintrag enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-ereigniszuordnung Eintrag muss innerhalb einer [DHTML- und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>Hinweise  
 Da mehrere HTML-Seiten ein mehrseitiges DHTML-Dialogfeld umfasst, werden Einträge für URL-Ereignis verwendet, um das Zuordnen von URLs oder HTML-Ressourcen, um die entsprechenden [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map). URL_EVENT_ENTRY-Makros zwischen BEGIN_URL_ENTRIES abgelegt und [END_URL_ENTRIES](#end_url_entries) Makros.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP  
 DHTML- und URL-Ereignis, um eine Zuordnung in einer Klassendefinition deklariert wird.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in der Definition der zu verwendende [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klassen.  
  
 Enthält eine DHTML- und URL-ereigniszuordnung [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [Einträge für URL-Ereignis](#begin_url_entries) DHTML-Ereignis Handler pro Seite zuordnen. Verwendung [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) die Zuordnung zu implementieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP  
 Markiert das Ende einer Zuordnung mit DHTML- und URL-Ereignis.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die ereigniszuordnung enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Dies sollte übereinstimmen *ClassName* im entsprechenden [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) Makro.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP  
 Markiert das Ende des eingebetteten DHTML-ereigniszuordnung.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="end_url_entries"></a>  END_URL_ENTRIES  
 Markiert das Ende einer URL-Ereignis-Eintrag-Zuordnung.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  
  
##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY  
 Ordnet eine URL oder HTML-Ressource auf eine Seite in ein mehrseitiges Dialogfeld an.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name der Klasse, die die URL-ereigniszuordnung Eintrag enthält. Diese Klasse sollte direkt oder indirekt aus ableiten [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-ereigniszuordnung Eintrag muss innerhalb einer [DHTML- und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).  
  
 *URL*  
 Die URL oder HTML-Ressource für die Seite.  
  
 *mapName*  
 Gibt die Seite an, dessen URL lautet *Url*. Dies entspricht *MapName* in der [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) Makro, das Ereignisse auf dieser Seite.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Seite eine HTML-Ressource ist *Url* muss die Zeichenfolgendarstellung der Ressourcen-ID-Nummer (d. h. "123", nicht 123 oder ID_HTMLRES1) sein.  
  
 Der seitenbezeichner *MapName*, ist ein beliebiges Symbol verwendet, um verknüpfen eingebetteter DHTML-ereigniszuordnungen auf URL-Eintrag ereigniszuordnungen. Es wird im Bereich für die ereigniszuordnung DHTML- und URL beschränkt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdhtml.h  

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE
Markiert das Ende der Zuordnung DHTML-Ereignis.  
   
### <a name="syntax"></a>Syntax    
```
END_DHTML_EVENT_MAP_INLINE( )    
```  
   
### <a name="remarks"></a>Hinweise  
 Muss verwendet werden, zusammen mit [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
