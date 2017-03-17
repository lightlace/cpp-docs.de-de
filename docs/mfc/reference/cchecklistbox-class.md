---
title: CCheckListBox Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CCheckListBox class
- checklist boxes
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2cce91e3b6cb6cdf6ec2f4564fcf5090a54c917f
ms.lasthandoff: 02/24/2017

---
# <a name="cchecklistbox-class"></a>CCheckListBox-Klasse
Stellt die Funktionalität eines Windows-Kontrolllistenfelds bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Erstellt ein `CCheckListBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Erstellt die Windows-kontrolllistenfelds und fügt es der `CCheckListBox` Objekt.|  
|[CCheckListBox::DrawItem](#drawitem)|Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.|  
|[CCheckListBox::Enable](#enable)|Aktiviert oder deaktiviert eine Prüflistenelement.|  
|[CCheckListBox::GetCheck](#getcheck)|Ruft den Zustand des Kontrollkästchens für ein Element.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Ruft den Stil der Kontrollkästchen für das Steuerelement ab.|  
|[CCheckListBox::IsEnabled](#isenabled)|Bestimmt, ob ein Element aktiviert ist.|  
|[CCheckListBox::MeasureItem](#measureitem)|Wird vom Framework aufgerufen, wenn ein Listenfeld mit einem Ownerdrawn-Stil erstellt wird.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Vom Framework aufgerufen, die Position des Kontrollkästchens für ein Element abzurufen.|  
|[CCheckListBox::SetCheck](#setcheck)|Legt den Zustand des Kontrollkästchens für ein Element.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Legt den Stil der Kontrollkästchen für das Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 "Checklistbox" zeigt eine Liste von Elementen, z. B. Dateinamen. Jedes Element in der Liste hat das Kontrollkästchen daneben, die der Benutzer aktivieren oder deaktivieren kann.  
  
 `CCheckListBox`gilt nur für Ownerdrawn-Schaltflächen, da die Liste mehr als Zeichenfolgen enthält. Im einfachsten Fall enthält ein Prüfliste, das Kontrollkästchen und Textzeichenfolgen, Sie müssen jedoch nicht Text überhaupt zu verwenden. Beispielsweise könnten Sie eine Liste der kleine Bitmaps mit einem Kontrollkästchen neben jedem Element haben.  
  
 Zum Erstellen einer eigenen Prüfliste, leiten Sie eine eigene Klasse von `CCheckListBox`. Leiten Sie eine eigene Klasse schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen Sie dann **erstellen**.  
  
 Wenn Sie Windows-Benachrichtigung gesendet von einem Listenfeld zum übergeordneten behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Meldungshandler Memberfunktion hinzugefügt.  
  
 Jede Meldungszuordnungseintrags hat das folgende Format:  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Steuerelements, das die Benachrichtigung gesendet und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Es gibt nur eine Meldungszuordnungseintrags, die speziell auf beziehen, **CCheckListBox** (aber auch die Meldungszuordnungseinträge für [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- **ON_CLBN_CHKCHANGE** den Zustand der Kontrollkästchen des Elements geändert wurde.  
  
 Ist die checklistbox eines Standard-kontrolllistenfelds (eine Liste von Zeichenfolgen mit der Standardgröße Kontrollkästchen links neben jeder), können Sie die Standardeinstellung [CCheckListBox::DrawItem](#drawitem) das Checkliste zu zeichnen. Andernfalls müssen Sie überschreiben die [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) Funktion und die [CCheckListBox::DrawItem](#drawitem) und [CCheckListBox::MeasureItem](#measureitem) Funktionen.  
  
 Sie können einem aus einer Dialogfeldvorlage oder direkt im Code erstellen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cchecklistbox"></a>CCheckListBox::CCheckListBox  
 Erstellt ein `CCheckListBox`-Objekt.  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CCheckListBox` Objekt in zwei Schritten. Zuerst definieren Sie eine Klasse, die von abgeleiteten `CCheckListBox`, rufen Sie dann **erstellen**, die die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&60;](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>CCheckListBox::Create  
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
 Gibt den Stil der kontrolllistenfelds. Das Format muss **LBS_HASSTRINGS** und **LBS_OWNERDRAWFIXED** (alle Elemente in der Liste sind die gleiche Höhe) oder **LBS_OWNERDRAWVARIABLE** (Elemente in der Liste sind mit unterschiedlichen Höhen). Dieses Format kann mit anderen kombiniert werden [listenfeldstile](../../mfc/reference/list-box-styles.md) außer **LBS_USETABSTOPS**.  
  
 `rect`  
 Gibt die Prüfliste-Größe und Position. Kann entweder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt das Checkliste des übergeordneten Fensters (in der Regel ein `CDialog` Objekt). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Checkliste des Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CCheckListBox` Objekt in zwei Schritten. Zuerst definieren Sie eine Klasse, die von abgeleiteten **CcheckListBox** und rufen Sie dann **erstellen**, die die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox`. Finden Sie unter [CCheckListBox::CCheckListBox](#cchecklistbox) ein Beispiel.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Prüfliste-Steuerelement.  
  
 Diese Nachrichten werden standardmäßig verarbeitet die [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, fügen Sie eine Karte angezeigt, in der der abgeleiteten Klasse und Überschreiben der vorherigen Meldungshandler-Memberfunktionen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) zu einer Checkliste-Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** eine vertikale Bildlaufleiste hinzu  
  
- **WS_HSCROLL** hinzufügen eine horizontalen Bildlaufleiste  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** , können die TAB-Taste zu diesem Steuerelement  
  
##  <a name="drawitem"></a>CCheckListBox::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt einer Ownerdrawn-Checkliste ändert sich.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** und **ItemState** Mitglieder der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig zeichnet diese Funktion eine Kontrollkästchen Standardliste, bestehend aus einer Liste von Zeichenfolgen, jede mit einem Kontrollkästchen Standardgröße auf der linken Seite. Die Kontrollkästchen Liste ist der [erstellen](#create).  
  
 Überschreiben Sie diese Memberfunktion zum Zeichnen von Ownerdrawn-Checkliste Felder zu implementieren, die nicht die Standardeinstellung, z. B. Prüfliste Felder mit Listen, die keine Zeichenfolgen sind, mit variabler Höhe Elementen oder mit Kontrollkästchen, die nicht auf der linken Seite. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor dem Beenden von dieser Memberfunktion.  
  
 Wenn Prüfliste Elemente nicht alle dieselbe Höhe sind, die Checkliste Knotenart (im angegebenen **erstellen**) muss **LBS_OWNERVARIABLE**, und müssen Sie überschreiben die [MeasureItem](#measureitem) Funktion.  
  
##  <a name="enable"></a>CCheckListBox::Enable  
 Rufen Sie diese Funktion aktivieren oder deaktivieren eine Prüflistenelement.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Listenfeldelements Prüfliste aktiviert werden.  
  
 `bEnabled`  
 Gibt an, ob das Element aktiviert oder deaktiviert ist.  
  
##  <a name="getcheck"></a>CCheckListBox::GetCheck  
 Ruft den Zustand des angegebenen Kontrollkästchens.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index des ein Kontrollkästchen, die Sie im Listenfeld enthalten sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status des angegebenen Kontrollkästchens. In der folgenden Tabelle sind die möglichen Werte aufgeführt.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`BST_CHECKED`|Das Kontrollkästchen aktiviert ist.|  
|`BST_UNCHECKED`|Das Kontrollkästchen ist nicht aktiviert.|  
|`BST_INDETERMINATE`|Status des Kontrollkästchens ist unbestimmt.|  
  
##  <a name="getcheckstyle"></a>CCheckListBox::GetCheckStyle  
 Rufen Sie diese Funktion, um den Stil der Checkliste zu erhalten.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stil der Kontrollkästchen für das Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu möglichen Formaten finden Sie unter [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>CCheckListBox::IsEnabled  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein Element aktiviert ist.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element aktiviert ist; andernfalls 0.  
  
##  <a name="measureitem"></a>CCheckListBox::MeasureItem  
 Wird vom Framework aufgerufen, wenn eine Prüfliste mit einem nicht standardmäßigen Format erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und füllen Sie die `MEASUREITEMSTRUCT` Struktur, informiert Windows Dimensionen des Prüfliste-Elemente. Wenn das Checkliste erstellt wird, mit der [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Stil das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.  
  
##  <a name="ongetcheckposition"></a>CCheckListBox::OnGetCheckPosition  
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
 Die Standardposition und Größe eines Elements das Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position und Größe eines Elements das Kontrollkästchen.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt nur die Standardposition und Größe des Kontrollkästchens ( `rectCheckBox`). Standardmäßig wird ein Kontrollkästchen in der oberen linken Ecke eines Elements ausgerichtet ist, und Sie ist die standardmäßige Größe. Es gibt möglicherweise Fälle, in denen die Kontrollkästchen auf der rechten Seite, oder soll ein Kontrollkästchen vergrößern oder verkleinern. Überschreiben Sie in diesen Fällen `OnGetCheckPosition` Kontrollkästchen Position und Größe innerhalb des Elements ändern.  
  
##  <a name="setcheck"></a>CCheckListBox::SetCheck  
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
 Der Schaltflächenstatus für das angegebene Kontrollkästchen. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die `nCheck` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**BST_CHECKED**|Aktivieren Sie das Kontrollkästchen angegebenen.|  
|**BST_UNCHECKED**|Deaktivieren Sie das Kontrollkästchen angegebenen.|  
|**BST_INDETERMINATE**|Legen Sie den Zustand der angegebenen Kontrollkästchen einem unbestimmten Zustand.<br /><br /> Dieser Status ist nur verfügbar, wenn das Kontrollkästchen Format `BS_AUTO3STATE` oder `BS_3STATE`. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/button-styles.md).|  
  
##  <a name="setcheckstyle"></a>CCheckListBox::SetCheckStyle  
 Rufen Sie diese Funktion, um das Kontrollkästchen im Feld Prüfliste festzulegen.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Bestimmt den Stil der Kontrollkästchen im Checkliste.  
  
### <a name="remarks"></a>Hinweise  
 Zulässige Werte sind:  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 Informationen zu diesen Formaten finden Sie unter [Schaltflächenstile](../../mfc/reference/button-styles.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TSTCON](../../visual-cpp-samples.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)

