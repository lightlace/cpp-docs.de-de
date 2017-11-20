---
title: CPropertySheet-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 02fca1aac6b197ae3f06b4cdb0254ea30cab4f14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CPropertySheet::Create](#create)|Zeigt eine nicht modalen Eigenschaftenblatts an.|  
|[CPropertySheet:: DoModal](#domodal)|Zeigt ein modales Eigenschaftenblatt.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Gibt an, ob das Eigenschaftenblatt gestapelte oder einen Scrollcursor Registerkarten verwendet.|  
|[CPropertySheet::EndDialog](#enddialog)|Das Eigenschaftenblatt wird beendet.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Ruft den Index der aktiven Seite des Eigenschaftsblatt ab.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Gibt das aktive Seite zurück.|  
|[CPropertySheet::GetPage](#getpage)|Ruft einen Zeiger auf die angegebene Seite ab.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten im Eigenschaftenblatt ab.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Ruft den Index der angegebenen Seite des Eigenschaftsblatt ab.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Ruft einen Zeiger auf ein Registerkarten-Steuerelement ab.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Konvertiert die Einheiten im Dialogfeld eines Rechtecks Bildschirm Einheiten.|  
|[CPropertySheet:: OnInitDialog](#oninitdialog)|Überschreiben Sie, um das Blatt eigenschaftsinitialisierung zu erweitern.|  
|[CPropertySheet::PressButton](#pressbutton)|Simuliert die Wahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.|  
|[CPropertySheet::RemovePage](#removepage)|Entfernt eine Seite aus dem Eigenschaftenblatt.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Programmgesteuert legt die aktive Seite-Objekt fest.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Legt den Text für "Fertig stellen".|  
|[CPropertySheet::SetTitle](#settitle)|Legt die Beschriftung des Eigenschaftsblatts an.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Ermöglicht die Assistentenschaltflächen.|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|Die Assistentenmodus aktiviert.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Die Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) Struktur. Bietet Zugriff auf grundlegende Blatt Eigenschaftenparameter.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Eigenschaftenblatt besteht aus einem `CPropertySheet` Objekt sowie einen oder mehrere [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte. Das Framework zeigt ein Eigenschaftenblatt, als ein Fenster mit einem Satz von Registerkartenindizes und ein Bereich, der die derzeit ausgewählte Seite enthält. Der Benutzer navigiert zu einer bestimmten Seite mithilfe der entsprechenden Registerkarte.  
  
 `CPropertySheet`bietet Unterstützung für den erweiterten [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) Struktur eingeführten [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] und Windows NT-2000. Die Struktur enthält zusätzliche Flags und Member, die mit einem Hintergrundbitmap "Watermark" zu unterstützen.  
  
 Um diese neue Images automatisch in Ihrem Arbeitsblatt Eigenschaftenobjekt anzuzeigen, übergeben Sie gültige Werte für die Bitmap und Palette Bilder im Aufruf [CPropertySheet::Construct](#construct) oder [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Obwohl `CPropertySheet` stammt nicht aus [CDialog](../../mfc/reference/cdialog-class.md), Verwalten von einer `CPropertySheet` Objekt ist wie das Verwalten von einer `CDialog` Objekt. Beispielsweise erfordert die Erstellung eines Eigenschaftenblatts zweiteiligen Konstruktion: Rufen Sie den Konstruktor aus, und rufen dann [DoModal](#domodal) für ein modales Eigenschaftenblatt oder [erstellen](#create) für eines nicht modalen Eigenschaftenblatts. `CPropertySheet`verfügt über zwei Arten von Konstruktoren: [CPropertySheet::Construct](#construct) und [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Bei der Erstellung einer `CPropertySheet` -Objekts können einige [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) kann dazu führen, dass eine nicht abgefangene Ausnahme auftritt. Dadurch wird aus dem System, bei dem Versuch, den Stil des Eigenschaftenblatts zu ändern, bevor das Blatt erstellt wird. Um diese Ausnahme zu vermeiden, stellen Sie sicher, dass Sie die folgenden Stile festlegen, bei der Erstellung Ihrer `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Die folgenden Formate sind optional, und führt nicht dazu, dass die abgefangene Ausnahme:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Alle anderen `Window Styles` sind unzulässig und Sie sollten sie nicht aktivieren.  
  
 Austauschen von Daten zwischen einem `CPropertySheet` Objekt und einem externen Objekt gleicht dem Austauschen von Daten mit einem `CDialog` Objekt. Die wichtiger Unterschied besteht darin, dass die Einstellungen eines Eigenschaftenblatts Membervariablen des in der Regel sind die `CPropertyPage` Objekte anstelle von der `CPropertySheet` Objekt selbst.  
  
 Sie können einen Typ von Tab-Dialogfeld wird aufgerufen, einen Assistenten, besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, mit denen den Benutzer durch die Schritte eines Vorgangs, beispielsweise das Einrichten eines Geräts oder das Erstellen von eines Newsletters begleitet erstellen. In einem Dialogfeld des Assistenten-Registerkarte die Eigenschaftenseiten keine Registerkarten, und nur eine Eigenschaftenseite ist immer sichtbar. Auch, anstatt **OK** und **jetzt anwenden** Schaltflächen, ein Dialogfeld des Assistenten-Registerkarte verfügt über eine **wieder** Schaltfläche eine **Weiter** oder  **Fertig stellen** Schaltfläche eine **"Abbrechen"** Schaltfläche und ein **Hilfe** Schaltfläche.  
  
 Um ein Dialogfeld des Assistenten-Typ zu erstellen, führen Sie die gleichen Schritte aus, die Sie ausführen müssen, um ein standard Eigenschaftenblatt Aufruf jedoch erstellen [SetWizardMode](#setwizardmode) vor dem Aufruf [DoModal](#domodal). Rufen Sie zum Aktivieren der Assistentenschaltflächen [SetWizardButtons](#setwizardbuttons), ihre Funktion und Darstellung anpassen mithilfe von Flags. So aktivieren Sie die **Fertig stellen** Schaltfläche, rufen Sie [SetFinishText](#setfinishtext) sobald der Benutzer eine Aktion auf der letzten Seite des Assistenten.  
  
 Weitere Informationen zur Verwendung von `CPropertySheet` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md). Darüber hinaus finden Sie in Knowledge Base-Artikel Q146916: So wird's gemacht: Erstellen einer ohne Modus CPropertySheet mit Standard-Schaltflächen und Artikel Q300606: So wird's gemacht: Entwerfen Sie in der Größe veränderbaren MFC Eigenschaftenblätter.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="addpage"></a>CPropertySheet::AddPage  
 Fügt die angegebene Seite mit der äußersten rechten Registerkarte im Eigenschaftenblatt.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Verweist auf das Zeichenblatt, um das Eigenschaftenblatt hinzugefügt werden. Nicht mit **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Fügen Sie Seiten hinzu, auf dem Eigenschaftenblatt in links-nach-rechts-Reihenfolge, dass Sie angezeigt werden sollen.  
  
 `AddPage`Fügt der [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) -Objekt an die `CPropertySheet` Objekt der Liste der Seiten, die aber nicht tatsächlich im Fenster für die Seite erstellt. Das Framework zurückstellt Erstellung des Fensters für die Seite, bis der Benutzer diese Seite auswählt.  
  
 Beim Hinzufügen einer Eigenschaftenseite mithilfe `AddPage`, `CPropertySheet` ist das übergeordnete Element von der `CPropertyPage`. Rufen Sie für den Zugriff auf dem Eigenschaftenblatt auf der Eigenschaftenseite [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Es ist nicht notwendig, warten, bis die Erstellung des Eigenschaftenfensters Blatt aufrufen `AddPage`. Rufen Sie in der Regel `AddPage` vor dem Aufruf [DoModal](#domodal) oder [erstellen](#create).  
  
 Beim Aufrufen `AddPage` die Registerkartenreihe wider nach dem Anzeigen der Eigenschaftenseite, die neu hinzugefügte Seite.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
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
 ID der Beschriftung für das Eigenschaftenblatt verwendet werden soll.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster eines Eigenschaftenblatt. Wenn **NULL**, das übergeordnete Fenster werden das Hauptfenster der Anwendung.  
  
 `iSelectPage`  
 Der Index der Seite, die ursprünglich an erster Stelle stehen. Standardmäßig ist die erste Seite auf das Arbeitsblatt hinzugefügt.  
  
 `pszCaption`  
 Ein Zeiger auf eine Zeichenfolge, enthält die Beschriftung für das Eigenschaftenblatt verwendet werden soll. Nicht mit **NULL**.  
  
 `hbmWatermark`  
 Handle für das Wasserzeichen Bitmuster der Eigenschaftenseite.  
  
 `hpalWatermark`  
 Handle für die Palette der Wasserzeichen Bitmap und/oder Header mithilfe einer Bitmap.  
  
 `hbmHeader`  
 Handle für die Bitmap "Header" der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, wenn die Klasse Konstruktoren nicht bereits aufgerufen wurde. Rufen Sie z. B. `Construct` beim Deklarieren oder Zuordnen von Arrays für `CPropertySheet` Objekte. Im Fall von Arrays, rufen Sie `Construct` für jedes Element im Array.  
  
 Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Die Zeichenfolge in den ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert.  
  
 Sie Bilder anzeigen können Wasserzeichen und/oder Header automatisch bei der Verwendung der dritten oder vierten Prototypes `Construct`oben aufgeführten und übergeben Sie gültige Werte für die `hbmWatermark`, `hpalWatermark`, und/oder `hbmHeader` Parameter.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, unter welchen Sie Umständen aufrufen würde `Construct`.  
  
 [!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
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
 ID der Beschriftung für das Eigenschaftenblatt verwendet werden soll.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster der Eigenschaftenseite. Wenn **NULL**, das übergeordnete Fenster werden das Hauptfenster der Anwendung.  
  
 `iSelectPage`  
 Der Index der Seite, die ursprünglich an erster Stelle stehen. Standardmäßig ist die erste Seite auf das Arbeitsblatt hinzugefügt.  
  
 `pszCaption`  
 Verweist auf eine Zeichenfolge, enthält die Beschriftung für das Eigenschaftenblatt verwendet werden soll. Nicht mit **NULL**.  
  
 `hbmWatermark`  
 Ein Handle für das Hintergrundbild des Eigenschaftenblatts.  
  
 `hpalWatermark`  
 Ein Handle für die Palette der Wasserzeichen Bitmap und/oder Header mithilfe einer Bitmap.  
  
 `hbmHeader`  
 Ein Handle für die Bitmap "Header" der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Um das Eigenschaftenfenster anzuzeigen, rufen [DoModal](#domodal) oder [erstellen](#create). Die Zeichenfolge in den ersten Parameter werden in der Titelleiste für das Eigenschaftenblatt platziert.  
  
 Wenn Sie mehrere Parameter (z. B., wenn Sie ein Array verwenden), verwenden [erstellen](#construct) anstelle von `CPropertySheet`.  
  
 Sie Bilder anzeigen können Wasserzeichen und/oder Header automatisch bei der Verwendung der dritten oder vierten Prototypes `CPropertySheet`oben, und übergeben Sie gültige Werte für die `hbmWatermark`, `hpalWatermark`, und/oder `hbmHeader` Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>CPropertySheet::Create  
 Zeigt eine nicht modalen Eigenschaftenblatts an.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster. Wenn **NULL**, übergeordnete stellt der Desktop dar.  
  
 `dwStyle`  
 Fensterstile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 `dwExStyle`  
 Erweiterte Fensterstile für Eigenschaftenblatt. Eine vollständige Liste der verfügbaren Formate finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Aufruf von **erstellen** innerhalb des Konstruktors kann oder Sie rufen es nach dem Aufruf des Konstruktors.  
  
 Das Standardformat, ausgedrückt als-1 übergeben `dwStyle`, handelt es sich tatsächlich **WS_SYSMENU &#124;** `WS_POPUP` **&#124; WS_CAPTION &#124; DS_MODALFRAME &#124; DS_CONTEXTHELP &#124; WS_VISIBLE**. Die Standardeinstellung erweiterten Stil des Fensters, übergeben Sie 0 als ausgedrückt `dwExStyle`, handelt es sich tatsächlich **WS_EX_DLGMODALFRAME**.  
  
 Die **erstellen** Memberfunktion gibt sofort nach dem Erstellen der Eigenschaftenblatt zurück. Aufrufen, um das Eigenschaftenfenster zu zerstören, [CWnd:: DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Nicht modulare Eigenschaftenblätter angezeigt, die mit einem Aufruf von **erstellen** keine OK, "Abbrechen", jetzt anwenden und Hilfe-Schaltflächen ebenso modale Eigenschaftenblätter. Gewünschte Schaltflächen müssen vom Benutzer erstellt werden.  
  
 Rufen Sie zum Anzeigen von modalen Eigenschaftenblatts [DoModal](#domodal) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>CPropertySheet:: DoModal  
 Zeigt ein modales Eigenschaftenblatt.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `IDOK`oder `IDCANCEL` war die Funktion erfolgreich ausgeführt; andernfalls 0 oder-1 zurück. Wenn das Eigenschaftenfenster wie ein Assistent eingerichtet wurde (finden Sie unter [SetWizardMode](#setwizardmode)), `DoModal` gibt `ID_WIZFINISH` oder `IDCANCEL`.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert entspricht der ID des Steuerelements, das die Eigenschaftenseite geschlossen. Nachdem diese Funktion zurückgibt, werden eine Windows entspricht dem Eigenschaftenblatt und alle Seiten zerstört wurden. Die Objekte selbst auch weiterhin vorhanden. Normalerweise rufen Sie Daten aus der [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekte nach `DoModal` gibt `IDOK`.  
  
 Rufen Sie zum Anzeigen eines nicht modalen Eigenschaftenblatts [erstellen](#create) stattdessen.  
  
 Wenn eine Eigenschaftsseite aus seiner entsprechenden Dialogfeldressource erstellt wird, kann eine nicht abgefangene Ausnahme verursachen. Dies führt auf der Eigenschaftenseite die Art des Dialog-Ressource in das erforderliche Format ändern, bevor die Seite erstellt wird. Da Ressourcen im Allgemeinen schreibgeschützt sind, bewirkt dies eine Ausnahme aus. Das System verarbeitet die Ausnahme und eine Kopie der geänderten Ressource. Die Ausnahme der ersten Chance kann aus diesem Grund ignoriert werden.  
  
> [!NOTE]
>  Diese Ausnahme muss vom Betriebssystem behandelt werden, wenn Sie mit dem Modell asynchrone Ausnahmebehandlung kompilieren. Weitere Informationen zu Modellen für die Ausnahmebehandlung, finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md). Umschließen Sie in diesem Fall keine Aufrufe von `CPropertySheet::DoModal` mit einem C++-Try / Catch-Block in dem Catch alle Ausnahmen behandelt, z. B. `catch (...)`. Dieser Block genauso wie die Ausnahme, die für das Betriebssystem und die Ursache zu einem unvorhersehbaren Verhalten vorgesehen behandelt. Allerdings können Sie problemlos verwenden C++-Ausnahmebehandlung mit bestimmte Ausnahmetypen oder strukturierte Ausnahmebehandlung, in dem die Zugriffsverletzung-Ausnahme für das Betriebssystem über übergeben.  
  
 Um zu vermeiden, diese erste-Chance-Ausnahme generiert, Sie können manuell sichergestellt, dass das Eigenschaftenblatt den richtigen [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Sie müssen die folgenden Formate für ein Eigenschaftenblatt festlegen:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Sie können die folgenden optionalen Stile verwenden, ohne eine nicht abgefangene Ausnahme verursacht:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Deaktivieren Sie alle anderen Windows-Formatvorlagen, da sie nicht mit Eigenschaftenblättern kompatibel sind. Diese Empfehlung gilt nicht für die erweiterten Stile. Diese standard-Stile entsprechend festgelegt wird sichergestellt, dass das Eigenschaftenblatt muss nicht geändert werden und wird zu vermeiden, dass die abgefangene Ausnahme.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::AddPage](#addpage).  
  
##  <a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs  
 Gibt an, ob Zeilen mit Registerkarten in einem Eigenschaftenblatt gestapelt.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Parameter  
 `bStacked`  
 Gibt an, ob im Eigenschaftenblatt gestapelte Registerkarten aktiviert sind. Gestapelte Zeilen von Tags zu deaktivieren, indem `bStacked` auf **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Verfügt ein Eigenschaftenblatt weitere Registerkarten als in einer einzelnen Zeile in der Breite des Eigenschaftenblatts, passen, werden standardmäßig die Registerkarten in mehreren Zeilen Stapeln. Rufen Sie zum Durchführen eines Bildlaufs Registerkarten anstelle von Stapeln Registerkarten verwenden `EnableStackedTabs` mit `bStacked` festgelegt **"false"** vor dem Aufruf [DoModal](#domodal) oder [erstellen](#create).  
  
 Rufen Sie `EnableStackedTabs` beim Erstellen eines modalen oder eines nicht modalen Eigenschaftenblatts. Integrieren Sie dieses Format in ein `CPropertySheet`-abgeleitete Klasse mit dem Schreiben eines meldungshandlers für `WM_CREATE`. In die überschriebene Version der [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), rufen Sie **EnableStackedTabs (FALSE)** vor der Implementierung der Basisklasse aufrufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>CPropertySheet::EndDialog  
 Das Eigenschaftenblatt wird beendet.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Parameter  
 *nEndID*  
 Der Bezeichner als Rückgabewert des Eigenschaftenblatts verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn die OK, die "Abbrechen" oder die Schaltfläche "Schließen" gedrückt wird. Rufen Sie, dass diese Memberfunktion auf, wenn ein Ereignis auftritt, das Eigenschaftenfenster geschlossen werden soll.  
  
 Diese Memberfunktion wird nur ein modales Dialogfeld verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="getactiveindex"></a>CPropertySheet::GetActiveIndex  
 Ruft die Indexnummer der aktive Seite Eigenschaftenblatt Fenster und verwendet dann als Parameter für die zurückgegebenen Indexnummer `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Indexnummer der aktiven Seite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="getactivepage"></a>CPropertySheet::GetActivePage  
 Ruft die Eigenschaftenblatt-Fenster aktive Seite ab.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die aktive Seite.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion auf, um eine Aktion auf der aktiven Seite auszuführen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>CPropertySheet::GetPage  
 Gibt einen Zeiger auf die angegebene Seite in diesem Eigenschaftenblatt.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPage`  
 Der Index der gewünschten Seite beginnend mit 0. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, inklusive.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf der Seite entspricht der `nPage` Parameter.  
  
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
 Ruft die Indexnummer für die angegebene Seite im Eigenschaftenblatt ab.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Zeigt auf der Seite mit dem Index gefunden werden. Nicht mit **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Indexnummer einer Seite.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie z. B. `GetPageIndex` den Seitenindex abgerufen, um verwenden [SetActivePage](#setactivepage) oder [GetPage](#getpage).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="gettabcontrol"></a>CPropertySheet::GetTabControl  
 Ruft einen Zeiger auf ein Registerkarten-Steuerelement, eine Aktion für das Registerkarten-Steuerelement (d. h. keine APIs im [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie beispielsweise diese Memberfunktion auf, wenn Sie Bitmaps auf den Registerkarten während der Initialisierung hinzufügen möchten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>CPropertySheet::m_psh  
 Eine Struktur, deren Mitglieder die Merkmale des speichern [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Hinweise  
 Diese Struktur verwenden, um die Darstellung des Eigenschaftenblatts zu initialisieren, nachdem es erstellt wurde, aber bevor er mit angezeigt wird der [DoModal](#domodal) Memberfunktion. Legen Sie z. B. die `dwSize` Mitglied `m_psh` auf die Größe der Eigenschaftenblatt haben sollen.  
  
 Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member, finden Sie unter **PROPSHEETHEADER** im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>CPropertySheet::MapDialogRect  
 Konvertiert die Einheiten im Dialogfeld eines Rechtecks Bildschirm Einheiten.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält koordiniert, der konvertiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet wurde. die durchschnittliche Breite und Höhe der Zeichen in der Schriftart für Text im Dialogfeld angegeben. Eine horizontale Einheit ist ein Viertel der im Dialogfeld Basis-Breite Einheit, und eine vertikale Einheit ist ein Achtel des Geräts im Dialogfeld Basis Höhe.  
  
 Die [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows-Funktion gibt Informationen zur Datenbankgröße für die Systemschriftart, aber Sie können eine andere Schriftart für jede Eigenschaftenblatt angeben, bei Verwendung der **DS_SETFONT** Stil die Ressource-Definitionsdatei. Die [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) beschriebenen im SDK für Windows, Windows-Funktion verwendet die passende Schriftart für das Dialogfeld zu öffnen.  
  
 Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten in `lpRect` mit Bildschirm Einheiten (in Pixel), damit das Rechteck zum Erstellen eines Dialogfelds oder positionieren ein Steuerelement innerhalb eines Felds verwendet werden kann.  
  
##  <a name="oninitdialog"></a>CPropertySheet:: OnInitDialog  
 Außerkraftsetzungen, um das Blatt eigenschaftsinitialisierung zu erweitern.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Eigenschaftenblatt festgelegt wurde. Wenn **OnInitDialog** ungleich NULL zurückgegeben wird, wird Windows den Eingabefokus auf das erste Steuerelement im Eigenschaftenblatt. Die Anwendung kann 0 zurückgeben, nur dann, wenn er den Eingabefokus auf eines der Steuerelemente im Eigenschaftenblatt explizit festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberfunktion wird als Antwort auf die **WM_INITDIALOG** Nachricht. Diese Nachricht wird gesendet, auf dem Eigenschaftenblatt während der [erstellen](#create) oder [DoModal](#domodal) Aufrufe, die auftreten, unmittelbar bevor die Eigenschaftenseite angezeigt wird.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn Sie besondere Verarbeitung bei der Initialisierung der Eigenschaftenblatt ausführen müssen. In der überschriebenen Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber dessen Rückgabewert ignorieren. Normalerweise wird nun wieder **"true"** von der überschriebenen Member-Funktion.  
  
 Sie benötigen für diese Memberfunktion keine Meldungszuordnungseintrags.  
  
##  <a name="pressbutton"></a>CPropertySheet::PressButton  
 Simuliert die Wahl der angegebenen Schaltfläche in einem Eigenschaftenblatt.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Parameter  
 `nButton`  
 nButton: die Schaltfläche gedrückt, identifiziert. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **PSBTN_BACK** wählt Sie die Schaltfläche "zurück".  
  
- **PSBTN_NEXT** wählt Sie die Schaltfläche "Weiter".  
  
- **PSBTN_FINISH** wählt "Fertig stellen".  
  
- **PSBTN_OK** wählt Sie die Schaltfläche "OK".  
  
- **PSBTN_APPLYNOW** wählt Sie die Schaltfläche "jetzt anwenden".  
  
- **Von PSBTN_CANCEL zurückgegeben** wählt Sie die Schaltfläche "Abbrechen".  
  
- **PSBTN_HELP** die Schaltfläche "Hilfe" auswählt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) für Weitere Informationen über die Windows SDK Pressbutton-Meldung.  
  
 Ein Aufruf von `PressButton` sendet keinen der [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Benachrichtigung vom eine Eigenschaftenseite, um das Framework. Um diese Benachrichtigung zu senden, rufen [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>CPropertySheet::RemovePage  
 Entfernt eine Seite aus dem Eigenschaftenblatt, und das zugeordnete Fenster zerstört.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 `pPage`  
 Zeigt auf der Seite aus dem Eigenschaftenblatt entfernt werden soll. Nicht mit `NULL`.  
  
 `nPage`  
 Der Index der Seite entfernt werden soll. Muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, inklusive.  
  
### <a name="remarks"></a>Hinweise  
 Die [CPropertyPage](../../mfc/reference/cpropertypage-class.md) Objekt selbst wird nicht zerstört, bis der Besitzer der `CPropertySheet` Fenster geschlossen wird.  
  
##  <a name="setactivepage"></a>CPropertySheet::SetActivePage  
 Ändert die aktive Seite.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 `nPage`  
 Der Index der Seite festlegen. Es muss zwischen 0 und kleiner als die Anzahl der Seiten im Eigenschaftenblatt, inklusive.  
  
 `pPage`  
 Zeigt auf, um im Eigenschaftenblatt festzulegen. Er darf nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Eigenschaftenfenster erfolgreich aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie z. B. `SetActivePage` Wenn bei einer anderen Seite wird die aktive Seite einer Benutzeraktion auf einer Seite auftreten soll.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="setfinishtext"></a>CPropertySheet::SetFinishText  
 Legt den Text in den Befehl "Fertig stellen".  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Verweist auf den Text für den Befehl "Fertig stellen" angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetFinishText` den Anzeigetext auf den Befehl "Fertig stellen", und blenden die Schaltflächen Weiter und zurück, nachdem der Benutzer die Aktion auf der letzten Seite des Assistenten abgeschlossen hat.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>CPropertySheet::SetTitle  
 Gibt die Beschriftung für das Eigenschaftenblatt (der Text, der in der Titelleiste Rand eines Rahmenfensters angezeigt wird).  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Gibt die Art der der Titel des Eigenschaftenblattes. Das Format muss angegeben werden, auf dem Wert 0 oder als **PSH_PROPTITLE**. Wenn das Format, als festgelegt ist **PSH_PROPTITLE**, das Wort "Eigenschaften" angezeigt wird, nach dem Text als Beschriftung angegeben. Beispielsweise Aufrufen `SetTitle`("Einfache" **PSH_PROPTITLE**) führt zu einer Eigenschaftenblatt Beschriftung der "Einfache Eigenschaften".  
  
 `lpszText`  
 Verweist auf den Text als Beschriftung in der Titelleiste des Eigenschaftenblatts verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verwendet ein Eigenschaftenblatt den Caption-Parameter im Konstruktor Eigenschaftenblatt an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons  
 Aktiviert oder deaktiviert die Schaltfläche zurück, Next oder Fertig stellen in einem Eigenschaftenblatt für den Assistenten.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Ein Satz von Flags, die die Funktion und Darstellung der Assistentenschaltflächen anpassen. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
- **PSWIZB_BACK** Schaltfläche "zurück"  
  
- **PSWIZB_NEXT** neben der Schaltfläche  
  
- **PSWIZB_FINISH** "Fertig stellen"  
  
- **PSWIZB_DISABLEDFINISH** Schaltfläche deaktiviert Fertig stellen  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetWizardButtons` , nachdem das Dialogfeld geöffnet ist Sie nicht aufrufen, `SetWizardButtons` vor dem Aufruf [DoModal](#domodal). Rufen Sie in der Regel sollte `SetWizardButtons` aus [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Wenn Sie verwenden möchten, ändern Sie den Text auf "Fertig stellen", oder das nächste ausblenden und wieder Tasten los, nachdem des Benutzers im Assistenten Aufruf abgeschlossen wurde [SetFinishText](#setfinishtext). Beachten Sie, dass die Schaltfläche "Angleichen" für "Finish" und weiter gemeinsam verwendet wird. Sie können die Beendigung oder eine Schaltfläche "Weiter" gleichzeitig, aber nicht beides anzeigen.  
  
### <a name="example"></a>Beispiel  
 Ein `CPropertySheet` hat drei Seiten des Assistenten-Eigenschaft: `CStylePage`, `CColorPage`, und `CShapePage`.  Im folgenden Codefragment wird gezeigt, wie beim Aktivieren und Deaktivieren der **wieder** und **Weiter** Schaltflächen auf der Seite des Assistenten-Eigenschaft.  
  
 [!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>CPropertySheet::SetWizardMode  
 Stellt eine Eigenschaftenseite wie ein Assistent her.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Hauptmerkmal einer Assistentenseite für die Eigenschaft ist, dass der Benutzer navigiert, verwenden als Nächstes oder Fertig stellen, Sichern und Abbrechen (Schaltflächen) anstelle von Registerkarten.  
  
 Rufen Sie `SetWizardMode` vor dem Aufruf [DoModal](#domodal). Nach dem Aufruf `SetWizardMode`, `DoModal` zurück entweder **ID_WIZFINISH** (wenn der Benutzer mit der Schaltfläche "Fertig stellen" schließt) oder **IDCANCEL**.  
  
 `SetWizardMode`Legt das Flag PSH_WIZARD fest.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



