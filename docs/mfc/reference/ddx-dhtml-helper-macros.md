---
title: Hilfsmakros DDX_DHtml | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- macros, exchanging data with HMTL pages
- DDX macros
- HTML pages, helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros, DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d3c5136b52206a1ec67e1e1fc78ec291a2954faf
ms.lasthandoff: 02/24/2017

---
# <a name="ddxdhtml-helper-macros"></a>Hilfsmakros DDX_DHtml
Die DDX_DHtml Hilfsmakros ermöglichen einen einfachen Zugriff auf die am häufigsten verwendeten Eigenschaften von Steuerelementen auf einer HTML-Seite.  
  
### <a name="data-exchange-macros"></a>Data Exchange-Makros  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Legt fest oder ruft die Value-Eigenschaft des ausgewählten Steuerelements.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Legt fest oder ruft den Text zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Legt fest oder ruft den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Legt fest oder ruft den Ziel-URL oder den Ankerpunkt Punkt.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Legt fest oder ruft das Zielfenster oder der Zielframe.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Legt fest oder ruft den Namen der ein Bild oder einen Videoclip in das Dokument.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Legt fest oder ruft die URL des zugeordneten Rahmen.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Legt fest oder ruft die URL des zugeordneten Rahmen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
Legt fest oder ruft den Ziel-URL oder den Ankerpunkt Punkt.  
  
  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLANCHORELEMENT_HREF dispatch-ID

## <a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
 Legt fest oder ruft das Zielfenster oder der Zielframe.  
    
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLANCHORELEMENT_TARGET dispatch-ID  

## <a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 Legt fest oder ruft den HTML-Code zwischen den Start- und Endtags des aktuellen Elements ab.  
  
  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLELEMENT_INNERHTML dispatch-ID  
  

## <a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLELEMENT_INNERTEXT dispatch-ID 

## <a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
Legt fest oder ruft die Value-Eigenschaft des ausgewählten Steuerelements.  
 
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden. Finden Sie unter *Wert* in [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ist nur erfolgreich, wenn Steuerelemente ausgeführt werden, eine Value-Eigenschaft. Steuerelemente, die eine Werteigenschaft umfassen Bearbeitungsfelder, Listenfelder und Kombinationsfelder.  
  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_A_VALUE dispatch-ID  

## <a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
Legt fest oder ruft die URL des zugeordneten Rahmen.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID  

## <a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
Legt fest oder ruft die URL des zugeordneten Rahmen.  
  
  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLFRAMEBASE_SRC dispatch-ID 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Ruft ab oder ruft den Namen der ein Bild oder einen Videoclip in das Dokument.  
  
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
 Der Wert, den Sie für das HTML-Steuerelement-ID-Parameter angegeben.  
  
 `var`  
 Der Wert ausgetauscht werden.  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung der `DDX_DHtml_Img_Src` Makro, um die Src-Eigenschaft für ein IMAGE-Element, das Internet Explorer-Image-Objekt abzurufen, wird der vollständig mit Escapezeichen URL für die Bildquelle zurückzugeben. Angenommen, Sie verwenden die `DDX_DHtml_Img_Src` der Src-Eigenschaft des IMAGE-Element festzulegen, auf die Zeichenfolge "einige interessantes Bild" beim Abrufen dieser Eigenschaft wird die Zeichenfolge "res://d:\myapplication\myapp.exe/some%20interesting%20picture." von Internet Explorer zurück  
  
 Dieses Makro ruft die [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) Funktion mithilfe der DISPID_IHTMLIMGELEMENT_SRC dispatch-ID  

  
## <a name="see-also"></a>Siehe auch  
 [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md)

