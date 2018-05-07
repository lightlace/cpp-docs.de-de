---
title: CCheckListBox Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
dev_langs:
- C++
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4129da35eca5aecfb1e976361d1716d1cd78e906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cchecklistbox-class"></a>CCheckListBox-Klasse
Stellt die Funktionalität eines Windows-Kontrolllistenfelds bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Erstellt ein `CCheckListBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Erstellt die Windows-kontrolllistenfelds und fügt es der `CCheckListBox` Objekt.|  
|[CCheckListBox::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.|  
|[CCheckListBox::Enable](#enable)|Aktiviert oder deaktiviert eine Prüflistenelement.|  
|[CCheckListBox::GetCheck](#getcheck)|Ruft den Zustand des Kontrollkästchens für ein Element ab.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Ruft das Format von Kontrollkästchen für das Steuerelement ab.|  
|[CCheckListBox::IsEnabled](#isenabled)|Bestimmt, ob ein Element aktiviert ist.|  
|[CCheckListBox::MeasureItem](#measureitem)|Vom Framework aufgerufen, wenn ein Listenfeld mit einem Ownerdrawn-Stil erstellt wird.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Vom Framework aufgerufen, die Position des Kontrollkästchens für ein Element abzurufen.|  
|[CCheckListBox::SetCheck](#setcheck)|Legt den Zustand des Kontrollkästchens für ein Element.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Legt den Stil von Kontrollkästchen für das Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 "Checklistbox" zeigt eine Liste von Elementen, beispielsweise Dateinamen an. Jedes Element in der Liste hat ein Kontrollkästchen daneben, die der Benutzer aktivieren oder deaktivieren kann.  
  
 `CCheckListBox` gilt nur für Ownerdrawn-Schaltflächen, da die Liste mehrere Textzeichenfolgen enthält. Am einfachsten eine Prüfliste Textzeichenfolgen und Kontrollkästchen enthält, aber nicht Text überhaupt verwenden möchten. Sie konnten z. B. eine Liste der kleine Bitmaps mit einem Kontrollkästchen neben jedem Element haben.  
  
 Um eine eigene checklistbox zu erstellen, leiten Sie eine eigene Klasse von `CCheckListBox`. Leiten Sie eine eigene Klasse schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen dann **erstellen**.  
  
 Wenn Sie ein Listenfeld an seinem übergeordneten Element per Windows-benachrichtigungsmeldungen behandeln möchten (normalerweise eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Nachrichtenhandler Memberfunktion hinzufügen.  
  
 Jede Meldungszuordnungseintrags weist folgende Form auf:  
  
 **ON_** Benachrichtigung **(**`id`, `memberFxn` **)**  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten-Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **Afx_msg** `void` `memberFxn` **();**  
  
 Es ist nur eine Meldungszuordnungseintrags, die sich speziell auf beziehen **CCheckListBox** (aber finden Sie auch die Meldungszuordnungseinträge für [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- **ON_CLBN_CHKCHANGE** den Status des Kontrollkästchens für ein Element geändert wurde.  
  
 Wenn Ihre checklistbox eine Standard-kontrolllistenfelds (eine Liste von Zeichenfolgen mit der Standardgröße Kontrollkästchen auf der linken Seite der einzelnen) ist, können Sie die Standardeinstellung [CCheckListBox::DrawItem](#drawitem) das Checkliste gezeichnet werden soll. Andernfalls müssen Sie überschreiben die [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) Funktion und die [CCheckListBox::DrawItem](#drawitem) und [CCheckListBox::MeasureItem](#measureitem) Funktionen.  
  
 Sie können eine checklistbox aus einer Dialogfeldvorlage oder direkt im Code erstellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cchecklistbox"></a>  CCheckListBox::CCheckListBox  
 Erstellt ein `CCheckListBox`-Objekt.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CCheckListBox` Objekt in zwei Schritten. Zuerst definieren Sie eine Klasse, die von abgeleiteten `CCheckListBox`, rufen Sie anschließend **erstellen**, die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>  CCheckListBox::Create  
 Erstellt die Windows-kontrolllistenfelds und fügt es der `CCheckListBox` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Art des Felds Prüfliste. Das Format muss **LBS_HASSTRINGS** und entweder **LBS_OWNERDRAWFIXED** (alle Elemente in der Liste sind die gleichen Höhe) oder **LBS_OWNERDRAWVARIABLE** (Elemente in der Liste ist ein variabler Höhe). Dieses Format kann zusammen mit anderen [listenfeldstile](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) außer **LBS_USETABSTOPS**.  
  
 `rect`  
 Gibt an, die checklistbox Größe und Position. Kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt an, die checklistbox übergeordnete Fenster (normalerweise eine `CDialog` Objekt). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, die checklistbox Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CCheckListBox` Objekt in zwei Schritten. Zuerst definieren eine Klasse abgeleitet wurde. **CcheckListBox** und rufen dann **erstellen**, die die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox`. Finden Sie unter [CCheckListBox::CCheckListBox](#cchecklistbox) ein Beispiel.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an die Prüfliste-Steuerelement.  
  
 Diese Nachrichten werden standardmäßig verarbeitet der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standard-Meldungsbehandlung zu erweitern, fügen Sie eine meldungszuordnung, die der abgeleiteten Klasse und Überschreiben der vorherigen Meldungshandler-Memberfunktionen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) an ein Prüfliste-Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** eine vertikale Bildlaufleiste hinzufügen  
  
- **WS_HSCROLL** eine horizontale Bildlaufleiste hinzufügen  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** zu ermöglichen, TAB-Taste auf dieses Steuerelement  
  
##  <a name="drawitem"></a>  CCheckListBox::DrawItem  
 Wird aufgerufen, durch das Framework, wenn ein visueller Aspekt des ein Ownerdrawn-Checkliste ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Eine long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** und **ItemState** Mitglied der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig zeichnet diese Funktion ist eine Kontrollkästchen Standardliste bestehend aus einer Liste von Zeichenfolgen, jede mit einem Standardgröße Kontrollkästchen auf der linken Seite. Die Listengröße Kontrollkästchen wird [erstellen](#create).  
  
 Überschreiben Sie diese Memberfunktion zum Zeichnen der Ownerdrawn-Checkliste Felder zu implementieren, die nicht die Standardeinstellung, z. B. Prüfliste Felder mit Listen, die keine Zeichenfolgen sind, mit variabler Höhe Elementen oder mit Kontrollkästchen dargestellt, die auf der linken Seite sind. Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor dem Beenden des diese Memberfunktion.  
  
 Wenn Prüfliste Listenfeldelemente nicht die gleiche Höhe sind, wird die Knotenart Prüfliste (im angegebenen **erstellen**) muss **LBS_OWNERVARIABLE**, und Sie überschreiben, müssen die [MeasureItem](#measureitem) Funktion.  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 Mit dieser Funktion wird zum Aktivieren oder deaktivieren eine Prüflistenelement.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Index des Elements im Feld Prüfliste aktiviert werden.  
  
 `bEnabled`  
 Gibt an, ob das Element aktiviert oder deaktiviert ist.  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 Ruft den Status des angegebenen Kontrollkästchens ab.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index des ein Kontrollkästchen, die Sie im Listenfeld enthalten sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status der angegebenen Kontrollkästchen. In der folgenden Tabelle sind die möglichen Werte aufgeführt.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`BST_CHECKED`|Dieses Kontrollkästchen aktiviert ist.|  
|`BST_UNCHECKED`|Das Kontrollkästchen ist nicht aktiviert.|  
|`BST_INDETERMINATE`|Der Status eines Kontrollkästchens ist unbestimmt.|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 Mit dieser Funktion wird zum Abrufen der Prüfliste-Box-Stil.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stil von Kontrollkästchen für das Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu möglichen Formaten finden Sie unter [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein Element aktiviert ist.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element aktiviert ist; andernfalls 0.  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 Vom Framework aufgerufen, wenn eine checklistbox mit einem nicht standardmäßigen Format erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Eine long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur informiert Windows über die Abmessungen des checklistbox Elemente. Wenn das Checkliste mit erstellt wird die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Format, das Framework ruft diese Memberfunktion für jedes Element im Listenfeld. Andernfalls wird bei diesem Member nur einmal aufgerufen.  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
 Das Framework ruft diese Funktion, um die Position und Größe des Kontrollkästchens in einem Element abzurufen.  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>Parameter  
 *rectItem*  
 Die Position und Größe des Listenelements.  
  
 `rectCheckBox`  
 Kontrollkästchen für die Standardposition und Größe eines Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Kontrollkästchen für die Position und Größe eines Elements.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt nur die Standardposition und Größe des Kontrollkästchens ( `rectCheckBox`). Standardmäßig wird ein Kontrollkästchen in der oberen linken Ecke eines Elements ausgerichtet ist, und Sie ist die standardmäßige Kontrollkästchen Größe. Es gibt möglicherweise Fälle, in dem das Kontrollkästchen auf der rechten Seite werden sollen, oder ein Kontrollkästchen größer oder kleiner werden soll. In diesen Fällen überschreiben `OnGetCheckPosition` so ändern Sie die Kontrollkästchen Position und Größe innerhalb des Elements.  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 Legt den Zustand des angegebenen Kontrollkästchens.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index des ein Kontrollkästchen, die Sie im Listenfeld enthalten sind.  
  
 `nCheck`  
 Der Schaltflächenzustand für das angegebene Kontrollkästchen. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nCheck` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**BST_CHECKED**|Wählen Sie das Kontrollkästchen angegebenen.|  
|**BST_UNCHECKED**|Deaktivieren Sie das Kontrollkästchen angegebenen.|  
|**BST_INDETERMINATE**|Legen Sie den angegebenen Kontrollkästchen-Status, einem unbestimmten Zustand.<br /><br /> Dieser Status ist nur verfügbar, wenn das Kontrollkästchen Format `BS_AUTO3STATE` oder `BS_3STATE`. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 Rufen Sie diese Funktion, um den Stil der Kontrollkästchen im Prüfliste festlegen.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Bestimmt den Stil der Kontrollkästchen im Prüfliste.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Formate sind:  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Schaltflächenstile](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TSTCON](../../visual-cpp-samples.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)
