---
title: Cmfctoolbarscustomizedialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
ms.openlocfilehash: 239532c78491f121423ca42a2c3dfc306997c841
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504687"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>Cmfctoolbarscustomizedialog-Klasse

Ein nicht modalem Registerkarten Dialogfeld ( [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)), das es dem Benutzer ermöglicht, die Symbolleisten, Menüs, Tastenkombinationen, benutzerdefinierten Tools und den visuellen Stil in einer Anwendung anzupassen. In der Regel greift der Benutzer durch Auswählen von **Anpassen** im Menü **Tools** auf dieses Dialogfeld zu.

Das Dialogfeld **Anpassen** enthält sechs Registerkarten: **Befehle**, **Symbolleisten**, **Tools**, **Tastatur**, **Menü**und **Optionen**.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Erstellt ein `CMFCToolBarsCustomizeDialog`-Objekt.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Fügt eine Symbolleisten-Schaltfläche in die Liste der Befehle auf der Seite **Befehle** ein.|
|`CMFCToolBarsCustomizeDialog::`[Cmfctoolbarscustomizedialog:: AddMenu](#addmenu)|Lädt ein Menü aus den Ressourcen und ruft [cmfctoolbarscustomizedialog:: addmenucommands](#addmenucommands) auf, um dieses Menü der Liste der Befehle auf der Seite **Befehle** hinzuzufügen.|
|`CMFCToolBarsCustomizeDialog::`[Cmfctoolbarscustomizedialog:: addmenucommands](#addmenucommands)|Lädt ein Menü aus den Ressourcen und ruft [cmfctoolbarscustomizedialog:: addmenucommands](#addmenucommands) auf, um dieses Menü der Liste der Befehle auf der Seite **Befehle** hinzuzufügen.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Lädt eine Symbolleiste aus den Ressourcen. Anschließend wird für jeden Befehl im Menü die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode aufgerufen, um eine Schaltfläche in der Liste der Befehle auf der Seite **Befehle** in der angegebenen Kategorie einzufügen.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|Zeigt das Dialogfeld **Anpassung** an.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Zur künftigen Verwendung reserviert.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Aktiviert oder deaktiviert das Erstellen neuer Symbolleisten mithilfe des Dialog Felds **Anpassen** .|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Füllt das angegebene `CListBox` -Objekt mit den Befehlen in der Kategorie **alle Befehle** auf.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Füllt das angegebene `CComboBox` -Objekt mit dem Namen jeder Befehls Kategorie im Dialogfeld **Anpassen** auf.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Füllt das angegebene `CListBox` -Objekt mit dem Namen jeder Befehls Kategorie im Dialogfeld **Anpassen** auf.|
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Ruft den Namen ab, der der angegebenen Befehls-ID zugeordnet ist.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Ruft die Anzahl der Elemente in der angegebenen Liste ab, die über eine angegebene Text Bezeichnung verfügen.|
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Ruft den Satz von Flags ab, die das Verhalten des Dialog Felds beeinflussen.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Startet einen Bild-Editor, damit ein Benutzer eine Symbolleisten-Schaltfläche oder ein Menü Element Symbol anpassen kann.|
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Überschreibt, um die Eigenschaften Blatt Initialisierung zu erweitern. (Überschreibt [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Wird von Framework aufgerufen, nachdem das Fenster zerstört wurde. (Überschreibt `CPropertySheet::PostNcDestroy`.)|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit der angegebenen Befehls-ID aus der angegebenen Kategorie oder aus allen Kategorien.|
|`CMFCToolBarsCustomizeDialog::`[Cmfctoolbarscustomizedialog:: renamecategory](#renamecategory)|Benennt eine Kategorie im Listenfeld der Kategorien auf der Registerkarte **Befehle** um.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Ersetzt eine Schaltfläche in der Liste der Befehle auf der Registerkarte **Befehle** mit einem neuen Symbolleisten-Schaltflächen Objekt.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Fügt der Liste der Kategorien, die auf der Registerkarte **Befehle** angezeigt werden, eine Kategorie hinzu.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::`[Cmfctoolbarscustomizedialog:: checktoolsgültigkeit](#checktoolsvalidity)|Wird von Framework aufgerufen, um zu bestimmen, ob die Liste der benutzerdefinierten Tools gültig ist.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Wird von Framework aufgerufen, wenn sich die Eigenschaften eines benutzerdefinierten Tools ändern.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Bestimmt, ob eine angegebene Tastenkombination einer Aktion zugewiesen werden kann.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Bestimmt, ob ein benutzerdefiniertes Tool geändert werden kann.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Wird von Framework aufgerufen, wenn der Benutzer die Registerkarte **Tools** auswählt.|

## <a name="remarks"></a>Hinweise

Um das Dialogfeld **Anpassen** anzuzeigen, erstellen Sie `CMFCToolBarsCustomizeDialog` ein-Objekt, und rufen Sie die [cmfctoolbarscustomizedialog:: Create](#create) -Methode auf.

Während das Dialogfeld **Anpassen** aktiviert ist, funktioniert die Anwendung in einem speziellen Modus, durch den der Benutzer auf Anpassungs Aufgaben beschränkt wird.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCToolBarsCustomizeDialog` -Klasse. Das Beispiel zeigt, wie Sie eine Symbolleisten-Schaltfläche im Listenfeld der Befehle auf der Seite **Befehle** ersetzen, die Erstellung neuer Symbolleisten mithilfe des Dialog Felds **Anpassen** aktivieren und das Dialogfeld **Anpassung** anzeigen. Dieser Code Ausschnitt ist Teil des IE- [Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxToolBarsCustomizeDialog.h

##  <a name="addbutton"></a>Cmfctoolbarscustomizedialog:: AddButton

Fügt eine Symbolleisten-Schaltfläche in die Liste der Befehle auf der Seite **Befehle** ein.

```
void AddButton(
    UINT uiCategoryId,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);
```

### <a name="parameters"></a>Parameter

*uiCategoryId*<br/>
in Gibt die Kategorie-ID an, in die die Schaltfläche eingefügt werden soll.

*button*<br/>
in Gibt die einzufügende Schaltfläche an.

*iInsertBefore*<br/>
in Gibt den NULL basierten Index einer Symbolleisten-Schaltfläche an, vor der die Schaltfläche eingefügt wird.

*lpszCategory*<br/>
in Gibt die Kategoriezeichenfolge zum Einfügen der Schaltfläche an

### <a name="remarks"></a>Hinweise

Die `AddButton` Methode ignoriert Schaltflächen, die über die Standard Befehls-IDs (z. b. ID_FILE_MRU_FILE1), nicht zugelassene Befehle (siehe [cmfctoolbar:: iscommandzugelassene](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) und Dummy-Schaltflächen verfügen.

Diese Methode erstellt ein neues Objekt desselben Typs wie `button` (in der Regel eine [cmfctoolbarbutton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)), indem die Lauf Zeit Klasse der Schaltfläche verwendet wird. Anschließend wird [cmfctoolbarbutton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) aufgerufen, um die Datenmember der Schaltfläche zu kopieren, und die Kopie wird in die angegebene Kategorie eingefügt.

Wenn die Schaltfläche "neu" eingefügt wird, `OnAddToCustomizePage` empfängt Sie die Benachrichtigung.

Wenn `iInsertBefore` -1 ist, wird die Schaltfläche an die Liste der Kategorien angehängt; andernfalls wird Sie vor dem Element mit dem angegebenen Index eingefügt.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `AddButton` -Methode `CMFCToolBarsCustomizeDialog` der-Klasse verwendet wird. Dieser Code Ausschnitt ist Teil des [Schiebereglers](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

##  <a name="addmenu"></a>Cmfctoolbarscustomizedialog:: AddMenu

Lädt ein Menü aus den Ressourcen und ruft [cmfctoolbarscustomizedialog:: addmenucommands](#addmenucommands) auf, um dieses Menü der Liste der Befehle auf der Seite **Befehle** hinzuzufügen.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parameter

*uiMenuResId*<br/>
in Gibt die Ressourcen-ID eines Menüs an, das geladen werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Menü erfolgreich hinzugefügt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Im-Befehl ist bpopup auf false fest. `AddMenuCommands` Folglich fügt diese Methode keine Menü Elemente hinzu, die Untermenüs zur Liste der Befehle enthalten. Diese Methode fügt die Menü Elemente in den Untermenüs der Liste der Befehle hinzu.

##  <a name="addmenucommands"></a>Cmfctoolbarscustomizedialog:: addmenucommands

Fügt der Liste der Befehle auf der Seite **Befehle** Elemente hinzu, um alle Elemente im angegebenen Menü darzustellen.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parameter

*pMenu*<br/>
in Ein Zeiger auf das hinzu zufügende CMenu-Objekt.

*bPopup*<br/>
in Gibt an, ob die Popup Menü Elemente in die Liste der Befehle eingefügt werden sollen.

*lpszCategory*<br/>
in Der Name der Kategorie, in die das Menü eingefügt werden soll.

*lpszMenuPath*<br/>
in Ein Präfix, das dem Namen hinzugefügt wird, wenn der Befehl in der Liste " **Alle Kategorien** " angezeigt wird.

### <a name="remarks"></a>Hinweise

Die `AddMenuCommands` -Methode durchläuft alle Menü Elemente von *pmenu*. Für jedes Menü Element, das kein Untermenü enthält, erstellt diese Methode ein [cmfctoolbarbutton-Klassen](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt und ruft die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode auf, um das Menü Element als Symbolleisten Schaltfläche zur Liste der Befehle imSeite "Befehle". Trennzeichen werden in diesem Prozess ignoriert.

Wenn *bpopup* auf true festgelegt ist, erstellt diese Methode für jedes Menü Element, das ein Untermenü enthält, ein [cmfctoolbarmenubutton-Klassen](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt und fügt es in `AddButton`die Liste der Befehle ein, indem aufgerufen wird. Andernfalls werden Menü Elemente, die Untermenüs enthalten, nicht in der Liste der Befehle angezeigt. Wenn `AddMenuCommands` in beiden Fällen ein Menü Element mit einem Untermenü gefunden wird, ruft es sich selbst rekursiv auf und übergibt einen Zeiger auf das Untermenü als *pmenu* -Parameter und fügt die Bezeichnung des Untermenüs an *lpszmenupath*an.

##  <a name="addtoolbar"></a>Cmfctoolbarscustomizedialog:: AddToolBar

Lädt eine Symbolleiste aus den Ressourcen. Anschließend wird für jeden Befehl im Menü die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode aufgerufen, um eine Schaltfläche in der Liste der Befehle auf der Seite **Befehle** in der angegebenen Kategorie einzufügen.

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>Parameter

*uiCategoryId*<br/>
in Gibt die Ressourcen-ID der Kategorie an, der die Symbolleiste hinzugefügt werden soll.

*uiToolbarResId*<br/>
in Gibt die Ressourcen-ID einer Symbolleiste an, deren Befehle in die Liste der Befehle eingefügt werden.

*lpszCategory*<br/>
in Gibt den Namen der Kategorie an, der die Symbolleiste hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich ist. andernfalls false.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `AddToolBar` -Methode in `CMFCToolBarsCustomizeDialog` der-Klasse verwendet wird. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Hinweise

Das Steuerelement, das zum Darstellen der einzelnen Befehle verwendet wird, ist ein [cmfctoolbarbutton-Klassen](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt. Nachdem Sie die Symbolleiste hinzugefügt haben, können Sie die Schaltfläche durch ein Steuerelement eines abgeleiteten Typs ersetzen, indem Sie [cmfctoolbarscustomizedialog:: replacebutton](#replacebutton)aufrufen.

##  <a name="checktoolsvalidity"></a>Cmfctoolbarscustomizedialog:: checktoolsgültigkeit

Überprüft die Gültigkeit der Liste der Benutzer Tools.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parameter

*lstTools*<br/>
in Die Liste der benutzerdefinierten Tools, die überprüft werden sollen.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Liste der benutzerdefinierten Tools gültig ist. andernfalls false. Die Standard Implementierung gibt immer true zurück.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, um die Gültigkeit von Objekten zu überprüfen, die benutzerdefinierte Tools darstellen, die von [cmfctoolbarscustomizedialog:: checktoolsgültigkeit](#checktoolsvalidity)zurückgegeben werden.

Überschreiben `CheckToolsValidity` Sie die-Methode in einer `CMFCToolBarsCustomizeDialog` Klasse, die von abgeleitet ist, wenn Sie die Benutzer Tools überprüfen möchten, bevor der Benutzer das Dialogfeld schließt. Wenn diese Methode false zurückgibt, wenn der Benutzer auf die Schaltfläche **Schließen** in der oberen rechten Ecke des Dialog Felds oder auf die Schaltfläche **Schließen** in der unteren rechten Ecke des Dialog Felds klickt, wird im Dialogfeld anstelle von Abschlusses. Wenn diese Methode false zurückgibt, wenn der Benutzer auf eine Registerkarte klickt, um von der Registerkarte " **Tools** " zu navigieren, erfolgt keine Navigation. Sie sollten ein entsprechendes Meldungs Feld anzeigen, um den Benutzer über das Problem zu informieren, das zu einem Fehler bei der Validierung geführt hat.

##  <a name="cmfctoolbarscustomizedialog"></a>Cmfctoolbarscustomizedialog:: cmfctoolbarscustomizedialog

Erstellt ein `CMFCToolBarsCustomizeDialog`-Objekt.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Parameter

*pWndParentFrame*<br/>
in Ein Zeiger auf den übergeordneten Frame. Dieser Parameter darf nicht NULL sein.

*bAutoSetFromMenus*<br/>
in Ein boolescher Wert, der angibt, ob die Menübefehle aus allen Menüs der Liste der Befehle auf der Seite **Befehle** hinzugefügt werden sollen. Wenn dieser Parameter true ist, werden die Menübefehle hinzugefügt. Andernfalls werden die Menübefehle nicht hinzugefügt.

*uiFlags*<br/>
in Eine Kombination von Flags, die das Verhalten des Dialog Felds beeinflussen. Dieser Parameter kann einen oder mehrere der folgenden Werte aufweisen:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
in Ein Zeiger auf eine Liste von `CRuntimeClass` -Objekten, die zusätzliche benutzerdefinierte Seiten angeben.

### <a name="remarks"></a>Hinweise

Der *plistcustompages* -Parameter verweist auf die Liste `CRuntimeClass` der-Objekte, die zusätzliche benutzerdefinierte Seiten angeben. Der-Konstruktor fügt dem Dialogfeld mithilfe der [CRuntimeClass:: deateobject](../../mfc/reference/cruntimeclass-structure.md#createobject) -Methode weitere Seiten hinzu. Ein Beispiel für das Hinzufügen von weiteren Seiten zum Dialogfeld " **Anpassen** " finden Sie im CustomPages-Beispiel.

Weitere Informationen zu den Werten, die Sie im *uiflags* -Parameter übergeben können, finden Sie unter [cmfctoolbarscustomizedialog:: GetFlags](#getflags).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCToolBarsCustomizeDialog` -Klasse erstellt wird. Dieser Code Ausschnitt ist Teil des Beispiels für [benutzerdefinierte Seiten](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

##  <a name="create"></a>Cmfctoolbarscustomizedialog:: Create

Zeigt das Dialogfeld **Anpassung** an.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Anpassungs Eigenschaften Blatt erfolgreich erstellt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Die `Create` -Methode wird erst aufgerufen, nachdem Sie die-Klasse vollständig initialisiert haben.

##  <a name="enableuserdefinedtoolbars"></a>Cmfctoolbarscustomizedialog:: enableuserdefinedtoolbars

Aktiviert oder deaktiviert das Erstellen neuer Symbolleisten mithilfe des Dialog Felds **Anpassen** .

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in TRUE, um die benutzerdefinierten Symbolleisten zu aktivieren. FALSE, um die Symbolleisten zu deaktivieren.

### <a name="remarks"></a>Hinweise

Wenn *benable* auf true festgelegt ist, werden die Schaltflächen **neu**, **Umbenennen** und **Löschen** auf der Seite **Symbolleisten** angezeigt.

Standardmäßig werden diese Schaltflächen nicht angezeigt, und der Benutzer kann keine neuen Symbolleisten definieren, wenn Sie den *Wert* false haben.

##  <a name="fillallcommandslist"></a>Cmfctoolbarscustomizedialog:: fillallcommandslist

Füllt das angegebene `CListBox` -Objekt mit den Befehlen in der Kategorie **alle Befehle** auf.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parameter

*wndListOfCommands*<br/>
vorgenommen Ein Verweis auf das `CListBox` -Objekt, das aufgefüllt werden soll.

### <a name="remarks"></a>Hinweise

Die Kategorie **alle Befehle** enthält die Befehle aller Kategorien. Die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode fügt der Kategorie **alle Befehle** den Befehl hinzu, der der bereitgestellten Schaltfläche zugeordnet ist.

Diese Methode löscht den Inhalt des bereitgestellten `CListBox` -Objekts, bevor es mit den Befehlen in der Kategorie **alle Befehle** aufgefüllt wird.

Die `CMFCMousePropertyPage` -Klasse verwendet diese Methode, um das Doppelklick Ereignis-Listenfeld aufzufüllen.

##  <a name="fillcategoriescombobox"></a>Cmfctoolbarscustomizedialog:: fillkategoriescombobox

Füllt das angegebene `CComboBox` -Objekt mit dem Namen jeder Befehls Kategorie im Dialogfeld **Anpassen** auf.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parameter

*wndCategory*<br/>
vorgenommen Ein Verweis auf das `CComboBox` -Objekt, das aufgefüllt werden soll.

*bAddEmpty*<br/>
in Ein boolescher Wert, der angibt, ob dem Kombinations Feld Kategorien hinzugefügt werden sollen, für die keine Befehle vorhanden sind. Wenn dieser Parameter true ist, werden dem Kombinations Feld leere Kategorien hinzugefügt. Andernfalls werden keine leeren Kategorien hinzugefügt.

### <a name="remarks"></a>Hinweise

Diese Methode ähnelt der [cmfctoolbarscustomizedialog:: fillcategorieslistbox](#fillcategorieslistbox) -Methode, mit der Ausnahme, dass diese `CComboBox` Methode mit einem-Objekt funktioniert.

Diese Methode löscht den Inhalt des `CComboBox` Objekts nicht, bevor Sie aufgefüllt wird. Es wird sichergestellt, dass die Kategorie **alle Befehle** das endgültige Element im Kombinations Feld ist.

Sie können neue Befehls Kategorien hinzufügen, indem Sie die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode verwenden. Sie können den Namen einer vorhandenen Kategorie ändern, indem Sie die [cmfctoolbarscustomizedialog:: renamecategory](#renamecategory) -Methode verwenden.

Die `CMFCToolBarsKeyboardPropertyPage` - `CMFCKeyMapDialog` Klasse und die-Klasse verwenden diese Methode zum Kategorisieren von Tastatur Zuordnungen.

##  <a name="fillcategorieslistbox"></a>Cmfctoolbarscustomizedialog:: fillcategorieslistbox

Füllt das angegebene `CListBox` -Objekt mit dem Namen jeder Befehls Kategorie im Dialogfeld **Anpassen** auf.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parameter

*wndCategory*<br/>
vorgenommen Ein Verweis auf das `CListBox` -Objekt, das aufgefüllt werden soll.

*bAddEmpty*<br/>
in Ein boolescher Wert, der angibt, ob dem Listenfeld Kategorien hinzugefügt werden sollen, für die keine Befehle vorhanden sind. Wenn dieser Parameter true ist, werden dem Listenfeld leere Kategorien hinzugefügt. Andernfalls werden keine leeren Kategorien hinzugefügt.

### <a name="remarks"></a>Hinweise

Diese Methode ähnelt der [cmfctoolbarscustomizedialog:: fillcategoriescombobox](#fillcategoriescombobox) -Methode, mit der Ausnahme, dass diese `CListBox` Methode mit einem-Objekt funktioniert.

Diese Methode löscht den Inhalt des `CListBox` Objekts nicht, bevor Sie aufgefüllt wird. Dadurch wird sichergestellt, dass es sich bei der Kategorie **alle Befehle** um das letzte Element im Listenfeld handelt.

Sie können neue Befehls Kategorien hinzufügen, indem Sie die [cmfctoolbarscustomizedialog:: AddButton](#addbutton) -Methode verwenden. Sie können den Namen einer vorhandenen Kategorie ändern, indem Sie die [cmfctoolbarscustomizedialog:: renamecategory](#renamecategory) -Methode verwenden.

Die `CMFCToolBarsCommandsPropertyPage` -Klasse verwendet diese Methode, um die Liste der Befehle anzuzeigen, die jeder Befehls Kategorie zugeordnet sind.

##  <a name="getcommandname"></a>Cmfctoolbarscustomizedialog:: getcommandname

Ruft den Namen ab, der der angegebenen Befehls-ID zugeordnet ist.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die ID des abzurufenden Befehls.

### <a name="return-value"></a>Rückgabewert

Der Name, der der angegebenen Befehls-ID zugeordnet ist, oder NULL, wenn der Befehl nicht vorhanden ist.

##  <a name="getcountincategory"></a>Cmfctoolbarscustomizedialog:: getzählcategory

Ruft die Anzahl der Elemente in der angegebenen Liste ab, die über eine angegebene Text Bezeichnung verfügen.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parameter

*lpszItemName*<br/>
in Die zu Übereinstimmungs Text Bezeichnung.

*lstCommands*<br/>
in Ein Verweis auf eine Liste, die `CMFCToolBarButton` -Objekte enthält.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der bereitgestellten Liste, deren Text Bezeichnung *lpszitemname*ist.

### <a name="remarks"></a>Hinweise

Jedes Element in der Liste der bereitgestellten Objekte muss vom `CMFCToolBarButton`Typ sein. Diese Methode vergleicht *lpszitemname* mit dem [cmfctoolbarbutton:: m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) -Datenmember.

##  <a name="getflags"></a>Cmfctoolbarscustomizedialog:: GetFlags

Ruft den Satz von Flags ab, die das Verhalten des Dialog Felds beeinflussen.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Rückgabewert

Der Satz von Flags, die das Verhalten des Dialog Felds beeinflussen.

### <a name="remarks"></a>Hinweise

Diese Methode ruft den Wert des *uiflags* -Parameters ab, der an den-Konstruktor übergeben wird. Der Rückgabewert kann einen oder mehrere der folgenden Werte aufweisen:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Ermöglicht es dem Benutzer, die Schatten Darstellung des Menüs anzugeben.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Ermöglicht es dem Benutzer anzugeben, ob Text Bezeichnungen unterhalb der Symbolleisten-Schaltflächen Bilder angezeigt werden.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Ermöglicht es dem Benutzer, den Menü Animationsstil anzugeben.  |
|AFX_CUSTOMIZE_NOHELP|Entfernt die Schaltfläche Hilfe aus dem Dialogfeld Anpassung.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Aktiviert den visuellen WS_EX_CONTEXTHELP-Stil.  |
|AFX_CUSTOMIZE_NOTOOLS|Entfernt die Seite **Tools** aus dem Dialogfeld Anpassung. Dieses Flag ist gültig, wenn die Anwendung die `CUserToolsManager` -Klasse verwendet.  |
|AFX_CUSTOMIZE_MENUAMPERS|Ermöglicht es, dass Schaltflächen Beschriftungen das kaufmännische und **&** -Zeichen () enthalten.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Entfernt die Option **große Symbole** aus dem Dialogfeld Anpassung.  |

Weitere Informationen zum visuellen Stil von WS_EX_CONTEXTHELP finden Sie unter [Erweiterte Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

##  <a name="onafterchangetool"></a>Cmfctoolbarscustomizedialog:: onafterchangetool

Reagiert auf eine Änderung in einem Benutzer Tool unmittelbar nach dem auftreten.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parameter

*pSelTool*<br/>
[in, out] Ein Zeiger auf das User Tool-Objekt, das geändert wurde.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer die Eigenschaften eines benutzerdefinierten Tools ändert. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer von `CMFCToolBarsCustomizeDialog` abgeleiteten Klasse, um die Verarbeitung nach einer Änderung an einem Benutzer Tool auszuführen.

##  <a name="onassignkey"></a>Cmfctoolbarscustomizedialog:: onzuzutragkey

Überprüft Tastenkombinationen, wenn Sie von einem Benutzer definiert werden.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parameter

*pAccel*<br/>
[in, out] Ein Zeiger auf die vorgeschlagene Tastatur Zuordnung, die als [Accel](/windows/win32/api/winuser/ns-winuser-accel) -Struktur ausgedrückt wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Schlüssel zugewiesen werden kann, oder false, wenn der Schlüssel nicht zugewiesen werden kann. Die Standard Implementierung gibt immer true zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um zusätzliche Verarbeitungsschritte auszuführen, wenn ein Benutzer eine neue Tastenkombination zuweist, oder um Tastenkombinationen zu überprüfen, die vom Benutzer definiert werden. Um zu verhindern, dass eine Verknüpfung zugewiesen wird, geben Sie false zurück. Sie sollten auch ein Meldungs Feld anzeigen oder den Benutzer über den Grund informieren, warum die Tastenkombination abgelehnt wurde.

##  <a name="onbeforechangetool"></a>Cmfctoolbarscustomizedialog:: onbeforechangetool

Führt eine benutzerdefinierte Verarbeitung durch, wenn eine Änderung an einem Benutzer Tool erfolgt, wenn der Benutzer eine Änderung anwendet.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parameter

*pSelTool*<br/>
[in, out] Ein Zeiger auf das User Tool-Objekt, das ersetzt werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode wird von Framework aufgerufen, wenn sich die Eigenschaften eines benutzerdefinierten Tools ändern. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben `OnBeforeChangeTool` Sie die-Methode in einer `CMFCToolBarsCustomizeDialog` Klasse, die von abgeleitet ist, wenn Sie die Verarbeitung durchführen möchten, bevor eine Änderung an einem Benutzer Tool stattfindet

##  <a name="onedittoolbarmenuimage"></a>Cmfctoolbarscustomizedialog:: onedittoolbarmenuimage

Startet einen Bild-Editor, damit ein Benutzer eine Symbolleisten-Schaltfläche oder ein Menü Element Symbol anpassen kann.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf das übergeordnete Fenster.

*bitmap*<br/>
in Ein Verweis auf ein Bitmap-Objekt, das bearbeitet werden soll.

*nBitsPerPixel*<br/>
in Bitmap-Farbauflösung in Bits pro Pixel.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Commit für eine Änderung ausgeführt wird. andernfalls false. Die Standard Implementierung zeigt ein Dialogfeld an und gibt true zurück, wenn der Benutzer auf **OK**klickt, oder false, wenn der Benutzer auf **Abbrechen** oder auf die Schaltfläche **Schließen** klickt.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn der Benutzer den Bild-Editor ausführt. Die Standard Implementierung zeigt das Dialogfeld [cmfcimageeditordialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md) an. Über `OnEditToolbarMenuImage` schreiben in einer abgeleiteten Klasse, um einen benutzerdefinierten Bild-Editor zu verwenden.

##  <a name="oninitdialog"></a>Cmfctoolbarscustomizedialog:: OnInitDialog

Überschreibt, um die Eigenschaften Blatt Initialisierung zu erweitern.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des Aufrufs der [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) -Methode.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird die Basisklassen Implementierung [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)erweitert, indem die Schaltfläche **Schließen** angezeigt wird, indem sichergestellt wird, dass das Dialogfeld der aktuellen Bildschirmgröße entspricht, und indem die Schaltfläche **Hilfe** in die linke untere Ecke verschoben wird. des Dialog Felds.

##  <a name="oninittoolspage"></a>Cmfctoolbarscustomizedialog:: oninittoolspage

Verarbeitet die Benachrichtigung vom Framework, dass die Seite Extras gerade initialisiert werden soll.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um diese Benachrichtigung zu verarbeiten.

##  <a name="postncdestroy"></a>Cmfctoolbarscustomizedialog::P ostncdestroy

Wird von Framework aufgerufen, nachdem das Fenster zerstört wurde.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung, `CPropertySheet::PostNcDestroy`, indem die Anwendung im vorherigen Modus wieder hergestellt wird.

Die [cmfctoolbarscustomizedialog:: Create](#create) -Methode versetzt die Anwendung in einen speziellen Modus, durch den der Benutzer auf Anpassungs Aufgaben beschränkt wird.

##  <a name="removebutton"></a>Cmfctoolbarscustomizedialog:: RemoveButton

Entfernt die Schaltfläche mit der angegebenen Befehls-ID aus der angegebenen Kategorie oder aus allen Kategorien.

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>Parameter

*uiCategoryId*<br/>
in Gibt die Kategorie-ID an, aus der die Schaltfläche entfernt werden soll.

*uiCmdId*<br/>
in Gibt die Befehls-ID der Schaltfläche an.

*lpszCategory*<br/>
in Gibt den Namen der Kategorie an, aus der die Schaltfläche entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index der entfernten Schaltfläche oder-1, wenn die angegebene Befehls-ID in der angegebenen Kategorie nicht gefunden wurde. Wenn *uicategoryid* den Wert-1 hat, ist der Rückgabewert 0.

### <a name="remarks"></a>Hinweise

Um eine Schaltfläche aus allen Kategorien zu entfernen, müssen Sie die erste Überladung dieser Methode aufrufen und *uicategoryid* auf-1 festlegen.

##  <a name="renamecategory"></a>Cmfctoolbarscustomizedialog:: renamecategory

Benennt eine Kategorie im Listenfeld der Kategorien auf der Seite **Befehle** um.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parameter

*lpszCategoryOld*<br/>
in Der zu ändernde Name der Kategorie.

*lpszCategoryNew*<br/>
in Der neue Kategoriename.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

Der Kategoriename muss eindeutig sein.

##  <a name="replacebutton"></a>Cmfctoolbarscustomizedialog:: replacebutton

Ersetzt eine Symbolleisten-Schaltfläche im Listenfeld der Befehle auf der Seite **Befehle** .

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Gibt den Befehl der zu ersetzenden Schaltfläche an.

*button*<br/>
in Ein konstanter Verweis auf das Symbolleisten-Schalt **Flächen** Objekt, das die alte Schaltfläche ersetzt.

### <a name="remarks"></a>Hinweise

Wenn [cmfctoolbarscustomizedialog:: AddMenu](#addmenu), [cmfctoolbarscustomizedialog:: addmenucommands](#addmenucommands)oder [cmfctoolbarscustomizedialog:: AddToolBar](#addtoolbar) einen Befehl auf der Seite **Befehle** hinzufügt, wird dieser Befehl in der Form [eines Cmfctoolbarbutton-Klassen](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt (oder ein [cmfctoolbarmenubutton-Klassen](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt für ein Menü Element, das ein durch `AddMenuCommands`hinzugefügtes Untermenü enthält). Das Framework ruft auch diese drei Methoden auf, um Befehle automatisch hinzuzufügen. Wenn Sie möchten, dass ein Befehl stattdessen durch einen abgeleiteten Typ dargestellt wird `ReplaceButton` , können Sie den Befehl verwenden und eine Schaltfläche des abgeleiteten Typs übergeben.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `ReplaceButton` -Methode in `CMFCToolBarsCustomizeDialog` der-Klasse verwendet wird. Dieser Code Ausschnitt ist Teil des [Visual Studio-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

##  <a name="setusercategory"></a>Cmfctoolbarscustomizedialog:: setusercategory

Gibt an, welche Kategorie in der Liste der Kategorien auf der Seite **Befehle** die Kategorie Benutzer ist. Sie müssen diese Funktion aufrufen, bevor Sie [cmfctoolbarscustomizedialog:: Create](#create)aufrufen.

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parameter

*lpszCategory*<br/>
in Der Name der Kategorie.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Die Einstellung für die Benutzer Kategorie wird zurzeit vom Framework nicht verwendet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)
