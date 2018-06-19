---
title: AFX_GLOBAL_DATA-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_GLOBAL_DATA
dev_langs:
- C++
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9230a304473c3f29bda2652f8941fb692b14c038
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357227"
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA-Struktur
Die `AFX_GLOBAL_DATA` -Struktur enthält Felder und Methoden, mit denen das Framework verwaltet oder die Darstellung und das Verhalten der Anwendung angepasst werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Erstellt eine `AFX_GLOBAL_DATA` -Struktur.|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::Cleanup](#cleanup)|Gibt Ressourcen frei, die vom Framework zugeordnet werden, z. B. Pinsel, Schriftarten und DLLs.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Erstellt eine Drehtransformation, die sich in einem angegebenen Winkel um einen angegebenen Punkt dreht.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Zeichnet den Hintergrund des übergeordneten Elements eines Steuerelements im angegebenen Bereich.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Zeichnet den angegebenen Text im Stil des angegebenen Designs.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Entfernt das angegebenen XML-Tagpaar aus einem angegebenen Puffer.|  
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Ruft die derzeitige Farbe eines angegebenen Benutzeroberflächen-Elements ab.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Gibt einen Zeiger auf die `ID2D1Factory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Ruft den vordefinierten Cursor ab, der einer Hand ähnelt und dessen Bezeichner `IDC_HAND`lautet.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|Erstellt und speichert in den globalen Daten einen Zeiger auf die ITaskBarList-Schnittstelle.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Erstellt und speichert in den globalen Daten einen Zeiger auf die ITaskBarList3-Schnittstelle.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|Ruft die Metriken ab, die dem Nichtclientbereich von nicht minimierten Fenstern zugeordnet sind.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Bestimmt Positionen von Leisten zum automatischen Ausblenden einer Shell.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Ruft die Höhe von Textzeichen in der aktuellen Schriftart ab.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Gibt einen Zeiger auf die `IWICImagingFactory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Gibt einen Zeiger auf die `IDWriteFactory` -Schnittstelle zurück, die in den globalen Daten gespeichert ist. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Initialisiert die Factorys `D2D`, `DirectWrite`und `WIC` . Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Gibt an, ob vordefinierte 32-Bit-Symbole unterstützt werden.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Bestimmt, ob `D2D` initialisiert wurde.|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) -Methode von Windows bereit.|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Registriert die angegebene MFC-Fensterklasse.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|Gibt Schnittstellen frei, die durch die Methoden GetITaskbarList und GetITaskbarList3 ermittelt wurden.|  
|[AFX_GLOBAL_DATA::Resume](#resume)|Initialisiert die internen Funktionszeiger für den Zugriff auf Methoden, die [Designs und visuelle Stile](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)in Windows unterstützen.|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) -Methode von Windows bereit.|  
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Erstellt die angegebene logische Schriftart.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Erstellt und initialisiert ein Shellelementobjekt aus einem Analysenamen.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Initialisiert die logischen Schriftarten erneut, die vom Framework verwendet werden.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Initialisiert die Farben, die Farbtiefe, die Stifte, die Pinsel und die Bilder, die vom Framework verwendet werden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung. Active Accessibility stellt zuverlässige Methoden zum Anzeigen von Informationen über Benutzeroberflächenelemente bereit.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Gibt an, ob das aktuelle Betriebssystem Alphablending unterstützt.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Gibt an, ob die Anwendung unter dem Betriebssystem Windows 7 oder höher ausgeführt wird.|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Gibt den Farbverlauf der aktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Gibt den Farbverlauf der inaktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Gibt an, ob das Framework vordefinierte 32-Bit-Farbsymbole oder Symbole mit einer niedrigeren Auflösung verwendet.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Gibt an, ob eine Systemschriftart für Menüs, Symbolleisten und Menübänder verwendet wird.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|Speichert das Handle für den Hand-Cursor.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Speichert das Handle für den horizontalen Streckungs-Cursor.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Speichert das Handle für den vertikalen Streckungs-Cursor.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Speichert das Handle für das Werkzeugsymbol.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Gibt den Offset von der äußersten linken Symbolleiste zum automatischen Ausblenden von der linken Seite der Andockleiste an.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Gibt die Lücke zwischen Symbolleisten zum automatischen Ausblenden an.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Gibt die Breite des Ziehrahmens an, mit dem der angedockten Zustand übermittelt wird.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Gibt die Breite des Ziehrahmens an, mit dem der unverankerte Zustand übermittelt wird.|  
  
### <a name="remarks"></a>Hinweise  
 Die meisten Daten in der `AFX_GLOBAL_DATA` -Struktur werden beim Start der Anwendung initialisiert.  
  
### <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `AFX_GLOBAL_DATA`   
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxglobals.h  
  
### <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
Gibt an, ob das Betriebssystem Alphablending unterstützt.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass Alphablending unterstützt wird. andernfalls `FALSE`.  
  

## <a name="cleanup"></a> AFX_GLOBAL_DATA::Cleanup
Gibt Ressourcen frei, die vom Framework zugeordnet werden, z. B. Pinsel, Schriftarten und DLLs.  
  
  
```  
void CleanUp();
```  
## <a name="d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Erstellt eine Drehtransformation, die sich in einem angegebenen Winkel um einen angegebenen Punkt dreht.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
### <a name="parameters"></a>Parameter   
 `angle`  
 Der Winkel der Drehung im Uhrzeigersinn in Grad.  
  
 `center`  
 Der Punkt, um die gedreht.  
  
 `matrix`  
 Wenn diese Methode zurückgibt, enthält neue Drehtransformation. Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich, oder einen Fehlerwert zurückgegeben andernfalls.  
  
## <a name="drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
Zeichnet den Hintergrund des übergeordneten Elements eines Steuerelements im angegebenen Bereich.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `pWnd`  
 Zeiger auf Fenster eines Steuerelements.  
  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `lpRect`  
 Ein Zeiger auf ein Rechteck, umschließt den Bereich gezeichnet werden soll. Der Standardwert ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
## <a name="drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
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
  
### <a name="parameters"></a>Parameter   
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
  
 Wenn die `hTheme` Parameter ist `NULL` oder wenn Designs sind nicht unterstützt und aktiviert die `nFormat` Parameter von der [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext) Methode beschreibt die gültigen Flags. Wenn Themen unterstützt werden, beschreibt der `dwFlags` -Parameter der [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) -Methode die gültigen Flags.  
  
 [in] `nGlowSize`  
 Die Größe eines Leuchteffekts, der auf dem Hintergrund gezeichnet wird, bevor der angegebene Text gezeichnet wird. Der Standardwert ist 0.  
  
 [in] `clrText`  
 Die Farbe, in der der angegebene Text gezeichnet wird. Der Standardwert ist die Standardfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn ein Design zum Zeichnen des angegebenen Texts verwendet wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Design definiert den visuellen Stil einer Anwendung. In folgenden Fällen wird kein Design zum Zeichnen des Textes verwendet: Der `hTheme` -Parameter lautet `NULL`; die [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) -Methode wird nicht unterstützt; die Komposition über den [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) ist deaktiviert.  
  
### <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Teile und Zustände](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Aktivieren und steuern DWM-Komposition](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `bEnable`  
 `TRUE` Accessibility-Unterstützung zu aktivieren; `FALSE` Accessibility-Unterstützung zu deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Active Accessibility ist eine COM-basierte Technologie, die die Programme und die Windows-Betriebssystem arbeiten zusammen mit Hilfstechnologieprodukten verbessert. Zum Anzeigen von Informationen über Benutzeroberflächenelemente auf zuverlässige Weise darüber. Eine neuere Zugriffsmodell namens Microsoft-UI-Automatisierung ist jetzt jedoch verfügbar. Einen Vergleich der beiden Technologien, finden Sie unter [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).  
  
 Verwenden der [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) Methode, um zu bestimmen, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.  
  
 
### <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)

## <a name="excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
Entfernt das angegebenen XML-Tagpaar aus einem angegebenen Puffer.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `strBuffer`  
 Ein Puffer von Text.  
  
 [in] `lpszTag`  
 Der Name eines Paars von öffnenden und schließenden XML-Tags.  
  
 [out] `strTag`  
 Bei Rückgabe dieser Methode die `strTag` Parameter enthält den Text, der zwischen den öffnenden und schließenden XML Tags, die durch benannte sind die `lpszTag` Parameter. Führende oder nachfolgende Leerzeichen werden aus dem Ergebnis gekürzt.  
  
 [in] `bIsCharsList`  
 `TRUE` Konvertieren von Symbolen für Escapezeichen in der `strTag` Parameter in der tatsächlichen Escapezeichen; `FALSE` nicht zum Durchführen der Konvertierung. Der Standardwert ist `FALSE`. Weitere Informationen finden Sie in den Hinweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein XML-Tagpaar besteht aus mit dem Namen Start- und Endtags, die angeben, die Start- und Ende einer Ausführung des Texts in den angegebenen Puffer. Die `strBuffer` Parameter gibt den Puffer und der `lpszTag` Parameter gibt den Namen des XML-Tags.  
  
 Verwenden Sie die Symbole in der folgenden Tabelle, um die Codierung eines Satzes von Escapezeichen in den angegebenen Puffer. Geben Sie `TRUE` für die `bIsCharsList` zu konvertierenden Symbole im Parameters die `strTag` Parameter in der tatsächlichen Escape-Zeichen. Die folgende Tabelle verwendet den [_T()](../../c-runtime-library/data-type-mappings.md) Makro auf das Symbol angeben und Zeichenfolgen mit Escapezeichen versehen.  
  
|Symbol|Escapezeichen|  
|------------|----------------------|  
|_T ("\\\t")|_T("\t")|  
|_T ("\\\n")|_T("\n")|  
|_T ("\\\r")|_T("\r")|  
|_T ("\\\b")|_T("\b")|  
|_T("LT")|_T ("\<")|  
|_T("GT")|_T("&GT;")|  
|_T("AMP")|_T("&AMP;")|  
  
## <a name="getcolor"></a> AFX_GLOBAL_DATA::GetColor
Ruft die derzeitige Farbe eines angegebenen Benutzeroberflächen-Elements ab.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `nColor`  
 Ein Wert, der ein Benutzeroberflächenelement angibt, dessen Farbe abgerufen wird. Eine Liste der gültigen Werte finden Sie unter der `nIndex` Parameter von der [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Der RGB-Farbe-Wert, der das angegebene Element der Debuggerbenutzeroberfläche werden soll. Weitere Informationen finden Sie in den Hinweisen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `nColor` Parameter liegt außerhalb des Bereichs, der Rückgabewert ist 0 (null). Da 0 (null), die auch einen gültigen RGB-Wert ist, können nicht Sie diese Methode verwenden, um zu bestimmen, ob eine Systemfarbe durch das aktuelle Betriebssystem unterstützt wird. Verwenden Sie stattdessen die [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) Methode, die zurückgibt `NULL` , wenn die Farbe nicht unterstützt wird.  
  
### <a name="see-also"></a>Siehe auch  

 [GetSysColor-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 Gibt einen Zeiger auf die ID2D1Factory-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die ID2D1Factory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich verlaufen, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine D2D-Unterstützung.  
  
## <a name="gethandcursor"></a>  AFX_GLOBAL_DATA::GetHandCursor
Ruft den vordefinierten Cursor ab, der einer Hand ähnelt und dessen Bezeichner `IDC_HAND`lautet.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für den Hand-Cursor.  

## <a name="getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
Ruft die Metriken ab, die dem Nichtclientbereich von nicht minimierten Fenstern zugeordnet sind.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
### <a name="parameters"></a>Parameter   
 [in, out] `info`  
 Ein [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) -Struktur, die skalierbare Metriken zugeordneten nicht-Clientbereich eines nicht minimierten Fensters enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
 
  
### <a name="see-also"></a>Siehe auch   
 [NONCLIENTMETRICS-Struktur](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 Ruft die Höhe von Textzeichen in der aktuellen Schriftart ab.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `bHorz`  
 `TRUE` die Höhe der Zeichen abrufen, wenn der Text horizontal verläuft; `FALSE` die Höhe der Zeichen abrufen, wenn der Text vertikal verläuft. Der Standardwert ist `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der aktuellen Schriftart, der auf die Unterlänge aus seiner Ascender gemessen wird.  
  
## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
Gibt einen Zeiger auf die IWICImagingFactory-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die IWICImagingFactory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich verlaufen, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine WIC-Unterstützung.  
  
## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
Gibt einen Zeiger auf die IDWriteFactory-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die IDWriteFactory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich verlaufen, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine DirectWrite-Unterstützung.  
 
## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D
Initialisiert die D2D DirectWrite und WIC-Factorys. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Parameter   
 `d2dFactoryType`  
 Das Threadingmodell der D2D-Factory und die Ressourcen erstellt.  
  
 `writeFactoryType`  
 Ein Wert, der angibt, ob das Write-Factoryobjekt freigegeben oder isoliert wird  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Factorys initialisiert, "false" -, andernfalls wurden  
  
## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
Gibt an, ob vordefinierte 32-Bit-Symbole unterstützt werden.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie vordefinierte 32-Bit-Symbole unterstützt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` Wenn das Framework vordefinierte 32-Bit-Symbole unterstützt, und wenn das Betriebssystem 16 Bits pro Pixel oder mehr unterstützt und Bilder nicht hohem Kontrast angezeigt werden.  
  
## <a name="isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.  
  
  
```  
BOOL IsAccessibilitySupport() const; 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Accessibility-Unterstützung aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Microsoft Active Accessibility konnte die vorherige Lösung zum treffen von Anwendungen zugegriffen werden kann. Microsoft-UI-Automatisierung ist das neue Zugriffsmodell für Microsoft Windows und richtet sich an die Bedürfnisse von Hilfstechnologieprodukten und automatisierte TestTools.   
  
 Verwenden der [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) Methode zum Aktivieren oder Deaktivieren von Active Accessibility-Unterstützung.  
  

### <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 Bestimmt, ob die D2D initialisiert wurde  
  
  
```  
BOOL IsD2DInitialized() const; 
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn D2D initialisiert wurde. andernfalls "false".  
  
## <a name="isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) -Methode von Windows bereit.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) Komposition (des DWMS) ist, aktiviert ist, andernfalls `FALSE`.  
  
### <a name="see-also"></a>Siehe auch    
 [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Aktivieren und steuern DWM-Komposition](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.    
```  
BOOL IsHighContrastMode() const; 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Bilder nur im Modus für hohe Kontraste von Schwarz oder Weiß angezeigt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 In Schwarz Kontrastmodus Kanten mit Internetzugriff das Licht weiß sind, und der Hintergrund ist schwarz. In weißen Kontrastmodus mit Internetzugriff das Licht Kanten werden schwarz angezeigt, und der Hintergrund ist weiß.  
  
## <a name="iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const; 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn überlappende Fenster unterstützt werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn überlappende Fenster unterstützt werden, *intelligentes Andocken* Marker verwenden überlappende Fenster.  
  
## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Gibt an, ob das Framework vordefinierte 32-Bit-Farbsymbole oder Symbole mit einer niedrigeren Auflösung verwendet.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass das Framework 32-Bit-Farbsymbole verwenden. `FALSE` niedriger Auflösung Symbole angibt. Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element `TRUE`.  
  
 Bei diesem Member muss beim Start der Anwendung festgelegt werden.  
  
## <a name="m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
Gibt an, ob eine Systemschriftart für Menüs, Symbolleisten und Menübänder verwendet wird.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE` Gibt an, dass eine Systemschriftart; andernfalls `FALSE`. Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element `FALSE`.  
  
 Testen dieses Element ist nicht die einzige Möglichkeit für das Framework, um die Schriftart zu ermitteln, verwenden. Die `AFX_GLOBAL_DATA::UpdateFonts` Methode überprüft auch die standardzuordnungen sowie die alternativen Schriftarten, um zu bestimmen, welche visuellen Stile auf Menüs, Symbolleisten und Menübänder anzuwendenden verfügbar sind.  
  
## <a name="m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
Speichert das Handle für den Hand-Cursor.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
Speichert das Handle für den horizontalen Streckungs-Cursor.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
Speichert das Handle für den vertikalen Streckungs-Cursor.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
Speichert das Handle für das Werkzeugsymbol.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Gibt den Offset von der am weitesten links stehende zum automatischen ausblenden Symbolleiste auf die linke Seite des Balkens andocken.  
  
  
```  
int  m_nAutoHideToolBarMargin;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 4 Pixel.  
  
## <a name="m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Gibt die Lücke zwischen Symbolleisten zum automatischen Ausblenden an.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Elements auf 14 Pixel.  
  
## <a name="m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Gibt die Stärke des Rahmens ziehen, die verwendet wird, an der angedockten Zustand.  
  
  
```  
int  m_nDragFrameThicknessDock;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 3 Pixel.  
  
## <a name="m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Gibt die Stärke des Rahmens ziehen, die verwendet wird, an der unverankerte Zustand.  
  
  
```  
int  m_nDragFrameThicknessFloat;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Element 4 Pixel.  
  
## <a name="onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.  
  
  
```  
void OnSettingChange();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode setzt Framework Variablen auf den Zustand der bestimmte Attribute der Desktop des Benutzers. Diese Methode erkennt den aktuellen Status der klicken Sie mit der, Menü zum ein-und Ausblenden der Menüanimation und Funktionen zum automatischen Ausblenden der Taskleiste an.  
  
## <a name="registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
Registriert die angegebene MFC-Fensterklasse.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `lpszClassNamePrefix`  
 Der Name der Fensterklasse registriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der qualifizierte Name der registrierten Klasse, wenn diese Methode erfolgreich ausgeführt wird; andernfalls ein [Ressourcenausnahme](http://msdn.microsoft.com/library/ddd99292-819b-4fa4-8371-b1954ed5856d).  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert ist ein Doppelpunkt getrennte Liste von der `lpszClassNamePrefix` -Parameterzeichenfolge verwenden und die hexadezimale Textdarstellungen von Handles für die aktuelle Anwendungsinstanz; die Anwendung-Cursor, in dem der Pfeilcursor, deren Bezeichner IDC_ARROW; und Der Hintergrundpinsel. Weitere Informationen zum Registrieren von Fensterklassen MFC finden Sie unter [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
### <a name="see-also"></a>Siehe auch    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a> AFX_GLOBAL_DATA::Resume
 Initialisiert die internen Funktionszeiger, der Zugriff auf Methoden, die Windows-Designs und visuelle Stile unterstützen. 
  
  
```  
BOOL Resume();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`. Im Debugmodus befindet bestätigt diese Methode auf, wenn diese Methode nicht erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn das Framework empfängt die [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) Nachricht.  
  
## <a name="setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) -Methode von Windows bereit.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `hwnd`  
 Handle für das überlappende Fenster.  
  
 [in] `crKey`  
 Die der Transparenzfarbe Schlüssel, der [Desktopfenster-Manager](http://msdn.microsoft.com/library/windows/desktop/aa969540) verwendet, um überlappende Fenster verfassen.  
  
 [in] `bAlpha`  
 Der alpha-Wert, der mit der die Deckkraft des Fensters geschichteten beschrieben werden.  
  
 [in] `dwFlags`  
 Eine bitweise Kombination (OR) von Flags, die angeben, welche Methodenparameter verwendet werden. Geben Sie LWA_COLORKEY verwenden die `crKey` Parameter als Transparenzfarbe. Geben Sie LWA_ALPHA verwenden die `bAlpha` Parameter, um die Deckkraft des Fensters mit Ebenen zu ermitteln.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.   
 
### <a name="see-also"></a>Siehe auch   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
Erstellt die angegebene logische Schriftart.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter   
 [in] `lpLogFont`  
 Ein Zeiger auf eine Struktur, die Attribute einer Schriftart enthält.  
  
 [in] `bHorz`  
 `TRUE` um anzugeben, dass der Text horizontal ausgeführt wird; `FALSE` um anzugeben, dass der Text vertikal verläuft.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`. Im Debugmodus befindet bestätigt diese Methode auf, wenn diese Methode nicht erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen horizontale normalen Schrift, eine unterstrichen, und fett formatierter Schrift, die verwendet im Standardmodus Menüelemente. Diese Methode erstellt optional einen normalen Schrift vertikalen. Weitere Informationen zu logischen Schriftarten, finden Sie unter [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).  
  
## <a name="updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
Initialisiert die logischen Schriftarten erneut, die vom Framework verwendet werden.  
  
  
```  
void UpdateFonts();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu logischen Schriftarten, finden Sie unter `CFont::CreateFontIndirect`.  
  
## <a name="updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
Initialisiert die Farben, die Farbtiefe, die Stifte, die Pinsel und die Bilder, die vom Framework verwendet werden.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Gibt an, ob die Anwendung unter Windows 7 oder höher ausgeführt wird.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
Gibt den Farbverlauf der aktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Gibt den Farbverlauf der inaktiven Beschriftung an. Wird im Allgemeinen für andockbare Bereiche verwendet.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
Erstellt und speichert Sie in den globalen Daten einen Zeiger auf die `ITaskBarList` Schnittstelle.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `ITaskbarList` Schnittstelle, wenn die Erstellung einer Aufgabe Strich Listenobjekt erfolgreich ist. `NULL` Wenn Erstellung ein Fehler auftritt oder wenn das aktuelle Betriebssystem kleiner als Windows 7 ist.  
  
## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
Erstellt und speichert Sie in den globalen Daten einen Zeiger auf die `ITaskBarList3` Schnittstelle.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `ITaskbarList3` Schnittstelle, wenn die Erstellung einer Aufgabe Strich Listenobjekt erfolgreich ist. `NULL` Wenn Erstellung ein Fehler auftritt oder wenn das aktuelle Betriebssystem kleiner als Windows 7 ist.  
  
## <a name="getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
Bestimmt Positionen von Leisten zum automatischen Ausblenden einer Shell.  
  
  
```  
int GetShellAutohideBars();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein ganzzahliger Wert mit codierte Flags, die Positionen von "Auto" angeben ausblenden Balken an. Sie können die folgenden Werte kombinieren: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Versionsschnittstellen der `GetITaskbarList` und `GetITaskbarList3` Methoden.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Erstellt und initialisiert ein Shellelementobjekt aus einem Analysenamen.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
### <a name="parameters"></a>Parameter   
 `pszPath`  
 [in] Ein Zeiger auf einen Anzeigenamen ein.  
  
 `pbc`  
 Ein Zeiger auf einen Bindungskontext, das den Analysevorgang steuert.  
  
 `riid`  
 Ein Verweis auf eine Schnittstellen-ID.  
  
 `ppv`  
 [out] Wenn diese Funktion zurückgibt, enthält den Schnittstellenzeiger, der im angeforderten `riid`. Dies ist in der Regel wird `IShellItem` oder `IShellItem2`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK, wenn erfolgreich; ein Fehlerwert andernfalls.  

