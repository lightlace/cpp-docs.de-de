---
title: CRichEditView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: 2eebfe18275aa63ac26c0c898a5d796300860db8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476614"
---
# <a name="cricheditview-class"></a>CRichEditView-Klasse

Mit [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-/ Ansichtarchitektur bereit.

## <a name="syntax"></a>Syntax

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditView::CRichEditView](#cricheditview)|Erstellt ein `CRichEditView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Verschiebt ein Dialogfeld an, damit, dass sie die aktuelle Auswahl erschwert nicht.|
|[CRichEditView::CanPaste](#canpaste)|Erfahren Sie, ob die Zwischenablage Daten enthält, die in die rich-Edit-Ansicht eingefügt werden können.|
|[CRichEditView::DoPaste](#dopaste)|Fügt ein OLE-Element in dieser rich-Edit-Ansicht.|
|[CRichEditView::FindText](#findtext)|Sucht den angegebenen Text, der den Wartecursor aufrufen.|
|[CRichEditView::FindTextSimple](#findtextsimple)|Sucht nach dem angegebenen Text.|
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Ruft das Zeichen, die Formatierung der Attribute für die aktuelle Auswahl ab.|
|[CRichEditView::GetDocument](#getdocument)|Ruft einen Zeiger auf den zugehörigen [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Ruft das OLE-Element, das derzeit direkt aktiv in der rich-Edit-Ansicht ab.|
|[CRichEditView::GetMargins](#getmargins)|Ruft die Ränder für diese rich-Edit-Ansicht ab.|
|[CRichEditView::GetPageRect](#getpagerect)|Ruft das Rechteck Seite für die rich-Edit-Ansicht ab.|
|[CRichEditView::GetPaperSize](#getpapersize)|Ruft die Papiergröße für diese rich-Edit-Ansicht ab.|
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Ruft die absatzformatierung Attribute für die aktuelle Auswahl ab.|
|[CRichEditView::GetPrintRect](#getprintrect)|Ruft das Drucken Rechteck für diese rich-Edit-Ansicht ab.|
|[CRichEditView::GetPrintWidth](#getprintwidth)|Ruft die Breite des Druck für diese rich-Edit-Ansicht ab.|
|[CRichEditView:: GetRichEditCtrl](#getricheditctrl)|Ruft das rich-Edit-Steuerelement ab.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|Ruft das ausgewählte Element aus der rich-Edit-Ansicht ab.|
|[CRichEditView::GetTextLength](#gettextlength)|Ruft die Länge des Texts in der rich-Edit-Ansicht ab.|
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Ruft die Anzahl von Zeichen oder Bytes in der rich-Edit-Ansicht. Erweiterte Flag-Liste für die Methode zur Bestimmung der Länge.|
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Fügt eine Datei als OLE-Element.|
|[CRichEditView::InsertItem](#insertitem)|Fügt ein neues Element als ein OLE-Element.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Erfahren Sie, ob die Zwischenablage Daten im rich-Edit oder Text-Format enthält.|
|[CRichEditView::OnCharEffect](#onchareffect)|Wird das Zeichen, die Formatierung für die aktuelle Auswahl umgeschaltet.|
|[CRichEditView::OnParaAlign](#onparaalign)|Ändert die Ausrichtung der Absätze.|
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Aktualisiert die Benutzeroberfläche für die öffentliche Memberfunktionen Zeichen.|
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Aktualisiert die Benutzeroberfläche für Öffentliche Memberfunktionen Absatz an.|
|[CRichEditView::PrintInsideRect](#printinsiderect)|Formatiert den angegebenen Text innerhalb des angegebenen Rechtecks.|
|[CRichEditView::PrintPage](#printpage)|Formatiert den angegebenen Text innerhalb der angegebenen Seite.|
|[CRichEditView::SetCharFormat](#setcharformat)|Legt fest, der die zeichenformatierung Attribute für die aktuelle Auswahl.|
|[CRichEditView::SetMargins](#setmargins)|Legt die Ränder für dieser umfassenden Bearbeiten Ansicht.|
|[CRichEditView::SetPaperSize](#setpapersize)|Legt fest, die Papiergröße für diese rich-Edit-Ansicht.|
|[CRichEditView::SetParaFormat](#setparaformat)|Legt die absatzformatierung Attribute für die aktuelle Auswahl fest.|
|[CRichEditView::TextNotFound](#textnotfound)|Setzt den internen Suche Zustand des Steuerelements zurück.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditView::GetClipboardData](#getclipboarddata)|Ruft ein Zwischenablagenobjekt für einen Bereich in dieser rich-Edit-Ansicht ab.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|Ruft ein Kontextmenü für die Verwendung auf einer Rechte Maustaste ab.|
|[CRichEditView::IsSelected](#isselected)|Gibt an, wenn das angegebene OLE-Element, oder nicht ausgewählt ist.|
|[CRichEditView::OnFindNext](#onfindnext)|Sucht das nächste Vorkommen einer Teilzeichenfolge.|
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Aktualisiert eine Ansicht, wenn er erstmals an ein Dokument angefügt.|
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Ruft die systemeigenen Daten von einem OLE-Element ab.|
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Legt die Druckeigenschaften für das angegebene Gerät fest.|
|[CRichEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer bestimmten Zeichenfolge durch eine neue Zeichenfolge.|
|[CRichEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Auswahl.|
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Verarbeitet die Benachrichtigung für Benutzer, die der angeforderte Text nicht gefunden wurde.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Fragt ab, zu den Daten auf den `IDataObject`.|
|[CRichEditView::WrapChanged](#wrapchanged)|Passt das Zielausgabegerät an, für diese Rich--Ansicht basierend auf den Wert der Edit `m_nWordWrap`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Gibt die Menge der Einzug für die Liste mit Aufzählungszeichen.|
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Gibt an, die Word-Wrap-Einschränkungen.|

## <a name="remarks"></a>Hinweise

Als "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text Zeichen- und absatzformatierung zugewiesen werden kann, und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die textformatierung an. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich, um Formatierungsvorgängen für den Benutzer verfügbar zu machen implementieren.

`CRichEditView` verwaltet den Text und Formatierung Merkmal des Texts. `CRichEditDoc` verwaltet die Liste der OLE-Clientelemente, in der Ansicht sind. `CRichEditCntrItem` Stellt die Container-Seite, auf das Client-OLE-Element.

Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandten Klassen) ist nur für Programme, die unter Versionen des Windows 95/98 und Windows NT 3.51 und höher.

Ein Beispiel mit einer rich-Edit-Ansicht in einer MFC-Anwendung, finden Sie unter den [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Anforderungen

**Header:** afxrich.h

##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition

Mit dieser Funktion können Sie die angegebenen Dialogfeld verschieben, sodass sie nicht die aktuelle Auswahl verdeckt.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Parameter

*pDlg*<br/>
Zeiger auf eine `CDialog` Objekt.

##  <a name="canpaste"></a>  CRichEditView::CanPaste

Rufen Sie diese Funktion, um zu bestimmen, ob die Zwischenablage Informationen enthält, die in dieser rich-Edit-Ansicht eingefügt werden kann.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Zwischenablage Daten in einem Format enthält, die dieser rich-Edit-Ansicht annehmen kann, andernfalls 0.

##  <a name="cricheditview"></a>  CRichEditView::CRichEditView

Mit dieser Funktion wird zum Erstellen einer `CRichEditView` Objekt.

```
CRichEditView();
```

##  <a name="dopaste"></a>  CRichEditView::DoPaste

Mit dieser Funktion können Sie in das OLE-Element einfügen *Dataobj* in die Rich-edit-Dokumente und Ansichten.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Parameter

*dataobj*<br/>
Die [COleDataObject](../../mfc/reference/coledataobject-class.md) mit den Daten zum Einfügen.

*CF*<br/>
Das gewünschte Format der Zwischenablage.

*hMetaPict*<br/>
Der Metadatei, die das einzufügende Element darstellt.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion als Teil der Standardimplementierung von [QueryAcceptData](#queryacceptdata).

Diese Funktion bestimmt den Typ des einfügen, die basierend auf den Ergebnissen des Handlers für Inhalte einfügen. Wenn *Cf* gleich 0 ist, das neue Element verwendet die aktuelle iconic-Darstellung. Wenn *Cf* ungleich NULL ist und *hMetaPict* ist nicht NULL ist, verwendet das neue Element *hMetaPict* für die Darstellung.

##  <a name="findtext"></a>  CRichEditView::FindText

Mit dieser Funktion können sucht den angegebenen Text und festlegen, dass die aktuelle Auswahl werden.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Enthält die zu suchende Zeichenfolge.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.

*bWord*<br/>
Gibt an, wenn die Suche nur ganze Wörter nicht Teilen von Wörtern übereinstimmen soll.

*bWeiter*<br/>
Gibt die Richtung für die Suche. Wenn TRUE, ist die suchrichtung zum Ende des Puffers. False gibt an, wird die Suche Richtung am Anfang des Puffers.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der *LpszFind* Text gefunden wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion wird der Wartecursor angezeigt, während des Suchvorgangs angibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple

Mit dieser Funktion können sucht den angegebenen Text und festlegen, dass die aktuelle Auswahl werden.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Enthält die zu suchende Zeichenfolge.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.

*bWord*<br/>
Gibt an, wenn die Suche nur ganze Wörter nicht Teilen von Wörtern übereinstimmen soll.

*bWeiter*<br/>
Gibt die Richtung für die Suche. Wenn TRUE, ist die suchrichtung zum Ende des Puffers. False gibt an, wird die Suche Richtung am Anfang des Puffers.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der *LpszFind* Text gefunden wird; andernfalls 0.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::FindText](#findtext).

##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection

Rufen Sie diese Funktion, um das Zeichen, die Formatierung der Attribute der aktuellen Auswahl abzurufen.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Rückgabewert

Ein [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Struktur, die das Zeichen, die Formatierung der Attribute der aktuellen Auswahl enthält.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den [EM_GETCHARFORMAT](/windows/desktop/Controls/em-getcharformat) Nachricht und die [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Struktur im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData

Das Framework ruft diese Funktion als Teil der Verarbeitung der [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata).

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Parameter

*lpchrg*<br/>
Zeiger auf die [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) angeben des Bereichs von Zeichen (und OLE-Elemente) zu kopieren, auf das Datenobjekt, das vom angegebenen Struktur *Lplpdataobj*.

*dwReco*<br/>
Zwischenablagen-Flags für Vorgang. Dabei kann es sich um einen der folgenden Werte sein.

- RECO_COPY Kopie in die Zwischenablage.

- RECO_CUT Ausschneiden in die Zwischenablage.

- Ziehen RECO_DRAG Vorgang (Drag & Drop).

- RECO_DROP Drop-Vorgang (Drag & Drop).

- RECO_PASTE einfügen aus der Zwischenablage.

*lpRichDataObj*<br/>
Zeiger auf ein [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Objekt mit Daten in der Zwischenablage in die Rich-Text-edit-Steuerelement ( [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
Zeiger auf die Zeigervariable, die die Adresse des empfängt die `IDataObject` Objekt, das im angegebenen Bereich darstellt. die *Lpchrg* Parameter. Der Wert des *Lplpdataobj* wird ignoriert, wenn ein Fehler zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Wert, der den Erfolg des Vorgangs gemeldet wird. Weitere Informationen zu HRESULT, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert gibt, Erfolg an `IRichEditOleCallback::GetClipboardData` gibt die `IDataObject` zugegriffen *Lplpdataobj*ist, andernfalls wird auf die zugegriffen werden, indem eine *LpRichDataObj*. Überschreiben Sie diese Funktion, um eigene Zwischenablagedaten bereitstellen. Die Standardimplementierung dieser Funktion gibt E_NOTIMPL zurück.

Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen finden Sie unter [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata), und [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) im Windows SDK und finden Sie unter [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) in das Windows SDK.

##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu

Das Framework ruft diese Funktion als Teil der Verarbeitung der [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Parameter

*seltyp*<br/>
Der Typ der Auswahl. Die Typwerte der Auswahl werden im Abschnitt "Hinweise" beschrieben.

*lpoleobj*<br/>
Zeiger auf eine `OLEOBJECT` -Struktur, die das erste ausgewählte OLE-Objekt angibt, wenn die Auswahl eines oder mehrere OLE-Elemente enthält. Wenn die Auswahl keine Elemente enthält *Lpoleobj* ist NULL. Die `OLEOBJECT` Struktur enthält einen Zeiger auf eine OLE-Objekt als V-Tabelle.

*lpchrg*<br/>
Zeiger auf eine [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) Struktur, die die aktuelle Auswahl enthält.

### <a name="return-value"></a>Rückgabewert

Handle für das Kontextmenü.

### <a name="remarks"></a>Hinweise

Diese Funktion ist eine typische Teil der rechten Maustaste Verarbeitung.

Der Auswahltyp kann es sich um eine beliebige Kombination der folgenden Flags sein:

- SEL_EMPTY gibt an, dass keine aktuelle Auswahl vorhanden ist.

- SEL_TEXT gibt an, dass die aktuelle Auswahl Text enthält.

- SEL_OBJECT gibt an, dass die aktuelle Auswahl mindestens ein OLE-Element enthält.

- SEL_MULTICHAR gibt an, dass die aktuelle Auswahl um mehr als ein Zeichen des Texts enthält.

- SEL_MULTIOBJECT gibt an, dass die aktuelle Auswahl mehrere OLE-Objekt enthält.

Die Standardimplementierung gibt NULL zurück. Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen finden Sie unter [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu) und [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) im Windows SDK.

##  <a name="getdocument"></a>  CRichEditView::GetDocument

Mit dieser Funktion können Sie einen Zeiger auf die `CRichEditDoc` dieser Ansicht zugeordnet.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) zugeordnete Objekt Ihrer `CRichEditView` Objekt.

##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem

Aufruf dieser Funktion zum Abrufen des OLE-Element ist derzeit aktiviert, an die Stelle in diesem `CRichEditView` Objekt.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den einzelnen, direkten aktiven [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in dieser Ansicht rich-Edit NULL, wenn keine OLE-Element derzeit in den aktiven Status des direktes.

##  <a name="getmargins"></a>  CRichEditView::GetMargins

Rufen Sie diese Funktion zum Abrufen der aktuellen Ränder, die beim Drucken verwendet.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Rückgabewert

Die Ränder verwendet beim Drucken, gemessen in MM_TWIPS.

##  <a name="getpagerect"></a>  CRichEditView::GetPageRect

Rufen Sie diese Funktion rufen Sie die Dimensionen von der Seite, die beim Drucken verwendet.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Grenzen der Seite verwendet, die beim Drucken, gemessen in MM_TWIPS.

### <a name="remarks"></a>Hinweise

Dieser Wert basiert auf das Papierformat.

##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize

Rufen Sie diese Funktion zum Abrufen der aktuellen Papierformat.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe des Papiers verwendet beim Drucken, gemessen in MM_TWIPS.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection

Rufen Sie diese Funktion zum Abrufen der absatzformatierung Attribute der aktuellen Auswahl.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Rückgabewert

Ein [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Struktur, die die Attribute der aktuellen Auswahl des absatzformatierung enthält.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [EM_GETPARAFORMAT](/windows/desktop/Controls/em-getparaformat) Nachricht und [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Struktur im Windows SDK.

##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect

Rufen Sie diese Funktion, um die Grenzen des Druckbereichs innerhalb des Rechtecks Seite abrufen.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Grenzen des dem Bildbereich verwendet beim Drucken, gemessen in MM_TWIPS.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth

Rufen Sie diese Funktion, um zu bestimmen, die Breite des Druckbereichs an.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite des Druckbereichs, gemessen in MM_TWIPS.

##  <a name="getricheditctrl"></a>  CRichEditView:: GetRichEditCtrl

Mit dieser Funktion wird zum Abrufen der [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) zugeordnete Objekt der `CRichEditView` Objekt.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Die `CRichEditCtrl` Objekt für diese Sicht.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::FindText](#findtext).

##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem

Mit dieser Funktion können Sie die OLE-Element abgerufen werden soll (eine `CRichEditCntrItem` Objekt) in diese ausgewählt `CRichEditView` Objekt.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) ausgewählte Objekt in der `CRichEditView` Objekt; NULL, wenn kein Element in dieser Ansicht ausgewählt ist.

##  <a name="gettextlength"></a>  CRichEditView::GetTextLength

Mit dieser Funktion wird zum Abrufen der Länge des Texts in dieser `CRichEditView` Objekt.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge des Texts in dieser `CRichEditView` Objekt.

##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx

Rufen Sie diese Memberfunktion zum Berechnen der Länge des Texts in dieser `CRichEditView` Objekt.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Wert, der die Methode, die verwendet werden, bei der Bestimmung der Länge angibt. Dieses Element kann eine oder mehrere der Werte in den Flags Member [GETTEXTLENGTHEX](/windows/desktop/api/richedit/ns-richedit-_gettextlengthex) im Windows SDK beschrieben.

*uCodePage*<br/>
Die Codepage für die Übersetzung (CP_ACP für ANSI-Codepage, 1.200 für Unicode).

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichen oder Bytes in das Steuerelement zum Bearbeiten. Wenn nicht kompatible Flags, im festgelegt wurden *DwFlags*, diese Memberfunktion wird E_INVALIDARG zurückgegeben.

### <a name="remarks"></a>Hinweise

`GetTextLengthEx` Stellt zusätzliche Methoden zum Bestimmen der Länge des Texts an. Die Funktionalität des Rich Edit 2.0 unterstützt. Weitere Informationen finden Sie unter [über Rich-Edit-Steuerelemente](/windows/desktop/Controls/about-rich-edit-controls) im Windows SDK.

##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject

Mit dieser Funktion wird zum Einfügen der angegebenen Datei (als eine [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt) in eine umfassende Ansicht bearbeiten.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Zeichenfolge, die mit dem Namen der Datei eingefügt werden soll.

##  <a name="insertitem"></a>  CRichEditView::InsertItem

Mit dieser Funktion wird zum Einfügen einer [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt in eine rich-Edit-Ansicht.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Element eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Wert, der angibt, der des Erfolgs der Einfügemarke.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu HRESULT, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat

Mit dieser Funktion wird ermittelt, ob *Cf* ist ein Zwischenablageformat wird Text, rich-Text oder rich-Text mit OLE-Elementen.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Parameter

*CF*<br/>
Das Zwischenablageformat an.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL *Cf* ist ein umfassender Zwischenablageformat bearbeiten oder Text.

##  <a name="isselected"></a>  CRichEditView::IsSelected

Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene OLE-Element derzeit in dieser Ansicht ausgewählt ist.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parameter

*pDocItem*<br/>
Zeiger auf ein Objekt in der Ansicht.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Objekt ausgewählt ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Ihrer abgeleiteten Ansichtsklasse eine andere Methode zur Behandlung der Auswahl von OLE-Elemente verfügt.

##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent

Die Einzüge für Aufzählungszeichen Elemente in einer Liste in der Standardeinstellung, 720 Einheiten, 1/2 Zoll.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap

Gibt den Typ des Zeilenumbruchs für diese rich-Edit-Ansicht an.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Hinweise

Einer der folgenden Werte:

- `WrapNone` Gibt an, keine automatischen Wortumbruch.

- `WrapToWindow` Gibt an, basierend auf der Breite des Fensters Wortumbruch.

- `WrapToTargetDevice` Gibt an, basierend auf den Merkmalen des Zielgeräts Wortumbruch.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::WrapChanged](#wrapchanged).

##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect

Rufen Sie diese Funktion, um die zeichenformatierung Effekte für die aktuelle Auswahl umzuschalten.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parameter

*dwMask*<br/>
Die Auswirkungen zu ändern, in der aktuellen Auswahl formatieren von Zeichen.

*dwEffect*<br/>
Die gewünschte Liste der zeichenformatierung Auswirkungen zu wechseln.

### <a name="remarks"></a>Hinweise

Jeder Aufruf dieser Funktion wird die angegebene Effekte für die Formatierung für die aktuelle Auswahl umgeschaltet.

Weitere Informationen zu den *DwMask* und *DwEffect* Parameter und deren mögliche Werte, finden Sie unter den entsprechenden Membern von Daten von [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>  CRichEditView::OnFindNext

Wird vom Framework aufgerufen, bei der Verarbeitung von Befehlen über das Dialogfeld Suchen/Ersetzen.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Die zu suchende Zeichenfolge.

*bWeiter*<br/>
Die Sortierrichtung zu suchen: "true" gibt an, nach unten; False gibt an, auf.

*bCase*<br/>
Gibt an, ob die Suche Groß-/Kleinschreibung beachtet werden.

*bWord*<br/>
Gibt an, ob die Suche nur ganze Wörter zu suchen.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können Sie Text in Suchen den `CRichEditView`. Überschreiben Sie diese Funktion zum Ändern der Eigenschaften Ihrer abgeleiteten Ansichtsklasse suchen.

##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate

Vom Framework aufgerufen, nachdem die Ansicht zuerst auf das Dokument angefügt ist, aber vor die Ansicht angezeigt wird.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung dieser Funktion die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Memberfunktion ohne Hinweis-Informationen (, also verwenden standardmäßig den Wert 0 für die *lHint* Parameter und NULL für den *pHint* Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung auszuführen, die Informationen über das Dokument erforderlich sind. Beispielsweise verfügt die Anwendung Dokumente mit fester Größe, können dieser Funktion Sie eine Ansicht der Bildlauf Einschränkungen aufgrund der Größe des Dokuments zu initialisieren. Wenn Ihre Anwendung variabler Größe von Dokumenten unterstützt, verwenden Sie `OnUpdate` zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument ändert.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::m_nWordWrap](#m_nwordwrap).

##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject

Verwenden Sie diese Funktion zum Laden nativer Daten über ein eingebettetes Element.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Parameter

*lpStg*<br/>
Zeiger auf ein [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; andernfalls 0

### <a name="remarks"></a>Hinweise

Normalerweise würde geschieht dies durch das Erstellen einer [COleStreamFile](../../mfc/reference/colestreamfile-class.md) rund um die `IStorage`. Die `COleStreamFile` angefügt werden können, um ein Archiv und [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) aufgerufen, um die Daten zu laden.

Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen finden Sie unter [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) im Windows SDK.

##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign

Rufen Sie diese Funktion, um die absatzausrichtung für die ausgewählte Absätze ändern.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Parameter

*wAlign*<br/>
Die gewünschte absatzausrichtung. Einer der folgenden Werte:

- PFA_LEFT richten Sie die Absätze mit dem linken Rand aus.

- PFA_RIGHT richten die Absätze mit den rechten Rand an.

- PFA_CENTER Absätze zwischen den Rändern des Datencenters.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged

Überschreiben Sie diese Funktion, um Eigenschaften für diese rich-Edit-Ansicht zu ändern, wenn der Drucker ändert.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Parameter

*dcPrinter*<br/>
Ein [CDC](../../mfc/reference/cdc-class.md) -Objekt für den neuen Drucker.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung legt das Papierformat auf die physischen Höhe und Breite für das Ausgabegerät (Drucker) fest. Es ist keine Gerätekontext zugeordnet *DcPrinter*, die standardmäßige Implementierung legt das Papierformat auf 8,5 x 11 Zoll.

##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll

Vom Framework aufgerufen, bei der Verarbeitung von ersetzen alle Befehle aus dem Dialogfeld ersetzen.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text ersetzt werden.

*lpszReplace*<br/>
Der Ersatztext.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.

*bWord*<br/>
Gibt an, ob es sich bei die Suche ganze Wörter oder nicht auswählen muss.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um alle Vorkommen des angegebenen Text durch eine andere Zeichenfolge ersetzen. Überschreiben Sie diese Funktion zum Durchsuchen von Eigenschaften für diese Ansicht zu ändern.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::FindText](#findtext).

##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel

Vom Framework aufgerufen, bei der Verarbeitung von Replace-Befehle aus dem Dialogfeld ersetzen.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text ersetzt werden.

*bWeiter*<br/>
Gibt die Richtung der Suche: "true" wird nach unten; False gibt an, auf.

*bCase*<br/>
Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird.

*bWord*<br/>
Gibt an, ob es sich bei die Suche ganze Wörter oder nicht auswählen muss.

*lpszReplace*<br/>
Der Ersatztext.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können ein Vorkommen des angegebenen Text durch eine andere Zeichenfolge ersetzen. Überschreiben Sie diese Funktion zum Durchsuchen von Eigenschaften für diese Ansicht zu ändern.

##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound

Vom Framework aufgerufen, wenn eine Suche ein Fehler auftritt.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Der Text wurde nicht gefunden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Ausgabe von änderungsbenachrichtigungen eine [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep).

Weitere Informationen finden Sie unter [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect

Das Framework ruft diese Funktion, um die Befehlsbenutzeroberfläche für Zeichen Auswirkungen Befehle zu aktualisieren.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt.

*dwMask*<br/>
Gibt an, der die zeichenformatierung Maske.

*dwEffect*<br/>
Gibt an, der die zeichenformatierung wirksam.

### <a name="remarks"></a>Hinweise

Die Maske *DwMask* gibt an, welches Formatierungsattribute überprüft Zeichen. Die Flags *DwEffect* Liste die zeichenformatierung Attribute Set/löschen.

Weitere Informationen zu den *DwMask* und *DwEffect* Parameter und deren mögliche Werte, finden Sie unter den entsprechenden Membern von Daten von [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign

Das Framework ruft diese Funktion, um die Befehlsbenutzeroberfläche für Absatz Auswirkungen Befehle zu aktualisieren.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Zeiger auf eine [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt.

*wAlign*<br/>
Die absatzausrichtung, um zu überprüfen. Einer der folgenden Werte:

- PFA_LEFT richten Sie die Absätze mit dem linken Rand aus.

- PFA_RIGHT richten die Absätze mit den rechten Rand an.

- PFA_CENTER Absätze zwischen den Rändern des Datencenters.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect

Mit dieser Funktion können Sie einen Textbereich in einem rich-Edit-Steuerelement in eingepasst formatieren *RectLayout* für das Gerät gemäß *pDC*.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeiger auf einen Gerätekontext für den Ausgabebereich.

*rectLayout*<br/>
[RECT](../../mfc/reference/rect-structure1.md) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) definiert, die den Ausgabebereich.

*nIndexStart*<br/>
Nullbasierte Index des ersten Zeichens, das formatiert werden.

*nIndexStop*<br/>
Nullbasierte Index des letzten Zeichens formatiert werden.

*bOutput*<br/>
Gibt an, ob der Text gerendert werden soll. False gibt an, wird der Text nur gemessen.

### <a name="return-value"></a>Rückgabewert

Der Index des letzten Zeichens, der in den Ausgabebereich plus eins passt.

### <a name="remarks"></a>Hinweise

Dieser Aufruf folgt in der Regel durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) durch die die Ausgabe generiert.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="printpage"></a>  CRichEditView::PrintPage

Mit dieser Funktion können Sie einen Textbereich in einem rich-Edit-Steuerelement für das Ausgabegerät gemäß formatieren *pDC*.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeiger auf einen Gerätekontext für Seite ausgegeben.

*nIndexStart*<br/>
Nullbasierte Index des ersten Zeichens, das formatiert werden.

*nIndexStop*<br/>
Nullbasierte Index des letzten Zeichens formatiert werden.

### <a name="return-value"></a>Rückgabewert

Der Index des letzten Zeichens, das auf der Seite plus 1 entspricht.

### <a name="remarks"></a>Hinweise

Das Layout jeder Seite wird gesteuert, indem [GetPageRect](#getpagerect) und [GetPrintRect](#getprintrect). Dieser Aufruf folgt in der Regel durch einen Aufruf von [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) durch die die Ausgabe generiert.

Beachten Sie, dass Ränder Bezug auf die physische Seite, nicht die logische Seite. Daher werden Ränder 0 (null) den Text häufig zugeschnitten, da viele Drucker nicht bedruckbaren Bereiche auf der Seite verfügen. Um zu vermeiden, kürzen den Text, rufen Sie [SetMargins](#setmargins) und legen Sie angemessene Ränder vor dem Drucken.

##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData

Wird aufgerufen, durch das Framework um ein Objekt in den rich-Edit einzufügen.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>Parameter

*lpdataobj*<br/>
Zeiger auf die [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Abfrage.

*lpcfFormat*<br/>
Zeiger auf das Format akzeptabel.

*dwReco*<br/>
Nicht verwendet.

*bReally*<br/>
Gibt an, ob die Einfügen-Vorgang werden oder nicht fortgesetzt soll.

*hMetaFile*<br/>
Ein Handle der Metadatei, die zum Zeichnen des Symbols.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Wert, der den Erfolg des Vorgangs gemeldet wird.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion zur Verarbeitung der anderen Organisation von COM-Elementen in der abgeleiteten Dokumentklasse. Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen zu HRESULT und `IDataObject`, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) und [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject)bzw., im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat

Mit dieser Funktion können Sie die Formatierung von Attributen für den neuen Text in diesem Zeichensatz `CRichEditView` Objekt.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Parameter

*CF*<br/>
[CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Struktur, die das neue Standardzeichen Formatierungsattribute enthält.

### <a name="remarks"></a>Hinweise

Nur die Attribute, die gemäß der `dwMask` Mitglied *Cf* , die von dieser Funktion geändert werden.

Weitere Informationen finden Sie unter [EM_SETCHARFORMAT](/windows/desktop/Controls/em-setcharformat) Nachricht und [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Struktur im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>  CRichEditView::SetMargins

Rufen Sie diese Funktion, um die Druckränder für diese rich-Edit-Ansicht festgelegt.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Parameter

*rectMargin*<br/>
Die neue Randwerte für das Drucken, gemessen in MM_TWIPS.

### <a name="remarks"></a>Hinweise

Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.

Beachten Sie, die die Ränder von verwendet [PrintPage](#printpage) sind relativ zum physischen Seite, nicht die logische Seite. Daher werden Ränder 0 (null) den Text häufig zugeschnitten, da viele Drucker nicht bedruckbaren Bereiche auf der Seite verfügen. Um zu vermeiden, kürzen den Text, rufen Sie die Verwendung `SetMargins` angemessenen Drucker Ränder vor dem Drucken festlegen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize

Rufen Sie diese Funktion zum Festlegen des Papierformats für diese rich-Edit-Ansicht zu drucken.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Parameter

*sizePaper*<br/>
Die neuen Werte der Dokument-Größe für den Druck, gemessen in MM_TWIPS.

### <a name="remarks"></a>Hinweise

Wenn [m_nWordWrap an](#m_nwordwrap) ist `WrapToTargetDevice`, rufen Sie [WrapChanged](#wrapchanged) nach der Verwendung dieser Funktion Druckeigenschaften anpassen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat

Mit dieser Funktion wird zum Festlegen des Formatierung der Attribute für die aktuelle Auswahl in diesem Absatzes `CRichEditView` Objekt.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Parameter

*pf*<br/>
[PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Struktur, die den neuen Standard enthält Absatz Formatierungsattribute.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Nur die Attribute, die gemäß der `dwMask` Mitglied *Pf* , die von dieser Funktion geändert werden.

Weitere Informationen finden Sie unter [EM_SETPARAFORMAT](/windows/desktop/Controls/em-setparaformat) Nachricht und [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Struktur im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>  CRichEditView::TextNotFound

Mit dieser Funktion können Sie den internen Suche Status zurücksetzen der [CRichEditView](../../mfc/reference/cricheditview-class.md) Steuerelement nach einem fehlgeschlagenen Aufruf [FindText](#findtext).

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parameter

*lpszFind*<br/>
Enthält die Zeichenfolge, die nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Es wird empfohlen, diese Methode aufgerufen werden, sofort nach fehlerhaften Aufrufen auf [FindText](#findtext) , damit die interne Suche Zustand des Steuerelements ordnungsgemäß zurückgesetzt wird.

Die *LpszFind* Parameter muss den gleichen Inhalt wie bereitgestellte Zeichenfolge enthalten [FindText](#findtext). Nach dem Zurücksetzen des Status interner suchen, diese Methode aufrufen, wird die [OnTextNotFound](#ontextnotfound) Methode mit der angegebenen Suchzeichenfolge.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRichEditView::FindText](#findtext).

##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged

Diese Funktion aufrufen, wenn die Druckeigenschaften geändert wurden ( [SetMargins](#setmargins) oder [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Hinweise

Außer Kraft setzen, die diese Funktion, die so zu ändern, die Rich--Ansicht Edit auf Änderungen in reagiert [m_nWordWrap an](#m_nwordwrap) oder die Druckeigenschaften ( [OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)
