---
title: Hilfsmakros DDX_DHtml | Microsoft Docs
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
ms.openlocfilehash: cb2e9d2494463b502fda85c03fa1b861e1182cfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ddxdhtml-helper-macros"></a>Hilfsmakros DDX_DHtml
Die DDX_DHtml Hilfsmakros ermöglichen einen einfachen Zugriff auf die häufig verwendeten Eigenschaften der Steuerelemente auf einer HTML-Seite.  
  
### <a name="data-exchange-macros"></a>Daten, Exchange-Makros  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft des markierten Steuerelements.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Legt fest oder ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft den HTML-Code zwischen die Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Ruft die Ziel-URL oder den Ankerpunkt Punkt ab oder legt sie fest.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Ruft das Zielfenster oder der Zielframe ab oder legt ihn fest.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Legt fest oder ruft den Namen ein Bild oder eine Videoclips an, in das Dokument ab.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Legt fest oder ruft die URL der zugeordneten Rahmen.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL der zugeordneten Rahmen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href
Ruft die Ziel-URL oder den Ankerpunkt Punkt ab oder legt sie fest.  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLANCHORELEMENT_HREF dispatch-ID

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target
 Ruft das Zielfenster oder der Zielframe ab oder legt ihn fest.  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLANCHORELEMENT_TARGET dispatch-ID  

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml
 Legt fest oder ruft den HTML-Code zwischen die Start- und Endtags des aktuellen Elements ab.  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLELEMENT_INNERHTML dispatch-ID  
  

## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText
Legt fest oder ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab.  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLELEMENT_INNERTEXT dispatch-ID 

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue  
Legt fest oder ruft die Value-Eigenschaft des markierten Steuerelements.  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird. Finden Sie unter *Wert* in [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ist nur erfolgreich, wenn auf Steuerelemente ausführen, die über ein Value-Eigenschaft verfügen. Steuerelemente, die eine Werteigenschaft umfassen Bearbeitungsfelder, Listenfelder und Kombinationsfelder.  
  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_A_VALUE dispatch-ID  

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src
Legt fest oder ruft die URL der zugeordneten Rahmen.  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID  

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src
Legt fest oder ruft die URL der zugeordneten Rahmen.  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Ruft ab, oder ruft den Namen ein Bild oder eine Videoclips an, in das Dokument ab.  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Parameter  
 `dx`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `name`  
 Der Wert, den Sie für die HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert, der ausgetauscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung der `DDX_DHtml_Img_Src` Makro, um die Src-Eigenschaft für ein IMAGE-Element, das Internet Explorer-Image-Objekt abzurufen, wird die vollständig mit Escapezeichen versehene URL für die Bildquelle zurückgegeben. Angenommen, Sie verwenden die `DDX_DHtml_Img_Src` Makro, das der Src-Eigenschaft eines Bild-Elements auf die Zeichenfolge "einige interessantes Bild" festgelegt, wenn Sie diese Eigenschaft abzurufen, wird die Zeichenfolge "res://d:\myapplication\myapp.exe/some% von Internet Explorer zurück 20interesting % 20picture."  
  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLIMGELEMENT_SRC dispatch-ID  

  
## <a name="see-also"></a>Siehe auch  
 [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)
