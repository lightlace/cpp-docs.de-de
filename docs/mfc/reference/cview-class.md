---
title: CView-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d97c12b54e644298edb21706b4659ba84e43256e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CView::DoPreparePrinting](#doprepareprinting)|Zeigt das Dialogfeld Drucken und Drucker-Gerätekontext erstellt; Rufen Sie zum Überschreiben der `OnPreparePrinting` Memberfunktion.|  
|[CView::GetDocument](#getdocument)|Gibt das Dokument mit der Ansicht verknüpfte zurück.|  
|[CView::IsSelected](#isselected)|Testet, ob ein Dokumentelement ausgewählt ist. Für OLE-Unterstützung erforderlich sind.|  
|[CView::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn ein Element in einer Sicht der Drag-and-Drop-Region zuerst gezogen wird.|  
|[CView::OnDragLeave](#ondragleave)|Wird aufgerufen, wenn ein gezogenes Element Drag-and-Drop-Bereich, einer Sicht verlässt.|  
|[CView::OnDragOver](#ondragover)|Wird aufgerufen, wenn über den Drag & Drop-Bereich einer Ansicht ein Element gezogen wird.|  
|[CView::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in das Scroll-Bereich des Fensters gezogen wird.|  
|[CView::OnDrop](#ondrop)|Wird aufgerufen, wenn ein Element in den Drag & Drop-Bereich einer Ansicht, Standardhandler gelöscht wurde.|  
|[CView::OnDropEx](#ondropex)|Wird aufgerufen, wenn ein Element in den Drag & Drop-Bereich einer Sicht, primäre Ereignishandler gelöscht wurde.|  
|[CView:: OnInitialUpdate](#oninitialupdate)|Wird aufgerufen, nachdem eine Sicht zunächst zu einem Dokument zugeordnet ist.|  
|[CView::OnPrepareDC](#onpreparedc)|Wird aufgerufen, bevor die `OnDraw` Memberfunktion aufgerufen wird, für die Bildschirmanzeige oder der `OnPrint` Memberfunktion für drucken oder seitenansichtauftrags aufgerufen wird.|  
|[CView::OnScroll](#onscroll)|Wird aufgerufen, wenn OLE-Elementen jenseits der Grenzen der Ansicht gezogen werden.|  
|[CView::OnScrollBy](#onscrollby)|Wird aufgerufen, wenn eine aktive direkten OLE-Elementen mit an ein Bildlauf durchgeführt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|Wird aufgerufen, wenn das Rahmenfenster, die die Sicht enthält, aktiviert oder deaktiviert wird.|  
|[CView::OnActivateView](#onactivateview)|Wird aufgerufen, wenn eine Sicht aktiviert ist.|  
|[CView::OnBeginPrinting](#onbeginprinting)|Wird aufgerufen, wenn ein Auftrag beginnt; Überschreiben Sie, um die Graphics Device Interface (GDI) Ressourcen zuteilen.|  
|[CView:: OnDraw](#ondraw)|Wird aufgerufen, um ein Dokument für die Bildschirmanzeige, Drucken und Druckvorschau-Bild rendert. Die Implementierung erforderlich sind.|  
|[CView::OnEndPrinting](#onendprinting)|Wird aufgerufen, wenn ein Druckauftrags beendet; überschreiben, um die GDI-Ressourcen freizugeben.|  
|[CView::OnEndPrintPreview](#onendprintpreview)|Wird aufgerufen, wenn im Vorschaumodus beendet wird.|  
|[CView::OnPreparePrinting](#onprepareprinting)|Wird aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird; außer Kraft setzen Sie, um das Dialogfeld Drucken zu initialisieren.|  
|[CView::OnPrint](#onprint)|Zum Drucken oder Anzeigen einer Vorschau einer Seite des Dokuments aufgerufen.|  
|[CView::OnUpdate](#onupdate)|Wird aufgerufen, um eine Ansicht zu informieren, die das Dokument wurde geändert.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Sicht ist an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und der Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm oder Drucker, und Benutzereingaben als Vorgänge auf das Dokument interpretiert.  
  
 Eine Sicht ist ein untergeordnetes Element von einem Rahmenfenster. Mehr als eine Ansicht kann einem Rahmenfenster, wie im Fall eines unterteilten Fensters freigeben. Wird die Beziehung zwischen einer Ansichtsklasse, einem Rahmenfenster (Klasse) und einer Dokumentklasse von einem `CDocTemplate` Objekt. Wenn der Benutzer öffnet ein neues Fenster oder eine vorhandene teilt eine das Framework erstellt eine neue Ansicht, und fügt ihn in das Dokument.  
  
 Eine Sicht kann nur ein Dokument angefügt werden, aber ein Dokument kann mehrere Sichten gleichzeitig angefügt haben – z. B., wenn das Dokument in einem Splitterfenster oder mehrere untergeordnete Fenster in einer Anwendung der multiple Document Interface (MDI) angezeigt wird. Ihre Anwendung kann verschiedene Arten von Ansichten für einen bestimmten Dokumenttyp unterstützen; Beispielsweise kann ein Textverarbeitungsprogramm bereitstellen, eine Ansicht der vollständige Text eines Dokuments und einer Gliederungsansicht, die nur die Überschriften anzeigt. Diese verschiedenen Typen von Sichten können in separaten Rahmenfenster oder in separate Bereiche für ein einzelnes Rahmenfenster platziert werden, wenn Sie ein unterteiltes Fenster verwenden.  
  
 Eine Sicht kann für die Handhabung von mehreren verschiedenen Arten von Eingaben, z. B. Tastatureingaben, Mauseingaben oder Eingaben über die Drag & Drop sowie Befehle über Menüs, Symbolleisten und Bildlaufleisten verantwortlich sein. Eine Ansicht erhält die Befehle, die vom zugehörigen Rahmenfenster weitergeleitet. Wenn die Sicht einen bestimmten Befehl nicht verarbeiten kann, werden den Befehl aus, um die zugeordnete Dokument weitergeleitet. Wie alle Befehlsziele verarbeitet eine Ansicht Nachrichten über eine meldungszuordnung.  
  
 Die Ansicht ist verantwortlich für das Anzeigen und Ändern von Daten für das Dokument jedoch nicht für sie gespeichert. Das Dokument enthält die Ansicht mit den erforderlichen Details über ihre Daten. Sie können den Zugriff auf lassen, den direkt die Datenmember des Dokuments ein, oder Sie Memberfunktionen in der Dokumentklasse für die Ansichtsklasse aufrufen bereitstellen können.  
  
 Wenn Daten eines Dokuments geändert wird, ruft die Sicht, die verantwortlich für die Änderungen in der Regel die [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) -Funktion für das Dokument, das durch Aufrufen von den anderen Ansichten benachrichtigt die `OnUpdate` Memberfunktion für Jede. Die standardmäßige Implementierung des `OnUpdate` wird die Ansicht des gesamten Clientbereich ungültig. Sie können überschreiben, um nur diejenigen Regionen der Clientbereich für ungültig zu erklären, die die geänderten Teile des Dokuments zugeordnet werden soll.  
  
 Mit `CView`, eine Klasse ableiten und Implementieren der `OnDraw` Memberfunktion Bildschirmanzeige ausführen. Sie können auch `OnDraw` zum Drucken und Druckvorschau ausführen. Das Framework verarbeitet die Druckschleife zum Drucken und die Vorschau des Dokuments.  
  
 Eine Sicht behandelt Bildlaufleisten-Nachrichten mit der [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Können Sie Bildlaufleisten-Meldungsbehandlung in diesen Funktionen implementieren, oder Sie können die `CView` abgeleitete Klasse [CScrollView](../../mfc/reference/cscrollview-class.md) , scrollen Sie zu behandeln.  
  
 Neben `CScrollView`, die Microsoft Foundation Class-Bibliothek stellt neun von abgeleiteten Klassen `CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md), eine Sicht, die die Verwendung von Dokument - View-Architektur mit Struktur, Liste und Rich-edit-Steuerelemente.  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), eine Sicht, die Datenbankdatensätze in Steuerelementen im Dialogfeld anzeigt.  
  
- [CEditView](../../mfc/reference/ceditview-class.md), eine Sicht, die einen einfache mehrzeiligen Text-Editor bietet. Sie können eine `CEditView` Objekt als ein Steuerelement in einem Dialogfeld sowie eine Ansicht eines Dokuments.  
  
- [CFormView](../../mfc/reference/cformview-class.md), eine bildlauffähige Ansicht, die im Dialogfeld-Steuerelemente enthält, und basiert auf einer Dialogfeldvorlagen-Ressource.  
  
- [CListView](../../mfc/reference/clistview-class.md), eine Sicht, die Verwendung der Dokument - View-Architektur mit List-Steuerelemente kann.  
  
- [CRecordView](../../mfc/reference/crecordview-class.md), eine Sicht, die Datenbankdatensätze in Steuerelementen im Dialogfeld anzeigt.  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md), eine Sicht, die die Verwendung von Dokument - View-Architektur mit Rich-edit-Steuerelemente.  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md), eine Sicht, die automatisch durchführen eines Bildlaufs unterstützt.  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md), eine Sicht, die Verwendung der Dokument - View-Architektur mit Struktursteuerelemente ermöglicht.  
  
 Die `CView` -Klasse verfügt auch über eine der abgeleiteten Implementierungsklasse mit dem Namen **CPreviewView**, die vom Framework Seitenansicht ausführen verwendet wird. Diese Klasse bietet Unterstützung für die Funktionen im Seitenansichtsfenster z. B. eine Symbolleiste, oder Double-Einzelseiten-Vorschau, und vergrößern/verkleinern, ist, die das angezeigte Bild vergrößern. Sie müssen aufrufen oder Überschreiben eines **CPreviewView**Memberfunktionen, es sei denn, Sie möchten eine eigene Benutzeroberfläche für die Seitenansicht implementieren (beispielsweise, wenn Sie im Seitenansichtsmodus Bearbeitung unterstützen möchten). Weitere Informationen zur Verwendung von `CView`, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [Drucken](../../mfc/printing.md). Darüber hinaus finden Sie unter [technischen Hinweis 30](../../mfc/tn030-customizing-printing-and-print-preview.md) detaillierte Informationen zum Anpassen der Seitenansicht zu blättern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cview"></a>CView::CView  
 Erstellt ein `CView`-Objekt.  
  
```  
CView();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft den Konstruktor auf, wenn ein neues Rahmenfenster erstellt wird, oder Teilen Sie ein Fenster ist. Überschreiben Sie die [OnInitialUpdate](#oninitialupdate) Memberfunktion, um die Ansicht zu initialisieren, nachdem das Dokument verbunden ist.  
  
##  <a name="doprepareprinting"></a>CView::DoPreparePrinting  
 Mit dieser Funktion wird von der Außerkraftsetzung von [OnPreparePrinting](#onprepareprinting) zum Aufrufen des Dialogfelds drucken und erstellen einen Drucker-Gerätekontext.  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn drucken oder seitenansichtauftrags beginnen kann; 0, wenn der Vorgang wurde abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhalten dieser Funktion hängt von, ob es für drucken oder seitenansichtauftrags aufgerufen wird (gemäß der **M_bPreview** Mitglied der `pInfo` Parameter). Wenn eine Datei gedruckt wird, ruft diese Funktion des Dialogfelds drucken, verwenden die Werte in der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Datenstruktur, `pInfo` zeigt auf, nachdem der Benutzer das Dialogfeld geschlossen wurde, erstellt die Funktion einen Drucker-Gerätekontext anhand der Einstellungen im Dialogfeld angegebenen Benutzer und gibt dieser Gerätekontext über die `pInfo` Parameter. Dieser Gerätekontext wird verwendet, um das Dokument zu drucken.  
  
 Wenn eine Datei in der Vorschau wird, erstellt diese Funktion einen druckergerätkontext mit der aktuellen Druckereinstellungen zu verwenden; Dieser Gerätekontext dient zum Simulieren des Druckers während der Vorschau.  
  
##  <a name="getdocument"></a>CView::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf die Ansicht Dokument erhalten.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CDocument](../../mfc/reference/cdocument-class.md) der Sicht zugeordneten Objekt. **NULL** , wenn die Ansicht nicht an ein Dokument angefügt ist.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch können Sie das Dokument Memberfunktionen aufrufen.  
  
##  <a name="isselected"></a>CView::IsSelected  
 Vom Framework aufgerufen wird, überprüfen Sie, ob das angegebene Dokumentelement ausgewählt ist.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDocItem`  
 Verweist auf das Dokumentelement getestet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Dokumentelement ausgewählt ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung dieser Funktion **"false"**. Überschreiben Sie diese Funktion, wenn Sie mit der Auswahl implementieren [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte. Sie müssen diese Funktion überschreiben, wenn Ihre Sicht OLE-Elemente enthält.  
  
##  <a name="onactivateframe"></a>CView::OnActivateFrame  
 Wird vom Framework aufgerufen, wenn das Rahmenfenster, die die Sicht enthält, aktiviert oder deaktiviert ist.  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `nState`  
 Gibt an, ob das Rahmenfenster ist aktiviert oder deaktiviert. Die folgenden Werte sind möglich:  
  
- **WA_INACTIVE** das Rahmenfenster wird deaktiviert.  
  
- **WA_ACTIVE** das Rahmenfenster abgesehen einen Mausklick (z. B. durch Verwenden der Tastaturschnittstelle an, wählen Sie im Fenster) über eine Methode aktiviert wird.  
  
- **WA_CLICKACTIVE** das Rahmenfenster per Mausklick aktiviert wird  
  
 `pFrameWnd`  
 Ein Zeiger auf das Rahmenfenster, die aktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion auf, wenn Sie besondere Verarbeitung, wenn das Rahmenfenster der Sicht zugeordneten aktiviert oder deaktiviert wird ausführen möchten. Beispielsweise [CFormView](../../mfc/reference/cformview-class.md) Außerkraftsetzung ausführt, wenn es speichert und wiederherstellt das Steuerelement, das Fokus besitzt.  
  
##  <a name="onactivateview"></a>CView::OnActivateView  
 Vom Framework aufgerufen, wenn eine Sicht aktiviert oder deaktiviert ist.  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  
  
 `pActivateView`  
 Verweist auf das Ansichtsobjekt, das aktiviert wird.  
  
 `pDeactiveView`  
 Verweist auf das Ansichtsobjekt, das deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion legt den Fokus auf die Ansicht aktiviert wird. Überschreiben Sie diese Funktion, wenn Ausführen spezieller Verarbeitung, wenn eine Sicht aktiviert oder deaktiviert ist. Z. B. Wenn Sie besondere visuelle Hinweise bereitstellen, die die aktive Ansicht von inaktiven Ansichten unterscheiden möchten, Sie würden Untersuchen der `bActivate` Parameter und die Ansicht Darstellung entsprechend aktualisieren.  
  
 Die `pActivateView` und `pDeactiveView` Parameter zeigen Sie auf die gleiche Ansicht, wenn Hauptrahmenfenster für die Anwendung, ändern sich die aktive Ansicht aktiviert ist – z. B. wenn der Fokus aus einer anderen Anwendung mit diesem, anstatt von einem übertragen werden Zeigen Sie in eine andere in der Anwendung oder beim Wechseln zwischen untergeordneten MDI-Fenster an. Dies ermöglicht eine Ansicht für ihre Palette erneut zu nutzen, bei Bedarf.  
  
 Diese Parameter unterscheiden sich beim [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) aufgerufen wird und eine Sicht, die sich von Was ist [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) zurück. Dies geschieht am häufigsten mit Splitterfenster.  
  
##  <a name="onbeginprinting"></a>CView::OnBeginPrinting  
 Wird zu Beginn eines Druckauftrags oder Seitenansichtauftrags vom Framework aufgerufen, nachdem `OnPreparePrinting` aufgerufen wurde.  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle speziell für den Druck benötigten GDI-Ressourcen, z. B. Stifte oder Schriftarten, zuzuordnen. Wählen Sie die GDI-Objekte im Gerätekontext aus der [OnPrint](#onprint) Memberfunktion für jede Seite, die sie verwendet. Wenn Sie das gleiche Ansichtsobjekt verwenden, um den Bildschirm anzuzeigen und zu drucken, verwenden Sie separate Variablen für die für jeden Bildschirm erforderlichen GDI-Ressourcen. Dadurch können Sie den Bildschirm während des Druckens aktualisieren.  
  
 Mit dieser Funktion können Sie auch Initialisierungen durchführen, die von Eigenschaften des Druckergerätekontextes abhängig sind. Beispielsweise kann die Anzahl der Seiten, die zum Drucken des Dokuments benötigt werden, von den Einstellungen abhängig sein, die der Benutzer im Dialogfeld „Drucken“ (z. B. Seitenlänge) angibt. In einem solchen Fall können Sie die Länge des Dokuments in angeben können nicht der [OnPreparePrinting](#onprepareprinting) Memberfunktion ist, wobei Sie würde dies normalerweise tun; Sie müssen warten, bis der Druckergerätekontext basierend auf den Einstellungen des Dialogfelds erstellt wurde. [OnBeginPrinting](#onbeginprinting) ist die erste überschreibbare Funktion, die Ihnen sofortigen Zugriff auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das den Druckergerätekontext darstellt, damit Sie die Länge des Dokuments mithilfe dieser Funktion festlegen können. Wenn die Länge des Dokuments nicht zu diesem Zeitpunkt angegeben wird, wird in der Seitenansicht keine Bildlaufleiste angezeigt.  
  
##  <a name="ondragenter"></a>CView::OnDragEnter  
 Vom Framework aufgerufen, wenn der Mauszeiger die Region nicht durchführen eines Bildlaufs im Zielfenster zuerst eintritt.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) in der Ansicht der Drop-Filterbereich gezogen wird.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` aufgezählt-Typ, der den Typ der Drop, die auftreten würden angibt, wenn der Benutzer das Objekt an dieser Position gelöscht. Der Typ des Drop in der Regel hängt von den aktuellen Status erkennbar `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Datenobjekt kann nicht in diesem Fenster nicht gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL &#124; MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und das ursprüngliche Objekt zu löschen. Dies ist die Standard-Drop-Effekt in der Regel auf, wenn die Sicht dieses Datenobjekt annehmen kann.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßige Implementierung werden keine Aktionen ausgeführt und zurückgegeben wird `DROPEFFECT_NONE`.  
  
 Überschreiben Sie diese Funktion zur Vorbereitung der späteren Aufrufen der [OnDragOver](#ondragover) Memberfunktion. Alle Daten, die erforderlich sind, aus dem Datenobjekt abgerufen werden sollen, zu diesem Zeitpunkt zur späteren Verwendung in der `OnDragOver` Memberfunktion. Die Ansicht sollte auch zu diesem Zeitpunkt visuelles Feedback erteilen aktualisiert werden. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondragleave"></a>CView::OnDragLeave  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn die Maus für dieses Fensters aus den gültigen Ablegebereich verschoben wird.  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn die aktuelle Ansicht so bereinigen Sie alle ausgeführten Aktionen während des muss [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) aufrufen, z. B. visueller Benutzerfeedback entfernen, während das Objekt gezogen und abgelegt und wurde .  
  
##  <a name="ondragover"></a>CView::OnDragOver  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über die Drop-Zielfenster bewegt wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) über das Ablageziel gezogen werden.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` aufgezählt-Typ, der den Typ der Drop, die auftreten würden angibt, wenn der Benutzer das Objekt an dieser Position gelöscht. Der Typ des Drop hängt oft von den aktuellen Status des Schlüssels durch `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Datenobjekt kann nicht in diesem Fenster nicht gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL &#124; MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und das ursprüngliche Objekt zu löschen. Dies ist der Standard-Drop-Effekt in der Regel auf, wenn die Ansicht das Datenobjekt annehmen kann.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt nichts zurück, und wählen Sie `DROPEFFECT_NONE`.  
  
 Überschreiben Sie diese Funktion, um während des Ziehvorgangs visuelles Feedback zu geben. Da diese Funktion kontinuierlich aufgerufen wird, sollten alle darin enthaltenen Code so weit wie möglich optimiert werden. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondragscroll"></a>CView::OnDragScroll  
 Wird aufgerufen, durch das Framework vor dem Aufruf [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) zu bestimmen, ob der Punkt im Bildlaufbereich ist.  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die Position des Cursors in Pixel relativ zu dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT` aufgezählt-Typ, der den Typ der Drop, die auftreten würden angibt, wenn der Benutzer das Objekt an dieser Position gelöscht. Der Typ des Drop in der Regel hängt von den aktuellen Status erkennbar `dwKeyState`. Eine standardmäßige Zuordnung von Keystates zu `DROPEFFECT` Werte sind:  
  
- `DROPEFFECT_NONE`Das Datenobjekt kann nicht in diesem Fenster nicht gelöscht werden.  
  
- `DROPEFFECT_LINK`für **MK_CONTROL &#124; MK_SHIFT** erstellt eine Verknüpfung zwischen dem Objekt und dem Server.  
  
- `DROPEFFECT_COPY`für **MK_CONTROL** erstellt eine Kopie des gelöschten Objekts.  
  
- `DROPEFFECT_MOVE`für **MK_ALT** erstellt eine Kopie des gelöschten Objekts und das ursprüngliche Objekt zu löschen.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird oder in der Ansicht der Ziel auftritt.  
  
 Weitere Informationen finden Sie im MFC Advanced Concepts-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie spezielle Verhaltensweisen für dieses Ereignis bereitstellen möchten. Die standardmäßige Implementierung scrollt Windows automatisch, wenn der Cursor in der Standardeinstellung Bildlaufbereich in den Rahmen jedes Fenster gezogen wird. Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren eines Drop-Ziels](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondraw"></a>CView:: OnDraw  
 Vom Framework aufgerufen wird, ein Bild des Dokuments gerendert.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern eines Bilds des Dokuments verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um die Bildschirmanzeige, Drucken und Druckvorschau ausführen, und übergibt einen anderes Gerätekontext in jedem Fall. Es ist keine Standardimplementierung vorhanden.  
  
 Sie müssen diese Funktion, um die Ansicht des Dokuments anzuzeigen, überschreiben. Grafik Device Interface (GDI) Aufrufe mithilfe der [CDC](../../mfc/reference/cdc-class.md) Objekt verweist die `pDC` Parameter. Auswählen von GDI-Ressourcen, z. B. Stifte oder Schriftarten, den Gerätekontext vor dem Zeichnen und deaktivieren diese anschließend. Der Code zum Zeichnen sein häufig geräteunabhängige; d. h. erfordert es Informationen zur Art des Geräts das Bild angezeigt wird.  
  
 Rufen Sie zum Zeichnen zu optimieren, die [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) Memberfunktion des Gerätekontexts, um herauszufinden, ob ein angegebenes Rechteck gezeichnet wird. Wenn Sie zwischen normalen Bildschirm anzeigen und Drucken unterscheiden müssen, rufen Sie die [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) Memberfunktion des Gerätekontexts.  
  
##  <a name="ondrop"></a>CView::OnDrop  
 Vom Framework aufgerufen, wenn der Benutzer über ein gültiges Ablageziel ein Datenobjekt loslässt.  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in das Ablageziel abgelegt wird.  
  
 `dropEffect`  
 Die Drop-Effekt, den der Benutzer angefordert hat.  
  
- `DROPEFFECT_COPY`Erstellt eine Kopie des Datenobjekts gelöscht wird.  
  
- `DROPEFFECT_MOVE`Verschiebt das Datenobjekt auf der aktuellen Position des Mauszeigers.  
  
- `DROPEFFECT_LINK`Erstellt einen Link zwischen einem Datenobjekt und den Server.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie der Löschvorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt **"false"**.  
  
 Überschreiben Sie diese Funktion, um die Auswirkung der OLE-Drop in den Clientbereich der Ansicht zu implementieren. Das Datenobjekt untersucht werden kann, über `pDataObject` Zwischenablagedaten Formate und Daten gelöscht am angegebenen Punkt.  
  
> [!NOTE]
>  Das Framework mit dieser Funktion wird nicht, wenn es eine Überschreibung ist [OnDropEx](#ondropex) in dieser Ansichtsklasse.  
  
##  <a name="ondropex"></a>CView::OnDropEx  
 Vom Framework aufgerufen, wenn der Benutzer über ein gültiges Ablageziel ein Datenobjekt loslässt.  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) , die in das Ablageziel abgelegt wird.  
  
 `dropDefault`  
 Die Auswirkungen, die für die Standard-Drop-Vorgang basierend auf den aktuellen Status der Benutzer ausgewählt haben. Es kann sein `DROPEFFECT_NONE`. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
 `dropList`  
 Eine Liste der Drop-Effekte, die die Drop-Quelle unterstützt. Drop-Effekt-Werte können mit dem bitweisen OR kombiniert werden ( **&#124;**) Vorgang. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
 `point`  
 Der aktuellen Position relativ zum Clientbereich anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Drop-Effekt, die aus der Drop-Versuch, an der vom angegebenen Position resultieren `point`. Diese Angabe muss einen der Werte erkennbar *DropEffectList*. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt nichts, und Zurückgeben von Dummywert (-1), um anzugeben, dass das Framework aufgerufen, sollte die [OnDrop](#ondrop) Handler.  
  
 Überschreiben Sie diese Funktion, um die Auswirkung einer Rechte Maustaste Drag- and -Drop zu implementieren. Rechte Maustaste Drag & Drop und zeigt in der Regel zur Auswahl, wenn die rechte Maustaste losgelassen wird.  
  
 Überschreiben der `OnDropEx` sollten Abfragen, für die rechte Maustaste. Sie erreichen [GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301) oder zum Speichern von des rechten Maustaste Zustands wird von Ihrem [OnDragEnter](#ondragenter) Handler.  
  
-   Wenn die rechte Maustaste ausgefallen ist, sollte die Außerkraftsetzung ein Popupmenü anzeigen, die Drop-Effekte durch die Quelle des Drop-Unterstützung bietet.  
  
    -   Untersuchen Sie `dropList` um zu bestimmen, die Drop-Effekte, die durch die Drop-Quelle unterstützt. Aktivieren Sie nur diese Aktionen über das Popupmenü.  
  
    -   Verwendung [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) festzulegende die Standardaktion, die basierend auf `dropDefault`.  
  
    -   Schalten Sie schließlich die Aktion, die durch die Auswahl des Benutzers im Popupmenü angegeben.  
  
-   Wenn die rechte Maustaste nicht ausgefallen ist, sollte die Außerkraftsetzung dies als standard-Drop-Anforderung verarbeiten. Verwenden Sie die Drop-Effekt, der im angegebenen `dropDefault`. Alternativ kann die Außerkraftsetzung den dummy Wert (-1), um anzugeben, dass zurückgeben `OnDrop` behandelt diese Drop-Vorgangs.  
  
 Verwendung `pDataObject` Untersuchen der `COleDataObject` Zwischenablagedaten Format und Daten gelöscht am angegebenen Punkt.  
  
 Drop-Effekte beschreiben die Aktion ein Drop-Vorgang zugeordnet ist. Die folgende Liste von Drop-Effekte finden Sie in:  
  
- `DROPEFFECT_NONE`Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird, oder im Ziel auftritt.  
  
 Weitere Informationen zum Festlegen des Standard-Menübefehls finden Sie unter [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) im Windows SDK und [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) in diesem Handbuch.  
  
##  <a name="onendprinting"></a>CView::OnEndPrinting  
 Vom Framework aufgerufen, nachdem ein Dokument gedruckt oder in der Vorschau angezeigt wurde.  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um alle GDI-Ressourcen freizugeben, Sie, in zugeordnet, der [OnBeginPrinting](#onbeginprinting) Memberfunktion.  
  
##  <a name="onendprintpreview"></a>CView::OnEndPrintPreview  
 Vom Framework aufgerufen, wenn der Benutzer die Seitenansicht beendet wird.  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
 `point`  
 Gibt den Punkt auf der Seite, die im Vorschaumodus zuletzt angezeigt wurden.  
  
 `pView`  
 Verweist auf das Ansichtsobjekt, für die Vorschau verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [OnEndPrinting](#onendprinting) Memberfunktion und eine Wiederherstellung begann das Hauptrahmenfenster in den Zustand vor der Seitenansicht war. Überschreiben Sie diese Funktion zum Ausführen der besonderen Verarbeitung, wenn im Vorschaumodus beendet wird. Z. B., wenn Sie die Position des Benutzers im Dokument beibehalten, beim Wechseln vom Vorschaumodus auf normalen Anzeigemodus möchten, Sie können einen Bildlauf zu der Position von beschrieben die `point` Parameter und die `m_nCurPage` Mitglied der `CPrintInfo` Struktur die die `pInfo` -Parameter zeigt.  
  
 Rufen Sie immer die Basisklassenversion von `OnEndPrintPreview` aus Ihrer Override "," in der Regel am Ende der Funktion.  
  
##  <a name="oninitialupdate"></a>CView:: OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [OnUpdate](#onupdate) Memberfunktion ohne Hinweis Informationen (d. h. unter Verwendung der Standardwerte von 0 für die `lHint` Parameter und **NULL** für die `pHint` Parameter). Überschreiben Sie diese Funktion, um die einmalige Initialisierung auszuführen, die Informationen über das Dokument erfordert. Beispielsweise verfügt die Anwendung Dokumente fester Größe, können dieser Funktion Sie zum Durchführen eines Bildlaufs Grenzwerte für eine Sicht basierend auf die Größe des Dokuments zu initialisieren. Wenn Ihre Anwendung variabler Größe von Dokumenten unterstützt, verwenden [OnUpdate](#onupdate) zum Aktualisieren der Bildlauf schränkt jedes Mal das Dokument geändert wird.  
  
##  <a name="onpreparedc"></a>CView::OnPrepareDC  
 Aufgerufen, bevor die [OnDraw](#ondraw) Memberfunktion aufgerufen wird, für die Bildschirmanzeige und vor der [OnPrint](#onprint) Memberfunktion für jede Seite beim Drucken oder seitenansichtauftrags aufgerufen wird.  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern eines Bilds des Dokuments verwendet werden soll.  
  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Struktur, die den aktuellen Druckauftrag beschreibt, wenn `OnPrepareDC` für die Vorschau Drucks oder zur aufgerufen wird die `m_nCurPage` Element gibt die Seite gedruckt werden soll. Dieser Parameter ist **NULL** Wenn `OnPrepareDC` für die Bildschirmanzeige aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion wird keine Aktion ausgeführt, wenn die Funktion für die Bildschirmanzeige aufgerufen wird. Aber diese Funktion ist in abgeleiteten Klassen überschrieben, wie z. B. [CScrollView](../../mfc/reference/cscrollview-class.md), Anpassen der Attribute des Gerätekontexts; deshalb sollten Sie immer Implementierung der Basisklasse aufrufen, am Anfang der Außerkraftsetzung.  
  
 Die Funktion für den Druck aufgerufen wird, untersucht die standardmäßige Implementierung der Seiteninformationen gespeichert, der `pInfo` Parameter. Wenn die Länge des Dokuments nicht angegeben wurde, `OnPrepareDC` geht davon aus dem Dokument, eine Seite lang werden, und das Drucken-Schleife beendet, nachdem eine Seite gedruckt wurde. Die Funktion beendet das Drucken-Schleife durch Festlegen der `m_bContinuePrinting` Member der Struktur auf **"false"**.  
  
 Überschreiben Sie `OnPrepareDC` für eine beliebige der folgenden Gründe:  
  
-   Anpassen der Attribute des Gerätekontexts für die angegebene Seite nach Bedarf. Z. B. Wenn Sie den Zuordnungsmodus oder andere Merkmale des Gerätekontexts festlegen müssen, tun in dieser Funktion.  
  
-   Drucken-Time-Paginierung ausführen zu können. Normalerweise geben Sie die Länge des Dokuments beim Beginn des Druckens mit der [OnPreparePrinting](#onprepareprinting) Memberfunktion. Wenn Sie nicht wissen, im voraus, wie lange das Dokument ist (z. B. wenn eine unbestimmte Anzahl von Datensätzen aus einer Datenbank zu drucken) jedoch außer Kraft setzen `OnPrepareDC` um für das Ende des Dokuments zu testen, während es gedruckt wird. Wenn des Dokuments gedruckt werden nicht mehr vorhanden ist, legen Sie die `m_bContinuePrinting` Mitglied der `CPrintInfo` -Struktur an **"false"**.  
  
-   Escapesequenzen, die an den Drucker auf Basis von Seite zu senden. Zum Senden von Escapezeichen aus `OnPrepareDC`, rufen Sie die **Escape** Memberfunktion von der `pDC` Parameter.  
  
 Rufen Sie die Basisklassenversion von `OnPrepareDC` am Anfang der Außerkraftsetzung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="onprepareprinting"></a>CView::OnPreparePrinting  
 Wird vom Framework aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau angezeigt wird.  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pInfo`  
 Verweist auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ist ungleich NULL, Druck beginnen; 0, wenn der Druckauftrag wurde abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Sie müssen diese Funktion zum Drucken und Druckvorschau aktivieren überschreiben. Aufrufen der [DoPreparePrinting](#doprepareprinting) Memberfunktion ist, und übergeben sie die `pInfo` Parameter, und klicken Sie dann dessen Rückgabewert; zurückgeben `DoPreparePrinting` zeigt das Dialogfeld "Drucken" und erstellt einen Drucker-Gerätekontext. Wenn Sie das Dialogfeld "Drucken" mit Werten als die Standardwerte initialisieren möchten, die Mitglieder der Werte zuweisen `pInfo`. Wenn Sie wissen, dass die Länge des Dokuments, übergeben Sie z. B. den Wert, der die [Anzahl](../../mfc/reference/cprintinfo-structure.md#setmaxpage) Memberfunktion von `pInfo` vor dem Aufruf `DoPreparePrinting`. Dieser Wert wird angezeigt, in der To: Feld im Bereich Teil des Dialogfelds drucken.  
  
 `DoPreparePrinting`Das Dialogfeld "Drucken" für einen Auftrag für die Vorschau wird nicht angezeigt werden. Wenn Sie das Dialogfeld "Drucken" für einen Druckauftrag umgehen möchten, überprüfen Sie, ob die **M_bPreview** Mitglied `pInfo` ist **"false"** und legen Sie es auf **"true"** vor der Übergabe an `DoPreparePrinting`; setzen Sie ihn auf **"false"** danach.  
  
 Wenn Sie Initialisierungen durchführen, die auf zugreifen müssen die `CDC` überschreiben Objekt, das den Druckergerätekontext (z. B., wenn Sie die Seitengröße zu kennen, bevor Sie die Länge des Dokuments angeben müssen), darstellt der `OnBeginPrinting` Member Funktion.  
  
 Wenn der Wert festgelegt werden sollen die **M_nNumPreviewPages** oder **M_strPageDesc** Mitglied der `pInfo` Parameter dazu nach dem Aufruf `DoPreparePrinting`. Die `DoPreparePrinting` Funktion Elementgruppen **M_nNumPreviewPages** auf den Wert in der Anwendungsverzeichnis gefunden. INI-Datei und legt **M_strPageDesc** auf seinen Standardwert.  
  
### <a name="example"></a>Beispiel  
  Außer Kraft setzen `OnPreparePrinting` , und rufen Sie `DoPreparePrinting` aus überschreiben, damit das Framework ein Druckdialogfeld angezeigt, und erstellen einen Drucker-Gerätekontext für Sie.  
  
 [!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 Wenn Sie, wie viele Seiten das Dokument wissen enthält, Seite "festlegen" die maximale `OnPreparePrinting` vor dem Aufruf `DoPreparePrinting`. Das Framework wird die maximale Seitenzahl in das Feld "an" im Dialogfeld "Drucken" angezeigt.  
  
 [!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="onprint"></a>CView::OnPrint  
 Vom Framework aufgerufen wird, zu drucken oder Anzeigen einer Vorschau eine Seite des Dokuments.  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Druckergerätekontext.  
  
 `pInfo`  
 Verweist auf eine `CPrintInfo` Struktur, die den aktuellen Druckauftrag beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion für jede Seite gedruckt wird, sofort nach dem Aufruf der [OnPrepareDC](#onpreparedc) Memberfunktion. Die Seite wird angegeben, indem die `m_nCurPage` Mitglied der [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Datenstruktur, `pInfo` verweist auf. Die Standardimplementierung Ruft die [OnDraw](#ondraw) Memberfunktion und übergibt den Druckergerätekontext.  
  
 Überschreiben Sie diese Funktion für eine beliebige der folgenden Gründe:  
  
-   Das Drucken von mehrseitigen Dokumenten zulässig. Rendern Sie nur den Teil des Dokuments, das die gerade gedruckte Seite entspricht. Bei Verwendung von `OnDraw` um das Rendering ausführen, können Sie den Ursprung des Viewports anpassen, damit nur die entsprechenden Teil des Dokuments gedruckt wurde.  
  
-   Zum Erstellen der gedruckten Bilddatei anders aus als die Bildschirmanzeige (d. h. Wenn Ihre Anwendung nicht WYSIWYG ist). Anstelle der Übergabe des Druckers-Gerätekontext, `OnDraw`, verwenden Sie den Gerätekontext, um ein Bild, das Verwenden von Attributen, die nicht auf dem Bildschirm angezeigten rendern.  
  
     Wenn Sie GDI-Ressourcen für das Drucken, die nicht für die Bildschirmanzeige verwenden möchten, wählen Sie diese in den Gerätekontext vor dem Zeichnen, und heben sie deren Auswahl anschließend. Diese GDI-Ressourcen zugewiesen werden soll, im [OnBeginPrinting](#onbeginprinting) und veröffentlichte in [OnEndPrinting](#onendprinting).  
  
-   So implementieren Sie Kopf- oder Fußzeilen Sie können weiterhin `OnDraw` dazu, dass das Rendering Einschränken des Bereichs, der auf Drucken können.  
  
 Beachten Sie, dass die **M_rectDraw** Mitglied der `pInfo` Parameter beschreibt die Druckbereichs der Seite in logischen Einheiten.  
  
 Rufen Sie nicht `OnPrepareDC` in der Überschreibung der `OnPrint`; das Framework ruft `OnPrepareDC` automatisch vor dem Aufruf `OnPrint`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden finden Sie eine Skelett für eine überschriebene `OnPrint` Funktion:  
  
 [!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).  
  
##  <a name="onscroll"></a>CView::OnScroll  
 Es ist möglich, durch das Framework, um festzustellen, ob das Durchführen eines Bildlaufs bezeichnet.  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nScrollCode`  
 Ein Bildlaufleisten-Code, der den Benutzer angibt, der Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertige Byte ist, die den Typ des horizontalen Bildlauf auftritt bestimmt wird, und ein höherwertige Byte ist, die festlegt, den Typ des vertikalen Bildlauf auftritt:  
  
- **SB_BOTTOM** führt einen Bildlauf nach unten.  
  
- **SB_LINEDOWN** führt einen Bildlauf eine Zeile nach unten.  
  
- **SB_LINEUP** führt einen Bildlauf eine Zeile einrichten.  
  
- **SB_PAGEDOWN** führt einen Bildlauf eine Seite nach unten.  
  
- **SB_PAGEUP** führt einen Bildlauf eine Seite einrichten.  
  
- **SB_THUMBTRACK** zieht Bildlauffeld auf die angegebene Position. Die aktuelle Position im angegeben `nPos`.  
  
- **SB_TOP** führt einen Bildlauf nach oben.  
  
 `nPos`  
 Enthält die aktuelle Position für das Bildlauffeld, wenn der Bildlaufleisten-Code ist **SB_THUMBTRACK**; andernfalls ist es nicht verwendet. Je nach der anfänglichen Scroll Bereich `nPos` kann negativ sein und sollte in umgewandelt werden ein `int` bei Bedarf.  
  
 `bDoScroll`  
 Bestimmt, ob Sie tatsächlich die angegebene Durchführen eines Bildlaufs Aktion ausführen soll. Wenn **"true"** und Durchführen eines Bildlaufs; Wenn stattfinden sollte **"false"**, und klicken Sie dann einen Bildlauf nicht ausgeführt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `bDoScroll` ist **"true"** und wurde die Sicht tatsächlich durch einen Bildlauf, dann zurückgeben ungleich NULL ist, andernfalls 0. Wenn `bDoScroll` ist **"false"**, klicken Sie dann den Wert, der Sie Wenn zurückgegeben wäre zurückgeben `bDoScroll` wurden **"true"**, obwohl Sie tatsächlich den Bildlauf nicht tun.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in einem Fall durch das Framework mit aufgerufen `bDoScroll` festgelegt **"true"** Wenn die Sicht eine Bildlaufleiste-Nachricht empfängt. In diesem Fall sollten Sie die Ansicht tatsächlich blättern. Diese Funktion wird im anderen Fall mit `bDoScroll` festgelegt **"false"** bei einem OLE-Element anfänglich gezogen wird in den Bereich des automatischen Bildlaufs, des Drop-Ziel vor dem Durchführen eines Bildlaufs tatsächlich erfolgt. In diesem Fall sollten Sie die Sicht nicht tatsächlich blättern.  
  
##  <a name="onscrollby"></a>CView::OnScrollBy  
 Wird vom Framework aufgerufen, wenn der Benutzer einen Bereich außerhalb der vorhanden Ansicht des Dokuments, entweder durch ein OLE-Element für die Sicht aktuelle Rahmen ziehen oder bearbeiten die vertikalen oder horizontalen Bildlaufleisten anzeigt.  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeScroll`  
 Anzahl der Pixel durch einen Bildlauf horizontal und vertikal.  
  
 `bDoScroll`  
 Bestimmt, ob der Bildlauf der Ansicht auftritt. Wenn **"true"** und Durchführen eines Bildlaufs; Wenn erfolgt **"false"**, und klicken Sie dann einen Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Ansicht gescrollt werden konnte; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In abgeleiteten Klassen überprüft diese Methode, ob die Ansicht in der Richtung gescrollt werden kann, der Benutzer angefordert und aktualisiert dann die neue Region aus, bei Bedarf. Diese Funktion wird automatisch aufgerufen, indem [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) zum Ausführen der eigentlichen Durchführen eines Bildlaufs Anforderung.  
  
 Wenn er nicht aufgerufen wird, wird die Sicht nicht einen die standardmäßige Implementierung dieser Methode ändert sich nicht auf die Ansicht ist jedoch eine `CScrollView`-Klasse.  
  
 Wenn die Breite oder Höhe 32767 Pixel überschreitet, Durchführen eines Bildlaufs nach 32767 schlägt fehl, da `OnScrollBy` aufgerufen wird, mit einem ungültigen `sizeScroll` Argument.  
  
##  <a name="onupdate"></a>CView::OnUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht Dokument geändert wurde; Diese Funktion wird aufgerufen, indem [UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) und ermöglicht die Ansicht, um die Aktualisierung der Anzeige, um diese Änderungen widerzuspiegeln.  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Verweist auf die Sicht, die das Dokument geändert oder **NULL** Wenn alle Sichten aktualisiert werden.  
  
 `lHint`  
 Enthält Informationen zu den Änderungen an.  
  
 `pHint`  
 Verweist auf ein Objekt, das Informationen zu den Änderungen zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Es wird auch aufgerufen, durch die standardmäßige Implementierung des [OnInitialUpdate](#oninitialupdate). Die standardmäßige Implementierung erklärt den gesamten Clientbereich, markieren sie zum Zeichnen, wenn die nächste `WM_PAINT` Nachricht empfangen wird. Überschreiben Sie diese Funktion, wenn Sie nur diejenigen Regionen zu aktualisieren, die die geänderten Teile des Dokuments zuordnen möchten. Zu diesem Zweck müssen Sie Informationen zu den Änderungen, die mit den Parametern-Hinweis übergeben.  
  
 Mit `lHint`Hinweis spezielle Werte, in der Regel eine Bitmaske oder ein enumerierter Typ zu definieren und das Dokument, übergeben Sie einen der folgenden Werte haben. Verwenden `pHint`, leiten Sie eine Klasse Hinweis aus [CObject](../../mfc/reference/cobject-class.md) und das Dokument, das einen Zeiger auf ein Objekt auf Hinweis übergeben werden, überschreiben `OnUpdate`, verwenden die [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) Memberfunktion Bestimmen der Laufzeittyp des Objekts Hinweis an.  
  
 In der Regel führen Sie eine direkte zeichnen `OnUpdate`. Stattdessen ermittelt das Rechteck beschreiben, in Gerätekoordinaten des Bereichs, der muss aktualisiert werden; übergeben Sie diesem Rechteck [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect). Dies bewirkt, dass das nächste Mal ausgeführt Malen eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht empfangen wird.  
  
 Wenn `lHint` ist 0 und `pHint` ist **NULL**, das Dokument verfügt über eine generische updatebenachrichtigung gesendet. Wenn eine Sicht eine generische updatebenachrichtigung empfängt oder die Hinweise nicht decodiert werden kann, sollte er seinen gesamten Clientbereich ungültig.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)
