---
title: CPropertySheet-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, tabs
- CPropertySheet class
- property sheets, CPropertySheet class
- tab dialog boxes
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
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
ms.openlocfilehash: 41ad7b598016b1fa04aa7ca63575f853195b5359
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertysheet-class"></a>CPropertySheet-Klasse
Stellt Eigenschaftenblätter dar, auch als "Dialogfelder im Registerformat" bezeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Erstellt ein `CPropertySheet`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertySheet::AddPage](#addpage)|Fügt dem Eigenschaftsblatt eine Seite hinzu.|  
|[CPropertySheet::Construct](#construct)|Erstellt ein `CPropertySheet`-Objekt.|  
|[CPropertySheet::Create](#create)|Zeigt ein nicht modales Eigenschaftenblatt.|  
|[CPropertySheet:: DoModal](#domodal)|Zeigt ein modales Eigenschaftenblatt.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Gibt an, ob es sich bei Eigenschaftenblatt gestapelte oder einen Scrollcursor Registerkarten verwendet.|  
|[CPropertySheet::EndDialog](#enddialog)|Das Eigenschaftenblatt wird beendet.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Ruft den Index der aktiven Seite der Eigenschaftenseite ab.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Gibt das aktive Seite zurück.|  
|[CPropertySheet::GetPage](#getpage)|Ruft einen Zeiger auf die angegebene Seite ab.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten im Eigenschaftenblatt.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Ruft den Index der angegebenen Seite des Eigenschaftenblatts ab.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Ruft einen Zeiger auf ein Registerkarten-Steuerelement ab.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|Überschreiben Sie, um die Initialisierung einer Eigenschaftenblatt zu erweitern.|  
|[CPropertySheet::PressButton](#pressbutton)|Simuliert die Auswahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.|  
|[CPropertySheet::RemovePage](#removepage)|Entfernt eine Seite aus dem Eigenschaftenblatt.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Das Objekt für die aktive Seite festgelegt programmgesteuert.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Legt den Text für die Schaltfläche "Fertig stellen".|  
|[CPropertySheet::SetTitle](#settitle)|Der Titel der Eigenschaftenseite festgelegt.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Die Assistentenschaltflächen aktiviert.|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|Die Assistentenmodus aktiviert.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) Struktur. Bietet Zugriff auf grundlegende Eigenschaft Stylesheet-Parameter.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Eigenschaftenblatt besteht aus einem `CPropertySheet` -Objekt und einem oder mehreren [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte. Das Framework zeigt ein Eigenschaftenblatt als Fenster mit einer Registerkartenindizes und einen Bereich, der die derzeit ausgewählte Seite enthält. Der Benutzer navigiert zu einer bestimmten Seite mithilfe der entsprechenden Registerkarte.  
  
 `CPropertySheet`bietet Unterstützung für das erweiterte [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) Struktur eingeführten [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] und Windows NT 2000. Die Struktur enthält zusätzliche Kennzeichen und Member, die mithilfe einer Bitmap im Hintergrund "Wasserzeichens" unterstützen.  
  
 Um diese neuen Bilder automatisch in die Eigenschaftenblattobjekt anzuzeigen, übergeben Sie gültige Werte für die Bitmap und Palette Bilder im Aufruf von [CPropertySheet::Construct](#construct) oder [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Obwohl `CPropertySheet` wird nicht abgeleitet [CDialog](../../mfc/reference/cdialog-class.md), Verwalten von eine `CPropertySheet` Objekt ist, wie etwa die Verwaltung ein `CDialog` Objekt. Erstellen eines Eigenschaftenblatts erfordert z. B. zweiteiligen Konstruktion: Rufen Sie den Konstruktor aus, und rufen dann [DoModal](#domodal) für ein modales Eigenschaftenblatt oder [erstellen](#create) für ein nicht modales Eigenschaftenblatt. `CPropertySheet`verfügt über zwei Arten von Konstruktoren: [CPropertySheet::Construct](#construct) und [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Bei der Erstellung einer `CPropertySheet` Objekt einige [Fensterstile](../../mfc/reference/window-styles.md) kann dazu führen, dass eine nicht abgefangene Ausnahme auftritt. Dadurch wird aus dem System, bei dem Versuch, den Stil des Eigenschaftenblatts zu ändern, bevor das Blatt erstellt wird. Um diese Ausnahme zu vermeiden, stellen Sie sicher, dass Sie die folgenden Formate festlegen, bei der Erstellung Ihrer `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Die folgenden Formate sind optional, und führt nicht dazu, dass die abgefangene Ausnahme:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Alle anderen `Window Styles` sind nicht zulässig, und Sie sollten sie nicht aktivieren.  
  
 Austauschen von Daten zwischen einer `CPropertySheet` -Objekt und ein externes Objekt ähnelt Austauschen von Daten mit einer `CDialog` Objekt. Der wichtige Unterschied besteht darin, dass die Einstellungen eines Eigenschaftenblatts Membervariablen des in der Regel sind die `CPropertyPage` Objekte anstatt der `CPropertySheet` Objekt selbst.  
  
 Sie können ein Dialogfeld im Registerformat bezeichnet einen Assistenten, besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, die den Benutzer durch die Schritte eines Vorgangs, z. B. ein Gerät einrichten oder Erstellen eines Magazins erstellen. Eine Assistententyp Registerkarte im Dialogfeld Eigenschaftenseiten keine Registerkarten, und nur eine Eigenschaftenseite zu einem Zeitpunkt sichtbar ist. Auch, anstatt **OK** und **jetzt** Schaltflächen ein Assistenten-Registerkarte verfügt über eine **zurück** Schaltfläche ein **Weiter** oder **Fertig stellen** Schaltfläche eine **Abbrechen** Schaltfläche und ein **Hilfe** Schaltfläche.  
  
 Um ein Dialogfeld des Assistenten-Typ zu erstellen, führen Sie die gleichen Schritte, die Sie ausführen müssen, um ein standard Eigenschaftenblatt Aufruf jedoch erstellen [SetWizardMode](#setwizardmode) vor dem Aufruf von [DoModal](#domodal). Rufen Sie zum Aktivieren der Wizard-Schaltflächen [SetWizardButtons](#setwizardbuttons), mithilfe von Flags, die ihre Funktion und Darstellung anpassen. So aktivieren Sie die **Fertig stellen** Schaltfläche, rufen Sie [SetFinishText](#setfinishtext) sobald der Benutzer eine Aktion auf der letzten Seite des Assistenten.  
  
 Weitere Informationen zur Verwendung von `CPropertySheet` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md). Darüber hinaus finden Sie in Knowledge Base-Artikel Q146916: So wird's gemacht: Erstellen einer nicht modaler CPropertySheet mit Standardschaltflächen und Artikel Q300606: So wird's gemacht: Entwerfen mit veränderbarer Größe MFC Eigenschaftenblätter.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="addpage"></a>CPropertySheet::AddPage  
 Fügt die angegebene Seite mit der Registerkarte ganz rechts im Eigenschaftenfenster an.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Verweist auf das Zeichenblatt, um das Eigenschaftenblatt hinzugefügt werden. Nicht **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Fügen Sie Seiten hinzu, das Eigenschaftenblatt in der links-nach-rechts-Reihenfolge angezeigt werden sollen.  
  
 `AddPage`Fügt der [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) -Objekt die `CPropertySheet` Objekt der Liste der Seiten, jedoch selbst nicht im Fenster für die Seite erstellt. Das Framework verschiebt Erstellung im Fenster für die Seite, bis der Benutzer die Seite auswählt.  
  
 Beim Hinzufügen einer Eigenschaftenseite mithilfe `AddPage`, `CPropertySheet` ist das übergeordnete Element der `CPropertyPage`. Rufen Sie für den Zugriff auf das Eigenschaftenfenster auf der Eigenschaftenseite [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Es ist nicht notwendig, warten, bis die Erstellung des Fensters für das-Eigenschaft aufrufen `AddPage`. Normalerweise rufen Sie `AddPage` vor dem Aufruf von [DoModal](#domodal) oder [erstellen](#create).  
  
 Wenn Sie aufrufen `AddPage` die Registerkartenreihe wider nach dem Anzeigen der Eigenschaftenseite, die neu hinzugefügte Seite.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#129;](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="construct"></a>CPropertySheet::Construct  
 Erstellt ein `CPropertySheet`-Objekt.  
  
```  
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCaption`  
 ID der Beschriftung für das Eigenschaftenblatt verwendet werden.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster der Eigenschaftenseite. Wenn **NULL**, das übergeordnete Fenster werden im Hauptfenster der Anwendung.  
  
 `iSelectPage`  
 Der Index der Seite, die anfänglich ganz oben stehen. Standardmäßig ist die erste Seite der Tabelle hinzugefügt.  
  
 `pszCaption`  
 Zeiger auf eine Zeichenfolge mit der Beschriftung für das Eigenschaftenblatt verwendet werden. Nicht **NULL**.  
  
 `hbmWatermark`  
 Handle für das Wasserzeichen Bitmap der Eigenschaftenseite.  
  
 `hpalWatermark`  
 Handle für die Palette der Bitmap Wasserzeichen und/oder Header-Bitmap.  
  
 `hbmHeader`  
 Handle für die Bitmap Header der Seite.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, wenn die Klasse Konstruktoren nicht bereits aufgerufen wurde. Rufen Sie z. B. `Construct` beim Deklarieren oder Zuordnen von Arrays für `CPropertySheet` Objekte. Bei Arrays, rufen Sie `Construct` für jedes Element im Array.  
  
 Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Zeichenfolge, die im ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert.  
  
 Sie können bei Verwendung der dritten oder vierten Prototypen von Wasserzeichen und/oder Headerparameter Bilder automatisch anzeigen `Construct`oben aufgeführten und übergeben Sie gültige Werte für die `hbmWatermark`, `hpalWatermark`, und/oder `hbmHeader` Parameter.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, unter welchen Sie Umständen aufgerufen und `Construct`.  
  
 [!code-cpp[NVC_MFCDocView&#130;](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="cpropertysheet"></a>CPropertySheet::CPropertySheet  
 Erstellt ein `CPropertySheet`-Objekt.  
  
```  
CPropertySheet();

 
explicit CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
explicit CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCaption`  
 ID der Beschriftung für das Eigenschaftenblatt verwendet werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster der Eigenschaftenseite. Wenn **NULL**, das übergeordnete Fenster werden im Hauptfenster der Anwendung.  
  
 `iSelectPage`  
 Der Index der Seite, die anfänglich ganz oben stehen. Standardmäßig ist die erste Seite der Tabelle hinzugefügt.  
  
 `pszCaption`  
 Zeigt auf eine Zeichenfolge mit der Beschriftung für das Eigenschaftenblatt verwendet werden. Nicht **NULL**.  
  
 `hbmWatermark`  
 Ein Handle für das Hintergrundbild des Eigenschaftenblatts.  
  
 `hpalWatermark`  
 Ein Handle für die Palette der Bitmap Wasserzeichen und/oder Header-Bitmap.  
  
 `hbmHeader`  
 Ein Handle für die Bitmap Header der Seite.  
  
### <a name="remarks"></a>Hinweise  
 Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Zeichenfolge, die im ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert.  
  
 Wenn Sie mehrere Parameter (z. B., wenn Sie ein Array verwenden), verwenden [erstellen](#construct) anstelle von `CPropertySheet`.  
  
 Sie können bei Verwendung der dritten oder vierten Prototypen von Wasserzeichen und/oder Headerparameter Bilder automatisch anzeigen `CPropertySheet`oben, und übergeben Sie gültige Werte für die `hbmWatermark`, `hpalWatermark`, und/oder `hbmHeader` Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#131;](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>CPropertySheet::Create  
 Zeigt ein nicht modales Eigenschaftenblatt.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)–1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster. Wenn **NULL**, übergeordnete ist der Desktop.  
  
 `dwStyle`  
 Fensterstile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate, finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 `dwExStyle`  
 Erweiterte Fensterstile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate, finden Sie unter [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md)  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Aufruf von **erstellen** innerhalb des Konstruktors kann, oder Sie können es aufrufen, nachdem der Konstruktor aufgerufen wird.  
  
 Das Standardformat, übergeben Sie –&1; als ausgedrückt `dwStyle`, handelt es sich tatsächlich **WS_SYSMENU |** `WS_POPUP`**| WS_CAPTION | DS_MODALFRAME | DS_CONTEXTHELP | WS_VISIBLE**. Die Standardeinstellung erweiterten Fensterstil, übergeben Sie 0 als ausgedrückt `dwExStyle`, handelt es sich tatsächlich **WS_EX_DLGMODALFRAME**.  
  
 Die **erstellen** -Memberfunktion zurückgegeben wird, unmittelbar nach dem Erstellen der Eigenschaftenblatt. Um das Eigenschaftenblatt zu löschen, rufen Sie [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Nicht modale Eigenschaftenblätter angezeigt, die mit einem Aufruf von **erstellen** keinen OK, Abbrechen, übernehmen und Hilfe-Schaltflächen wie modale Eigenschaftenblätter. Gewünschte Schaltflächen müssen vom Benutzer erstellt werden.  
  
 Um ein modales Eigenschaftsblatt anzuzeigen, rufen [DoModal](#domodal) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#132;](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#133;](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>CPropertySheet:: DoModal  
 Zeigt ein modales Eigenschaftenblatt.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `IDOK`oder `IDCANCEL` , wenn die Funktion erfolgreich war, andernfalls 0 oder-1 wurde. Wenn das Eigenschaftenfenster als Assistent eingerichtet wurde (siehe [SetWizardMode](#setwizardmode)), `DoModal` gibt `ID_WIZFINISH` oder `IDCANCEL`.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert entspricht der ID des Steuerelements, das das Eigenschaftenblatt zu schließen. Nachdem die Funktion zurückgibt, werden wurde das Eigenschaftenfenster und alle Seiten für Windows zerstört. Die Objekte selbst bleibt dabei erhalten. Normalerweise rufen Sie Daten aus der [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte nach `DoModal` gibt `IDOK`.  
  
 Rufen Sie zum Anzeigen eines nicht modalen Eigenschaftenblatts [erstellen](#create) stattdessen.  
  
 Wenn auf einer Eigenschaftenseite aus den entsprechenden Dialog-Ressource erstellt wird, kann dies eine nicht abgefangene Ausnahme führen. Dadurch wird auf der Eigenschaftenseite die Formatvorlage der Dialogfeldressource in den gewünschten Stil geändert wird, bevor die Seite erstellt wird. Da Ressourcen im Allgemeinen schreibgeschützt sind, wird dadurch eine Ausnahme aus. Das System die Ausnahme behandelt und erstellt eine Kopie der geänderten Ressource. Die abgefangene Ausnahme kann daher ignoriert werden.  
  
> [!NOTE]
>  Diese Ausnahme muss vom Betriebssystem behandelt werden, wenn Sie mit dem Modell asynchrone Ausnahmebehandlung kompilieren. Weitere Informationen über die Modelle für die Ausnahmebehandlung finden Sie unter [/EH (Exception Handling Model)](../../build/reference/eh-exception-handling-model.md). Umschließen Sie in diesem Fall keine Aufrufe von `CPropertySheet::DoModal` mit einem C++-Try-Catch-Block in dem Catch alle Ausnahmen verarbeitet, z. B. `catch (...)`. Dieser Block behandelt die Ausnahme, die für das Betriebssystem und die Ursache zu unvorhersehbarem Verhalten vorgesehen. Allerdings können Sie problemlos verwenden C++-Ausnahmebehandlung mit bestimmte Ausnahmetypen oder strukturierte Ausnahmebehandlung, in dem die Verletzung Ausnahme über an das Betriebssystem übergeben.  
  
 Um zu vermeiden, generiert diese Ausnahme der ersten Chance, Sie können manuell sicherstellen, dass das Eigenschaftenblatt der richtige hat [Fensterstile](../../mfc/reference/window-styles.md). Sie müssen die folgenden Formate für ein Eigenschaftenblatt festlegen:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Die folgenden optionalen Stile können Sie ohne eine nicht abgefangene Ausnahme:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Deaktivieren Sie alle anderen Arten von Windows, da sie nicht mit Eigenschaftenblättern kompatibel sind. Diese Empfehlung gilt nicht für erweiterte Stile. Dieser standard Stile entsprechend festgelegt wird sichergestellt, dass das Eigenschaftenfenster muss nicht geändert werden und verhindert, dass die abgefangene Ausnahme generiert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::AddPage](#addpage).  
  
##  <a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs  
 Gibt an, ob Zeilen mit Registerkarten in einem Eigenschaftenblatt Stapeln.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Parameter  
 `bStacked`  
 Gibt an, ob es sich bei gestapelte Registerkarten im Eigenschaftenblatt aktiviert sind. Gestapelte Zeilen von Tags zu deaktivieren, indem `bStacked` auf **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Verfügt ein Eigenschaftenblatt weitere Registerkarten als in einer einzelnen Zeile in der Breite des Eigenschaftenblatts, passen werden die Registerkarten standardmäßig in mehreren Reihen gestapelt. Rufen Sie zum Verwenden von fortlaufenden Registerkarten anstelle von Stapeln Registerkarten `EnableStackedTabs` mit `bStacked` festgelegt **FALSE** vor dem Aufruf von [DoModal](#domodal) oder [erstellen](#create).  
  
 Sie müssen Aufrufen `EnableStackedTabs` beim Erstellen eines modalen oder eines nicht modalen Eigenschaftenblatts. Integrieren Sie dieses Format in ein `CPropertySheet`-abgeleiteten Klasse schreiben Sie einen Meldungshandler für `WM_CREATE`. In der überschriebenen Version der [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), rufen Sie **EnableStackedTabs (FALSE)** vor der Implementierung der Basisklasse aufrufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#134;](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>CPropertySheet::EndDialog  
 Das Eigenschaftenblatt wird beendet.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Parameter  
 *nEndID*  
 Bezeichner, der als Rückgabewert der Eigenschaftenseite verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn die OK, Abbrechen oder Schließen Schaltfläche gedrückt wird. Rufen Sie, dass diese Member-Funktion, wenn ein Ereignis auftritt, das Eigenschaftenfenster geschlossen werden soll.  
  
 Diese Memberfunktion ist nur mit einem modalen Dialogfeld verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="getactiveindex"></a>CPropertySheet::GetActiveIndex  
 Ruft die Indexnummer des Blatt Eigenschaftenfenster die aktive Seite ab und verwendet dann die zurückgegebenen Indexnummer als Parameter für `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Indexnummer der aktiven Seite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="getactivepage"></a>CPropertySheet::GetActivePage  
 Ruft die Eigenschaftenblatt Fenster aktive Seite ab.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die aktive Seite.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Member-Funktion, um bestimmte Aktionen für die aktive Seite ausführen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#135;](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>CPropertySheet::GetPage  
 Gibt einen Zeiger auf die angegebene Seite in diesem Eigenschaftenblatt.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPage`  
 Der Index der gewünschten Seite beginnend mit 0. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die Seite, entspricht der `nPage` Parameter.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpagecount"></a>CPropertySheet::GetPageCount  
 Bestimmt die Anzahl der Seiten, die derzeit im Eigenschaftenblatt.  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Seiten im Eigenschaftenblatt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpageindex"></a>CPropertySheet::GetPageIndex  
 Ruft die Indexnummer der angegebenen Seite im Eigenschaftenfenster an.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Zeigt auf die Seite mit dem Index gefunden werden. Nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Indexnummer der Seite.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie z. B. `GetPageIndex` den Seitenindex abrufen, um verwenden [SetActivePage](#setactivepage) oder [GetPage](#getpage).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="gettabcontrol"></a>CPropertySheet::GetTabControl  
 Ruft einen Zeiger auf ein Registerkarten-Steuerelement zu einer Aktion für das Registerkarten-Steuerelement (d. h. keine der APIs im [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie beispielsweise diese Memberfunktion auf, wenn Sie während der Initialisierung Bitmaps auf den Registerkarten hinzufügen möchten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#136;](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>CPropertySheet::m_psh  
 Eine Struktur, deren Mitglieder die Merkmale des speichern [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Hinweise  
 Diese Struktur verwenden, um die Darstellung der Eigenschaftenseite zu initialisieren, sobald es erstellt wurde, jedoch vor der Anzeige mit den [DoModal](#domodal) Member-Funktion. Legen Sie z. B. die `dwSize` Mitglied `m_psh` der Größe Eigenschaftenblatt haben sollen.  
  
 Weitere Informationen zu dieser Struktur, die eine Auflistung von Membern, einschließlich finden Sie unter **PROPSHEETHEADER** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#143;](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>CPropertySheet::MapDialogRect  
 Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält Koordinaten konvertiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet, die durchschnittliche Breite und Höhe der Zeichen in der Schriftart für Text im Dialogfeld angegeben. Eine horizontale Einheit ist ein Viertel der Einheit Base Breite im Dialogfeld, und eine vertikale Einheit ist ein Achtel der Dialogfeld-Basis Höhe Einheit.  
  
 Die [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows-Funktion gibt Informationen zur Datenbankgröße für die Systemschriftart, aber Sie können eine andere Schriftart für jede Eigenschaftenblatt angeben, wenn Sie verwenden die **DS_SETFONT** Stil in der Ressourcendefinition Datei. Die [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) in beschriebenen Windows-Funktion die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], verwendet die entsprechende Schriftart für das Dialogfeld zu öffnen.  
  
 Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten im `lpRect` mit Bildschirm Einheiten (Pixel), damit das Rechteck zum Erstellen eines Dialogfelds oder Positionieren Sie ein Steuerelement in einem Feld verwendet werden kann.  
  
##  <a name="oninitdialog"></a>CPropertySheet::OnInitDialog  
 Außerkraftsetzungen, um die Initialisierung einer Eigenschaftenblatt zu erweitern.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Eigenschaftenfenster festgelegt. Wenn **OnInitDialog** gibt einen Wert ungleich NULL, Windows legt den Eingabefokus auf das erste Steuerelement im Eigenschaftenblatt. Die Anwendung kann 0 zurückgeben, nur dann, wenn sie den Eingabefokus auf eines der Steuerelemente im Eigenschaftenblatt explizit festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist als Reaktion auf die **WM_INITDIALOG** Nachricht. Diese Nachricht wird gesendet, während das Eigenschaftenblatt der [erstellen](#create) oder [DoModal](#domodal) Aufrufe, die auftreten, unmittelbar bevor das Eigenschaftenblatt angezeigt wird.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn spezielle Verarbeitung bei der Initialisierung der Eigenschaftenblatt müssen. In der überschriebenen Version, rufen Sie zunächst die Basisklasse `OnInitDialog` aber ihren Rückgabewert ignorieren. Normalerweise wird nun wieder **TRUE** Ihrer überschriebene Member-Funktion.  
  
 Sie benötigen keine Meldungszuordnungseintrags für diese Member-Funktion.  
  
##  <a name="pressbutton"></a>CPropertySheet::PressButton  
 Simuliert die Auswahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Parameter  
 `nButton`  
 nButton: identifiziert die Schaltfläche gedrückt. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **PSBTN_BACK** die zurück-Taste auswählt.  
  
- **PSBTN_NEXT** wählt die Schaltfläche "Weiter".  
  
- **PSBTN_FINISH** wählt die Schaltfläche Fertig stellen.  
  
- **PSBTN_OK** wählt die Schaltfläche OK.  
  
- **PSBTN_APPLYNOW** wählt die Schaltfläche jetzt anwenden.  
  
- **Von PSBTN_CANCEL zurückgegeben** wählt die Schaltfläche "Abbrechen".  
  
- **PSBTN_HELP** wählt die Schaltfläche "Hilfe".  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) für Weitere Informationen über die Windows SDK-Pressbutton-Meldung.  
  
 Ein Aufruf von `PressButton` sendet keine der [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Benachrichtigung auf einer Eigenschaftenseite für das Framework. Um diese Benachrichtigung zu senden, ruft [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#137;](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>CPropertySheet::RemovePage  
 Entfernt eine Seite aus dem Eigenschaftenblatt, und das zugeordnete Fenster zerstört.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Zeigt auf die Seite aus dem Eigenschaftenblatt entfernt werden soll. Nicht `NULL`.  
  
 `nPage`  
 Der Index der Seite entfernt werden soll. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.  
  
### <a name="remarks"></a>Hinweise  
 Die [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekt selbst wird nicht zerstört, bis der Besitzer der `CPropertySheet` Fenster wird geschlossen.  
  
##  <a name="setactivepage"></a>CPropertySheet::SetActivePage  
 Ändert die aktive Seite.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `nPage`  
 Der Index der Seite festlegen. Er muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, einschließlich sein.  
  
 `pPage`  
 Zeigt auf die Seite im Eigenschaftenfenster festlegen. Nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenblatt aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie z. B. `SetActivePage` , wenn eine Benutzeraktion auf einer Seite einer anderen Seite wird die aktive Seite auftreten soll.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="setfinishtext"></a>CPropertySheet::SetFinishText  
 Legt den Text in die Schaltfläche "Fertig stellen".  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Zeigt auf den Text auf die Schaltfläche "Fertig stellen" angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetFinishText` zeigt den Text auf die Schaltfläche "Fertig stellen", und blenden die Schaltflächen Weiter und zurück, der Benutzer die Aktion auf der letzten Seite des Assistenten abgeschlossen hat.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>CPropertySheet::SetTitle  
 Gibt das Eigenschaftenblatt Beschriftung (der Text, der in der Titelleiste eines Rahmenfensters angezeigt wird).  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Gibt die Art der der Titel des Eigenschaftenblattes. Das Format muss angegeben werden, bei 0 oder als **PSH_PROPTITLE**. Wenn das Format, als festgelegt ist **PSH_PROPTITLE**, das Wort "Eigenschaften" angezeigt wird, nach dem Text, der als Beschriftung angegeben. Zum Beispiel der Aufruf `SetTitle`("Einfache" **PSH_PROPTITLE**) führt dazu, dass eine Eigenschaftenblatt Beschriftung "Einfacher Eigenschaften".  
  
 `lpszText`  
 Zeigt auf den Text als Beschriftung in der Titelleiste des Eigenschaftenblatts verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verwendet ein Eigenschaftenblatt Caption-Parameter im Konstruktor Eigenschaftenblatt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#139;](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons  
 Aktiviert oder deaktiviert die Schaltfläche zurück, weiter oder Fertig stellen in einem Eigenschaftenblatt Assistenten.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Ein Satz von Flags, die die Funktion und die Darstellung der Assistentenschaltflächen anpassen. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
- **PSWIZB_BACK** Schaltfläche "zurück"  
  
- **PSWIZB_NEXT** Weiter-Schaltfläche  
  
- **PSWIZB_FINISH** Fertig stellen  
  
- **PSWIZB_DISABLEDFINISH** Schaltfläche deaktiviert Fertig stellen  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetWizardButtons` nur nach dem im Dialogfeld öffnen; kann nicht aufgerufen werden `SetWizardButtons` vor dem Aufruf von [DoModal](#domodal). Sie sollten in der Regel Aufrufen `SetWizardButtons` von [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Wenn Sie möchten, ändern Sie den Text auf die Schaltfläche Fertig stellen oder die nächste ausblenden und wieder Tasten los, nachdem des Benutzers hat der Assistent wurde abgeschlossen, Aufruf [SetFinishText](#setfinishtext). Beachten Sie, dass die gleiche Schaltfläche Fertig stellen und weiter freigegeben wird. Sie können einen Endtermin oder eine Schaltfläche "Weiter" gleichzeitig, aber nicht beides anzeigen.  
  
### <a name="example"></a>Beispiel  
 Ein `CPropertySheet` gibt es drei Assistenten Eigenschaftenseiten: `CStylePage`, `CColorPage`, und `CShapePage`.  Das folgende Codefragment zeigt, wie beim Aktivieren und Deaktivieren der **wieder** und **Weiter** Schaltflächen auf der Seite des Assistenten-Eigenschaft.  
  
 [!code-cpp[NVC_MFCDocView&#140;](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#141;](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>CPropertySheet::SetWizardMode  
 Stellt eine Eigenschaftenseite als Assistent her.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Hauptmerkmal einer Eigenschaftenseite des Assistenten wird der Benutzer navigiert mithilfe von weiter oder Fertig stellen, Sichern und Abbrechen (Schaltflächen) anstelle von Registerkarten.  
  
 Rufen Sie `SetWizardMode` vor dem Aufruf von [DoModal](#domodal). Nach dem Aufruf von `SetWizardMode`, `DoModal` gibt entweder **ID_WIZFINISH** (wenn der Benutzer mit der Schaltfläche "Fertig stellen" schließt) oder **IDCANCEL**.  
  
 `SetWizardMode`Das PSH_WIZARD-Flag festlegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#142;](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




