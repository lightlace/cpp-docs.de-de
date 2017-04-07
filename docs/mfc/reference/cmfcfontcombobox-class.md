---
title: Klasse CMFCFontComboBox | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox::DrawItem method
- CMFCFontComboBox::PreTranslateMessage method
- CMFCFontComboBox::MeasureItem method
- CMFCFontComboBox class
- CMFCFontComboBox::CompareItem method
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1252f5ca102637e70cc384afd723464aec4144b4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox-Klasse
Die `CMFCFontComboBox` -Klasse erstellt ein Kombinationsfeld-Steuerelement, das eine Liste von Schriftarten enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Erstellt ein `CMFCFontComboBox`-Objekt.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Aufgerufen, um die relative Position eines neuen Elements im Feld sortierte Liste der aktuellen Schriftart ein Kombinationsfeld-Steuerelement zu bestimmen. (Überschreibt [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Aufgerufen, um ein angegebenes Element in der aktuellen Schriftart Kombinationsfeld-Steuerelement zu zeichnen. (Überschreibt [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Ruft Informationen zu den derzeit ausgewählten Schriftart.|  
|`CMFCFontComboBox::MeasureItem`|Vom Framework aufgerufen wird, informiert Windows der Dimensionen des Listenfelds in der aktuellen Schriftart Kombinationsfeld-Steuerelement. (Überschreibt [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Wählt die Schriftart, die den angegebenen Kriterien aus dem Kombinationsfeld Schriftart entspricht.|  
|[CMFCFontComboBox::Setup](#setup)|Initialisiert die Liste der Elemente im Kombinationsfeld Schriftart an.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Gibt das Framework die Schriftart zum Zeichnen der Elementnamen in der aktuellen Schriftart-Kombinationsfeld.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CMFCFontComboBox` Objekt in einem Dialogfeld, fügen Sie eine `CMFCFontComboBox` -Variablen in die Dialogfeldklasse. Klicken Sie dann in der `OnInitDialog` Methode die Dialogfeldklasse Aufruf der [CMFCFontComboBox::Setup](#setup) Methode, um die Liste der Elemente im Kombinationsfeld-Steuerelement zu initialisieren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox  
 Erstellt ein `CMFCFontComboBox`-Objekt.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getselfont"></a>CMFCFontComboBox::GetSelFont  
 Ruft Informationen zu den derzeit ausgewählten Schriftart.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf [CMFCFontInfo Klasse](../../mfc/reference/cmfcfontinfo-class.md) -Objekt, das eine Schriftart beschreibt. Es kann sein `NULL` Wenn keine Schriftart im Kombinationsfeld ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 Gibt das Framework die Schriftart zum Zeichnen der Elementnamen in der aktuellen Schriftart-Kombinationsfeld.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` leiten das Framework dieselbe Schriftart verwendet wird, um jedem Elementnamen zu zeichnen. Legen Sie dieses Element auf `FALSE` das Framework jedem Elementnamen mit der Schriftart gezeichnet wird, dessen Name identisch mit der Bezeichnung ist, weiterleiten. Der Standardwert dieses Elements ist `FALSE`.  
  
##  <a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 Wählt die Schriftart, die den angegebenen Kriterien aus dem Kombinationsfeld Schriftart entspricht.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDesc`  
 Zeigt auf eine Schriftart Beschreibungsobjekt.  
  
 [in] `lpszName`  
 Gibt den Namen einer Schriftart an.  
  
 [in] `nCharSet`  
 Gibt einen Zeichensatz. Der Standardwert ist DEFAULT_CHARSET. Weitere Informationen finden Sie unter der `lfCharSet` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Element im Kombinationsfeld Schriftart angegebenen Schriftart Beschreibungsobjekt oder Schriftart und Zeichensatz übereinstimmt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um auszuwählen, und führen Sie einen Bildlauf zum Element im Kombinationsfeld Schriftart, die der angegebenen Schriftart entspricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SelectFont` -Methode in der `CMFCFontComboBox` Klasse. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#35;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>CMFCFontComboBox::Setup  
 Initialisiert die Liste der Elemente im Kombinationsfeld Schriftart an.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFontType`  
 Gibt die Schriftart an. Der Standardwert ist die bitweise Kombination (OR) DEVICE_FONTTYPE, RASTER_FONTTYPE und TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Gibt den Zeichensatz der Schriftart an. Der Standardwert ist DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Gibt die Schriftbreite der Schriftart und die Familie. Der Standardwert ist DEFAULT_PITCH.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kombinationsfeld Schriftart erfolgreich initialisiert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode initialisiert das Kombinationsfeld Schriftart durch Auflisten der installierten Schriftarten, die mit die angegebenen Parametern übereinstimmen und die Namen von Schriftarten in das Kombinationsfeld "Schriftart" einfügen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Setup` -Methode in der `CMFCFontComboBox` Klasse. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls Nr.&36;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)

