---
title: CView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
ms.openlocfilehash: f325423c940df46940d7074c599eb8e502e90586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50669078"
---
# <a name="cview-class"></a>CView-Klasse

Stellt die grundlegende Funktionalität für benutzerdefinierte Ansichtsklassen bereit.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CView::CView](#cview)|Erstellt ein `CView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CView::DoPreparePrinting](#doprepareprinting)|Zeigt das Dialogfeld Drucken und Drucker-Gerätekontext erstellt; Beim Überschreiben von Aufrufen der `OnPreparePrinting` Member-Funktion.|
|[CView::GetDocument](#getdocument)|Gibt zurück, das Dokument, das der Ansicht zugeordnet.|
|[CView::IsSelected](#isselected)|Testet, ob ein Dokumentelement ausgewählt ist. Für OLE-Unterstützung erforderlich sind.|
|[CView::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn ein Element in der Region ziehen und Ablegen einer Ansicht zunächst gezogen wird.|
|[CView::OnDragLeave](#ondragleave)|Aufgerufen, wenn ein gezogenes Element auf die Region ziehen und Ablegen einer Sicht verlässt.|
|[CView::OnDragOver](#ondragover)|Aufgerufen, wenn ein Element über dem Bereich ziehen und Ablegen einer Sicht gezogen wird.|
|[CView::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in der Region Scrollen Sie im Fenster gezogen wird.|
|[CView::OnDrop](#ondrop)|Aufgerufen, wenn ein Element in der Region ziehen und Ablegen einer Ansicht Standardhandler gelöscht wurde.|
|[CView::OnDropEx](#ondropex)|Aufgerufen, wenn ein Element in der Region ziehen und Ablegen einer Sicht, die primären Ereignishandler gelöscht wurde.|
|[CView:: OnInitialUpdate](#oninitialupdate)|Wird aufgerufen, nachdem ein Dokument zuerst eine Ansicht zugeordnet ist.|
|[CView::OnPrepareDC](#onpreparedc)|Wird aufgerufen, bevor die `OnDraw` Memberfunktion aufgerufen wird, für die Bildschirmanzeige oder der `OnPrint` für Druck oder den Seitenansichtmodus Memberfunktion aufgerufen wird.|
|[CView::OnScroll](#onscroll)|Wird aufgerufen, wenn OLE-Elementen, jenseits der Grenzen der Ansicht gezogen werden.|
|[CView::OnScrollBy](#onscrollby)|Wird aufgerufen, wenn eine Ansicht mit der aktiven direkten OLE-Elemente ein Bildlauf durchgeführt wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CView::OnActivateFrame](#onactivateframe)|Wird aufgerufen, wenn das Rahmenfenster, das die Sicht aktiviert oder deaktiviert wird.|
|[CView::OnActivateView](#onactivateview)|Wird aufgerufen, wenn eine Ansicht aktiviert wird.|
|[CView::OnBeginPrinting](#onbeginprinting)|Wird aufgerufen, wenn ein Auftrag beginnt; Überschreiben Sie, um die Graphics Device Interface (GDI) Ressourcen zuordnen.|
|[CView:: OnDraw](#ondraw)|Wird aufgerufen, um ein Bild des Dokuments für die Bildschirmanzeige, Drucken und Druckvorschau zu rendern. Die Implementierung erforderlich sind.|
|[CView::OnEndPrinting](#onendprinting)|Wird aufgerufen, wenn ein Auftrag beendet; außer Kraft setzen, um GDI-Ressourcen freizugeben.|
|[CView::OnEndPrintPreview](#onendprintpreview)|Aufgerufen, wenn Sie den Vorschaumodus beendet wird.|
|[CView::OnPreparePrinting](#onprepareprinting)|Wird aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird; außer Kraft setzen Sie, um das Dialogfeld Drucken zu initialisieren.|
|[CView::OnPrint](#onprint)|Wird aufgerufen, um drucken oder Anzeigen einer Seite des Dokuments.|
|[CView::OnUpdate](#onupdate)|Wird aufgerufen, um eine Ansicht zu benachrichtigen, die sein Dokument wurde geändert.|

## <a name="remarks"></a>Hinweise

Eine Sicht ist an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und der Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm oder Drucker und Benutzereingaben als Vorgänge, bei dem Dokument interpretiert.

Eine Sicht ist ein untergeordnetes Element des ein Rahmenfenster. Mehrere Ansichten kann ein Rahmenfenster, wie im Fall eines unterteilten Fensters freigeben. Die Beziehung zwischen einer View-Klasse, ein Rahmenfenster (Klasse) und eine "Document"-Klasse wird hergestellt, indem eine `CDocTemplate` Objekt. Wenn der Benutzer öffnet ein neues Fenster oder teilt eine vorhandene eines, das Framework erstellt eine neue Ansicht, und fügt sie dem Dokument.

Eine Sicht kann nur ein Dokument angefügt werden, aber ein Dokument kann mehrere Sichten gleichzeitig angefügt aufweisen, z. B., wenn das Dokument in einem Splitterfenster oder in mehreren untergeordneten Fenstern in eine Anwendung der multiple Document Interface (MDI) angezeigt wird. Ihre Anwendung kann verschiedene Arten von Ansichten für einen bestimmten Dokumenttyp unterstützen; Beispielsweise kann ein Textverarbeitungsprogramm bereitstellen, sowohl eine vollständige Textansicht eines Dokuments und einer Gliederungsansicht, die nur die Abschnittsüberschriften anzeigt. Die unterschiedlichen Arten von Ansichten können in separaten Rahmenfenster oder in separaten Bereichen von einem einzelnen Rahmenfenster platziert werden, bei der Verwendung eines unterteilten Fensters.

Eine Ansicht möglicherweise für die Behandlung von verschiedenen Arten von Eingaben wie Tastatureingaben, Mauseingaben oder Eingaben über die Drag & Drop sowie Befehle in Menüs, Symbolleisten oder Bildlaufleisten verantwortlich. Eine Ansicht erhält die Befehle, die vom zugehörigen Rahmenfenster weitergeleitet. Wenn die Sicht keinen bestimmten Befehl behandelt, wird der Befehl aus, um die zugeordnete Dokument weitergeleitet. Wie alle Befehlsziele verarbeitet eine Ansicht für Nachrichten über einer meldungszuordnung.

Die Ansicht ist verantwortlich für das Anzeigen und ändern die Daten des Dokuments jedoch nicht für sie zu speichern. Das Dokument enthält die Ansicht mit den erforderlichen Details über ihre Daten. Sie können den Zugriff auf, die, den direkt die Datenmember des Dokuments ein, oder Sie Member-Funktionen in der Dokumentklasse für den View-Klasse aufrufen, bereitstellen können.

Wenn Daten eines Dokuments geändert wird, ruft die Ansicht, die dafür verantwortlich, die Änderungen in der Regel die [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) -Funktion für das Dokument, das die anderen Ansichten von Aufrufen benachrichtigt die `OnUpdate` Memberfunktion Jeder. Die standardmäßige Implementierung des `OnUpdate` macht die Ansicht des gesamten Clientbereich ungültig. Sie können überschreiben, um nur solche Bereiche von den Clientbereich für ungültig zu erklären, die die geänderten Teile des Dokuments zugeordnet, werden soll.

Mit `CView`, eine Klasse ableiten und Implementieren der `OnDraw` Memberfunktion Bildschirmanzeige ausführen. Sie können auch `OnDraw` zum Drucken und Druckvorschau ausführen. Das Framework verarbeitet die print, Loop zum Drucken und die Vorschau des Dokuments.

Eine Ansicht verarbeitet Bildlaufleisten-Nachrichten mit der [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Können Sie Bildlaufleisten-meldungsverarbeitung in diesen Funktionen implementieren, oder Sie können die `CView` abgeleitete Klasse [CScrollView](../../mfc/reference/cscrollview-class.md) , behandeln Sie einen Bildlauf.

Darüber hinaus `CScrollView`, die Microsoft Foundation Class-Bibliothek stellt neun Klassen, die von `CView`:

- [CCtrlView](../../mfc/reference/cctrlview-class.md), eine Sicht, die die Verwendung von Dokument - View-Architektur mit der Struktur, Liste und Rich edit-Steuerelemente.

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), eine Sicht, die Datensätze im Dialogfeld-Steuerelemente anzeigt.

- [CEditView](../../mfc/reference/ceditview-class.md), eine Sicht, die einen einfachen mehrzeiligen Text-Editor bereitstellt. Sie können eine `CEditView` -Objekt als ein Steuerelement in einem Dialogfeld als auch für eine Ansicht in einem Dokument.

- [CFormView](../../mfc/reference/cformview-class.md), eine bildlauffähige Ansicht, die im Dialogfeld Steuerelemente enthält und basiert auf einer Dialogfeldvorlagen-Ressource.

- [CListView](../../mfc/reference/clistview-class.md), eine Sicht, die Verwendung von Dokument - / Ansichtsarchitektur mit Listensteuerelemente ermöglicht.

- [CRecordView](../../mfc/reference/crecordview-class.md), eine Sicht, die Datensätze im Dialogfeld-Steuerelemente anzeigt.

- [CRichEditView](../../mfc/reference/cricheditview-class.md), eine Sicht, die die Verwendung von Dokument - View-Architektur mit Rich edit-Steuerelemente.

- [CScrollView](../../mfc/reference/cscrollview-class.md), eine Sicht, die automatisch Bildlauf unterstützt.

- [CTreeView](../../mfc/reference/ctreeview-class.md), eine Sicht, die Verwendung von Dokument - / Ansichtsarchitektur mit Strukturansicht-Steuerelementen ermöglicht.

Die `CView` -Klasse verfügt auch über eine abgeleitete Implementierung-Klasse, die mit dem Namen `CPreviewView`, der von dem Framework verwendet wird, zum Ausführen der Seitenansicht. Diese Klasse bietet Unterstützung für den einzigartigen Features von Seitenansicht-Fenster, z. B. eine Symbolleiste, oder Double-Wert-Einzelseiten - Vorschau und Zoomen wird, die das in der Vorschau angezeigten Bild vergrößern. Müssen nicht aufrufen oder Überschreiben eines `CPreviewView`der Memberfunktionen, es sei denn, Sie möchten Ihre eigene Schnittstelle für die Seitenansicht implementieren (beispielsweise, wenn Sie unterstützen die Bearbeitung im Seitenansichtsmodus möchten). Weitere Informationen zur Verwendung von `CView`, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [Drucken](../../mfc/printing.md). Darüber hinaus finden Sie unter [technischen Hinweis 30](../../mfc/tn030-customizing-printing-and-print-preview.md) ausführliche Informationen zum Anpassen der Seitenansicht angezeigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cview"></a>  CView::CView

Erstellt ein `CView`-Objekt.

```
CView();
```

### <a name="remarks"></a>Hinweise

Das Framework Ruft den Konstruktor, wenn ein neues Rahmenfensterobjekt erstellt wird, oder Teilen Sie ein Fenster ist. Überschreiben der [OnInitialUpdate](#oninitialupdate) Memberfunktion, um die Ansicht zu initialisieren, nachdem das Dokument angefügt ist.

##  <a name="doprepareprinting"></a>  CView::DoPreparePrinting

Mit dieser Funktion wird von der Ihre Überschreibung der [OnPreparePrinting](#onprepareprinting) zum Aufrufen des Dialogfelds drucken, und erstellen einen Drucker-Gerätekontext.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Druck oder den Seitenansichtmodus beginnen kann; 0, wenn der Vorgang abgebrochen wurde.

### <a name="remarks"></a>Hinweise

Hängt von dieser Funktion Verhalten gibt an, ob es für den Druck oder den Seitenansichtmodus aufgerufen wird (gemäß der `m_bPreview` Mitglied der *"pInfo"* Parameter). Wenn eine Datei gedruckt wird, ruft diese Funktion das Dialogfeld "Drucken", mithilfe der Werte in der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Datenstruktur, *"pInfo"* zeigt auf, nachdem der Benutzer das Dialogfeld geschlossen, die Funktion erstellt ein Druckergerätekontext basierend auf Einstellungen im Dialogfeld angegebenen Benutzer und gibt dieser Gerätekontext über die *"pInfo"* Parameter. Dieser Gerätekontext wird verwendet, um das Dokument zu drucken.

Wenn eine Datei in der Vorschau ist, erstellt diese Funktion einen Drucker-Gerätekontext mithilfe der aktuellen Druckereinstellungen; Dieser Gerätekontext wird verwendet, für die Simulation des Druckers während der Vorschauphase.

##  <a name="getdocument"></a>  CView::GetDocument

Rufen Sie diese Funktion, um einen Zeiger auf die Ansicht des Dokuments erhalten.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CDocument](../../mfc/reference/cdocument-class.md) Objekt, mit der Ansicht verknüpft ist. NULL, wenn die Ansicht nicht an ein Dokument angefügt ist.

### <a name="remarks"></a>Hinweise

Dadurch können Sie zum Aufrufen von Memberfunktionen des Dokuments ab.

##  <a name="isselected"></a>  CView::IsSelected

Wird aufgerufen, durch das Framework zu überprüfen, ob das angegebene Dokument-Element ausgewählt ist.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parameter

*pDocItem*<br/>
Verweist auf das Dokumentelement getestet wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das angegebene Dokument-Element ausgewählt ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion gibt FALSE zurück. Überschreiben Sie diese Funktion, wenn Sie mit der Auswahl implementieren [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte. Sie müssen diese Funktion überschreiben, wenn Ihrer Ansicht OLE-Elemente enthält.

##  <a name="onactivateframe"></a>  CView::OnActivateFrame

Wird vom Framework aufgerufen, wenn das Rahmenfenster, das die Sicht aktiviert oder deaktiviert ist.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parameter

*nState*<br/>
Gibt an, ob das Rahmenfenster wird aktiviert oder deaktiviert. Es kann eine der folgenden Werte sein:

- WA_INACTIVE das Rahmenfenster ist deaktiviert.

- WA_ACTIVE, die das Rahmenfenster aktiviert wird, über eine Methode als eine Maus klicken Sie auf (z. B. durch Verwenden der Tastaturschnittstelle des Fensters auswählen).

- WA_CLICKACTIVE das Rahmenfenster ist durch einen Mausklick aktiviert wird

*pFrameWnd*<br/>
Zeiger auf das Rahmenfenster, das aktiviert werden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Memberfunktion auf, sollten Sie durchführen, besondere Bearbeitung, wenn das Rahmenfenster der Ansicht zugeordnet sind, aktiviert oder deaktiviert wird. Z. B. [CFormView](../../mfc/reference/cformview-class.md) führt diese außer Kraft setzen, speichert und stellt das Steuerelement, das Fokus besitzt.

##  <a name="onactivateview"></a>  CView::OnActivateView

Vom Framework aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert ist.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>Parameter

*bActivate*<br/>
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.

*pActivateView*<br/>
Verweist auf das Objekt, das aktiviert wird.

*pDeactiveView*<br/>
Verweist auf das Objekt, das deaktiviert wird.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion setzt den Fokus auf die Ansicht aktiviert wird. Überschreiben Sie diese Funktion, sollten Sie durchführen, besondere Bearbeitung, wenn eine Ansicht aktiviert oder deaktiviert ist. Beispielsweise sollten Sie besondere visuelle Hinweise bereitzustellen, die die aktive Ansicht, die von den inaktiven Ansichten unterscheiden zu können, Sie werden analysiert die *bActivate* Parameter und der Ansicht Darstellung entsprechend aktualisieren.

Die *pActivateView* und *pDeactiveView* Parameter zeigen Sie auf der gleichen Ansicht, wenn der Anwendung Hauptrahmenfenster ohne Änderung in der aktiven Ansicht aktiviert ist, wenn der Fokus wird z. B. Wenn Sie für untergeordnete MDI-Fenster wechseln von einer anderen Anwendung dieser Klasse und nicht von einer Sicht in eine andere in der Anwendung oder übertragen werden soll. Dies ermöglicht eine Ansicht für die Palette, erneut zu erkennen, bei Bedarf.

Diese Parameter unterscheiden sich bei der [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) aufgerufen wird und eine Ansicht, die von Was unterscheidet [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) zurück. Dies geschieht meist, Splitterfenster.

##  <a name="onbeginprinting"></a>  CView::OnBeginPrinting

Wird zu Beginn eines Druckauftrags oder Seitenansichtauftrags vom Framework aufgerufen, nachdem `OnPreparePrinting` aufgerufen wurde.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Druckergerätekontext.

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle speziell für den Druck benötigten GDI-Ressourcen, z. B. Stifte oder Schriftarten, zuzuordnen. Wählen Sie die GDI-Objekte für den Gerätekontext aus der [OnPrint](#onprint) -Memberfunktion für jede Seite auf, von der sie verwendet werden. Wenn Sie das gleiche Ansichtsobjekt verwenden, um den Bildschirm anzuzeigen und zu drucken, verwenden Sie separate Variablen für die für jeden Bildschirm erforderlichen GDI-Ressourcen. Dadurch können Sie den Bildschirm während des Druckens aktualisieren.

Mit dieser Funktion können Sie auch Initialisierungen durchführen, die von Eigenschaften des Druckergerätekontextes abhängig sind. Beispielsweise kann die Anzahl der Seiten, die zum Drucken des Dokuments benötigt werden, von den Einstellungen abhängig sein, die der Benutzer im Dialogfeld „Drucken“ (z. B. Seitenlänge) angibt. In einem solchen Fall können Sie die Länge des Dokuments nicht wie normalerweise in der [OnPreparePrinting](#onprepareprinting) -Memberfunktion angeben; Sie müssen warten, bis der Druckergerätekontext basierend auf den Einstellungen des Dialogfelds erstellt wurde. [OnBeginPrinting](#onbeginprinting) ist die erste überschreibbare Funktion, die Ihnen sofortigen Zugriff auf das [CDC](../../mfc/reference/cdc-class.md) -Objekt gibt, das den Druckergerätekontext darstellt, daher können Sie die Länge des Dokuments mithilfe dieser Funktion festlegen. Wenn die Länge des Dokuments nicht zu diesem Zeitpunkt angegeben wird, wird in der Seitenansicht keine Bildlaufleiste angezeigt.

##  <a name="ondragenter"></a>  CView::OnDragEnter

Vom Framework aufgerufen, wenn die Maus in der Region ohne Bildlauf im Zielfenster zuerst eintritt.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pDataObject*<br/>
Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) in den Ablagebereich der Ansicht gezogen wird.

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Eine Kombination aus einer beliebigen Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Zeigen Sie*<br/>
Der aktuellen Position relativ zum Clientbereich der Ansicht.

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der-DropEffect-aufgelistet, Typ, der den Typ der Dropdownliste gibt an, die auftreten würden, wenn der Benutzer das Objekt an dieser Position abgelegt wird. Der Typ des Drop hängt normalerweise von den aktuellen Schlüssel Zustand erkennbar *DwKeyState*. Eine standardmäßige Zuordnung von Keystates-DropEffect-Werte ist:

- DROPEFFECT_NONE das Datenobjekt, das kann nicht in diesem Fenster gelöscht werden.

- DROPEFFECT_LINK für MK_CONTROL &#124; MK_SHIFT erstellt eine Verknüpfung zwischen dem Objekt und den Server.

- DROPEFFECT_COPY für MK_CONTROL erstellt eine Kopie des gelöschten Objekts.

- DROPEFFECT_MOVE für MK_ALT erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt. Dies ist normalerweise die Standard-Drop-Effekt, wenn die Ansicht dieses Datenobjekt annehmen kann.

Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).

### <a name="remarks"></a>Hinweise

Standardimplementierung wird keine Aktion durchführen und DROPEFFECT_NONE zurück.

Überschreiben Sie diese Funktion zur Vorbereitung der zukünftiger Aufrufen von der [OnDragOver](#ondragover) Member-Funktion. Alle Daten, die erforderlich sind, aus dem Datenobjekt abgerufen werden soll, zu diesem Zeitpunkt zur späteren Verwendung in der `OnDragOver` Member-Funktion. Die Ansicht sollte ebenfalls aktualisiert werden, zu diesem Zeitpunkt um visuelles Feedback zu geben. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondragleave"></a>  CView::OnDragLeave

Wird von Framework während eines Ziehvorgangs aufgerufen, wenn die Maus aus den gültigen Ablegebereich für dieses Fenster verschoben wird.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn die aktuelle Ansicht benötigt, um alle ausgeführten Aktionen während des zu bereinigen [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) aufrufen, z. B. alle visuelles Benutzerfeedback auf Entfernen, während das Objekt gezogen und dort abgelegt wurde .

##  <a name="ondragover"></a>  CView::OnDragOver

Wird von Framework während eines Ziehvorgangs aufgerufen, wenn die Maus über dem Drop-Ziel-Fenster verschoben wird.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pDataObject*<br/>
Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) über das Ablageziel gezogen wird.

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Eine Kombination aus einer beliebigen Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Zeigen Sie*<br/>
Der aktuellen Position relativ zum Clientbereich anzeigen.

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der-DropEffect-aufgelistet, Typ, der den Typ der Dropdownliste gibt an, die auftreten würden, wenn der Benutzer das Objekt an dieser Position abgelegt wird. Der Typ des Drop häufig hängt von den aktuellen Status des Schlüssels durch *DwKeyState*. Eine standardmäßige Zuordnung von Keystates-DropEffect-Werte ist:

- DROPEFFECT_NONE das Datenobjekt, das kann nicht in diesem Fenster gelöscht werden.

- DROPEFFECT_LINK für MK_CONTROL &#124; MK_SHIFT erstellt eine Verknüpfung zwischen dem Objekt und den Server.

- DROPEFFECT_COPY für MK_CONTROL erstellt eine Kopie des gelöschten Objekts.

- DROPEFFECT_MOVE für MK_ALT erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt. Dies ist normalerweise die Standard-Drop-Effekt, wenn die Ansicht das-Objekt akzeptieren kann.

Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ist keine Aktion durchführen und DROPEFFECT_NONE zurück.

Überschreiben Sie diese Funktion, um während des Ziehvorgangs visuelles Feedback zu geben. Da diese Funktion kontinuierlich aufgerufen wird, sollten alle darin enthaltenen Code so weit wie möglich optimiert werden. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondragscroll"></a>  CView::OnDragScroll

Wird aufgerufen, durch das Framework vor dem Aufruf [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) zu bestimmen, ob der Punkt im Bildlaufbereich ist.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Eine Kombination aus einer beliebigen Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Zeigen Sie*<br/>
Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der-DropEffect-aufgelistet, Typ, der den Typ der Dropdownliste gibt an, die auftreten würden, wenn der Benutzer das Objekt an dieser Position abgelegt wird. Der Typ des Drop hängt normalerweise von den aktuellen Schlüssel Zustand erkennbar *DwKeyState*. Eine standardmäßige Zuordnung von Keystates-DropEffect-Werte ist:

- DROPEFFECT_NONE das Datenobjekt, das kann nicht in diesem Fenster gelöscht werden.

- DROPEFFECT_LINK für MK_CONTROL &#124; MK_SHIFT erstellt eine Verknüpfung zwischen dem Objekt und den Server.

- DROPEFFECT_COPY für MK_CONTROL erstellt eine Kopie des gelöschten Objekts.

- DROPEFFECT_MOVE für MK_ALT erstellt eine Kopie des gelöschten Objekts und löschen Sie das ursprüngliche Objekt.

- DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für den Bildlauf durchgeführt wird oder in der Ansicht stattfindet.

Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie für dieses Ereignis besonderes Verhalten bereitstellen möchten. Die Standardimplementierung scrollt Windows automatisch, wenn der Cursor in die Standard-Bildlaufbereich in den Rahmen der einzelnen Fenster gezogen wird. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondraw"></a>  CView:: OnDraw

Wird aufgerufen, durch das Framework um ein Bild des Dokuments zu rendern.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Gerätekontext zum Rendern eines Bilds des Dokuments verwendet werden soll.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion, um die Bildschirmanzeige, Drucken und Druckvorschau ausführen, und übergibt einen anderes Gerätekontext in jedem Fall. Es ist keine Standardimplementierung vorhanden.

Sie müssen diese Funktion, um Ihre Ansicht des Dokuments anzuzeigen, überschreiben. Aufrufe grafische Device Interface (GDI) mithilfe der [CDC](../../mfc/reference/cdc-class.md) Objekt verweist die *pDC* Parameter. Sie GDI-Ressourcen, z. B. Stifte oder Schriftarten, für den Gerätekontext vor dem Zeichnen aktivieren und deaktivieren diese anschließend. Häufig kann Ihr Code zum Zeichnen geräteunabhängige sein. Es erfordert, also keine Informationen über die Art des Geräts auf das Bild angezeigt wird.

Um die Zeichnung weiter zu optimieren, rufen Sie die [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) -Memberfunktion des Gerätekontexts, um herauszufinden, ob ein angegebenes Rechteck gezeichnet werden. Wenn Sie die Unterscheidung zwischen normalen Bildschirm anzeigen und drucken möchten, rufen Sie die [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) -Memberfunktion des Gerätekontexts.

##  <a name="ondrop"></a>  CView::OnDrop

Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt über ein gültiges Ablageziel.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parameter

"pDataObject * verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in das Ablageziel abgelegt wurde.

*-DropEffect-*<br/>
Der Drop-Effekt, den der Benutzer angefordert hat.

- DROPEFFECT_COPY erstellt eine Kopie der Datenobjekt, das gelöscht werden.

- DROPEFFECT_MOVE verschiebt das Objekt an die aktuelle Position des Mauszeigers.

- DROPEFFECT_LINK erstellt eine Verknüpfung zwischen einem Datenobjekt und einem Server.

*Zeigen Sie*<br/>
Der aktuellen Position relativ zum Clientbereich anzeigen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Dropdownliste erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung führt keine Aktion aus und gibt FALSE zurück.

Überschreiben Sie diese Funktion, um die Auswirkungen der OLE-Drop in den Clientbereich der Ansicht zu implementieren. Das Datenobjekt, das untersucht werden kann, über *pDataObject* Zwischenablagedaten-Formate und -Daten gelöscht am angegebenen Punkt.

> [!NOTE]
>  Das Framework ruft diese Funktion nicht, liegt eine Außerkraftsetzung für [OnDropEx](#ondropex) in dieser Ansichtsklasse.

##  <a name="ondropex"></a>  CView::OnDropEx

Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt über ein gültiges Ablageziel.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pDataObject*<br/>
Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in das Ablageziel abgelegt wurde.

*dropDefault*<br/>
Die Auswirkungen, die der Benutzer für den Standard-Drop-Vorgang basierend auf dem aktuellen Schlüssel Status auswählen. Es kann DROPEFFECT_NONE sein. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

*Dropdownliste*<br/>
Eine Liste mit der Drop-Effekten, die die Quelle unterstützt. Drop-Effekt-Werte können kombiniert werden, mit dem bitweisen OR ( **&#124;**) Vorgang. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

*Zeigen Sie*<br/>
Der aktuellen Position relativ zum Clientbereich anzeigen.

### <a name="return-value"></a>Rückgabewert

Die Drop-Effekt, die bei der Löschversuch an die vom angegebenen Speicherort *zeigen*. Dies muss einer der Werte erkennbar sein *DropEffectList*. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ist keine Aktion durchführen und Zurückgeben einer Dummywert (-1), um anzugeben, dass das Framework aufrufen soll die [OnDrop](#ondrop) Handler.

Überschreiben Sie diese Funktion, um die Auswirkungen einer rechten Maustaste Drag & Drop zu implementieren. Drag & Drop von rechten Maustaste und zeigt in der Regel zur Auswahl, wenn die rechte Maustaste losgelassen wird.

Ihre Überschreibung der `OnDropEx` sollten Abfragen für die rechte Maustaste. Rufen Sie [GetKeyState](https://msdn.microsoft.com/library/windows/desktop/ms646301) oder speichern Sie den Zustand der rechten Maustaste aus Ihrem [OnDragEnter](#ondragenter) Handler.

- Wenn auf der rechten Maustaste angezeigt wird, sollte Ihre Überschreibung ein Popupmenü angezeigt die bietet, dass die Drop-Effekten durch die Drop-Quelle unterstützt werden.

   - Untersuchen Sie *Dropdownliste* um zu bestimmen, die Drop-Effekten, die von der Drop-Quelle unterstützt werden. Aktivieren Sie nur diese Aktionen im Popup-Menü.

   - Verwendung [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) , legen Sie die Standardaktion, die basierend auf *DropDefault*.

   - Abschließend führen Sie die Aktion, die durch die Auswahl des Benutzers im Popupmenü angegeben.

- Ist der rechten Maustaste nicht nach unten, sollte dies die Außerkraftsetzung als standard &-Drop-Anforderung verarbeiten. Verwenden Sie die Drop-Effekt, der im angegebenen *DropDefault*. Alternativ kann Ihre Überschreibung den dummy-Wert (1), um anzugeben, dass zurückgeben `OnDrop` dieser Drop-Vorgang behandelt wird.

Verwendung *pDataObject* Untersuchen der `COleDataObject` Zwischenablagedaten Format und Daten gelöscht am angegebenen Punkt.

& Drop-Effekte wird beschrieben, die ein Drop-Vorgang zugeordnete Aktion. Finden Sie in der folgenden Liste der Drop-Effekten:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für den Bildlauf durchgeführt wird oder im Ziel stattfindet.

Weitere Informationen zum Festlegen der Kontextmenübefehl von "Standard" finden Sie unter [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) im Windows SDK und [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) in diesem Handbuch.

##  <a name="onendprinting"></a>  CView::OnEndPrinting

Wird vom Framework aufgerufen, nachdem ein Dokument gedruckt oder in der Vorschau angezeigt wurde.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Druckergerätekontext.

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle GDI-Ressourcen freizugeben, Sie, in zugeordnet, der [OnBeginPrinting](#onbeginprinting) Member-Funktion.

##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview

Wird vom Framework aufgerufen, wenn der Benutzer den Seitenansichtmodus verlässt.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Druckergerätekontext.

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt.

*Zeigen Sie*<br/>
Legt den Punkt auf der Seite, die zuletzt im Vorschaumodus angezeigt wurde.

*pView*<br/>
Verweist auf das Objekt für die Vorschau verwendet.

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung dieser Funktion die [OnEndPrinting](#onendprinting) Memberfunktion und Wiederherstellungen begann das Hauptrahmenfenster in den Zustand vor der Seitenansicht war. Überschreiben Sie diese Funktion zum durchführen, besondere Bearbeitung, wenn Sie den Vorschaumodus beendet wird. Beispielsweise sollten Sie die Position des Benutzers im Dokument beibehalten, beim Wechseln von im Vorschaumodus zu normalen Anzeigemodus, Sie können scrollen, an die Position von beschrieben die *zeigen* Parameter und die `m_nCurPage` Mitglied der `CPrintInfo` Datenstruktur, die *"pInfo"* -Parameter zeigt.

Rufen Sie immer die Basisklassenversion von `OnEndPrintPreview` aus der Außerkraftsetzung, in der Regel am Ende der Funktion.

##  <a name="oninitialupdate"></a>  CView:: OnInitialUpdate

Vom Framework aufgerufen, nachdem die Ansicht zuerst auf das Dokument angefügt ist, aber vor die Ansicht angezeigt wird.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung dieser Funktion die [OnUpdate](#onupdate) Memberfunktion ohne Hinweis-Informationen (, also verwenden standardmäßig den Wert 0 für die *lHint* Parameter und NULL für die  *pHint* Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung auszuführen, die Informationen über das Dokument erforderlich sind. Beispielsweise verfügt die Anwendung Dokumente mit fester Größe, können dieser Funktion Sie eine Ansicht der Bildlauf Einschränkungen aufgrund der Größe des Dokuments zu initialisieren. Wenn Ihre Anwendung variabler Größe von Dokumenten unterstützt, verwenden Sie [OnUpdate](#onupdate) zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument ändert.

##  <a name="onpreparedc"></a>  CView::OnPrepareDC

Aufgerufen, bevor Sie die [OnDraw](#ondraw) Memberfunktion aufgerufen wird, für die Bildschirmanzeige und vor der [OnPrint](#onprint) Memberfunktion für jede Seite aufgerufen wird, während der Druck oder einer Seitenansicht.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Gerätekontext zum Rendern eines Bilds des Dokuments verwendet werden soll.

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt, wenn `OnPrepareDC` für Druck oder einer Seitenansicht; aufgerufen wird die `m_nCurPage` -Member gibt an, die Seite gedruckt werden sollen. Dieser Parameter ist NULL, wenn `OnPrepareDC` für die Bildschirmanzeige aufgerufen wird.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion führt keine Aktion aus, wenn die Funktion für die Bildschirmanzeige aufgerufen wird. Jedoch diese Funktion wird in abgeleiteten Klassen überschrieben, wie z. B. [CScrollView](../../mfc/reference/cscrollview-class.md), passen Sie die Attribute des Gerätekontexts; daher sollten Sie die basisklassenimplementierung immer aufrufen, am Anfang der Außerkraftsetzung.

Die Funktion für den Druck aufgerufen wird, untersucht die standardmäßige Implementierung der Seiteninformationen aus der *"pInfo"* Parameter. Wenn die Länge des Dokuments nicht angegeben wurde, `OnPrepareDC` geht davon aus dem Dokument, eine Seite lang werden, und die print-Schleife beendet, nachdem eine Seite gedruckt wurde. Die Funktion beendet die print-Schleife durch Festlegen der `m_bContinuePrinting` Member der Struktur auf "false".

Außer Kraft setzen `OnPrepareDC` für eine der folgenden Gründe:

- Attribute des Gerätekontexts anpassen nach Bedarf für die angegebene Seite. Wenn Sie den Zuordnungsmodus oder andere Eigenschaften des Gerätekontexts festlegen möchten, holen Sie dies z. B. in dieser Funktion.

- Drucken-Time-Paginierung ausführen zu können. Normalerweise geben Sie die Länge des Dokuments bei Beginn des Druckens mit der [OnPreparePrinting](#onprepareprinting) Member-Funktion. Wenn Sie nicht wissen, ist im voraus, wie lange das Dokument (z. B. wenn eine unbestimmte Anzahl von Datensätzen aus einer Datenbank zu drucken) jedoch außer Kraft setzen `OnPrepareDC` um für das Ende des Dokuments zu testen, während es gedruckt wird. Wenn des Dokuments gedruckt werden nicht mehr vorhanden ist, legen Sie die `m_bContinuePrinting` Mitglied der `CPrintInfo` Struktur auf "false".

- Escapesequenzen, die an den Drucker pro Seite von Seite zu senden. Zum Senden von Escapesequenzen aus `OnPrepareDC`, rufen Sie die `Escape` Memberfunktion die *pDC* Parameter.

Rufen Sie die Basisklassenversion von `OnPrepareDC` am Anfang der Außerkraftsetzung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

##  <a name="onprepareprinting"></a>  CView::OnPreparePrinting

Wird von Framework aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*"pInfo"*<br/>
Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, die ausgeführt werden; 0, wenn der Druckauftrag abgebrochen wurde.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt.

Sie müssen diese Funktion zum Drucken und Druckvorschau aktivieren überschreiben. Rufen Sie die [DoPreparePrinting](#doprepareprinting) Member-Funktion, und übergeben sie die *"pInfo"* Parameter, und wieder ihr Rückgabewert; `DoPreparePrinting` zeigt das Dialogfeld "Drucken" an und erstellt einen Drucker-Gerätekontext. Wenn Sie das Dialogfeld "Drucken" mit Werten als die Standardwerte initialisieren möchten, Werte zuweisen, die Mitglieder der *"pInfo"*. Beispielsweise, wenn Sie die Länge des Dokuments kennen, übergeben den Wert der [Anzahl](../../mfc/reference/cprintinfo-structure.md#setmaxpage) Memberfunktion *"pInfo"* vor dem Aufruf `DoPreparePrinting`. Dieser Wert wird angezeigt, in den: Feld im Bereich-Teil des Dialogfelds drucken.

`DoPreparePrinting` Das Dialogfeld "Drucken" für einen Auftrag für die Vorschau wird nicht angezeigt werden. Wenn Sie das Dialogfeld "Drucken" für einen Druckauftrag umgehen möchten, überprüfen Sie, ob die `m_bPreview` Mitglied *"pInfo"* ist "false", und klicken Sie dann auf "true" festlegen, bevor Sie die Übergabe an `DoPreparePrinting`; es anschließend auf "false" zurücksetzen.

Wenn Sie Initialisierungen durchführen, die Zugriff auf benötigen, müssen die `CDC` Objekt, das den Druckergerätekontext (z. B., wenn Sie die Größe einer Seite vor der Angabe der Länge des Dokuments wissen müssen), darstellt, außer Kraft setzen der `OnBeginPrinting` Member -Funktion.

Wenn Sie den Wert festlegen möchten die `m_nNumPreviewPages` oder `m_strPageDesc` Mitglied der *"pInfo"* -Parameter dazu nach dem Aufruf `DoPreparePrinting`. Die `DoPreparePrinting` Funktion Elementgruppen `m_nNumPreviewPages` auf den Wert finden Sie in der Anwendung. INI-Datei und legt `m_strPageDesc` auf den Standardwert zurück.

### <a name="example"></a>Beispiel

  Außer Kraft setzen `OnPreparePrinting` , und rufen Sie `DoPreparePrinting` aus der außer Kraft setzen, damit das Framework, ein Druckdialogfeld anzeigen und erstellen einen Drucker-Gerätekontext für Sie.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

Wenn Sie, wie viele Seiten das Dokument enthält wissen, legen Sie die maximalen `OnPreparePrinting` vor dem Aufruf `DoPreparePrinting`. Das Framework wird die maximale Seitenzahl in das Feld "an" im Dialogfeld "Drucken" angezeigt.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

##  <a name="onprint"></a>  CView::OnPrint

Wird aufgerufen, durch das Framework drucken oder Anzeigen einer Seite des Dokuments.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Druckergerätekontext.

*"pInfo"*<br/>
Verweist auf eine `CPrintInfo` Struktur, die den aktuellen Druckauftrag beschreibt.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion für jede Seite gedruckt wird, sofort nach dem Aufruf der [OnPrepareDC](#onpreparedc) Member-Funktion. Die zu druckende Seite wird angegeben, indem die `m_nCurPage` Mitglied der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Datenstruktur, *"pInfo"* verweist auf. Die Standardimplementierung Ruft die [OnDraw](#ondraw) Memberfunktion und übergibt sie den Druckergerätekontext.

Überschreiben Sie diese Funktion für eine der folgenden Gründe:

- Das Drucken von mehrseitige Dokumenten zulässig. Rendern Sie nur den Teil des Dokuments, das gegenwärtig gedruckte Seite entspricht. Bei Verwendung von `OnDraw` um, der Rendering ausführen, können Sie den Viewport-Ursprung anpassen, so dass nur der entsprechenden Teil des Dokuments gedruckt wird.

- Machen Sie das gedruckte Bild unterscheiden sich von der Bildschirmanzeige (d.h., wenn Ihre Anwendung nicht WYSIWYG ist). Anstelle der Übergabe des Druckers-Gerätekontext zu `OnDraw`, verwenden Sie den Gerätekontext zum Rendern eines Abbilds mithilfe von Attributen, die nicht auf dem Bildschirm angezeigt.

   Bei Bedarf von GDI-Ressourcen für den Druck, die Sie nicht für die Bildschirmanzeige verwenden, wählen Sie sie in den Gerätekontext vor dem Zeichnen, und heben sie deren Auswahl anschließend. Diese GDI-Ressourcen zugewiesen werden soll, im [OnBeginPrinting](#onbeginprinting) und veröffentlichte in [OnEndPrinting](#onendprinting).

- So implementieren Sie Kopf- oder Fußzeilen Sie können weiterhin verwenden `OnDraw` möchten Sie das Rendering durch Einschränken des Bereichs, der auf dem sie drucken kann.

Beachten Sie, dass die `m_rectDraw` Mitglied der *"pInfo"* Parameter beschreibt den Druckbereich der Seite in logischen Einheiten.

Rufen Sie keine `OnPrepareDC` in der Überschreibung der `OnPrint`; das Framework ruft `OnPrepareDC` automatisch vor dem Aufruf `OnPrint`.

### <a name="example"></a>Beispiel

Im folgenden finden Sie ein Grundgerüst für die eine überschriebene `OnPrint` Funktion:

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

Ein weiteres Beispiel finden Sie unter [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).

##  <a name="onscroll"></a>  CView::OnScroll

Es ist möglich, aufgerufen, um festzustellen, ob Scrollen.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parameter

*nScrollCode*<br/>
Ein Schiebeleisten-Code, der der Benutzer zeigt an, die Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertigen Byte ist, der bestimmt, den Typ der horizontalen Bildlauf auftritt, und ein höherwertige Byte ist, der bestimmt, den Typ des vertikalen Bildlauf auftritt:

- SB_BOTTOM führt einen Bildlauf nach unten.

- SB_LINEDOWN führt einen Bildlauf eine Zeile nach unten.

- SB_LINEUP führt einen Bildlauf eine Zeile nach oben.

- SB_PAGEDOWN führt einen Bildlauf eine Seite nach unten.

- SB_PAGEUP führt einen Bildlauf eine Seite nach oben.

- SB_THUMBTRACK zieht Bildlauffeld auf der angegebenen Position. Die aktuelle Position im angegeben *nPos*.

- SB_TOP führt einen Bildlauf nach oben.

*nPos*<br/>
Die aktuelle Position des Bildlauffelds enthält, ist der Bildlaufleisten-Code SB_THUMBTRACK; Andernfalls wird sie nicht verwendet. Je nach der anfänglichen scrollbereich *nPos* kann negativ sein und umgewandelt werden soll, um eine **Int** bei Bedarf.

*bDoScroll*<br/>
Bestimmt, ob tatsächlich die angegebene Aktion für die Bildlauf durchführen. Bei "true", sollten die dann ausgeführt werden; False gibt an, soll klicken Sie dann einen Bildlauf nicht ausgeführt werden.

### <a name="return-value"></a>Rückgabewert

Wenn *bDoScroll* ist "true", und die Ansicht wurde tatsächlich gerollt, dann zurückkehren ungleich NULL ist, andernfalls 0. Wenn *bDoScroll* ist "false", und klicken Sie dann auf die Rückgabe der Wert, der Sie Wenn zurückgegeben hätte *bDoScroll* wurden von "true", auch wenn Sie den Bildlauf tatsächlich nicht tun.

### <a name="remarks"></a>Hinweise

Diese Funktion wird in einem Fall durch das Framework mit aufgerufen *bDoScroll* auf "true" festgelegt werden, wenn die Sicht eine Bildlaufleiste-Nachricht empfängt. In diesem Fall sollten Sie tatsächlich die Ansicht einen Bildlauf durchführen. Diese Funktion heißt im anderen Fall mit *bDoScroll* auf "false" festgelegt werden, wenn ein OLE-Element zunächst in den automatischen Bildlauf Bereich eines Dropziels gezogen wird, vor dem Durchführen eines Bildlaufs tatsächlich abgebrochen stattfindet. In diesem Fall sollten Sie die Sicht nicht tatsächlich scrollen.

##  <a name="onscrollby"></a>  CView::OnScrollBy

Vom Framework aufgerufen, wenn der Benutzer einen Bereich außerhalb der vorhanden Ansicht des Dokuments an, indem ein OLE-Element für die Ansicht des aktuellen Rahmen ziehen oder bearbeiten die vertikalen oder horizontalen Bildlaufleisten anzeigt.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parameter

*sizeScroll*<br/>
Anzahl der Pixel, ein Bildlauf durchgeführt werden, horizontal und vertikal.

*bDoScroll*<br/>
Bestimmt, ob der Ansicht einen Bildlauf auftritt. Bei "true", findet dann; False gibt an, erfolgt dann nicht.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Ansicht gescrollt werden konnte; andernfalls 0.

### <a name="remarks"></a>Hinweise

In abgeleiteten Klassen überprüft diese Methode, ob die Ansicht in der Richtung gescrollt werden kann, der Benutzer angefordert, und aktualisiert dann die neue Region aus, falls erforderlich. Diese Funktion wird automatisch aufgerufen, indem [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) zum Ausführen der eigentlichen Bildlauf-Anforderung.

Die Standardimplementierung dieser Methode ändert sich nicht auf die Sicht, aber wenn sie nicht aufgerufen wird, die Ansicht wird kein Bildlauf in einem `CScrollView`-abgeleitete Klasse.

Wenn die Dokumentbreite oder Höhe 32767 Pixel überschreitet, scrollen nach 32767 schlägt fehl, da `OnScrollBy` wird aufgerufen, mit einem ungültigen *SizeScroll* Argument.

##  <a name="onupdate"></a>  CView::OnUpdate

Vom Framework aufgerufen, nachdem das Dokument von der Ansicht geändert wurde; Diese Funktion wird aufgerufen, indem [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) und die Ansicht seine Anzeige entsprechend diesen Änderungen aktualisiert.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>Parameter

*pSender*<br/>
Verweist auf die Ansicht, die das Dokument, geändert oder NULL, wenn alle Ansichten werden aktualisiert werden.

*lHint*<br/>
Enthält Informationen zu den Änderungen an.

*pHint*<br/>
Verweist auf ein Objekt, das Informationen zu den Änderungen zu speichern.

### <a name="remarks"></a>Hinweise

Es heißt auch von der Standardimplementierung des [OnInitialUpdate](#oninitialupdate). Die Standardimplementierung erklärt den gesamten Clientbereich, der zum Zeichnen zu markieren, wenn die nächste WM_PAINT-Nachricht empfangen wird. Überschreiben Sie diese Funktion, wenn Sie nur solche Bereiche zu aktualisieren, die die geänderten Teile des Dokuments zuordnen möchten. Zu diesem Zweck müssen Sie Informationen zu den Änderungen, die über die Hinweis-Parameter übergeben.

Verwendung von *lHint*spezieller Hinweis-Werte, in der Regel eine Bitmaske oder ein enumerierter Typ definiert und das Dokument, übergeben Sie einen der folgenden Werte haben. Mit *pHint*, leiten eine Klasse Hinweis von [CObject](../../mfc/reference/cobject-class.md) und das Dokument, das einen Zeiger auf ein Objekt Hinweis zu übergeben, wenn überschreiben `OnUpdate`, verwenden Sie die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) die Memberfunktion bestimmt den Laufzeittyp des Objekts Hinweis.

In der Regel sollten Sie nicht Ausführen einer Zeichnung direkt aus `OnUpdate`. Bestimmen Sie das Rechteck, die beschreiben, in Gerätekoordinaten, Bereich, die erforderlich sind, aktualisieren, stattdessen. übergeben Sie dieses Rechteck [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect). Dies bewirkt, dass Zeichnen auf der nächsten Ausführung ein [WM_PAINT](/windows/desktop/gdi/wm-paint) Nachricht empfangen wird.

Wenn *lHint* ist 0 und *pHint* NULL ist, das Dokument verfügt über eine generische Benachrichtigung gesendet. Wenn eine Sicht eine generische Benachrichtigung empfängt, oder die Hinweise nicht decodiert werden können, sollten sie seine gesamte Clientbereich für ungültig erklärt.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument-Klasse](../../mfc/reference/cdocument-class.md)
