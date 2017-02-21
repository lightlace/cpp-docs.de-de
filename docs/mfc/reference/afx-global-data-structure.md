---
title: "AFX_GLOBAL_DATA-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GLOBAL_DATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_GLOBAL_DATA-Struktur"
  - "AFX_GLOBAL_DATA-Konstruktor"
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# AFX_GLOBAL_DATA-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `AFX_GLOBAL_DATA` -Struktur enthält Felder und Methoden, mit denen das Framework verwaltet oder die Darstellung und das Verhalten der Anwendung angepasst werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Erstellt eine `AFX_GLOBAL_DATA` -Struktur.|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::Cleanup](#afx_global_data__cleanup)|Gibt Ressourcen frei, die vom Framework zugeordnet werden, z. B. Pinsel, Schriftarten und DLLs.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#afx_global_data__d2d1makerotatematrix)|Erstellt eine Drehtransformation, die sich in einem angegebenen Winkel um einen angegebenen Punkt dreht.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#afx_global_data__drawparentbackground)|Zeichnet den Hintergrund des übergeordneten Elements eines Steuerelements im angegebenen Bereich.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#afx_global_data__drawtextonglass)|Zeichnet den angegebenen Text im Stil des angegebenen Designs.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#afx_global_data__excludetag)|Entfernt das angegebenen XML-Tagpaar aus einem angegebenen Puffer.|  
|[AFX_GLOBAL_DATA::GetColor](#afx_global_data__getcolor)|Ruft die derzeitige Farbe eines angegebenen Benutzeroberflächen-Elements ab.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#afx_global_data__getdirect2dfactory)|Gibt einen Zeiger auf die `ID2D1Factory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#afx_global_data__gethandcursor)|Ruft den vordefinierten Cursor ab, der einer Hand ähnelt und dessen Bezeichner `IDC_HAND`lautet.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#afx_global_data__getitaskbarlist)|Erstellt und speichert in den globalen Daten einen Zeiger auf die ITaskBarList-Schnittstelle.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#afx_global_data__getitaskbarlist3)|Erstellt und speichert in den globalen Daten einen Zeiger auf die ITaskBarList3-Schnittstelle.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#afx_global_data__getnonclientmetrics)|Ruft die Metriken ab, die dem Nichtclientbereich von nicht minimierten Fenstern zugeordnet sind.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#afx_global_data__getshellautohidebars)|Bestimmt Positionen von Leisten zum automatischen Ausblenden einer Shell.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#afx_global_data__gettextheight)|Ruft die Höhe von Textzeichen in der aktuellen Schriftart ab.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#afx_global_data__getwicfactory)|Gibt einen Zeiger auf die `IWICImagingFactory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#afx_global_data__getwritefactory)|Gibt einen Zeiger auf die `IDWriteFactory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Initialisiert die Factorys `D2D`, `DirectWrite`und `WIC` . Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#afx_global_data__is32biticons)|Gibt an, ob vordefinierte 32-Bit-Symbole unterstützt werden.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Bestimmt, ob `D2D` initialisiert wurde.|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#afx_global_data__isdwmcompositionenabled)|Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) -Methode von Windows bereit.|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#afx_global_data__ishighcontrastmode)|Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#afx_global_data__onsettingchange)|Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#afx_global_data__registerwindowclass)|Registriert die angegebene MFC-Fensterklasse.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#afx_global_data__releasetaskbarrefs)|Gibt Schnittstellen frei, die durch die Methoden GetITaskbarList und GetITaskbarList3 ermittelt wurden.|  
|[AFX_GLOBAL_DATA::Resume](#afx_global_data__resume)|Initialisiert die internen Funktionszeiger für den Zugriff auf Methoden, die [Designs und visuelle Stile](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)in Windows unterstützen.|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#afx_global_data__setlayeredattrib)|Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) -Methode von Windows bereit.|  
|[AFX_GLOBAL_DATA::SetMenuFont](#afx_global_data__setmenufont)|Erstellt die angegebene logische Schriftart.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#afx_global_data__shellcreateitemfromparsingname)|Erstellt und initialisiert ein Shellelementobjekt aus einem Analysenamen.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#afx_global_data__updatefonts)|Initialisiert die logischen Schriftarten erneut, die vom Framework verwendet werden.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#afx_global_data__updatesyscolors)|Initialisiert die Farben, die Farbtiefe, die Stifte, die Pinsel und die Bilder, die vom Framework verwendet werden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__enableaccessibilitysupport)|Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung. Active Accessibility stellt zuverlässige Methoden zum Anzeigen von Informationen über Benutzeroberflächenelemente bereit.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__isaccessibilitysupport)|Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#afx_global_data__iswindowslayersupportavailable)|Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#afx_global_data__bisosalphablendingsupport)|Gibt an, ob das aktuelle Betriebssystem Alphablending unterstützt.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#afx_global_data__biswindows7)|Gibt an, ob die Anwendung unter dem Betriebssystem Windows 7 oder höher ausgeführt wird.|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#afx_global_data__clractivecaptiongradient)|Gibt den Farbverlauf der aktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#afx_global_data__clrinactivecaptiongradient)|Gibt den Farbverlauf der inaktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#afx_global_data__m_busebuiltin32biticons)|Gibt an, ob das Framework vordefinierte 32-Bit-Farbsymbole oder Symbole mit einer niedrigeren Auflösung verwendet.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#afx_global_data__m_busesystemfont)|Gibt an, ob eine Systemschriftart für Menüs, Symbolleisten und Menübänder verwendet wird.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#afx_global_data__m_hcurhand)|Speichert das Handle für den Hand-Cursor.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#afx_global_data__m_hcurstretch)|Speichert das Handle für den horizontalen Streckungs-Cursor.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#afx_global_data__m_hcurstretchvert)|Speichert das Handle für den vertikalen Streckungs-Cursor.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#afx_global_data__m_hicontool)|Speichert das Handle für das Werkzeugsymbol.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#afx_global_data__m_nautohidetoolbarmargin)|Gibt den Offset von der äußersten linken Symbolleiste zum automatischen Ausblenden von der linken Seite der Andockleiste an.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#afx_global_data__m_nautohidetoolbarspacing)|Gibt die Lücke zwischen Symbolleisten zum automatischen Ausblenden an.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#afx_global_data__m_ndragframethicknessdock)|Gibt die Breite des Ziehrahmens an, mit dem der angedockten Zustand übermittelt wird.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#afx_global_data__m_ndragframethicknessfloat)|Gibt die Breite des Ziehrahmens an, mit dem der unverankerte Zustand übermittelt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die meisten Daten in der `AFX_GLOBAL_DATA` -Struktur werden beim Start der Anwendung initialisiert.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxglobals.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="a-nameafxglobaldatabisosalphablendingsupporta-afxglobaldatabisosalphablendingsupport"></a><a name="afx_global_data__bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
Gibt an, ob das Betriebssystem Alphablending unterstützt.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
## <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass alpha-blending unterstützt wird. andernfalls `FALSE`.  
  

## <a name="a-nameafxglobaldatacleanupa-afxglobaldatacleanup"></a><a name="afx_global_data__cleanup"></a> AFX_GLOBAL_DATA::Cleanup
Gibt Ressourcen frei, die vom Framework zugeordnet werden, z. B. Pinsel, Schriftarten und DLLs.  
  
  
```  
void CleanUp();
```  
## <a name="a-nameafxglobaldatad2d1makerotatematrixa-afxglobaldatad2d1makerotatematrix"></a><a name="afx_global_data__d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Erstellt eine Drehtransformation, die sich in einem angegebenen Winkel um einen angegebenen Punkt dreht.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
#### <a name="parameters"></a>Parameter  
 `angle`  
 Der Winkel der Drehung im Uhrzeigersinn in Grad.  
  
 `center`  
 Der Punkt, um die gedreht.  
  
 `matrix`  
 Wenn diese Methode zurückgibt, enthält die neue Drehtransformation. Sie müssen Speicher für diesen Parameter reservieren.  
  
## <a name="return-value"></a>Rückgabewert  
 Andernfalls gibt S_OK zurück, wenn erfolgreich, oder einen Fehler zurück.  
  
## <a name="a-nameafxglobaldatadrawparentbackgrounda-afxglobaldatadrawparentbackground"></a><a name="afx_global_data__drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
Zeichnet den Hintergrund des übergeordneten Elements eines Steuerelements im angegebenen Bereich.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Zeiger auf ein Steuerelement-Fenster.  
  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `lpRect`  
 Ein Zeiger auf ein Rechteck, das den Bereich zum Zeichnen umschließt. Der Standardwert ist `NULL`.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
## <a name="a-nameafxglobaldatadrawtextonglassa-afxglobaldatadrawtextonglass"></a><a name="afx_global_data__drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
Zeichnet den angegebenen Text im Stil des angegebenen Designs.  
  
  
```  
BOOL DrawTextOnGlass(
    HTHEME hTheme,   
    CDC* pDC,   
    int iPartId,   
    int iStateId,   
    CString strText,   
    CRect rect,   
    DWORD dwFlags,   
    int nGlowSize = 0,   
    COLORREF clrText = (COLORREF)-1);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `hTheme`  
 Handle zu den Designdaten eines Fensters oder `NULL`. Das Framework verwendet das angegebene Design, um den Text zu zeichnen, wenn dieser Parameter nicht `NULL` lautet und Designs unterstützt werden. Andernfalls verwendet das Framework kein Design zum Zeichnen des Texts.  
  
 Verwenden Sie die [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) -Methode, um `HTHEME`zu erstellen.  
  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `iPartId`  
 Das Steuerelementteil, in dem das gewünschte Erscheinungsbild für den Text gespeichert ist. Weitere Informationen finden Sie im Artikel [Parts and States](http://msdn.microsoft.com/library/windows/desktop/bb773210)(Teile und Zustände) in der Tabellenspalte „Part“ (Teil). Wenn der Wert 0 lautet, wird der Text in der Standardschriftart oder in einer im Gerätekontext ausgewählten Schriftart gezeichnet.  
  
 [in] `iStateId`  
 Der Steuerelementzustand, in dem das gewünschte Erscheinungsbild für den Text gespeichert ist. Weitere Informationen finden Sie im Artikel [Parts and States](http://msdn.microsoft.com/library/windows/desktop/bb773210)(Teile und Zustände) in der Tabellenspalte „States“ (Zustände).  
  
 [in] `strText`  
 Der zu zeichnende Text.  
  
 [in] `rect`  
 Die Grenze des Bereichs, in dem der angegebene Text gezeichnet wird.  
  
 [in] `dwFlags`  
 Eine bitweise Kombination (OR) von Flags, die angibt, wie der angegebene Text gezeichnet wird.  
  
 Wenn der `hTheme` -Parameter ist `NULL` oder Designs werden nicht unterstützt und aktiviert, der `nFormat` Parameter von der [CDC:: DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext) Methode werden die gültigen Flags beschrieben. Wenn Themen unterstützt werden, beschreibt der `dwFlags` -Parameter der [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) -Methode die gültigen Flags.  
  
 [in] `nGlowSize`  
 Die Größe eines Leuchteffekts, der auf dem Hintergrund gezeichnet wird, bevor der angegebene Text gezeichnet wird. Der Standardwert ist 0.  
  
 [in] `clrText`  
 Die Farbe, in der der angegebene Text gezeichnet wird. Der Standardwert ist die Standardfarbe.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn ein Design zum Zeichnen des angegebenen Texts verwendet wird. andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Ein Design definiert den visuellen Stil einer Anwendung. In folgenden Fällen wird kein Design zum Zeichnen des Textes verwendet: Der `hTheme` -Parameter lautet `NULL`; die [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) -Methode wird nicht unterstützt; die Komposition über den [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) ist deaktiviert.  
  
 
## <a name="see-also"></a>Siehe auch  
 [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Teile und Zustände](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC:: DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Aktivieren und steuern DWM-Komposition](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataenableaccessibilitysupporta-afxglobaldataenableaccessibilitysupport"></a><a name="afx_global_data__enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie die Unterstützung von Eingabehilfen; `FALSE` Accessibility-Unterstützung deaktivieren. Der Standardwert ist `TRUE`.  
  
## <a name="remarks"></a>Hinweise  
 Active Accessibility ist eine COM-basierte Technologie, die die Programme und die Windows-Betriebssystem arbeiten zusammen mit Hilfstechnologieprodukten verbessert. Zum Anzeigen von Informationen über Benutzeroberflächenelemente auf zuverlässige Weise darüber. Eine neuere Zugriffsmodell namens Microsoft-Benutzeroberflächenautomatisierung ist jedoch jetzt verfügbar. Einen Vergleich der beiden Technologien finden Sie unter [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Verwenden der [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md) Methode, um zu bestimmen, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.  
  
 
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md)

## <a name="a-nameafxglobaldataexcludetaga-afxglobaldataexcludetag"></a><a name="afx_global_data__excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
Entfernt das angegebenen XML-Tagpaar aus einem angegebenen Puffer.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `strBuffer`  
 Ein Puffer von Text.  
  
 [in] `lpszTag`  
 Der Name eines Paars von öffnenden und schließenden XML-Tags.  
  
 [out] `strTag`  
 Bei dieser Methode wird der `strTag` Parameter enthält den Text zwischen den öffnenden und schließenden XML Tags, die von lauten die `lpszTag` Parameter. Das Ergebnis ist keine führenden oder nachgestellten Leerzeichen entfernt.  
  
 [in] `bIsCharsList`  
 `TRUE` Konvertieren Sie Symbole für Escapezeichen in der `strTag` Parameter in der tatsächlichen Escapezeichen; `FALSE` nicht zum Ausführen der Konvertierung. Der Standardwert ist `FALSE`. Weitere Informationen finden Sie in den Hinweisen.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Ein XML-Tag-Paar besteht aus mit dem Namen Start- und Endtags, die Anfang und Ende einer Abfolge von Text im angegebenen Puffer angeben. Die `strBuffer` -Parameter gibt den Puffer und der `lpszTag` Parameter gibt den Namen des XML-Tags.  
  
 Verwenden Sie die Symbole in der folgenden Tabelle, um die Codierung eines Satzes von Escapezeichen in den angegebenen Puffer. Geben Sie `TRUE` für die `bIsCharsList` Parameter konvertiert die Symbole in der `strTag` Parameter in der tatsächlichen Escape-Zeichen. Die folgende Tabelle wird die [_T()](../../c-runtime-library/data-type-mappings.md) Makro, geben Sie das Symbol und Zeichenfolgen mit Escapezeichen versehen.  
  
|Symbol|Escapezeichen|  
|------------|----------------------|  
|_T("\\\t")|_T("\t")|  
|_T("\\\n")|_T("\n")|  
|_T("\\\r")|_T("\r")|  
|_T("\\\b")|_T("\b")|  
|_T("LT")|_T("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="a-nameafxglobaldatagetcolora-afxglobaldatagetcolor"></a><a name="afx_global_data__getcolor"></a> AFX_GLOBAL_DATA::GetColor
Ruft die derzeitige Farbe eines angegebenen Benutzeroberflächen-Elements ab.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `nColor`  
 Ein Wert, der ein Element der Benutzeroberfläche angibt, dessen Farbe abgerufen wird. Eine Liste der gültigen Werte finden Sie unter der `nIndex` Parameter von der [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 Die RGB-Farbwert für das angegebene Benutzeroberflächenelement. Weitere Informationen finden Sie in den Hinweisen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `nColor` Parameter liegt außerhalb des Bereichs, der Rückgabewert ist 0 (null). Da 0 (null), die ebenfalls einen gültigen RGB-Wert ist, können nicht Sie diese Methode verwenden, um festzustellen, ob eine Systemfarbe durch das aktuelle Betriebssystem unterstützt wird. Verwenden Sie stattdessen die [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) -Methode, die gibt `NULL` wenn die Farbe nicht unterstützt wird.  
  
## <a name="see-also"></a>Siehe auch  

 [GetSysColor-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="a-nameafxglobaldatagetdirect2dfactorya-afxglobaldatagetdirect2dfactory"></a><a name="afx_global_data__getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 Gibt einen Zeiger auf die ID2D1Factory-Schnittstelle, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die ID2D1Factory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung fehlschlägt oder das aktuelle Betriebssystem keine D2D-Unterstützung.  
  
AFX_GLOBAL_DATA::GetHandCursor Ruft den vordefinierten Cursor, der eine Hand ähnelt und dessen Bezeichner `IDC_HAND`.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das Handle für den Hand-Cursor.  

## <a name="a-nameafxglobaldatagetnonclientmetricsa-afxglobaldatagetnonclientmetrics"></a><a name="afx_global_data__getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
Ruft die Metriken ab, die dem Nichtclientbereich von nicht minimierten Fenstern zugeordnet sind.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
#### <a name="parameters"></a>Parameter  
 [in, out] `info`  
 Ein [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) -Struktur, die skalierbare Metriken im Zusammenhang mit den nicht-Clientbereich eines nicht minimierten Fensters enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
 
  
## <a name="see-also"></a>Siehe auch   
 [NONCLIENTMETRICS-Struktur](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="a-nameafxglobaldatagettextheighta-afxglobaldatagettextheight"></a><a name="afx_global_data__gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 Ruft die Höhe von Textzeichen in der aktuellen Schriftart ab.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `bHorz`  
 `TRUE` um die Höhe der Zeichen abrufen, wenn der Text horizontal verläuft. `FALSE` die Höhe der Zeichen abrufen, wenn der Text vertikal verläuft. Der Standardwert ist `TRUE`.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Höhe der aktuellen Schriftart an, die die Oberlänge auf seine Unterlänge gemessen wird.  
  
## <a name="a-nameafxglobaldatagetwicfactorya-afxglobaldatagetwicfactory"></a><a name="afx_global_data__getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
Gibt einen Zeiger auf die IWICImagingFactory-Schnittstelle, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die IWICImagingFactory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung fehlschlägt oder das aktuelle Betriebssystem keine WIC-Unterstützung bietet.  
  
## <a name="a-nameafxglobaldatagetwritefactorya-afxglobaldatagetwritefactory"></a><a name="afx_global_data__getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
Gibt einen Zeiger auf die IDWriteFactory-Schnittstelle, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die IDWriteFactory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung fehlschlägt oder das aktuelle Betriebssystem keine DirectWrite-Unterstützung.  
 
## <a name="a-nameafxglobaldatainitd2da-afxglobaldatainitd2d"></a><a name="afx_global_data__initd2d"></a> AFX_GLOBAL_DATA::InitD2D
Initialisiert D2D, DirectWrite und WIC-Factorys. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
#### <a name="parameters"></a>Parameter  
 `d2dFactoryType`  
 Das Threadingmodell der D2D-Factory und die Ressourcen erstellt.  
  
 `writeFactoryType`  
 Ein Wert, der angibt, ob das Write-Factoryobjekt freigegeben oder isoliert wird  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn die Factorys initialisiert, FALSE - andernfalls wurden  
  
## <a name="a-nameafxglobaldatais32biticonsa-afxglobaldatais32biticons"></a><a name="afx_global_data__is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
Gibt an, ob vordefinierte 32-Bit-Symbole unterstützt werden.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn vordefinierte 32-Bit-Symbole unterstützt werden. andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` wenn das Framework vordefinierte 32-Bit-Symbole, unterstützt und wenn das Betriebssystem 16 Bits pro Pixel oder mehr unterstützt, und Bilder nicht in hohem Kontrast angezeigt werden.  
  
## <a name="a-nameafxglobaldataisaccessibilitysupporta-afxglobaldataisaccessibilitysupport"></a><a name="afx_global_data__isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.  
  
  
```  
BOOL IsAccessibilitySupport() const;

 
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Accessibility-Unterstützung aktiviert ist. andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Microsoft Active Accessibility wurde die frühere Lösung für Clientanwendungen zugänglich gemacht. Microsoft-Benutzeroberflächenautomatisierung ist das neue Zugriffsmodell für Microsoft Windows und dient zum Erfüllen der Anforderungen von Hilfstechnologieprodukten und automatisierte TestTools. Weitere Informationen finden Sie unter [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Verwenden der [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__EnableAccessibilitySupport.md) Methode zum Aktivieren oder Deaktivieren von Active Accessibility-Unterstützung.  
  

## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)

## <a name="a-nameafxglobaldataisd2dinitializeda-afxglobaldataisd2dinitialized"></a><a name="afx_global_data__isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 Bestimmt, ob die D2D initialisiert wurde  
  
  
```  
BOOL IsD2DInitialized() const;

 
```  
  
## <a name="return-value"></a>Rückgabewert  
 True, wenn D2D initialisiert wurde. andernfalls FALSE.  
  
## <a name="a-nameafxglobaldataisdwmcompositionenableda-afxglobaldataisdwmcompositionenabled"></a><a name="afx_global_data__isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) -Methode von Windows bereit.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) Komposition aktiviert ist, andernfalls, `FALSE`.  
  
## <a name="see-also"></a>Siehe auch    
 [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Aktivieren und steuern DWM-Komposition](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataishighcontrastmodea-afxglobaldataishighcontrastmode"></a><a name="afx_global_data__ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.    
```  
BOOL IsHighContrastMode() const;

 
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Bilder in Schwarz oder weiß Kontrastmodus derzeit angezeigt werden; andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Hohen Kontrast Schwarz Kanten, die mit dem Licht weiß sind, und der Hintergrund Schwarz ist. In Kontrastmodus weißen zeigt das Licht Kanten werden schwarz angezeigt, und der Hintergrund ist weiß.  
  
## <a name="a-nameafxglobaldataiswindowslayersupportavailablea-afxglobaldataiswindowslayersupportavailable"></a><a name="afx_global_data__iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const;

 
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn überlappende Fenster unterstützt werden. andernfalls `FALSE`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn überlappende Fenster unterstützt werden, *intelligentes Andocken* Marker überlappende Fenster verwenden.  
  
## <a name="a-nameafxglobaldatambusebuiltin32biticonsa-afxglobaldatambusebuiltin32biticons"></a><a name="afx_global_data__m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Gibt an, ob das Framework vordefinierte 32-Bit-Farbsymbole oder Symbole mit einer niedrigeren Auflösung verwendet.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
## <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass das Framework 32-Bit-Farbsymbole verwenden. `FALSE` Gibt die niedrigere Auflösung Symbole an. Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` -Konstruktor initialisiert das Mitglied `TRUE`.  
  
 Dieser Member muss beim Start der Anwendung festgelegt werden.  
  
## <a name="a-nameafxglobaldatambusesystemfonta-afxglobaldatambusesystemfont"></a><a name="afx_global_data__m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
Gibt an, ob eine Systemschriftart für Menüs, Symbolleisten und Menübänder verwendet wird.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
## <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass eine Systemschriftart; andernfalls `FALSE`. Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` -Konstruktor initialisiert das Mitglied `FALSE`.  
  
 Testen dieses Element ist nicht die einzige Möglichkeit für das Framework die Schriftart zu bestimmen, verwenden. Die `AFX_GLOBAL_DATA::UpdateFonts` Methode außerdem tests für Standard- und Alternative Schriftarten, um zu bestimmen, welche visuellen Stile Menüs, Symbolleisten und Menübänder anzuwendenden verfügbar sind.  
  
## <a name="a-nameafxglobaldatamhcurhanda-afxglobaldatamhcurhand"></a><a name="afx_global_data__m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
Speichert das Handle für den Hand-Cursor.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="a-nameafxglobaldatamhcurstretcha-afxglobaldatamhcurstretch"></a><a name="afx_global_data__m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
Speichert das Handle für den horizontalen Streckungs-Cursor.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="a-nameafxglobaldatamhcurstretchverta-afxglobaldatamhcurstretchvert"></a><a name="afx_global_data__m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
Speichert das Handle für den vertikalen Streckungs-Cursor.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="a-nameafxglobaldatamhicontoola-afxglobaldatamhicontool"></a><a name="afx_global_data__m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
Speichert das Handle für das Werkzeugsymbol.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="a-nameafxglobaldatamnautohidetoolbarmargina-afxglobaldatamnautohidetoolbarmargin"></a><a name="afx_global_data__m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Gibt den Offset in der Symbolleiste am weitesten links stehende automatisch im Hintergrund auf der linken Seite des Balkens andocken.  
  
  
```  
int   m_nAutoHideToolBarMargin;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 4 Pixel.  
  
## <a name="a-nameafxglobaldatamnautohidetoolbarspacinga-afxglobaldatamnautohidetoolbarspacing"></a><a name="afx_global_data__m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Gibt die Lücke zwischen Symbolleisten zum automatischen Ausblenden an.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Mitglied auf 14 Pixel.  
  
## <a name="a-nameafxglobaldatamndragframethicknessdocka-afxglobaldatamndragframethicknessdock"></a><a name="afx_global_data__m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Gibt die Stärke des Rahmens ziehen, mit dem den angedockten Zustand anzugeben.  
  
  
```  
int   m_nDragFrameThicknessDock;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 3 Pixel.  
  
## <a name="a-nameafxglobaldatamndragframethicknessfloata-afxglobaldatamndragframethicknessfloat"></a><a name="afx_global_data__m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Gibt die Stärke des Rahmens ziehen, die verwendet wird, um den schwebenden Status anzugeben.  
  
  
```  
int   m_nDragFrameThicknessFloat;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 4 Pixel.  
  
## <a name="a-nameafxglobaldataonsettingchangea-afxglobaldataonsettingchange"></a><a name="afx_global_data__onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.  
  
  
```  
void OnSettingChange();
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode legt die Framework-Variablen in den Zustand der bestimmte Attribute der Desktop des Benutzers. Diese Methode erkennt den aktuellen Zustand der Menüanimation Menü ausblenden sowie Funktionen zum automatischen Ausblenden der Taskleiste.  
  
## <a name="a-nameafxglobaldataregisterwindowclassa-afxglobaldataregisterwindowclass"></a><a name="afx_global_data__registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
Registriert die angegebene MFC-Fensterklasse.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `lpszClassNamePrefix`  
 Der Name der Fensterklasse, zu registrieren.  
  
## <a name="return-value"></a>Rückgabewert  
 Der gekennzeichnete Name der registrierten-Klasse, wenn diese Methode erfolgreich ist. andernfalls ein [Ressourcenausnahme](../Topic/AfxThrowResourceException.md).  
  
## <a name="remarks"></a>Hinweise  
 Der Rückgabewert ist ein Doppelpunkt getrennte Liste von der `lpszClassNamePrefix` Parameterzeichenfolge und die hexadezimale Textdarstellungen von Handles von der aktuellen Anwendungsinstanz ist die Pfeil-Cursor, deren Bezeichner ist IDC_ARROW; und der Hintergrundpinsel Anwendung Cursor. Weitere Informationen zum Registrieren von Fensterklassen MFC finden Sie unter [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
## <a name="see-also"></a>Siehe auch    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="a-nameafxglobaldataresumea-afxglobaldataresume"></a><a name="afx_global_data__resume"></a> AFX_GLOBAL_DATA::Resume
 Initialisiert die internen Funktionszeiger, der Zugriff auf Methoden, die Windows-Designs und visuelle Stile unterstützen. 
  
  
```  
BOOL Resume();
```  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`. Im Debugmodus befindet überprüft diese Methode, wenn diese Methode nicht erfolgreich ist.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn das Framework erhält das [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) Nachricht.  
  
## <a name="a-nameafxglobaldatasetlayeredattriba-afxglobaldatasetlayeredattrib"></a><a name="afx_global_data__setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) -Methode von Windows bereit.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
 Handle für das überlappende Fenster.  
  
 [in] `crKey`  
 Die Transparenzfarbe Schlüssel, die [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) verwendet, um das überlappende Fenster zu erstellen.  
  
 [in] `bAlpha`  
 Der alpha-Wert, der verwendet wird, um die Deckkraft des überlappenden Fensters zu beschreiben.  
  
 [in] `dwFlags`  
 Eine bitweise Kombination (OR) von Flags, die angeben, welche Methodenparameter verwendet werden. Geben Sie LWA_COLORKEY verwenden die `crKey` Parameter als die der Transparenzfarbe. Geben Sie LWA_ALPHA verwenden die `bAlpha` Parameter, um die Durchlässigkeit des überlappenden Fensters bestimmt.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.   
 
## <a name="see-also"></a>Siehe auch   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="a-nameafxglobaldatasetmenufonta-afxglobaldatasetmenufont"></a><a name="afx_global_data__setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
Erstellt die angegebene logische Schriftart.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `lpLogFont`  
 Ein Zeiger auf eine Struktur, die die Attribute einer Schriftart enthält.  
  
 [in] `bHorz`  
 `TRUE` um anzugeben, dass der Text horizontal ausgeführt wird; `FALSE` angeben, dass der Text vertikal verläuft.  
  
## <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`. Im Debugmodus befindet überprüft diese Methode, wenn diese Methode nicht erfolgreich ist.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen horizontale normalen Schrift, eine unterstrichen, und ist fett verwendet in Menüelemente. Diese Methode erstellt optional eine reguläre-Schriftart. Weitere Informationen über logische Schriftarten finden Sie unter [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#cfont__createfontindirect).  
  
## <a name="a-nameafxglobaldataupdatefontsa-afxglobaldataupdatefonts"></a><a name="afx_global_data__updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
Initialisiert die logischen Schriftarten erneut, die vom Framework verwendet werden.  
  
  
```  
void UpdateFonts();
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über logische Schriftarten finden Sie unter `CFont::CreateFontIndirect`.  
  
## <a name="a-nameafxglobaldataupdatesyscolorsa-afxglobaldataupdatesyscolors"></a><a name="afx_global_data__updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
Initialisiert die Farben, die Farbtiefe, die Stifte, die Pinsel und die Bilder, die vom Framework verwendet werden.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="a-nameafxglobaldatabiswindows7a-afxglobaldatabiswindows7"></a><a name="afx_global_data__biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Gibt an, ob die Anwendung unter Windows 7 oder höher ausgeführt wird.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="a-nameafxglobaldataclractivecaptiongradienta-afxglobaldataclractivecaptiongradient"></a><a name="afx_global_data__clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
Gibt den Farbverlauf der aktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldataclrinactivecaptiongradienta-afxglobaldataclrinactivecaptiongradient"></a><a name="afx_global_data__clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Gibt den Farbverlauf der inaktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldatagetitaskbarlista-afxglobaldatagetitaskbarlist"></a><a name="afx_global_data__getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
Erstellt und speichert Sie in den globalen Daten einen Zeiger auf die `ITaskBarList` Schnittstelle.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `ITaskbarList` Schnittstelle nach erfolgreicher Erstellung einer Aufgabe Balken Listenobjekt; `NULL` Wenn die Erstellung fehlschlägt oder wenn das aktuelle Betriebssystem Windows 7 unterschreitet.  
  
## <a name="a-nameafxglobaldatagetitaskbarlist3a-afxglobaldatagetitaskbarlist3"></a><a name="afx_global_data__getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
Erstellt und speichert Sie in den globalen Daten einen Zeiger auf die `ITaskBarList3` Schnittstelle.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `ITaskbarList3` Schnittstelle nach erfolgreicher Erstellung einer Aufgabe Balken Listenobjekt; `NULL` Wenn die Erstellung fehlschlägt oder wenn das aktuelle Betriebssystem Windows 7 unterschreitet.  
  
## <a name="a-nameafxglobaldatagetshellautohidebarsa-afxglobaldatagetshellautohidebars"></a><a name="afx_global_data__getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
Bestimmt Positionen von Leisten zum automatischen Ausblenden einer Shell.  
  
  
```  
int GetShellAutohideBars();
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Ganzzahlwert mit codierten Flags, die Positionen Auto angeben ausblenden Balken. Sie können die folgenden Werte kombinieren: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="a-nameafxglobaldatareleasetaskbarrefsa-afxglobaldatareleasetaskbarrefs"></a><a name="afx_global_data__releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Versionsschnittstellen der `GetITaskbarList` und `GetITaskbarList3` Methoden.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="a-nameafxglobaldatashellcreateitemfromparsingnamea-afxglobaldatashellcreateitemfromparsingname"></a><a name="afx_global_data__shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Erstellt und initialisiert ein Shellelementobjekt aus einem Analysenamen.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
#### <a name="parameters"></a>Parameter  
 `pszPath`  
 [in] Ein Zeiger auf einen Anzeigenamen ein.  
  
 `pbc`  
 Ein Zeiger auf einen Bindungskontext, der den Analysevorgang steuert.  
  
 `riid`  
 Ein Verweis auf ein Schnittstellen-ID.  
  
 `ppv`  
 [out] Diese Funktion enthält den Schnittstellenzeiger, der im angeforderten `riid`. Normalerweise ist `IShellItem` oder `IShellItem2`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn erfolgreich. ein Fehlerwert andernfalls.  

