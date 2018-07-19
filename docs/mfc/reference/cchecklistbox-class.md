---
title: CCheckListBox-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 2118344df9d97ddd8c8ba8f194b5653dea3ba001
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338374"
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
|[CCheckListBox::GetCheck](#getcheck)|Ruft den Zustand des Kontrollkästchens eines Elements.|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Ruft den Stil der Kontrollkästchen des Steuerelements ab.|  
|[CCheckListBox::IsEnabled](#isenabled)|Bestimmt, ob ein Element aktiviert ist.|  
|[CCheckListBox::MeasureItem](#measureitem)|Vom Framework aufgerufen, wenn ein Listenfeld, das mit einem Ownerdrawn-Format erstellt wird.|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Vom Framework aufgerufen, die Position des Elements ein Kontrollkästchen abzurufen.|  
|[CCheckListBox::SetCheck](#setcheck)|Legt den Zustand des Kontrollkästchens eines Elements.|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Legt fest, der die Darstellung des Steuerelements-Kontrollkästchen.|  
  
## <a name="remarks"></a>Hinweise  
 "Checkliste für die Box" zeigt eine Liste der Elemente, z. B. Dateinamen. Jedes Element in der Liste hat ein Kontrollkästchen, die der Benutzer aktivieren oder deaktivieren kann.  
  
 `CCheckListBox` gilt nur für die Ownerdrawn-Schaltflächen ein, da die Liste mehr als Zeichenfolgen enthält. Klicken Sie im einfachsten Fall einem prüflistenfeld enthält, Kontrollkästchen und Zeichenfolgen, aber Sie müssen sich nicht um Text zu erhalten. Beispielsweise könnten Sie eine Liste der kleine Bitmaps mit einem Kontrollkästchen neben jedem Element haben.  
  
 Um Ihre eigenen checklistbox zu erstellen, müssen Sie eine eigene Klasse von ableiten `CCheckListBox`. Leiten Sie Ihre eigene Klasse, Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen Sie dann `Create`.  
  
 Wenn Sie Windows gesendete benachrichtigungsmeldungen von ein Listenfeld, das an der übergeordnete behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag "und"-Nachrichtenhandler-Memberfunktion hinzugefügt.  
  
 Jede Nachricht-Zuordnungseintrag weist folgende Form:  
  
 **ON_** Benachrichtigung **(**`id`, `memberFxn` **)**  
  
 wo `id` gibt die untergeordneten Fenster-ID des Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Funktionsprototyp des übergeordneten Elements lautet wie folgt aus:  
  
 **Afx_msg** `void` `memberFxn` **();**  
  
 Es gibt nur eine Meldungszuordnungseintrags, die speziell gehört `CCheckListBox` (aber auch die Meldungszuordnungseinträge für [CListBox](../../mfc/reference/clistbox-class.md)):  
  
- ON_CLBN_CHKCHANGE der Benutzer hat den Status des Kontrollkästchen des Elements geändert.  
  
 Wenn Ihre checklistbox einem prüflistenfeld "Standard" (eine Liste von Zeichenfolgen mit der Standardgröße Kontrollkästchen auf der linken Seite der einzelnen) ist, können Sie die Standardeinstellung [CCheckListBox::DrawItem](#drawitem) das Checkliste zu zeichnen. Andernfalls müssen Sie überschreiben die [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem) Funktion und die [CCheckListBox::DrawItem](#drawitem) und [CCheckListBox::MeasureItem](#measureitem) Funktionen.  
  
 Sie können einem prüflistenfeld entweder aus einer Dialogfeldvorlage oder direkt in Ihrem Code erstellen.  
  
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
 Sie erstellen eine `CCheckListBox` Objekt in zwei Schritten. Zuerst definieren Sie eine Klasse, die von abgeleiteten `CCheckListBox`, rufen Sie anschließend `Create`, die die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox` Objekt.  
  
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
 *dwStyle*  
 Gibt die Art des Felds Prüfliste. Das Format muss LBS_HASSTRINGS und LBS_OWNERDRAWFIXED (alle Elemente in der Liste sind die gleiche Höhe) oder LBS_OWNERDRAWVARIABLE sein (Elemente in der Liste sind unterschiedlicher Höhe). Dieses Format kann kombiniert werden, mit anderen [listenfeldstile](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) außer LBS_USETABSTOPS.  
  
 *Rect*  
 Gibt an, die Prüfliste-Box-Größe und Position. Kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 *pParentWnd*  
 Gibt an, das Checkliste des übergeordneten Fensters (in der Regel eine `CDialog` Objekt). Es darf nicht NULL sein.  
  
 *nID*  
 Gibt an, das Checkliste des Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CCheckListBox` Objekt in zwei Schritten. Definieren Sie zuerst eine Klasse, die von abgeleiteten `CcheckListBox` und rufen dann `Create`, die die Windows-kontrolllistenfelds initialisiert und fügt es der `CCheckListBox`. Finden Sie unter [CCheckListBox::CCheckListBox](#cchecklistbox) ein Beispiel.  
  
 Wenn `Create` ausgeführt wird, handelt es sich bei Windows sendet die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) die Nachrichten an die Prüfliste-Steuerelement.  
  
 Diese Nachrichten werden standardmäßig behandelt der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, fügen Sie eine meldungszuordnung, die Ihre abgeleitete Klasse und Überschreiben der vorherigen Meldungshandler-Memberfunktionen. Außer Kraft setzen `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) zu einer Prüfliste-Steuerelement:  
  
- WS_CHILD immer  
  
- WS_VISIBLE in der Regel  
  
- WS_DISABLED selten  
  
- WS_VSCROLL hinzufügen eine vertikale Bildlaufleiste  
  
- WS_HSCROLL hinzufügen eine horizontalen Schiebeleiste  
  
- WS_GROUP zum Gruppieren von Steuerelementen  
  
- WS_TABSTOP können TAB-Taste auf dieses Steuerelement  
  
##  <a name="drawitem"></a>  CCheckListBox::DrawItem  
 Wird aufgerufen, durch das Framework, wenn ein visueller Aspekt des ein Ownerdrawn-Prüfliste ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDrawItemStruct*  
 Ein long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die `itemAction` und `itemState` Mitglied der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig zeichnet diese Funktion eine Kontrollkästchen Standardliste, bestehend aus einer Liste von Zeichenfolgen, jede mit einem Standardgröße Kontrollkästchen auf der linken Seite. Die Listengröße Kontrollkästchen wird [erstellen](#create).  
  
 Überschreiben Sie diese Memberfunktion zum Zeichnen von Ownerdrawn-Checkliste für die Felder zu implementieren, die nicht die Standardeinstellung, z. B. Checklist Felder mit Listen, die Zeichenfolgen nicht mit variabler Höhe Elementen oder mit Kontrollkästchen, die auf der linken Seite nicht. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor der Beendigung von dieser Memberfunktion.  
  
 Wenn Elemente der Checkliste Feld nicht alle die gleiche Höhe sind, wird die Prüfliste Feld Stil (im angegebenen `Create`) muss ** LBS_OWNERVARIABLE, und Sie überschreiben müssen die [MeasureItem](#measureitem) Funktion.  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 Rufen Sie diese Funktion aktivieren oder deaktivieren eine Prüflistenelement.  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Listenfeldelements Prüfliste aktiviert werden.  
  
 *bAktiviert*  
 Gibt an, ob das Element aktiviert oder deaktiviert ist.  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 Ruft den Zustand des angegebenen Kontrollkästchens ab.  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Nullbasierte Index eines Kontrollkästchens an, die Sie im Listenfeld enthalten ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status des angegebenen Kontrollkästchens. In der folgende Tabelle sind die möglichen Werte aufgeführt.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|BST_CHECKED|Das Kontrollkästchen aktiviert ist.|  
|BST_UNCHECKED|Das Kontrollkästchen ist nicht aktiviert.|  
|BST_INDETERMINATE|Status des Kontrollkästchens ist unbestimmt.|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 Rufen Sie diese Funktion rufen Sie die checklistbox-Stil.  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stil des Steuerelements-Kontrollkästchen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu möglichen Formaten finden Sie unter [SetCheckStyle](#setcheckstyle).  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein Element aktiviert ist.  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element aktiviert ist; andernfalls 0.  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 Wird von Framework aufgerufen, wenn es sich bei einem prüflistenfeld mit einem nicht standardmäßigen erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 *lpMeasureItemStruct*  
 Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur, um Windows Dimensionen des checklistbox Elemente zu informieren. Wenn das Checkliste mit erstellt haben, wird die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Format, das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
 Das Framework ruft diese Funktion, um die Position und Größe des Kontrollkästchens in einem Element zu erhalten.  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>Parameter  
 *rectItem*  
 Die Position und Größe des Listenelements.  
  
 *rectCheckBox*  
 Die Standardposition und Größe eines Elements in der Sie das Kontrollkästchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position und Größe des Elements ein Kontrollkästchen.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt nur die Standardposition und Größe des Kontrollkästchens zurück (`rectCheckBox`). Standardmäßig wird ein Kontrollkästchen ausgerichtet ist, in der oberen linken Ecke eines Elements und entspricht der Größe standard Kontrollkästchen. Gibt es möglicherweise Fälle, in dem die Kontrollkästchen auf der rechten Seite werden soll, oder ein Kontrollkästchen vergrößert oder verkleinert werden soll. Überschreiben Sie in diesen Fällen `OnGetCheckPosition` so ändern Sie die Kontrollkästchen-Position und Größe innerhalb des Elements.  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 Legt den Zustand des angegebenen Kontrollkästchens.  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Nullbasierte Index eines Kontrollkästchens an, die Sie im Listenfeld enthalten ist.  
  
 *nPrüfen*  
 Der Schaltflächenzustand für das angegebene Kontrollkästchen. Finden Sie im Abschnitt "Hinweise" Mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Werte für die *nPrüfen* Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|BST_CHECKED|Aktivieren Sie das Kontrollkästchen angegebenen.|  
|BST_UNCHECKED|Deaktivieren Sie das Kontrollkästchen angegebenen.|  
|BST_INDETERMINATE|Legen Sie den angegebenen Kontrollkästchen-Status einem unbestimmten Zustand.<br /><br /> Dieser Status ist nur verfügbar, wenn das Kontrollkästchen Format BS_AUTO3STATE oder BS_3STATE ist. Weitere Informationen finden Sie unter [Button-Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 Rufen Sie diese Funktion, um den Stil der Kontrollkästchen im Prüfliste festlegen.  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *nStyle*  
 Bestimmt den Stil der Kontrollkästchen im prüflistenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Zulässige Werte sind:  
  
- BS_CHECKBOX  
  
- BS_AUTOCHECKBOX  
  
- BS_AUTO3STATE  
  
- BS_3STATE  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Button-Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TSTCON](../../visual-cpp-samples.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)
