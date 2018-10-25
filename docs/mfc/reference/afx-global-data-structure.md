---
title: AFX_GLOBAL_DATA-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::CleanUp
- AFXGLOBALS/AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawParentBackground
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawTextOnGlass
- AFXGLOBALS/AFX_GLOBAL_DATA::ExcludeTag
- AFXGLOBALS/AFX_GLOBAL_DATA::GetColor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetDirect2dFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetHandCursor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList3
- AFXGLOBALS/AFX_GLOBAL_DATA::GetNonClientMetrics
- AFXGLOBALS/AFX_GLOBAL_DATA::GetShellAutohideBars
- AFXGLOBALS/AFX_GLOBAL_DATA::GetTextHeight
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWICFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWriteFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::Is32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::IsDwmCompositionEnabled
- AFXGLOBALS/AFX_GLOBAL_DATA::IsHighContrastMode
- AFXGLOBALS/AFX_GLOBAL_DATA::OnSettingChange
- AFXGLOBALS/AFX_GLOBAL_DATA::RegisterWindowClass
- AFXGLOBALS/AFX_GLOBAL_DATA::ReleaseTaskBarRefs
- AFXGLOBALS/AFX_GLOBAL_DATA::Resume
- AFXGLOBALS/AFX_GLOBAL_DATA::SetLayeredAttrib
- AFXGLOBALS/AFX_GLOBAL_DATA::SetMenuFont
- AFXGLOBALS/AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateFonts
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateSysColors
- AFXGLOBALS/AFX_GLOBAL_DATA::EnableAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsWindows7
- AFXGLOBALS/AFX_GLOBAL_DATA::clrActiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::clrInactiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseSystemFont
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurHand
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretch
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretchVert
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hiconTool
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
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
ms.openlocfilehash: 935a92beb49d26240aa63f5cfbd4adc9f22d06e8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078010"
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
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) -Methode von Windows bereit.|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Registriert die angegebene MFC-Fensterklasse.|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|Gibt Schnittstellen frei, die durch die Methoden GetITaskbarList und GetITaskbarList3 ermittelt wurden.|
|[AFX_GLOBAL_DATA::Resume](#resume)|Initialisiert die internen Funktionszeiger für den Zugriff auf Methoden, die [Designs und visuelle Stile](/windows/desktop/Controls/visual-styles-overview)in Windows unterstützen.|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) -Methode von Windows bereit.|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Erstellt die angegebene logische Schriftart.|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Erstellt und initialisiert ein Shellelementobjekt aus einem Analysenamen.|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Initialisiert die logischen Schriftarten erneut, die vom Framework verwendet werden.|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Initialisiert die Farben, die Farbtiefe, die Stifte, die Pinsel und die Bilder, die vom Framework verwendet werden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung. Active Accessibility stellt zuverlässige Methoden zum Anzeigen von Informationen über Benutzeroberflächenelemente bereit.|
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.|
|[Iswindowslayersupportavailable](#iswindowslayersupportavailable)|Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.|

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

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

## <a name="bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

Gibt an, ob das Betriebssystem Alphablending unterstützt.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Hinweise

TRUE gibt an, dass Alphablending unterstützt wird; andernfalls "false".

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

*Winkel*<br/>
Der Winkel der Drehung im Uhrzeigersinn in Grad.

*Center*<br/>
Der Punkt, um die gedreht werden soll.

*Matrix*<br/>
Bei der Rückgabe dieser Methode enthält die neue Drehungstransformation. Sie müssen diesen Parameter Speicher zuweisen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn erfolgreich, oder einen Fehlerwert andernfalls.

## <a name="drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground

Zeichnet den Hintergrund des übergeordneten Elements eines Steuerelements im angegebenen Bereich.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Zeiger auf Fenster eines Steuerelements.

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext.

*lpRect*<br/>
[in] Zeiger auf ein Rechteck, das den Bereich zum Zeichnen umschließt. Der Standardwert ist NULL.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

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

*hTheme*<br/>
[in] Handle für den Designdaten eines Fensters, oder NULL. Das Framework verwendet das angegebene Design zum Zeichnen des Texts, wenn dieser Parameter nicht NULL ist und Designs unterstützt werden. Andernfalls verwendet das Framework kein Design zum Zeichnen des Texts.

Verwenden der [OpenThemeData](/windows/desktop/api/uxtheme/nf-uxtheme-openthemedata) Methode, um eine HTHEME zu erstellen.

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext.

*iPartId*<br/>
[in] Der Teil des Steuerelements mit dem gewünschten Text aussehen. Weitere Informationen finden Sie im Artikel [Parts and States](https://msdn.microsoft.com/library/windows/desktop/bb773210)(Teile und Zustände) in der Tabellenspalte „Part“ (Teil). Wenn der Wert 0 lautet, wird der Text in der Standardschriftart oder in einer im Gerätekontext ausgewählten Schriftart gezeichnet.

*iStateId*<br/>
[in] Der Steuerelementzustand, der dem gewünschten Text aussehen. Weitere Informationen finden Sie im Artikel [Parts and States](https://msdn.microsoft.com/library/windows/desktop/bb773210)(Teile und Zustände) in der Tabellenspalte „States“ (Zustände).

*strText*<br/>
[in] Der zu zeichnende Text.

*Rect*<br/>
[in] Die Begrenzung des Bereichs, in dem der angegebene Text gezeichnet wird.

*dwFlags*<br/>
[in] Eine bitweise Kombination (OR) von Flags, die angeben, wie der angegebene Text gezeichnet wird.

Wenn die *hTheme* -Parameter ist `NULL` oder Designs werden nicht unterstützt und aktiviert, die *nFormat* Parameter, der die [CDC:: DrawText](../../mfc/reference/cdc-class.md#drawtext) Methode beschreibt die gültigen Flags. Wenn Themen unterstützt werden, die *DwFlags* Parameter, der die [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex) Methode beschreibt die gültigen Flags.

*nGlowSize*<br/>
[in] Die Größe eines Leuchteffekts, der im Hintergrund gezeichnet wird, bevor der angegebene Text gezeichnet werden soll. Der Standardwert ist 0.

*clrText*<br/>
[in] Die Farbe, in der der angegebene Text gezeichnet wird. Der Standardwert ist die Standardfarbe.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Design wird zum Zeichnen des angegebenen Texts verwendet. andernfalls "false".

### <a name="remarks"></a>Hinweise

Ein Design definiert den visuellen Stil einer Anwendung. Ein Design wird nicht zum Zeichnen des Textes der *hTheme* Parameter NULL ist, oder, wenn die [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex) Methode wird nicht unterstützt, oder wenn [Desktopfenster-Manager](/windows/desktop/dwm/dwm-overview) (DWM) Komposition ist deaktiviert.

### <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[Teile und Zustände](https://msdn.microsoft.com/library/windows/desktop/bb773210)<br/>
[CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[Desktopfenster-Manager](/windows/desktop/dwm/dwm-overview)<br/>
[Aktivieren und Steuern der DWM-Komposition](/windows/desktop/dwm/composition-ovw)

## <a name="enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport

Aktiviert oder deaktiviert Microsoft Active Accessibility-Unterstützung.

```
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] True, um Unterstützung für Barrierefreiheit aktivieren. "False", um Unterstützung für Barrierefreiheit zu deaktivieren. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Active Accessibility ist eine COM-basierte Technologie, die die Weise, wie Programme und gemeinsam mit der Windows-Betriebssystem hilfstechnologie-Produkte verbessert. Es stellt zum Anzeigen von Informationen über Benutzeroberflächenelemente auf zuverlässige Weise bereit. Allerdings ist ein neueres Barrierefreiheitsmodell namens Microsoft-Benutzeroberflächenautomatisierung jetzt verfügbar. Einen Vergleich der beiden Technologien finden Sie unter [Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).

Verwenden der [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) Methode, um zu bestimmen, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.

### <a name="see-also"></a>Siehe auch

[Benutzeroberflächenautomatisierung und Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
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

*strBuffer*<br/>
[in] Ein Puffer von Text.

*lpszTag*<br/>
[in] Der Name eines Paars von öffnenden und schließenden XML-Tags.

*strTag*<br/>
[out] Bei der Rückgabe dieser Methode die *StrTag* -Parameter enthält den Text, der zwischen den öffnenden und schließenden XML Tags, die von benannt sind die *LpszTag* Parameter. Führende oder nachfolgende Leerzeichen werden aus dem Ergebnis gekürzt.

*bIsCharsList*<br/>
[in] "True" Convert-Symbole für Escapezeichen in der *StrTag* Parameter in die eigentliche Escapezeichen; "False" nicht zum Durchführen der Konvertierung. Der Standardwert ist "false". Weitere Informationen finden Sie in den Hinweisen.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Ein XML-Tagpaar besteht aus mit dem Namen öffnenden und schließenden Tags, die den Beginn und Ende einer Ausführung des Texts in den angegebenen Puffer angeben. Die *StrBuffer* Parameter gibt den Puffer und die *LpszTag* Parameter gibt den Namen der XML-Tags.

Verwenden Sie die Symbole in der folgenden Tabelle, um die Codierung eines Satzes von Escapezeichen in den angegebenen Puffer. Geben Sie "true" für die *bIsCharsList* Parameter, um die Symbole in konvertieren die *StrTag* Parameter in der tatsächlichen Escape-Zeichen. Die folgende Tabelle wird die [_T()](../../c-runtime-library/data-type-mappings.md) Makro, geben Sie das Symbol und Zeichenfolgen mit Escapezeichen versehen.

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

*nColor*<br/>
[in] Ein Wert, der ein Benutzeroberflächenelement angibt, dessen Farbe abgerufen wird. Eine Liste der gültigen Werte finden Sie unter den *nIndex* Parameter, der die [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) Methode.

### <a name="return-value"></a>Rückgabewert

Die RGB-Farbwert, der das angegebene Benutzeroberflächenelement. Weitere Informationen finden Sie in den Hinweisen.

### <a name="remarks"></a>Hinweise

Wenn die *nColor* Parameter liegt außerhalb des Bereichs, der Rückgabewert ist 0 (null). Da 0 (null), die auch einen gültigen RGB-Wert ist, können nicht Sie diese Methode verwenden, um zu bestimmen, ob eine Systemfarbe vom aktuellen Betriebssystem unterstützt wird. Verwenden Sie stattdessen die [GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush) -Methode, die NULL zurückgibt, wenn die Farbe nicht unterstützt wird.

### <a name="see-also"></a>Siehe auch

[GetSysColor-Funktion](/windows/desktop/api/winuser/nf-winuser-getsyscolor)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush)

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory

Gibt einen Zeiger auf die ID2D1Factory-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ID2D1Factory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine D2D-Unterstützung.

## <a name="gethandcursor"></a>  AFX_GLOBAL_DATA::GetHandCursor

Ruft den vordefinierten Cursor, der eine Hand ähnelt und dessen Bezeichner idc_hand, ab.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Rückgabewert

Das Handle des den Handcursor.

## <a name="getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics

Ruft die Metriken ab, die dem Nichtclientbereich von nicht minimierten Fenstern zugeordnet sind.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>Parameter

*Info*<br/>
[in, out] Ein [NONCLIENTMETRICS](https://msdn.microsoft.com/library/windows/desktop/ff729175) -Struktur, die skalierbare Metriken zugeordneten nicht-Clientbereichs eines nicht minimierten Fensters enthält.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="see-also"></a>Siehe auch

[NONCLIENTMETRICS-Struktur](https://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight

Ruft die Höhe von Textzeichen in der aktuellen Schriftart ab.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parameter

*bHorz*<br/>
[in] TRUE, die Höhe der Zeichen abgerufen, wenn Text horizontal ausgeführt wird. "False", um die Höhe der Zeichen abzurufen, wenn der Text vertikal verläuft. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Die Höhe der aktuellen Schriftart an, die auf die Unterlänge der Ascender gemessen wird.

## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory

Gibt einen Zeiger auf die IWICImagingFactory-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf IWICImagingFactory-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine WIC-Unterstützung.

## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory

Gibt einen Zeiger auf die "IDWriteFactory"-Schnittstelle, die in den globalen Daten gespeichert sind. Wenn die Schnittstelle nicht initialisiert wurde, wird sie mit den Standardparametern erstellt.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf "IDWriteFactory"-Schnittstelle, wenn die Erstellung einer Factory erfolgreich war, oder NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem keine Unterstützung von DirectWrite.

## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D

Initialisiert D2D, DirectWrite und WIC-Factorys. Rufen Sie diese Methode vor der Initialisierung des Hauptfensters auf.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Parameter

*d2dFactoryType*<br/>
Das Threadingmodell der D2D-Factory und die Ressourcen erstellt.

*writeFactoryType*<br/>
Ein Wert, der angibt, ob das Factoryobjekt für den Schreibzugriff freigegeben oder isoliert werden

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Factorys initialisiert, "false" –, andernfalls wurden

## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons

Gibt an, ob vordefinierte 32-Bit-Symbole unterstützt werden.

```
BOOL Is32BitIcons() const;

```

### <a name="return-value"></a>Rückgabewert

True, wenn Sie vordefinierte 32-Bit-Symbole unterstützt werden. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode gibt TRUE zurück, wenn das Framework integrierte 32-Bit-Symbole unterstützt und wenn das Betriebssystem 16 Bits pro Pixel oder mehr unterstützt und Bilder mit hohem Kontrast nicht angezeigt werden.

## <a name="isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport

Gibt an, ob Microsoft Active Accessibility-Unterstützung aktiviert ist.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn Accessibility-Unterstützung aktiviert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Microsoft Active Accessibility war die vorherige Lösung zum Herstellen von Anwendungen zugegriffen werden kann. Microsoft-Benutzeroberflächenautomatisierung ist das neue Zugriffsmodell für Microsoft Windows und dient zum Erfüllen der Anforderungen von Hilfstechnologieprodukten und automatisierte TestTools.

Verwenden der [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) zu aktivieren oder deaktivieren Sie die Active Accessibility-Unterstützung.

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

Stellt eine einfache Möglichkeit zum Aufrufen der [DwmIsCompositionEnabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) -Methode von Windows bereit.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn [Desktopfenster-Manager](/windows/desktop/dwm/dwm-overview) (DWM) Komposition ist aktiviert; andernfalls "false".

### <a name="see-also"></a>Siehe auch

[Desktopfenster-Manager](/windows/desktop/dwm/dwm-overview)<br/>
[Aktivieren und Steuern der DWM-Komposition](/windows/desktop/dwm/composition-ovw)

## <a name="ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode

Gibt an, ob Bilder nur mit hohem Kontrast angezeigt werden.
```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn Images derzeit im Modus für hohe Kontraste von Schwarz oder Weiß angezeigt werden. andernfalls "false".

### <a name="remarks"></a>Hinweise

Hohen Kontrast Schwarz der Lichtquelle zugewandte Seiten sind weiß und des Hintergrunds Schwarz. Hohen Kontrast weiß Schwarz sind, der Lichtquelle zugewandte Seiten aus, und der Hintergrund weiß ist.

## <a name="iswindowslayersupportavailable"></a> Iswindowslayersupportavailable

Gibt an, ob das Betriebssystem überlappende Fenster unterstützt.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn überlappende Fenster unterstützt werden. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn überlappende Fenster unterstützt werden, *intelligentes Andocken* Marker verwenden überlappende Fenster.

## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

Gibt an, ob das Framework vordefinierte 32-Bit-Farbsymbole oder Symbole mit einer niedrigeren Auflösung verwendet.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Hinweise

"True" gibt an, dass das Framework die 32-Bit-Farbsymbole verwenden. FALSE gibt an, vom niedrigere Auflösung Symbole. Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member auf "true".

Dieses Element muss beim Start der Anwendung festgelegt werden.

## <a name="m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont

Gibt an, ob eine Systemschriftart für Menüs, Symbolleisten und Menübänder verwendet wird.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Hinweise

"True" gibt an, dass eine Systemschriftart; andernfalls "false". Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member auf "false".

Testen dieses Element ist nicht die einzige Möglichkeit für das Framework die Schriftart zu ermitteln, verwenden. Die `AFX_GLOBAL_DATA::UpdateFonts` Methode testet auch die standardzuordnungen sowie die alternativen Schriftarten, um zu bestimmen, welche formatierungsvisualisierungen für Menüs, Symbolleisten und Menübänder anzuwendenden verfügbar sind.

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

Gibt den Offset der am weitesten links stehende automatisch im Hintergrund-Symbolleiste auf die linke Seite des Balkens andocken.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Hinweise

Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member auf 4 Pixel.

## <a name="m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

Gibt die Lücke zwischen Symbolleisten zum automatischen Ausblenden an.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Hinweise

Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member auf 14 Pixel.

## <a name="m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Gibt die Stärke des Rahmens ziehen, die verwendet wird, um den angedockten Zustand anzugeben.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Hinweise

Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member um 3 Pixel.

## <a name="m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

Gibt die Stärke des Rahmens ziehen, die mit dem den unverankerten Zustand angegeben.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Hinweise

Die `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Konstruktor initialisiert dieses Member auf 4 Pixel.

## <a name="onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange

Erkennt den aktuellen Zustand der Funktionen zum automatischen Ausblenden der Menüanimation und Taskleisten auf dem Desktop.

```
void OnSettingChange();
```

### <a name="remarks"></a>Hinweise

Diese Methode legt die Framework-Variablen in den Zustand bestimmter Attribute der Desktop des Benutzers. Diese Methode erkennt den aktuellen Status der Menüanimation, Menü ausblenden und Taskleiste und automatisch im Hintergrund-Funktionen.

## <a name="registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass

Registriert die angegebene MFC-Fensterklasse.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>Parameter

*lpszClassNamePrefix*<br/>
[in] Der Name der Fensterklasse registrieren.

### <a name="return-value"></a>Rückgabewert

Der qualifizierte Name der registrierten Klasse, wenn diese Methode erfolgreich ist; andernfalls ein [Ressourcenausnahme](exception-processing.md#afxthrowresourceexception).

### <a name="remarks"></a>Hinweise

Der Rückgabewert ist ein Doppelpunkt getrennte Liste von der *LpszClassNamePrefix* Parameterzeichenfolge und die hexadezimale Textdarstellungen der Handles von der aktuellen Anwendungsinstanz ist die Anwendung-Cursor, der es der Pfeil ist Cursor, dessen Bezeichner IDC_ARROW ist; und der Hintergrundpinsel. Weitere Informationen zum Registrieren von MFC-Klassen finden Sie unter [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).

### <a name="see-also"></a>Siehe auch

[AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a> AFX_GLOBAL_DATA::Resume

Initialisiert die internen Funktionszeiger für den Zugriff auf Methoden, die Windows-Designs und visuelle Stile unterstützen.

```
BOOL Resume();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls "false". Im Debugmodus befindet bestätigt diese Methode auf, wenn diese Methode nicht erfolgreich ist.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn das Framework erhält die [WM_POWERBROADCAST](/windows/desktop/Power/wm-powerbroadcast) Nachricht.

## <a name="setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib

Stellt eine einfache Möglichkeit zum Aufrufen der [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) -Methode von Windows bereit.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parameter

*HWND*<br/>
[in] Handle für das überlappende Fenster.

*crKey*<br/>
[in] Die der Transparenzfarbe zu finden, die die [Desktopfenster-Manager](/windows/desktop/dwm/dwm-overview) verwendet, um das überlappende Fenster zu erstellen.

*bAlpha*<br/>
[in] Der alpha-Wert, der verwendet wird, um die Deckkraft des überlappenden Fensters zu beschreiben.

*dwFlags*<br/>
[in] Eine bitweise Kombination (OR) von Flags, die angeben, welche Parameter der Methode verwenden. Geben Sie LWA_COLORKEY verwenden die *CrKey* Parameter als die der Transparenzfarbe. Geben Sie LWA_ALPHA verwenden die *bAlpha* Parameter, um die Durchlässigkeit des überlappenden Fensters bestimmt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="see-also"></a>Siehe auch

[COLORREF](/windows/desktop/gdi/colorref)<br/>
[SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes)

## <a name="setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont

Erstellt die angegebene logische Schriftart.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*lpLogFont*<br/>
[in] Zeiger auf eine Struktur, die Attribute einer Schriftart enthält.

*bHorz*<br/>
[in] True, um anzugeben, dass der Text horizontal ausgeführt wird. "False", um anzugeben, dass der Text vertikal verläuft.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls "false". Im Debugmodus befindet bestätigt diese Methode auf, wenn diese Methode nicht erfolgreich ist.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt einen horizontalen normalen Schrift, einen unterstrichenen Schriftschnitt, und verwendet, fett formatierter Schrift, die im standardmäßigen Menüelemente. Diese Methode erstellt optional eine reguläre-Schriftart. Weitere Informationen zu logischen Schriftarten, finden Sie unter [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).

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

Ein Zeiger auf die `ITaskbarList` Schnittstelle, wenn die Erstellung einer Aufgabe Leiste List-Objekt erfolgreich ist. NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem Windows 7 unterschreitet.

## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3

Erstellt und speichert Sie in den globalen Daten einen Zeiger auf die `ITaskBarList3` Schnittstelle.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `ITaskbarList3` Schnittstelle, wenn die Erstellung einer Aufgabe Leiste List-Objekt erfolgreich ist. NULL, wenn die Erstellung ein Fehler auftritt oder das aktuelle Betriebssystem Windows 7 unterschreitet.

## <a name="getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars

Bestimmt Positionen von Leisten zum automatischen Ausblenden einer Shell.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger Wert mit codierten Flags, die angeben, die Positionen von "Auto" ausblenden Balken. Sie können die folgenden Werte kombinieren: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.

## <a name="releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs

Gibt Schnittstellen die `GetITaskbarList` und `GetITaskbarList3` Methoden.

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

*pszPath*<br/>
[in] Ein Zeiger auf einen Anzeigenamen ein.

*pbc*<br/>
Ein Zeiger auf einen Bindungskontext, der den Analysevorgang steuert.

*riid*<br/>
Ein Verweis auf eine Schnittstellen-ID.

*ppv*<br/>
[out] Wenn diese Funktion zurückkehrt, enthält die im angeforderten Schnittstellenzeiger *Riid*. In der Regel wird dies `IShellItem` oder `IShellItem2`.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn erfolgreich; einen Fehlerwert, die andernfalls.

