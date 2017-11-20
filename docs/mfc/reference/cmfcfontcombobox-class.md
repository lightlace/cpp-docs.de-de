---
title: CMFCFontComboBox Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 53958d1a9f2a2647a42405a2b535441dee162b70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox-Klasse
Die `CMFCFontComboBox` Klasse erstellt ein Kombinationsfeld-Steuerelement, das eine Liste von Schriftarten enthält.  
  
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
|`CMFCFontComboBox::CompareItem`|Vom Framework aufgerufen, die die relative Position eines neuen Elements im Feld sortierte Liste der aktuellen Schriftart ein Kombinationsfeld-Steuerelement zu ermitteln. (Überschreibt [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Wird aufgerufen, durch das Framework ein angegebenes Element in der aktuellen Schriftart Kombinationsfeld-Steuerelement gezeichnet werden soll. (Überschreibt [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Ruft Informationen zu den aktuell ausgewählten Schriftart ab.|  
|`CMFCFontComboBox::MeasureItem`|Wird aufgerufen, durch das Framework informiert Windows über die Abmessungen des Listenfelds in der aktuellen Schriftart Kombinationsfeld-Steuerelement. (Überschreibt [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Wählt die Schriftart, die aus der schriftartkombinationsfeld für den angegebenen Kriterien entspricht.|  
|[CMFCFontComboBox::Setup](#setup)|Initialisiert die Liste der Elemente im Kombinationsfeld Schriftart an.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Zeigt das Framework der Schriftart zu verwenden, um den Elementnamen in das aktuelle schriftartkombinationsfeld zeichnen.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CMFCFontComboBox` Objekt in einem Dialogfeld, fügen Sie eine `CMFCFontComboBox` Variable auf der Dialogfeldklasse. Klicken Sie dann in der `OnInitDialog` Methode der Dialogfeldklasse Aufruf der [CMFCFontComboBox::Setup](#setup) Methode, um die Liste der Elemente im Kombinationsfeld-Steuerelement zu initialisieren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ruft Informationen zu den aktuell ausgewählten Schriftart ab.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf [CMFCFontInfo Klasse](../../mfc/reference/cmfcfontinfo-class.md) Objekt, das eine Schriftart beschreibt. Es kann sein `NULL` Wenn keine Schriftart im Kombinationsfeld ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 Zeigt das Framework der Schriftart zu verwenden, um den Elementnamen in das aktuelle schriftartkombinationsfeld zeichnen.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` , leiten das Framework Schriftart zu verwenden, um jedes Element Bezeichnung gezeichnet werden soll. Legen Sie dieses Element auf `FALSE` , leiten das Framework jedem Elementnamen mit der Schriftart gezeichnet werden soll, deren Name identisch mit der Bezeichnung ist. Der Standardwert dieses Elements ist `FALSE`.  
  
##  <a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 Wählt die Schriftart, die aus der schriftartkombinationsfeld für den angegebenen Kriterien entspricht.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDesc`  
 Zeigt auf eine Schriftart Beschreibung-Objekt.  
  
 [in] `lpszName`  
 Gibt den Namen einer Schriftart an.  
  
 [in] `nCharSet`  
 Gibt einen Zeichensatz. Der Standardwert ist DEFAULT_CHARSET. Weitere Informationen finden Sie unter der `lfCharSet` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Element in das schriftartkombinationsfeld für die angegebene Schriftart-Beschreibungsobjekt oder Schriftartname und Charset entspricht. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um auszuwählen, und führen Sie einen Bildlauf zum Element in das schriftartkombinationsfeld, das die angegebene Schriftart entspricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SelectFont` Methode in der `CMFCFontComboBox` Klasse. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
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
 Gibt den Schriftarttyp. Der Standardwert ist die bitweise Kombination (OR) DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Gibt den Zeichensatz der Schriftart an. Der Standardwert ist DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Gibt die Schriftbreite der Schriftart und Familie. Der Standardwert ist DEFAULT_PITCH.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das schriftartkombinationsfeld erfolgreich initialisiert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode initialisiert das schriftartkombinationsfeld beim Aufzählen der installierten Schriftarten, die mit die angegebenen Parametern übereinstimmen, und diese Schriftartnamen in das schriftartkombinationsfeld einfügen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Setup` Methode in der `CMFCFontComboBox` Klasse. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)
