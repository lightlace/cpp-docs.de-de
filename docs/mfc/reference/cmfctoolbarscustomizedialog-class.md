---
title: Klasse CMFCToolBarsCustomizeDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog class
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 069498d958dd5d9c3befc2a179c67636ce0ac9ae
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog-Klasse
Ein Dialogfeld ohne Modus Registerkarte ( [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)), die den Benutzer die Symbolleisten, Menüs, Tastenkombinationen, benutzerdefinierte Tools und Stil in einer Anwendung anpassen können. In der Regel greift der Benutzer durch Auswählen von **Anpassen** im Menü **Tools** auf dieses Dialogfeld zu.  
  
 Die **anpassen** Dialogfeld verfügt über sechs Registerkarten: **Befehle**, **Symbolleisten**, **Tools**, **Tastatur**, **Menü**, und **Optionen**.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Erstellt ein `CMFCToolBarsCustomizeDialog`-Objekt.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Fügt eine Symbolleisten-Schaltfläche in der Liste der Befehle auf der **Befehle** Seite|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Lädt ein Menü aus der Ressourcen und ruft [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf der Liste der Befehle auf das Menü hinzufügen die **Befehle** Seite.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Lädt ein Menü aus der Ressourcen und ruft [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf der Liste der Befehle auf das Menü hinzufügen die **Befehle** Seite.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Lädt eine Symbolleiste aus den Ressourcen. Klicken Sie dann für jeden Befehl in dem Menü Aufrufen der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode zum Einfügen einer Schaltfläche in der Liste der Befehle auf der **Befehle** Seite in der angegebenen Kategorie.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|Zeigt die **Anpassung** Dialogfeld.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Für zukünftige Verwendung reserviert.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Aktiviert oder deaktiviert das Erstellen neuer Symbolleisten mithilfe der **anpassen** Dialogfeld.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Füllt die angegebene `CListBox` -Objekt mit den Befehlen in der **alle Befehle** Kategorie.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Füllt die angegebene `CComboBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Füllt die angegebene `CListBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Ruft den Namen ab, der der angegebenen Befehls-ID zugeordnet ist.|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Ruft die Anzahl der Elemente in der Liste, die eine bestimmte Bezeichnung aufweisen.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|Ruft den Satz von Flags, die das Verhalten des Dialogfelds beeinflussen ab.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Starten Sie einen Bild-Editor, damit ein Benutzer auf einer Symbolleiste oder eines Symbols anpassen kann.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Außerkraftsetzungen, um die Initialisierung einer Eigenschaftenblatt zu erweitern. (Überschreibt [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Wird vom Framework aufgerufen, nachdem das Fenster zerstört wurde. (Überschreibt `CPropertySheet::PostNcDestroy`.)|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit der angegebenen Befehls-ID aus der angegebenen Kategorie oder aller Kategorien.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Benennt eine Kategorie im Listenfeld Kategorien in der **Befehle** Registerkarte.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Ersetzt eine Schaltfläche in der Liste der Befehle auf der **Befehle** Registerkarte durch ein neues Objekt der Symbolleisten-Schaltfläche.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Fügt eine Kategorie der Liste der Kategorien, die auf angezeigt wird, die **Befehle** Registerkarte.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Aufgerufen, um zu bestimmen, ob die Liste der benutzerdefinierten Tools gültig ist.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Wird vom Framework aufgerufen, wenn die Eigenschaften eines benutzerdefinierten Tools zu ändern.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Bestimmt, ob eine Aktion mit einer angegebenen Tastenkombination zugewiesen werden kann.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Bestimmt, ob ein benutzerdefiniertes Tool geändert werden kann.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Vom Framework aufgerufen, wenn der Benutzer die **Tools** Registerkarte angefordert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Anzeigen der **anpassen** Dialogfeld Erstellen einer `CMFCToolBarsCustomizeDialog` Objekt, und rufen die [CMFCToolBarsCustomizeDialog::Create](#create) Methode.  
  
 Während der **anpassen** Dialogfeld aktiv ist, die Anwendung funktioniert, in einem speziellen Modus, der den Benutzer Aufgaben zur Anpassung von beschränkt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarsCustomizeDialog` Klasse. Veranschaulicht, wie eine Symbolleisten-Schaltfläche im Listenfeld Befehle auf ersetzen die **Befehle** Seite, ermöglichen das Erstellen neuer Symbolleisten mithilfe der **anpassen** (Dialogfeld), und zeigen Sie die **Anpassung** Dialogfeld. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&4;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
 Fügt eine Symbolleisten-Schaltfläche in der Liste der Befehle auf der **Befehle** Seite.  
  
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
 [in] `uiCategoryId`  
 Gibt die Kategorie-ID in das die Schaltfläche eingefügt.  
  
 [in] `button`  
 Gibt die Schaltfläche einfügen.  
  
 [in] `iInsertBefore`  
 Gibt den nullbasierten Index des eine Symbolleisten-Schaltfläche, die vor der die Schaltfläche eingefügt wird.  
  
 [in] `lpszCategory`  
 Gibt die Kategoriezeichenfolge, um die Schaltfläche einzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Die `AddButton` -Methode ignoriert die Schaltflächen, die standard-Befehls-IDs (z. B. ID_FILE_MRU_FILE1), Befehle, sind nicht zulässig (finden Sie unter [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) und dummy-Schaltflächen.  
  
 Diese Methode erstellt ein neues Objekt des gleichen Typs als `button` (in der Regel eine [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)) mit der Common Language Runtime-Klasse der Schaltfläche. Es ruft dann [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) Datenmember der Schaltfläche Kopieren und die Kopie in der angegebenen Kategorie eingefügt.  
  
 Wenn die neue Schaltfläche eingefügt wird, erhält er die `OnAddToCustomizePage` Benachrichtigung.  
  
 Wenn `iInsertBefore`&1;, ist die Schaltfläche in die Liste der Kategorien angefügt wird; andernfalls wird er vor dem Element mit dem angegebenen Index eingefügt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddButton` Methode der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [Slider-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Slider&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 Lädt ein Menü aus der Ressourcen und ruft [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) auf der Liste der Befehle auf das Menü hinzufügen die **Befehle** Seite.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiMenuResId`  
 Gibt die Ressourcen-ID eines Menüs zu laden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Menü erfolgreich hinzugefügt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Aufruf von `AddMenuCommands`, `bPopup` ist `FALSE`. Diese Methode ist daher nicht Menüelemente hinzufügen, die Untermenüs zur Liste der Befehle enthalten. Diese Methode fügt die Elemente in den Untermenüs der Liste der Befehle.  
  
##  <a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 Fügt Elemente zur Liste der Befehle in der **Befehle** Seite, um alle Elemente im angegebenen Menü darstellen.  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Ein Zeiger auf das hinzuzufügende Objekt CMenu.  
  
 [in] `bPopup`  
 Gibt an, ob Popupmenüelemente zur Liste der Befehle einfügen.  
  
 [in] `lpszCategory`  
 Der Name der Kategorie, die Sie im Menü Einfügen.  
  
 [in] `lpszMenuPath`  
 Ein Präfix, das den Namen hinzugefügt wird, wenn der Befehl, in angezeigt wird, der **alle Kategorien** Liste.  
  
### <a name="remarks"></a>Hinweise  
 Die `AddMenuCommands` Methode durchläuft alle Menüelemente des `pMenu`. Für jedes Menüelement, das nicht über ein Untermenü enthält, erstellt diese Methode eine [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) -Objekt und ruft die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) -Methode zum Hinzufügen des Menüelements als eine Symbolleisten-Schaltfläche in die Liste der Befehle auf der **Befehle** Seite. Trennzeichen werden dabei ignoriert.  
  
 Wenn `bPopup` ist `TRUE`, für jedes Menüelement, das ein Untermenü enthält diese Methode erstellt eine [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) -Objekt und fügt es in der Liste der Befehle durch Aufrufen von `AddButton`. Andernfalls werden die Menüelemente, die Untermenüs enthalten nicht in der Liste der Befehle angezeigt. In beiden Fällen bei `AddMenuCommands` findet ein Menüelement mit einem Untermenü ruft sich selbst rekursiv, die Übergabe eines Zeigers an das Untermenü als die `pMenu` Parameter und hängen Sie die Bezeichnung der im Untermenü auf `lpszMenuPath`.  
  
##  <a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 Lädt eine Symbolleiste aus den Ressourcen. Klicken Sie dann für jeden Befehl in dem Menü Aufrufen der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode zum Einfügen einer Schaltfläche in der Liste der Befehle auf der **Befehle** Seite in der angegebenen Kategorie.  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCategoryId`  
 Gibt die Ressourcen-ID der Kategorie, um der Symbolleiste auf Hinzufügen.  
  
 [in] `uiToolbarResId`  
 Gibt die Ressourcen-ID einer Symbolleiste die Liste der Befehle, deren Befehle eingefügt werden.  
  
 [in] `lpszCategory`  
 Gibt den Namen der Kategorie, der die Symbolleiste hinzugefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddToolBar` -Methode in der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#11;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement, das zum Darstellen von jedem Befehl ist eine [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt. Die Symbolleiste hinzugefügt haben, können Sie die Schaltfläche mit einem Steuerelement eines abgeleiteten Typs ersetzen, durch Aufrufen von [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).  
  
##  <a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 Überprüft die Gültigkeit der Liste der Benutzertools.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstTools`  
 Die Liste der benutzerdefinierten Tools überprüfen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` ist die Liste der benutzerdefinierten Tools gültig ist, andernfalls `FALSE`. Die standardmäßige Implementierung gibt immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um die Gültigkeit von Objekten zu überprüfen, die benutzerdefinierte Tools zurückgegebene darstellen [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).  
  
 Überschreiben Sie die `CheckToolsValidity` Methode in einer Klasse abgeleitet `CMFCToolBarsCustomizeDialog` Sie ggf. die Benutzertools zu überprüfen, bevor der Benutzer das Dialogfeld geschlossen wird. Wenn diese Methode zurückgibt `FALSE` klickt der Benutzer entweder der **schließen** in der Ecke oben rechts im Dialogfeld oder die Schaltfläche **schließen** in der unteren rechten Ecke des Dialogfelds, das Dialogfeld zeigt die **Tools** anstelle schließen. Wenn diese Methode zurückgibt `FALSE` Wenn klickt der Benutzer eine Registerkarte zum Verlassen der **Tools** Registerkarte Navigation tritt nicht auf. Eine entsprechende Meldungsfeld, um die Benutzer über das Problem informiert werden, die einen Fehler verursacht wird, sollte angezeigt werden.  
  
##  <a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 Erstellt ein `CMFCToolBarsCustomizeDialog`-Objekt.  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParentFrame`  
 Ein Zeiger auf den übergeordneten Frame. Dieser Parameter darf nicht `NULL` sein.  
  
 [in] `bAutoSetFromMenus`  
 Ein boolescher Wert, der angibt, ob die Befehle im Menü auf alle Menüs in die Liste der Befehle hinzufügen der **Befehle** Seite. Wenn dieser Parameter `TRUE`, werden die Befehle im Menü hinzugefügt. Andernfalls werden die Befehle im Menü nicht hinzugefügt werden.  
  
 [in] `uiFlags`  
 Eine Kombination von Flags, die das Verhalten des Dialogfelds beeinflussen. Dieser Parameter kann eine oder mehrere der folgenden Werte sein:  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [in] `plistCustomPages`  
 Ein Zeiger auf eine Liste der `CRuntimeClass` Objekte, die zusätzliche benutzerdefinierte Seiten angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die `plistCustomPages` Parameter bezieht sich auf die Liste der `CRuntimeClass` Objekte, die zusätzliche benutzerdefinierte Seiten angeben. Der Konstruktor fügt mehr Seiten im Dialogfeld mit den [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) Methode. Finden Sie ein Beispiel für die weiteren Seiten fügt das CustomPages-Beispiel der **anpassen** Dialogfeld.  
  
 Weitere Informationen zu den Werten, die übergeben werden kann der `uiFlags` -Parameter finden Sie unter [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [benutzerdefinierte Seiten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&3;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 Zeigt die **Anpassung** Dialogfeld.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Eigenschaftenfenster Anpassung erfolgreich erstellt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Create` Methode erst vollständig der Klasse initialisieren.  
  
##  <a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 Aktiviert oder deaktiviert das Erstellen neuer Symbolleisten mithilfe der **anpassen** Dialogfeld.  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die benutzerdefinierte Symbolleisten; `FALSE` Symbolleisten deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bEnable` ist `TRUE`, **neu**, **umbenennen** und **löschen** Schaltflächen werden angezeigt, auf die **Symbolleisten** Seite.  
  
 Standardmäßig oder wenn `bEnable` ist `FALSE`, diese Schaltflächen nicht angezeigt, und der Benutzer keine neue Symbolleisten definieren.  
  
##  <a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 Füllt die angegebene `CListBox` -Objekt mit den Befehlen in der **alle Befehle** Kategorie.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `wndListOfCommands`  
 Ein Verweis auf die `CListBox` zu füllende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die **alle Befehle** Kategorie enthält die Befehle aller Kategorien. Die [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) -Methode fügt den Befehl, der die angegebene Schaltfläche zugeordnet ist die **alle Befehle** Kategorie für Sie.  
  
 Diese Methode löscht den Inhalt des bereitgestellten `CListBox` Objekt vor dem Befüllen mit den Befehlen in der **alle Befehle** Kategorie.  
  
 Die `CMFCMousePropertyPage` Klasse verwendet diese Methode zum Auffüllen der im Listenfeld Ereignis doppelklicken.  
  
##  <a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 Füllt die angegebene `CComboBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `wndCategory`  
 Ein Verweis auf die `CComboBox` zu füllende Objekt.  
  
 [in] `bAddEmpty`  
 Ein boolescher Wert, der angibt, ob Kategorien im Kombinationsfeld, die keine Befehle hinzufügen. Wenn dieser Parameter `TRUE`, leere Kategorien im Kombinationsfeld hinzugefügt werden. Andernfalls werden leere Kategorien nicht hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist mit der [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) Methode, funktioniert diese Methode mit einem `CComboBox` Objekt.  
  
 Diese Methode wird der Inhalt nicht gelöscht der `CComboBox` Objekt vor dem Auffüllen. Es wird sichergestellt, dass die **alle Befehle** Kategorie ist das letzte Element im Kombinationsfeld.  
  
 Sie können neue Befehlskategorien hinzufügen, indem Sie mit der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode. Sie können den Namen einer vorhandenen Kategorie ändern, mit der [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) Methode.  
  
 Die `CMFCToolBarsKeyboardPropertyPage` und `CMFCKeyMapDialog` Klassen verwenden diese Methode zum Kategorisieren von Tastenkombinationen.  
  
##  <a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 Füllt die angegebene `CListBox` Objekt mit dem Namen der einzelnen Kategorien Befehl in der **anpassen** Dialogfeld.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `wndCategory`  
 Ein Verweis auf die `CListBox` zu füllende Objekt.  
  
 [in] `bAddEmpty`  
 Ein boolescher Wert, der angibt, ob Kategorien in die Liste, die keine Befehle hinzufügen. Wenn dieser Parameter `TRUE`, leere Kategorien im Listenfeld hinzugefügt werden. Andernfalls werden leere Kategorien nicht hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist mit der [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) Methode, funktioniert diese Methode mit einem `CListBox` Objekt.  
  
 Diese Methode wird der Inhalt nicht gelöscht der `CListBox` Objekt vor dem Auffüllen. Es wird sichergestellt, dass die **alle Befehle** Kategorie ist das letzte Element im Listenfeld.  
  
 Sie können neue Befehlskategorien hinzufügen, indem Sie mit der [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) Methode. Sie können den Namen einer vorhandenen Kategorie ändern, mit der [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) Methode.  
  
 Die `CMFCToolBarsCommandsPropertyPage` Klasse diese Methode verwendet, um die Liste der Befehle anzuzeigen, die jede Kategorie zugeordnet ist.  
  
##  <a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 Ruft den Namen ab, der der angegebenen Befehls-ID zugeordnet ist.  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die ID des Befehls abrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name, der der angegebenen Befehls-ID zugeordnet ist oder `NULL` ist der Befehl nicht vorhanden.  
  
##  <a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 Ruft die Anzahl der Elemente in der Liste, die eine bestimmte Bezeichnung aufweisen.  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItemName`  
 Die Beschriftung entsprechend.  
  
 [in] `lstCommands`  
 Ein Verweis auf eine Liste mit `CMFCToolBarButton` Objekte.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der bereitgestellten Liste mit Text Bezeichnung gleich `lpszItemName`.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Element in der angegebenen Liste muss vom Typ `CMFCToolBarButton`. Diese Methode vergleicht `lpszItemName` mit der [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) -Datenmember.  
  
##  <a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags  
 Ruft den Satz von Flags, die das Verhalten des Dialogfelds beeinflussen ab.  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Satz von Flags, die das Verhalten des Dialogfelds beeinflussen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft den Wert des der `uiFlags` -Parameter, der an den Konstruktor übergeben wird. Der Rückgabewert kann eine oder mehrere der folgenden Werte sein:  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 Ermöglicht die Angabe der Volumeschattenkopie-Darstellung des Menüs.  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 Ermöglicht die Angabe, ob die Beschriftungen unterhalb der Symbolleisten-Schaltflächen angezeigt werden.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 Ermöglicht dem Benutzer das Menü Animation angegeben.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 Entfernt die Schaltfläche "Hilfe" aus dem Dialogfeld Anpassen.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 Ermöglicht die `WS_EX_CONTEXTHELP` visuellen Stil.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 Entfernt die **Tools** Seite aus dem Dialogfeld Anpassen. Dieses Flag ist gültig, wenn die Anwendung verwendet die `CUserToolsManager` Klasse.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 Ermöglicht das kaufmännische und-Zeichen enthält die Beschriftung der Schaltflächen ( ** & **) Zeichen.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 Entfernt die **große Symbole** Option im Dialogfeld Anpassen.  
  
 Weitere Informationen zu den `WS_EX_CONTEXTHELP` visuellen Stil finden Sie unter [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md).  
  
##  <a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 Reagiert auf eine Änderung in einem Tool, das sofort nach dem auftreten.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pSelTool`  
 Ein Zeiger auf das Benutzerobjekt für das Tool, das geändert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer die Eigenschaften eines benutzerdefinierten Tools geändert wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse `CMFCToolBarsCustomizeDialog` , Verarbeitung auszuführen, nachdem ein Tool, das eine Änderung vorgenommen wird.  
  
##  <a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 Tastenkombinationen überprüft, wie ein Benutzer, die sie definiert.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pAccel`  
 Zeiger auf die vorgeschlagene Tastatur-Zuweisung, die als ausgedrückt ist ein [ZUGRIFFSTASTE](http://msdn.microsoft.com/library/windows/desktop/ms646340) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Schlüssel zugewiesen werden kann, oder `FALSE` , wenn der Schlüssel nicht zugeordnet werden kann. Die standardmäßige Implementierung gibt immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zusätzliche Verarbeitung, wenn ein Benutzer eine neue Tastenkombination zuweisen oder zum Überprüfen von Tastenkombinationen als der Benutzer werden definiert. Um zu verhindern, dass eine Verknüpfung zugewiesen wird, zurückgeben `FALSE`. Sie sollten auch ein Meldungsfeld anzeigen oder andernfalls informiert den Benutzer über den Grund, warum die Tastenkombination abgelehnt wurde.  
  
##  <a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 Führt benutzerdefinierte Verarbeitung, wenn eine Änderung an ein Tool wird der Benutzer zu eine Änderung zu übernehmen.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pSelTool`  
 Ein Zeiger auf das Benutzerobjekt für das Tool, die ersetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn die Eigenschaften eines benutzerdefinierten Tools geändert wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie die `OnBeforeChangeTool` -Methode in einer Klasse abgeleitet `CMFCToolBarsCustomizeDialog` Wunsch Verarbeitung auszuführen, bevor eine Änderung an einem Tool, das auftritt, z. B. Freigeben von Ressourcen, `pSelTool` verwendet.  
  
##  <a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 Starten Sie einen Bild-Editor, damit ein Benutzer auf einer Symbolleiste oder eines Symbols anpassen kann.  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `bitmap`  
 Ein Verweis auf ein Bitmap-Objekt bearbeitet werden kann.  
  
 [in] `nBitsPerPixel`  
 Bitmap-Farbe Auflösung in Bits pro Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Änderung festgeschrieben wird; andernfalls `FALSE`. Die standardmäßige Implementierung zeigt ein Dialogfeld an und gibt `TRUE` klickt der Benutzer **OK**, oder `FALSE` klickt der Benutzer **Abbrechen** oder **schließen** Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer die Bild-Editor ausgeführt wird. Zeigt die Standard-Implementierung [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md) (Dialogfeld). Überschreiben Sie `OnEditToolbarMenuImage` in einer abgeleiteten Klasse ein benutzerdefiniertes Bild-Editor.  
  
##  <a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 Außerkraftsetzungen, um die Initialisierung einer Eigenschaftenblatt zu erweitern.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Aufrufs der [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) Methode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), durch Anzeigen der **schließen** Schaltfläche, und sicherstellen, dass das Dialogfeld die aktuelle Größe des Bildschirms passt, und Verschieben der **Hilfe** Schaltfläche auf der unteren linken Ecke des Dialogfelds.  
  
##  <a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Die Benachrichtigung vom Framework verarbeitet, die **Tools** initialisiert werden soll.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Benachrichtigung zu verarbeiten.  
  
##  <a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 Wird vom Framework aufgerufen, nachdem das Fenster zerstört wurde.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse `CPropertySheet::PostNcDestroy`, durch die Anwendung in den vorherigen Modus wiederherstellen.  
  
 Die [CMFCToolBarsCustomizeDialog::Create](#create) Methode versetzt die Anwendung in einem speziellen Modus, der den Benutzer Aufgaben zur Anpassung von beschränkt.  
  
##  <a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton  
 Entfernt die Schaltfläche mit der angegebenen Befehls-ID aus der angegebenen Kategorie oder aller Kategorien.  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCategoryId`  
 Gibt die Kategorie-ID aus dem die Schaltfläche entfernen.  
  
 [in] `uiCmdId`  
 Gibt die Befehls-ID der Schaltfläche.  
  
 [in] `lpszCategory`  
 Gibt den Namen der Kategorie, von denen die Schaltfläche entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der entfernten Schaltfläche oder -1, wenn die angegebene Befehls-ID in der angegebenen Kategorie nicht gefunden wurde. Wenn `uiCategoryId` ist-1 und der Rückgabewert ist 0.  
  
### <a name="remarks"></a>Hinweise  
 Um eine Schaltfläche in allen Kategorien zu entfernen, rufen Sie die erste Überladung dieser Methode, und legen `uiCategoryId` auf-1 festgelegt.  
  
##  <a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameCategory  
 Benennt eine Kategorie im Listenfeld Kategorien in der **Befehle** Seite.  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCategoryOld`  
 Der Name der Kategorie zu ändern.  
  
 [in] `lpszCategoryNew`  
 Der neue Kategoriename.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Kategoriename muss eindeutig sein.  
  
##  <a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton  
 Ersetzt eine Symbolleisten-Schaltfläche im Listenfeld Befehle auf der **Befehle** Seite.  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Gibt den Befehl an der Schaltfläche ersetzt werden.  
  
 [in] `button`  
 Ein `const` Verweis auf das Objekt der Symbolleisten-Schaltfläche, die die alte Schaltfläche ersetzt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), oder [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) fügt den Befehl hinzu der **Befehle** Seite in Form von Befehl ist ein [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt (oder eine [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) Objekt für ein Menüelement, das ein Untermenü hinzugefügt, indem enthält `AddMenuCommands`). Das Framework ruft auch diese drei Methoden zum automatischen Hinzufügen von Befehlen. Wenn Sie einen Befehl aus, um stattdessen von einem abgeleiteten Typ dargestellt werden soll, rufen Sie `ReplaceButton` und eine Schaltfläche des abgeleiteten Typs übergeben.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `ReplaceButton` -Methode in der `CMFCToolBarsCustomizeDialog` Klasse. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#34;](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 Gibt die Kategorie in der Liste der Kategorien auf die **Befehle** Seite ist der Kategorie. Sie müssen diese Funktion aufrufen, vor dem Aufruf von [CMFCToolBarsCustomizeDialog::Create](#create).  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCategory`  
 Der Name der Kategorie.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Einstellung des Benutzers Kategorie wird derzeit nicht vom Framework verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)

