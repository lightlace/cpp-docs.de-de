---
title: DDX_DHtml-Hilfsmakros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a4dbf1b085ca5ffddd87396fc367bf19f2ad02e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383053"
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml-Hilfsmakros

DDX_DHtml-Hilfsmakros ermöglichen einen einfachen Zugriff auf die häufig verwendeten Eigenschaften von Steuerelementen auf einer HTML-Seite.

### <a name="data-exchange-macros"></a>Registrierungsdatenaustausch-Makros

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft aus dem ausgewählten Steuerelement.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab, oder legt diesen fest.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft Sie den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Legt fest oder ruft ab, der Ziel-URL oder den Ankerpunkt Punkt.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Ruft das Zielfenster oder den Zielframe ab, ab oder legt diesen fest.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Legt fest oder ruft den Namen ein Bild oder einen Videoclip in das Dokument ab.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Legt fest oder ruft die URL des zugeordneten Frames ab.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL des zugeordneten Frames ab.|

## <a name="requirements"></a>Anforderungen

**Header:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

Legt fest oder ruft ab, der Ziel-URL oder den Ankerpunkt Punkt.



```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLANCHORELEMENT_HREF dispatch-ID an

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target

Ruft das Zielfenster oder den Zielframe ab, ab oder legt diesen fest.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLANCHORELEMENT_TARGET dispatch-ID an

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml

Legt fest oder ruft Sie den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.



```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLELEMENT_INNERHTML dispatch-ID an


## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText

Ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab, oder legt diesen fest.



```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLELEMENT_INNERTEXT dispatch-ID an

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

Legt fest oder ruft die Value-Eigenschaft aus dem ausgewählten Steuerelement.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden. Finden Sie unter *Wert* in [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Hinweise

Dieses Makro ist nur erfolgreich, wenn Steuerelemente ausführen, die eine Value-Eigenschaft aufweisen. Steuerelemente, die eine Value-Eigenschaft umfassen Bearbeitungsfelder, Listenfelder und Kombinationsfelder.

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_A_VALUE dispatch-ID an

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

Legt fest oder ruft die URL des zugeordneten Frames ab.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID an

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

Legt fest oder ruft die URL des zugeordneten Frames ab.



```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID an

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Ruft ab, oder ruft den Namen ein Bild oder einen Videoclip in das Dokument ab.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Parameter

*DX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*name*<br/>
Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.

*var*<br/>
Der Wert, die ausgetauscht werden.

## <a name="remarks"></a>Hinweise

Wird das Makro DDX_DHtml_Img_Src verwendet, die Src-Eigenschaft für ein IMAGE-Element abzurufen, wird der Bildobjekt Internet Explorer die vollständig mit Escapezeichen versehene URL für die Bildquelle zurückgegeben. Z. B. Wenn Sie das Makro DDX_DHtml_Img_Src verwenden, um der Src-Eigenschaft eines IMAGE-Elements auf die Zeichenfolge "einige interessante Bild" festgelegt, gibt Wenn Sie diese Eigenschaft, die Internet Explorer abrufen, die Zeichenfolge "res://d:\myapplication\myapp.exe/some% zurück 20interesting % 20picture."

Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion unter Verwendung der DISPID_IHTMLIMGELEMENT_SRC dispatch-ID an


## <a name="see-also"></a>Siehe auch

[CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)
