---
title: DHTML-Ereigniszuordnungen | Microsoft-Dokumentation
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
ms.openlocfilehash: 777180468ec377b50ee0affaa29bd04a302bda52
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057919"
---
# <a name="dhtml-event-maps"></a>DHTML-Ereigniszuordnungen

Die folgenden Makros können verwendet werden, um DHTML-Ereignisse zu behandeln.

## <a name="dhtml-event-map-macros"></a>DHTML Ereigniszuordnungs-Makros

Die folgenden Makros können verwendet werden, um die Behandlung von DHTML-Ereignissen in [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleiteten Klassen.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Markiert den Anfang der DHTML-ereigniszuordnung an.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Markiert den Anfang der DHTML-ereigniszuordnung an.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Deklariert die DHTML-ereigniszuordnung an.|
|[DHTML_EVENT](#dhtml_event)|Verwendet, um ein Ereignis auf Dokumentebene für eine einzelne HTML-Element zu behandeln.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Verwendet, um ein Ereignis ausgelöst, die für ein ActiveX-Steuerelement zu behandeln.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Verwendet, um ein Ereignis auf Dokumentebene für alle HTML-Elemente mit einer bestimmten CSS-Klasse zu behandeln.|
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
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Verwendet, um ein Ereignis auf Dokumentebene für alle Elemente mit einem bestimmten HTML-Tag zu behandeln.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Markiert das Ende der Zuordnung DHTML-Ereignis.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Markiert das Ende der Zuordnung DHTML-Ereignis. |

## <a name="url-event-map-macros"></a>URL Ereigniszuordnungs-Makros

Die folgenden Makros können verwendet werden, um die Behandlung von DHTML-Ereignissen in [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleiteten Klassen.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Markiert den Anfang der mehrseitigen DHTML und URL-Event-Zuordnung.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Kennzeichnet den Beginn einer eingebetteten DHTML-ereigniszuordnung an.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Kennzeichnet den Beginn einer URL-ereigniszuordnung Eintrag an.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Deklariert die mehrseitige DHTML und URL-Event-Zuordnung.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Markiert das Ende der Zuordnung mehrseitigen DHTML und URL-Ereignis.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Markiert das Ende einer eingebetteten DHTML-ereigniszuordnung an.|
|[END_URL_ENTRIES](#end_url_entries)|Markiert das Ende einer URL-Event-Eintrag-Zuordnung.|
|[URL_EVENT_ENTRY](#url_event_entry)|Ordnet eine URL oder HTML-Ressource auf eine Seite in ein mehrseitiges Dialogfeld an.|

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP

Markiert den Anfang der DHTML-ereigniszuordnung, wenn in der Quelldatei für die identifizierte Klasse platziert `className`.

```
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Parameter

*Klassenname*<br/>
Der Name der Klasse, die die DHTML-ereigniszuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und enthalten die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.

### <a name="remarks"></a>Hinweise

Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzugefügt `CDHtmlDialog` , die zum Weiterleiten von Ereignissen ausgelöst wird, indem ActiveX-Steuerelemente mit Handlerfunktionen in der Klasse auf einer Webseite oder HTML-Elemente verwendet werden kann.

Platzieren Sie die BEGIN_DHTML_EVENT_MAP-Makro in der Klasse Implementierungsdatei (.cpp) gefolgt von DHTML_EVENT-Makros für die Ereignisse, die die Klasse behandelt wird (z. B. DHTML_EVENT_ONMOUSEOVER für die Mouseover-Ereignisse). Verwenden der [END_DHTML_EVENT_MAP](#end_dhtml_event_map) Makro, um das Ende der ereigniszuordnung zu markieren. Diese Makros implementieren Sie die folgende Funktion:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE

Markiert den Anfang von innerhalb der Klassendefinition für die DHTML-ereigniszuordnung *ClassName*.

```
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Parameter

*Klassenname*<br/>
Der Name der Klasse, die die DHTML-ereigniszuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) und enthalten die [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) Makro innerhalb der Klassendefinition.

### <a name="remarks"></a>Hinweise

Die Klasse, um Informationen zum Bereitstellen einer DHTML-ereigniszuordnung hinzugefügt `CDHtmlDialog` , die zum Weiterleiten von Ereignissen ausgelöst wird, indem ActiveX-Steuerelemente mit Handlerfunktionen in der Klasse auf einer Webseite oder HTML-Elemente verwendet werden kann.

Platzieren Sie die BEGIN_DHTML_EVENT_MAP-Makro in der Klasse (. h)-Definitionsdatei gefolgt von DHTML_EVENT-Makros für die Ereignisse, die die Klasse behandelt wird (z. B. DHTML_EVENT_ONMOUSEOVER für die Mouseover-Ereignisse). Verwenden der [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) Makro, um das Ende der ereigniszuordnung zu markieren. Diese Makros implementieren Sie die folgende Funktion:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP

Deklariert ein DHTML-ereigniszuordnung in einer Klassendefinition.

```
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Hinweise

Dieses Makro wird in der Definition der zu verwendende [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-abgeleiteten Klassen.

Verwendung [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) oder [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) die Zuordnung zu implementieren.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) deklariert die folgende Funktion:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event"></a>  DHTML_EVENT

Behandelt (auf Dokumentebene) ein identifizierte Ereignis *Dispid* stammt vom HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die DISPID des Ereignisses, das verarbeitet werden.

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses oder NULL, wenn Dokumentereignisse behandeln.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL

Behandelt das identifizierte Ereignis *Dispid* wird ausgelöst, durch das ActiveX-Steuerelement identifizierte *Steuerelementname*.

```
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die Dispatch-ID des Ereignisses, das verarbeitet werden.

*Steuerelementname*<br/>
Ein LPCWSTR, enthält die HTML-ID des Steuerelements, das das Ereignis ausgelöst wird.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS

Behandelt (auf Dokumentebene) ein identifizierte Ereignis *Dispid* stammt jedes HTML-Element mit der CSS-Klasse, die identifizierte *ElemName*.

```
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die Dispatch-ID des Ereignisses, das verarbeitet werden.

*elemName*<br/>
Ein LPCWSTR, enthält die CSS-Klasse, die HTML-Elemente, die der Event-sourcing.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT

Behandelt (auf das Element, das identifizierte *ElemName*) ein identifizierte Ereignis *Dispid*.

```
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die Dispatch-ID des Ereignisses, das verarbeitet werden.

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

Wenn Sie dieses Makro verwendet wird, um nonbubbling Ereignisse zu behandeln, werden die Quelle des Ereignisses durch identifizierte *ElemName*.

Wenn dieses Makro bubbling-Ereignisse behandeln verwendet wird, wird das Element identifiziert, von *ElemName* möglicherweise nicht die Quelle des Ereignisses (die Quelle kann ein Element enthalten sein *ElemName*).

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE

(Auf Dokumentebene) verarbeitet die `onafterupdate` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE

(Auf Dokumentebene) verarbeitet die `onbeforeupdate` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR

(Auf der Elementebene) verarbeitet die `onblur` Ereignis. Dies ist ein nonbubbling-Ereignis.

```
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE

(Auf der Elementebene) verarbeitet die `onchange` Ereignis. Dies ist ein nonbubbling-Ereignis.

```
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK

(Auf Dokumentebene) verarbeitet die `onclick` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE

(Auf Dokumentebene) verarbeitet die `ondataavailable` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED

(Auf Dokumentebene) verarbeitet die `ondatasetchanged` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE

(Auf Dokumentebene) verarbeitet die `ondatasetcomplete` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte `elemName`.

```
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK

(Auf Dokumentebene) verarbeitet die `ondblclick` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART

(Auf Dokumentebene) verarbeitet die `ondragstart` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE

(Auf Dokumentebene) verarbeitet die `onerrorupdate` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE

(Auf Dokumentebene) verarbeitet die `onfilterchange` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS

(Auf der Elementebene) verarbeitet die `onfocus` Ereignis. Dies ist ein nonbubbling-Ereignis.

```

DHTML_EVENT_ONFOCUS(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP

(Auf Dokumentebene) verarbeitet die `onhelp` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONHELP(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN

(Auf Dokumentebene) verarbeitet die `onkeydown` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS

(Auf Dokumentebene) verarbeitet die `onkeypress` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP

(Auf Dokumentebene) verarbeitet die `onkeyup` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONKEYUP(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN

(Auf Dokumentebene) verarbeitet die `onmousedown` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE

(Auf Dokumentebene) verarbeitet die `onmousemove` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT

(Auf Dokumentebene) verarbeitet die `onmouseout` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER

(Auf Dokumentebene) verarbeitet die `onmouseover` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP

(Auf Dokumentebene) verarbeitet die `onmouseup` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE

(Auf der Elementebene) verarbeitet die `onresize` Ereignis. Dies ist ein nonbubbling-Ereignis.

```

DHTML_EVENT_ONRESIZE(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER

(Auf Dokumentebene) verarbeitet die `onrowenter` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONROWENTER(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT

(Auf Dokumentebene) verarbeitet die `onrowexit` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONROWEXIT(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART

(Auf Dokumentebene) verarbeitet die `onselectstart` Ereignis ausgelöst wurde, durch das HTML-Element identifizierte *ElemName*.

```

DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)

```

### <a name="parameters"></a>Parameter

*elemName*<br/>
Ein LPCWSTR, enthält die ID des HTML-Elements als Quelle des Ereignisses.

*memberFxn*<br/>
Die Handlerfunktion für das Ereignis.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro zum Hinzufügen eines Eintrags auf dem [DHTML-ereigniszuordnung](#begin_dhtml_event_map_inline) in Ihrer Klasse.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG

Behandelt (auf Dokumentebene) ein identifizierte Ereignis `dispid` stammt jedes HTML-Element mit dem HTML-Tag identifizierte *ElemName*.

```
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Die Dispatch-ID des Ereignisses, das verarbeitet werden.

*elemName*<br/>
Das HTML-Tag, die HTML-Elemente, die der Event-sourcing.

*memberFxn*<br/>
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

Wird die Definition einer DHTML und URL-Event-Zuordnung in ein mehrseitiges Dialogfeld gestartet.

```
BEGIN_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Hinweise

Fügen in der Implementierungsdatei des BEGIN_DHTML_URL_EVENT_MAP Ihre [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleitete Klasse. Führen Sie es mit [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [URL-Einträgen](#begin_url_entries), und schließen Sie sie mit [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Enthalten die [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) Makro innerhalb der Klassendefinition.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP

Wird die Definition von einem eingebetteten DHTML-ereigniszuordnung in ein mehrseitiges Dialogfeld gestartet.

```
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)

```

### <a name="parameters"></a>Parameter

*Klassenname*<br/>
Der Name der Klasse, die die ereigniszuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die eingebettete DHTML-ereigniszuordnung muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).

*mapName*<br/>
Gibt an, dass die Seite, dessen Ereignis eine Zuordnung, ist. Dies entspricht *MapName* in die [URL_EVENT_ENTRY](#url_event_entry) Makro tatsächlich definieren die URL oder HTML-Ressource.

### <a name="remarks"></a>Hinweise

Da ein mehrseitiges Dialogfeld für die DHTML mehrere HTML-Seiten umfasst, von denen jede DHTML-Ereignisse auslösen kann, werden eingebettete ereigniszuordnungen zum Zuordnen von Ereignissen an Handler pro pro Seite verwendet.

Eingebettete ereigniszuordnungen innerhalb einer DHTML und URL-Event-Zuordnung bestehen aus einem BEGIN_EMBED_DHTML_EVENT_MAP-Makro, gefolgt von [DHTML_EVENT](#dhtml_event) Makros und [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) Makro.

Jedes eingebettete ereigniszuordnung erfordert einen entsprechenden [URL Ereigniseintrags](#url_event_entry) zuordnen *MapName* (angegeben in BEGIN_EMBED_DHTML_EVENT_MAP) auf eine URL oder HTML-Ressource.

### <a name="example"></a>Beispiel

Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES

Wird die Definition einer URL-Event-Eintrag-Zuordnung in ein mehrseitiges Dialogfeld gestartet.

```
BEGIN_URL_ENTRIES(className)

```

### <a name="parameters"></a>Parameter

*Klassenname*<br/>
Der Name der Klasse, die die URL-ereigniszuordnung Eintrag enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-ereigniszuordnung Eintrag muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).

### <a name="remarks"></a>Hinweise

Da ein mehrseitiges Dialogfeld für die DHTML mehrere HTML-Seiten umfasst, URL Ereigniseinträge werden zum Zuordnen von URLs oder HTML-Ressourcen, die entsprechenden [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map). URL_EVENT_ENTRY-Makros zwischen BEGIN_URL_ENTRIES platzieren und [END_URL_ENTRIES](#end_url_entries) Makros.

### <a name="example"></a>Beispiel

Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP

Deklariert eine DHTML und URL-Zuordnung in einer Klassendefinition-Ereignis.

```
DECLARE_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Hinweise

Dieses Makro wird in der Definition der zu verwendende [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-abgeleiteten Klassen.

Enthält ein DHTML und URL-ereigniszuordnung [eingebettet DHTML-ereigniszuordnungen](#begin_embed_dhtml_event_map) und [URL Ereigniseinträge](#begin_url_entries) DHTML-Ereignissen mit Handlern, die auf einer Basis pro Seite zuordnen. Verwendung [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) die Zuordnung zu implementieren.

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP

Markiert das Ende einer Zuordnung mit DHTML und URL-Ereignis.

```
END_DHTML_URL_EVENT_MAP(className)

```

### <a name="parameters"></a>Parameter

*Klassenname*<br/>
Der Name der Klasse, die die ereigniszuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Dies sollte entsprechen *ClassName* in den entsprechenden [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) Makro.

### <a name="example"></a>Beispiel

Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP

Markiert das Ende einer eingebetteten DHTML-ereigniszuordnung an.

```
END_EMBED_DHTML_EVENT_MAP()

```

### <a name="example"></a>Beispiel

Siehe das Beispiel in [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Anforderungen

  **Header** afxdhtml.h

##  <a name="end_url_entries"></a>  END_URL_ENTRIES

Markiert das Ende einer URL-Event-Eintrag-Zuordnung.

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

*Klassenname*<br/>
Der Name der Klasse, die die URL-ereigniszuordnung Eintrag enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Die URL-ereigniszuordnung Eintrag muss innerhalb einer [DHTML und URL-ereigniszuordnung](#begin_dhtml_url_event_map)).

*URL*<br/>
Die URL oder HTML-Ressource für die Seite.

*mapName*<br/>
Gibt an, die Seite, deren URL *Url*. Dies entspricht *MapName* in die [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) Makro, das Ereignisse auf dieser Seite.

### <a name="remarks"></a>Hinweise

Wenn die Seite eine HTML-Ressource ist *Url* muss die Zeichenfolgendarstellung der Ressource-ID-Nummer (d. h. "123", nicht 123 oder ID_HTMLRES1) sein.

Der seitenbezeichner *MapName*, ein beliebiges Symbol verwendet, um verknüpfen Embedded DHTML-ereigniszuordnungen auf URL-Eintrag ereigniszuordnungen. Es wird im Bereich der DHTML und URL-Event-Zuordnung beschränkt.

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
