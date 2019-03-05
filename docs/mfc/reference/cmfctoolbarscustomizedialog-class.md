---
title: CMFCToolBarsCustomizeDialog-Klasse
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
ms.openlocfilehash: e4aaede3eb2d5c922c196e2bdfbbe533c4e65e47
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295031"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog-Klasse

Ein nicht modales Dialogfeld im Registerformat ( [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)), die den Benutzer die Symbolleisten, Menüs, Tastenkombinationen in Visual Studio, benutzerdefinierte Tools und visuellen Stil in einer Anwendung anpassen können. In der Regel greift der Benutzer durch Auswählen von **Anpassen** im Menü **Tools** auf dieses Dialogfeld zu.

Die **anpassen** Dialogfeld verfügt über sechs Registerkarten: **Befehle**, **Symbolleisten**, **Tools**, **Tastatur**, **Menü**, und **Optionen**.

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
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Fügt eine Symbolleisten-Schaltfläche in der Liste der Befehle auf den **Befehle** Seite|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Lädt ein Menü von Ressourcen und Aufrufe [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf die Liste der Befehle in diesem Menü hinzufügen der **Befehle** Seite.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Lädt ein Menü von Ressourcen und Aufrufe [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf die Liste der Befehle in diesem Menü hinzufügen der **Befehle** Seite.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Lädt eine Symbolleiste aus den Ressourcen. Klicken Sie dann für jeden Befehl in den Menü-Aufrufen die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode, um auf eine Schaltfläche in der Liste der Befehle legen Sie die **Befehle** Seite in der angegebenen Kategorie.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|Zeigt die **Anpassung** Dialogfeld.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Für zukünftige Verwendung reserviert.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Aktiviert oder deaktiviert wird, Erstellen neuer Symbolleisten mithilfe der **anpassen** Dialogfeld.|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Füllt die angegebene `CListBox` Objekt mit den Befehlen in der **alle Befehle** Kategorie.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Füllt die angegebene `CComboBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Füllt die angegebene `CListBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.|
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Ruft den Namen, der der angegebenen Befehls-ID zugeordnet ist.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Ruft die Anzahl der Elemente in der angegebenen Liste mit einer bestimmten textbezeichnung ab.|
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Ruft den Satz von Flags, die das Verhalten des Dialogfelds beeinflussen.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Startet Sie einen Bild-Editor, sodass ein Benutzer eine Schaltfläche oder Element Symbol auf der Symbolleiste anpassen kann.|
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Außerkraftsetzungen, um das Blatt eigenschafteninitialisierung zu erweitern. (Overrides [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Vom Framework aufgerufen, nachdem das Fenster zerstört wurde. (Überschreibt `CPropertySheet::PostNcDestroy`.)|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit den angegebenen Befehls-ID aus der angegebenen Kategorie oder aus allen Kategorien.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Benennt eine Kategorie im Listenfeld der Kategorien auf die **Befehle** Registerkarte.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Ersetzt eine Schaltfläche in der Liste der Befehle auf den **Befehle** Registerkarte mit einem neuen Objekt der Symbolleisten-Schaltfläche.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Eine Kategorie der Liste der Kategorien, die auf angezeigt wird, fügt die **Befehle** Registerkarte.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Wird aufgerufen, durch das Framework, um zu bestimmen, ob die Liste der benutzerdefinierten Tools gültig ist.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Vom Framework aufgerufen, wenn die Eigenschaften eines benutzerdefinierten Tools ändern.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Bestimmt, ob eine Aktion eine angegebene Tastenkombination zugewiesen werden kann.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Bestimmt, ob ein benutzerdefiniertes Tool geändert werden kann.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Vom Framework aufgerufen, wenn der Benutzer wählt die **Tools** Registerkarte angefordert wird.|

## <a name="remarks"></a>Hinweise

Zum Anzeigen der **anpassen** Dialogfeld erstellen eine `CMFCToolBarsCustomizeDialog` Objekt, und rufen die [CMFCToolBarsCustomizeDialog::Create](#create) Methode.

Während der **anpassen** Dialogfeld aktiv ist, werden die Anwendung funktioniert in einem speziellen Modus, die den Benutzer Aufgaben zur Anpassung beschränkt.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCToolBarsCustomizeDialog` -Klasse. Das Beispiel zeigt, wie eine Symbolleisten-Schaltfläche im Listenfeld der Befehle auf ersetzt der **Befehle** Seite, ermöglichen das Erstellen neuer Symbolleisten mithilfe der **anpassen** Dialogfeld, und die Anzeige der  **Anpassung** Dialogfeld. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxToolBarsCustomizeDialog.h

##  <a name="addbutton"></a>  CMFCToolBarsCustomizeDialog::AddButton

Fügt eine Symbolleisten-Schaltfläche in der Liste der Befehle auf den **Befehle** Seite.

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
[in] Gibt die Kategorie-ID, in dem die Schaltfläche eingefügt werden soll.

*button*<br/>
[in] Gibt die Schaltfläche zum Einfügen.

*iInsertBefore*<br/>
[in] Gibt den nullbasierten Index des eine Symbolleisten-Schaltfläche, die vor der die Schaltfläche eingefügt wird.

*lpszCategory*<br/>
[in] Gibt die Kategoriezeichenfolge, um die Schaltfläche eingefügt werden soll.

### <a name="remarks"></a>Hinweise

Die `AddButton` Methode Schaltflächen mit den Standardbefehls-IDs (z. B. ID_FILE_MRU_FILE1) ignoriert, Befehle, sind nicht zulässig (finden Sie unter [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) und das Pseudoupdate von Schaltflächen.

Diese Methode erstellt ein neues Objekt des gleichen Typs wie `button` (in der Regel eine [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)) mit der Common Language Runtime-Klasse der Schaltfläche. Es ruft dann [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) Datenmember der Schaltfläche zu kopieren und fügt Sie die Kopie in der angegebenen Kategorie.

Wenn die Schaltfläche "neue" eingefügt wird, erhält es die `OnAddToCustomizePage` Benachrichtigung.

Wenn `iInsertBefore` ist-1. die Schaltfläche mit der an die Liste der Kategorien angefügt wird; andernfalls wird es vor dem Element mit dem angegebenen Index eingefügt.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `AddButton` Methode der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [Slider-Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu

Lädt ein Menü von Ressourcen und Aufrufe [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf die Liste der Befehle in diesem Menü hinzufügen der **Befehle** Seite.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parameter

*uiMenuResId*<br/>
[in] Gibt die Ressourcen-ID zum Laden eines Menüs an.

### <a name="return-value"></a>Rückgabewert

True, wenn ein Menü erfolgreich hinzugefügt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Im Aufruf von `AddMenuCommands`, *bPopup* ist "false". Diese Methode ist daher nicht Menüelemente hinzufügen, die Untermenüs zur Liste der Befehle enthalten. Diese Methode die Liste der Befehle der Menüelemente in die Untermenüs hinzufügen.

##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands

Fügt Elemente der Liste der Befehle in der **Befehle** Seite, um alle Elemente im angegebenen Menü darstellt.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parameter

*pMenu*<br/>
[in] Ein Zeiger auf das hinzuzufügende CMenu-Objekt.

*bPopup*<br/>
[in] Gibt an, ob die Popup-Menüelemente zur Liste der Befehle einfügen.

*lpszCategory*<br/>
[in] Der Name der Kategorie, die Sie im Menü Einfügen.

*lpszMenuPath*<br/>
[in] Ein Präfix, das den Namen hinzugefügt wird, wenn der Befehl, in angezeigt wird, der **alle Kategorien** Liste.

### <a name="remarks"></a>Hinweise

Die `AddMenuCommands` Methode durchläuft alle Menüelemente *pMenu*. Für jedes Menü, das nicht über ein Untermenü enthält, diese Methode erstellt eine [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) -Objekt und ruft die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode, um dem Menüelement, das als eine Symbolleiste hinzufügen um die Liste der Befehle in auf die Schaltfläche der **Befehle** Seite. In diesem Prozess werden die Trennzeichen ignoriert.

Wenn *bPopup* "true" wird für jedes Menü, das ein Untermenü enthält diese Methode erstellt eine [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) -Objekt und fügt es in der Liste der Befehle, durch den Aufruf `AddButton`. Andernfalls werden die Menüelemente, die Untermenüs enthalten nicht in der Liste der Befehle angezeigt. In beiden Fällen bei `AddMenuCommands` findet ein Menüelement mit einem Untermenü er ruft rekursiv auf, die Übergabe eines Zeigers auf das Untermenü, als die *pMenu* Parameter und die Bezeichnung des Untermenüs zum Anfügen *LpszMenuPath*.

##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar

Lädt eine Symbolleiste aus den Ressourcen. Klicken Sie dann für jeden Befehl in den Menü-Aufrufen die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode, um auf eine Schaltfläche in der Liste der Befehle legen Sie die **Befehle** Seite in der angegebenen Kategorie.

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
[in] Gibt an, die Ressourcen-ID der Kategorie, um die Symbolleiste hinzugefügt.

*uiToolbarResId*<br/>
[in] Gibt an, die Ressourcen-ID, einer Symbolleiste die Liste der Befehle, dessen Befehle eingefügt werden.

*lpszCategory*<br/>
[in] Gibt den Namen der Kategorie, in der Symbolleiste hinzufügen.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `AddToolBar` -Methode in der die `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Hinweise

Das Steuerelement, das verwendet wird, um jeden Befehl zu repräsentieren ist eine [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt. Nachdem Sie auf die Symbolleiste hinzufügen, können Sie die Schaltfläche mit den durch ein Steuerelement eines abgeleiteten Typs ersetzen, durch den Aufruf [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).

##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity

Überprüft die Gültigkeit der Liste der Benutzertools.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parameter

*lstTools*<br/>
[in] Die Liste der benutzerdefinierten Tools, um zu überprüfen.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Liste der benutzerdefinierten Tools gültig ist. andernfalls "false". Immer die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um die Gültigkeit der Objekte zu überprüfen, die benutzerdefinierte Tools, die vom darstellen [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).

Überschreiben der `CheckToolsValidity` Methode in einer Klasse abgeleitet `CMFCToolBarsCustomizeDialog` sollten Sie die Tools zu überprüfen, bevor der Benutzer das Dialogfeld geschlossen wird. Wenn diese Methode FALSE zurückgibt, wenn der Benutzer, entweder klickt die **schließen** Schaltfläche in der Ecke oben rechts im Dialogfeld "oder" die Schaltfläche **schließen** in der unteren rechten Ecke des Dialogfelds, das Dialogfeld Zeigt die **Tools** Registerkarte schließen. Wenn diese Methode "false" zurückgibt, klickt der Benutzer eine Registerkarte, um eine verlassen die **Tools** Registerkarte, die Navigation erfolgt nicht. Ein entsprechendes Meldungsfenster an, um die Benutzer über das Problem zu informieren, die Validierung fehlschlägt verursacht wird, sollte angezeigt werden.

##  <a name="cmfctoolbarscustomizedialog"></a>  CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

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
[in] Ein Zeiger auf den übergeordneten Rahmen. Dieser Parameter darf nicht NULL sein.

*bAutoSetFromMenus*<br/>
[in] Ein boolescher Wert, der angibt, ob die Befehle im Menü auf alle Menüs zur Liste der Befehle hinzufügen der **Befehle** Seite. Wenn dieser Parameter TRUE ist, werden die Befehle im Menü hinzugefügt. Andernfalls werden die Menübefehle nicht hinzugefügt werden.

*uiFlags*<br/>
[in] Eine Kombination von Flags, die das Verhalten des Dialogfelds beeinflussen. Dieser Parameter kann eine oder mehrere der folgenden Werte sein:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
[in] Ein Zeiger auf eine Liste der `CRuntimeClass` Objekten, die zusätzliche benutzerdefinierte Seiten angeben.

### <a name="remarks"></a>Hinweise

Die *PlistCustomPages* Parameter verweist auf die Liste der `CRuntimeClass` Objekten, die zusätzliche benutzerdefinierte Seiten angeben. Der Konstruktor fügt mehr Seiten an das Dialogfeld mithilfe der [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) Methode. Finden Sie im Beispiel CustomPages ein Beispiel für die mehr Seiten fügt die **anpassen** Dialogfeld.

Weitere Informationen zu den Werten, die Sie übergeben können die *UiFlags* Parameter finden Sie unter [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [Beispiel für benutzerdefinierte Seiten](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create

Zeigt die **Anpassung** Dialogfeld.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Eigenschaftenblatt für die Anpassung wurde erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie die `Create` Methode nur, nachdem Sie vollständig der Klasse initialisieren.

##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars

Aktiviert oder deaktiviert wird, Erstellen neuer Symbolleisten mithilfe der **anpassen** Dialogfeld.

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] True, um die benutzerdefinierten Symbolleisten aktivieren. "False", um Symbolleisten zu deaktivieren.

### <a name="remarks"></a>Hinweise

Wenn *bAktivieren* ist "true", die **neu**, **umbenennen** und **löschen** Schaltflächen werden angezeigt, auf die **Symbolleisten** Seite ".

Standardmäßig oder wenn *bAktivieren* FALSE ist, diese Schaltflächen nicht angezeigt, und der Benutzer keine neue Symbolleisten definieren.

##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList

Füllt die angegebene `CListBox` Objekt mit den Befehlen in der **alle Befehle** Kategorie.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parameter

*wndListOfCommands*<br/>
[out] Ein Verweis auf die `CListBox` zu füllende Objekt.

### <a name="remarks"></a>Hinweise

Die **alle Befehle** Kategorie enthält die Befehle aller Kategorien. Die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode fügt den Befehl, der die angegebene Schaltfläche zugeordnet ist die **alle Befehle** Kategorie für Sie.

Diese Methode löscht den Inhalt des bereitgestellten `CListBox` Objekt vor dem Auffüllen der Gruppe mit den Befehlen in der **alle Befehle** Kategorie.

Die `CMFCMousePropertyPage` Klasse verwendet diese Methode zum Auffüllen der im Listenfeld Ereignis doppelklicken.

##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox

Füllt die angegebene `CComboBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parameter

*wndCategory*<br/>
[out] Ein Verweis auf die `CComboBox` zu füllende Objekt.

*bAddEmpty*<br/>
[in] Ein boolescher Wert, der angibt, ob Kategorien im Kombinationsfeld, denen keine Befehle hinzugefügt. Wenn dieser Parameter werden im Kombinationsfeld "true" werden leere Kategorien hinzugefügt. Andernfalls werden leere Kategorien nicht hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Diese Methode entspricht der [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) Methode mit dem Unterschied, dass diese Methode funktioniert, mit einem `CComboBox` Objekt.

Diese Methode löscht nicht den Inhalt der `CComboBox` Objekt vor dem Auffüllen. Es wird sichergestellt, dass die **alle Befehle** Kategorie ist das letzte Element im Kombinationsfeld.

Sie können neue Befehlskategorien hinzufügen, indem Sie mit der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode. Sie können den Namen einer vorhandenen Kategorie ändern, mit der [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) Methode.

Die `CMFCToolBarsKeyboardPropertyPage` und `CMFCKeyMapDialog` Klassen, die diese Methode verwenden, um die tastaturzuordnungen zu kategorisieren.

##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox

Füllt die angegebene `CListBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parameter

*wndCategory*<br/>
[out] Ein Verweis auf die `CListBox` zu füllende Objekt.

*bAddEmpty*<br/>
[in] Ein boolescher Wert, der angibt, ob Kategorien in die Liste, denen keine Befehle hinzugefügt. Wenn dieser Parameter werden im Listenfeld "true" werden leere Kategorien hinzugefügt. Andernfalls werden leere Kategorien nicht hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Diese Methode entspricht der [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) Methode mit dem Unterschied, dass diese Methode funktioniert, mit einem `CListBox` Objekt.

Diese Methode löscht nicht den Inhalt der `CListBox` Objekt vor dem Auffüllen. Es wird sichergestellt, dass die **alle Befehle** Kategorie ist das letzte Element im Listenfeld.

Sie können neue Befehlskategorien hinzufügen, indem Sie mit der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode. Sie können den Namen einer vorhandenen Kategorie ändern, mit der [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) Methode.

Die `CMFCToolBarsCommandsPropertyPage` Klasse diese Methode verwendet, um die Liste der Befehle anzuzeigen, die jeder Befehlskategorie zugeordnet ist.

##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName

Ruft den Namen, der der angegebenen Befehls-ID zugeordnet ist.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die ID des Befehls, der abgerufen werden.

### <a name="return-value"></a>Rückgabewert

Der Name, der mit der angegebenen Befehls-ID oder NULL, verknüpft ist, wenn der Befehl nicht vorhanden ist.

##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory

Ruft die Anzahl der Elemente in der angegebenen Liste mit einer bestimmten textbezeichnung ab.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parameter

*lpszItemName*<br/>
[in] Die textbezeichnung entsprechend.

*lstCommands*<br/>
[in] Ein Verweis auf eine Liste mit `CMFCToolBarButton` Objekte.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der bereitgestellten Liste entspricht, dessen Text-Bezeichnung *LpszItemName*.

### <a name="remarks"></a>Hinweise

Jedes Element in der angegebenen Liste muss vom Typ `CMFCToolBarButton`. Diese Methode vergleicht *LpszItemName* mit der [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) -Datenmember.

##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags

Ruft den Satz von Flags, die das Verhalten des Dialogfelds beeinflussen.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Rückgabewert

Der Satz von Flags, die das Verhalten des Dialogfelds beeinflussen.

### <a name="remarks"></a>Hinweise

Diese Methode ruft den Wert der *UiFlags* Parameter, an den Konstruktor übergeben wird. Der Rückgabewert kann es sich um eine oder mehrere der folgenden Werte sein:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Ermöglicht dem Benutzer die Schatten-Darstellung des Menüs an.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Ermöglicht dem Benutzer an, ob Beschriftungen unterhalb der Symbolleisten-Schaltflächen angezeigt werden.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Ermöglicht den Benutzer, den im Menü Animationsstil ein Stil anzugeben.  |
|AFX_CUSTOMIZE_NOHELP|Entfernt die Hilfeschaltfläche im Dialogfeld "anpassen".  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Aktiviert den visuellen Stil des WS_EX_CONTEXTHELP an.  |
|AFX_CUSTOMIZE_NOTOOLS|Entfernt die **Tools** Seite im Dialogfeld "anpassen". Dieses Flag ist gültig, wenn Ihre Anwendung verwendet die `CUserToolsManager` Klasse.  |
|AFX_CUSTOMIZE_MENUAMPERS|Ermöglicht die schaltflächenbeschriftungen, enthält das kaufmännische und-Zeichen ( **&**) Zeichen.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Entfernt die **große Symbole** Option im Dialogfeld "anpassen".  |

Weitere Informationen zu den visuellen Stil des WS_EX_CONTEXTHELP, finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Reagiert auf eine Änderung in ein Tool, sofort nach dem auftreten.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parameter

*pSelTool*<br/>
[in, out] Ein Zeiger auf die Benutzer-Tool-Objekt, das geändert wurde.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer die Eigenschaften eines benutzerdefinierten Tools ändert. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer Klasse abgeleitet `CMFCToolBarsCustomizeDialog` zu Verarbeitung auszuführen, nachdem eine Änderung ein Tool vorgenommen wird.

##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey

Tastenkombinationen in Visual Studio überprüft, wie ein Benutzer, die sie definiert.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parameter

*pAccel*<br/>
[in, out] Zeiger auf die vorgeschlagene Tastatur-speicherzuweisung, die als ausgedrückt ist eine [ACCELERATION](/windows/desktop/api/winuser/ns-winuser-tagaccel) Struktur.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Schlüssel zugewiesen oder "false" werden kann, wenn der Schlüssel kann nicht zugewiesen werden. Immer die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Ausführen der zusätzliche Verarbeitung, wenn ein Benutzer weist eine neue Tastenkombination zum Überprüfen von Tastenkombinationen in Visual Studio als Benutzer definiert werden. Um zu verhindern, dass eine Tastenkombination zugewiesen wird, geben Sie "false" zurück. Sie sollten auch ein Meldungsfenster anzeigt, oder andernfalls informiert den Benutzer über den Grund, warum die Tastenkombination abgelehnt wurde.

##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool

Führt die benutzerdefinierte Verarbeitung, wenn eine Änderung an ein Tool, wenn der Benutzer ist, zu eine Änderung zu übernehmen.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parameter

*pSelTool*<br/>
[in, out] Ein Zeiger auf das Tool-Benutzerobjekt, die ersetzt werden.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn die Eigenschaften eines benutzerdefinierten Tools geändert wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben der `OnBeforeChangeTool` Methode in einer Klasse abgeleitet `CMFCToolBarsCustomizeDialog` Wenn Verarbeitung auszuführen, bevor eine Änderung ein Tool wie z. B. das Freigeben von Ressourcen vorgenommen wird, werden sollen, *pSelTool* verwendet.

##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage

Startet Sie einen Bild-Editor, sodass ein Benutzer eine Schaltfläche oder Element Symbol auf der Symbolleiste anpassen kann.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster.

*bitmap*<br/>
[in] Ein Verweis auf ein Bitmap-Objekt, das bearbeitet werden.

*nBitsPerPixel*<br/>
[in] Bitmap-farbauflösung, in Bits pro Pixel.

### <a name="return-value"></a>Rückgabewert

True, wenn eine Änderung ein Commit ausgeführt wird. andernfalls "false". Die Standardimplementierung wird ein Dialogfeld angezeigt, und gibt TRUE zurück, wenn der Benutzer klickt **OK**, bzw. FALSE, wenn der Benutzer klickt **Abbrechen** oder **schließen** Schaltfläche.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn der Benutzer die Bild-Editor ausgeführt wird. Zeigt die Standard-Implementierung [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md) Dialogfeld. Außer Kraft setzen `OnEditToolbarMenuImage` in einer abgeleiteten Klasse mit einem benutzerdefinierten Bild-Editor.

##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog

Außerkraftsetzungen, um das Blatt eigenschafteninitialisierung zu erweitern.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des Aufrufs der [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) Methode.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), durch Anzeigen der **schließen** Schaltfläche, indem Sie sicherstellen, dass Sie das Dialogfeld die vorgegebene Bildschirmgröße passt, und Verschieben der **Hilfe** Schaltfläche auf der unteren linken Ecke des Dialogfelds.

##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage

Verarbeitet die Benachrichtigung aus dem Framework, die die **Tools** Seite ist, initialisiert werden soll.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse diese Benachrichtigung verarbeitet.

##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy

Vom Framework aufgerufen, nachdem das Fenster zerstört wurde.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung `CPropertySheet::PostNcDestroy`, indem Sie die Anwendung in den vorherigen Modus wiederherstellen.

Die [CMFCToolBarsCustomizeDialog::Create](#create) Methode wird die Anwendung in einem speziellen Modus, die den Benutzer Aufgaben zur Anpassung beschränkt.

##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton

Entfernt die Schaltfläche mit den angegebenen Befehls-ID aus der angegebenen Kategorie oder aus allen Kategorien.

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
[in] Gibt die Kategorie-ID aus dem die Schaltfläche entfernt.

*uiCmdId*<br/>
[in] Gibt die Befehls-ID der Schaltfläche an.

*lpszCategory*<br/>
[in] Gibt den Namen der Kategorie aus der die Schaltfläche entfernt.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Schaltfläche mit den entfernten oder -1, wenn die angegebene Befehls-ID in der angegebenen Kategorie nicht gefunden wurde. Wenn *UiCategoryId* -1 ist, wird 0 zurückgegeben.

### <a name="remarks"></a>Hinweise

Um eine Schaltfläche aus allen Kategorien zu entfernen, rufen Sie die erste Überladung dieser Methode, und legen *UiCategoryId* -1.

##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory

Benennt eine Kategorie im Listenfeld der Kategorien auf die **Befehle** Seite.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parameter

*lpszCategoryOld*<br/>
[in] Der Kategoriename ändern.

*lpszCategoryNew*<br/>
[in] Der neue Kategoriename.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Kategoriename muss eindeutig sein.

##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton

Ersetzt eine Symbolleisten-Schaltfläche im Listenfeld der Befehle auf den **Befehle** Seite.

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Gibt den Befehl an der Schaltfläche ersetzt werden.

*button*<br/>
[in] Ein **const** Verweis auf die Symbolleiste Button-Objekt, das die Schaltfläche mit den alten ersetzt.

### <a name="remarks"></a>Hinweise

Wenn [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), oder [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) Fügt eine Befehl der **Befehle** Seite in Form von Befehl ist ein [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt (oder ein [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt für ein Menü Element, das ein Untermenü hinzugefügt, indem enthält `AddMenuCommands`). Das Framework ruft auch diese drei Methoden zum automatischen Hinzufügen von Befehlen. Wenn Sie einen Befehl aus, um stattdessen von einem abgeleiteten Typ dargestellt werden soll, rufen Sie `ReplaceButton` und eine Schaltfläche des abgeleiteten Typs übergeben.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `ReplaceButton` -Methode in der die `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory

Gibt die Kategorie in der Liste der Kategorien auf die **Befehle** Seite ist, der die Kategorie. Sie müssen diese Funktion aufrufen, vor dem Aufruf [CMFCToolBarsCustomizeDialog::Create](#create).

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parameter

*lpszCategory*<br/>
[in] Der Name der Kategorie.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die benutzereinstellung für die Kategorie ist nicht aktuell vom Framework verwendet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)
