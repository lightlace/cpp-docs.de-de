---
title: CDocument-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: 2d87ff67000fb5b70c0a5c965638875e6f50b22c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164115"
---
# <a name="cdocument-class"></a>CDocument-Klasse

Stellt die grundlegende Funktionalität für benutzerdefinierte Dokumentklassen bereit.

## <a name="syntax"></a>Syntax

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDocument::CDocument](#cdocument)|Erstellt ein `CDocument`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDocument::AddView](#addview)|Fügt eine Ansicht an das Dokument an.|
|[CDocument::BeginReadChunks](#beginreadchunks)|Initialisiert chunk lesen.|
|[CDocument::CanCloseFrame](#cancloseframe)|Erweiterte überschreibbare; wird aufgerufen, vor dem Schließen eines Rahmenfensters dieses Dokument anzeigen.|
|[CDocument::ClearChunkList](#clearchunklist)|Löscht die Blockliste an.|
|[CDocument::ClearPathName](#clearpathname)|Löscht den Pfad des das Document-Objekt.|
|[CDocument::DeleteContents](#deletecontents)|Wird aufgerufen, um die Bereinigung des Dokuments auszuführen.|
|[CDocument::FindChunk](#findchunk)|Sucht nach der ein Segment mit der angegebenen GUID.|
|[CDocument::GetAdapter](#getadapter)|Gibt einen Zeiger auf die objektimplementierung `IDocument` Schnittstelle.|
|[CDocument::GetDocTemplate](#getdoctemplate)|Gibt einen Zeiger auf die Dokumentvorlage, die den Typ des Dokuments beschreibt.|
|[CDocument::GetFile](#getfile)|Gibt einen Zeiger auf die gewünschte `CFile` Objekt.|
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Gibt die Position des ersten in der Liste der Ansichten, verwendet, um die Iteration starten.|
|[CDocument::GetNextView](#getnextview)|Iteriert durch die Liste der Ansichten, die dem Dokument zugeordnet.|
|[CDocument::GetPathName](#getpathname)|Gibt den Pfad der Datendatei des Dokuments ab.|
|[CDocument::GetThumbnail](#getthumbnail)|Wird aufgerufen, um eine Bitmap von Miniaturansicht-Provider verwendet werden, zum Anzeigen der Miniaturansicht zu erstellen.|
|[CDocument::GetTitle](#gettitle)|Gibt den Titel des Dokuments zurück.|
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Wird aufgerufen, um Suchinhalt für Suche Handler zu initialisieren.|
|[CDocument::IsModified](#ismodified)|Gibt an, ob das Dokument geändert wurde, seit es zuletzt gespeichert wurde.|
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Informiert, ob diese Instanz von `CDocument` Objekt zu suchen und Organisieren Handler erstellt wurde.|
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Wird aufgerufen, um das Laden der Dokumentdaten aus Stream.|
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Wird aufgerufen, bevor Rich Preview Schriftart geändert wird.|
|[CDocument::OnChangedViewList](#onchangedviewlist)|Wird aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.|
|[CDocument::OnCloseDocument](#onclosedocument)|Wird aufgerufen, um das Dokument zu schließen.|
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Vom Framework aufgerufen, wenn sie eine Vorschauframe for Rich Preview erstellen muss.|
|[CDocument::OnDocumentEvent](#ondocumentevent)|Wird aufgerufen, durch das Framework als Reaktion auf ein Dokumentereignis.|
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Zeichnen der Inhalte der Miniaturansicht an.|
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Vom Framework aufgerufen, wenn die Dokumentdaten aus Stream geladen werden muss.|
|[CDocument::OnNewDocument](#onnewdocument)|Wird aufgerufen, um ein neues Dokument erstellen.|
|[CDocument::OnOpenDocument](#onopendocument)|Wird aufgerufen, um ein vorhandenes Dokument zu öffnen.|
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Weist den Vorschauhandler zur Rückgabe des HWND über die GetFocus-Funktion aufrufen.|
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Weist den Vorschauhandler verarbeitet eine Tastatureingabe nach oben übergeben wird, aus dem Nachrichtensystem des Prozesses in der der Vorschauhandler ausgeführt wird.|
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Aufgerufen, wenn die Hintergrundfarbe für die umfassende Vorschau geändert wurde.|
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Aufgerufen, wenn Sie Rich Preview Schriftart geändert hat.|
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Aufgerufen, wenn Sie Rich Preview-Standorts geändert hat.|
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Aufgerufen, wenn die Textfarbe für die umfassende Vorschau geändert wurde.|
|[CDocument::OnSaveDocument](#onsavedocument)|Wird aufgerufen, um das Dokument auf den Datenträger zu speichern.|
|[CDocument::OnUnloadHandler](#onunloadhandler)|Vom Framework aufgerufen, wenn der Vorschauhandler entladen wird.|
|[CDocument::PreCloseFrame](#precloseframe)|Wird aufgerufen, bevor das Rahmenfenster geschlossen wird.|
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Liest die nächsten Block-Wert.|
|[CDocument::ReleaseFile](#releasefile)|Gibt eine Datei, um es für die Verwendung von anderen Anwendungen zur Verfügung.|
|[CDocument::RemoveChunk](#removechunk)|Entfernt ein Segment mit der angegebenen GUID.|
|[CDocument::RemoveView](#removeview)|Trennt eine Ansicht aus dem Dokument.|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Erweiterte überschreibbare; wird aufgerufen, wenn eine offene oder Speichervorgang kann nicht aufgrund einer Ausnahme abgeschlossen werden.|
|[CDocument::SaveModified](#savemodified)|Erweiterte überschreibbare; wird aufgerufen, um die Benutzer zu Fragen, ob das Dokument gespeichert werden soll.|
|[CDocument::SetChunkValue](#setchunkvalue)|Legt einen Block-Wert.|
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Legt ein Flag, das angibt, dass Sie das Dokument geändert haben, seit es zuletzt gespeichert wurde.|
|[CDocument::SetPathName](#setpathname)|Legt den Pfad der Datendatei ein, die das Dokument fest.|
|[CDocument::SetTitle](#settitle)|Legt den Titel des Dokuments fest.|
|[CDocument::UpdateAllViews](#updateallviews)|Benachrichtigt alle Ansichten das Dokument geändert wurde.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDocument::OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Können den Befehl Mail senden, wenn e-Mail-Unterstützung vorhanden ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Gibt an, dass `CDocument` Objekt durch Dllhost für Miniaturansichten erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.|
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Gibt an, dass `CDocument` -Objekt wurde erstellt, indem Prevhost für `Rich Preview`. Sollte aktiviert sein, `CView::OnDraw`.|
|[CDocument::m_bSearchMode](#m_bsearchmode)|Gibt an, dass `CDocument` Objekt erstellt wurde, durch den Indexer oder einer anderen Suchanwendung.|
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Gibt die Hintergrundfarbe des Rich-Vorschaufenster an. Diese Farbe wird vom Host festgelegt.|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Gibt die Vordergrundfarbe des Rich-Vorschaufenster an. Diese Farbe wird vom Host festgelegt.|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Gibt die Textschriftart für Rich-Vorschaufenster an. Diese Schriftartinformationen wird vom Host festgelegt.|

## <a name="remarks"></a>Hinweise

Ein Dokument repräsentiert die Einheit von Daten, die der Benutzer normalerweise mit der Datei öffnen (Befehl) wird geöffnet und speichert, die mit dem Befehl Datei zu speichern.

`CDocument` unterstützt die standard-Vorgänge wie z. B. ein Dokument zu erstellen, laden und speichern es. Das Framework bearbeitet, Dokumente, die mithilfe der Benutzeroberfläche von definierten `CDocument`.

Eine Anwendung kann mehr als einen Typ des Dokuments unterstützen; Beispielsweise kann eine Anwendung sowohl Tabellen als auch Text unterstützen. Jede Art von Dokument verfügt über eine zugeordnete Dokumentvorlage; die Dokumentvorlage gibt an, welche Ressourcen (z. B. Menüs, Symbol oder Accelerator-Tabelle) für diesen Typ des Dokuments verwendet werden. Jedes Dokument enthält einen Zeiger auf die zugehörigen `CDocTemplate` Objekt.

Benutzer interagieren mit einem Dokument über die [CView](../../mfc/reference/cview-class.md) Objekte zugeordnet. Eine Ansicht rendert ein Bild des Dokuments in einem Rahmenfenster und Benutzereingaben als Vorgänge des Dokuments interpretiert. Ein Dokument kann mehrere Ansichten zugeordnet haben. Wenn der Benutzer ein Fenster auf ein Dokument öffnet, wird das Framework wird eine Sicht erstellt, und fügt sie dem Dokument. Die Dokumentvorlage gibt an, welche Art von Ansicht- und Frame-Fensters werden verwendet, um jeden Typ von Dokument anzuzeigen.

Dokumente sind Teil der Standard für die Framework Befehl, routing und empfangen folglich Befehle von standard-Benutzeroberflächen-Komponenten (z. B. das Menüelement Datei zu speichern). Ein Dokument empfängt, Befehle, die von der aktiven Ansicht weitergeleitet wird. Wenn das Dokument einen bestimmten Befehl nicht behandelt werden, wird der Befehl aus, um die Dokumentvorlage, die er verwaltet weitergeleitet.

Wenn Daten eines Dokuments geändert werden, muss jedes der zugehörigen Ansichten diese Änderungen widerspiegeln. `CDocument` Stellt die [UpdateAllViews](#updateallviews) Memberfunktion für die Sie benachrichtigen Sie die Ansichten der solche Änderungen aus, damit die Ansichten selbst nach Bedarf neu zeichnen können. Das Framework auch der Benutzer aufgefordert, eine geänderte Datei, die vor dem Schließen gespeichert.

Um Dokumente in einer typischen Anwendung zu implementieren, müssen Sie die folgenden Schritte ausführen:

- Leiten Sie eine Klasse von `CDocument` für jeden Typ des Dokuments.

- Hinzufügen von Membervariablen zum Speichern von Daten des Dokuments.

- Implementieren Sie die Memberfunktionen für das Lesen und ändern die Daten des Dokuments. Die Ansichten des Dokuments sind die wichtigsten Benutzer diese Memberfunktionen.

- Überschreiben der [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) Member-Funktion in der Dokumentklasse zum Schreiben und lesen die Daten des Dokuments zum und vom Datenträger.

`CDocument` unterstützt das das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).

Weitere Informationen zu `CDocument`, finden Sie unter [Serialisierung](../../mfc/serialization-in-mfc.md), [Dokument-/Ansicht-Cloudarchitektur – Themen](../../mfc/document-view-architecture.md), und [Dokument-/Ansicht-Erstellung](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="addview"></a>  CDocument:: AddView

Rufen Sie diese Funktion, um eine Ansicht an das Dokument angefügt.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>Parameter

*pView*<br/>
Verweist auf die Ansicht hinzugefügt wird.

### <a name="remarks"></a>Hinweise

Diese Funktion fügt die angegebene Ansicht hinzu, um die Liste der Ansichten, die dem Dokument zugeordnet; die Funktion legt auch die Ansicht des Dokuments Zeiger zu diesem Dokument fest. Das Framework ruft diese Funktion an, wenn ein neu erstelltes Objekt in ein Dokument anfügen; Dieser Fehler tritt in Reaktion auf eine neue Datei, neues Fenster oder Datei öffnen-Befehl, oder wenn ein Teilungsfenster aufgeteilt wird.

Rufen Sie diese Funktion nur, wenn Sie manuell erstellen und Anfügen eine Ansicht. In der Regel können Sie das Framework, das Verbinden von Dokumenten und Ansichten durch Definieren einer [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt, das eine "Document"-Klasse Ansichtsklasse und Rahmenfenster (Klasse) zuordnen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks

Initialisiert chunk lesen.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Hinweise

##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame

Vom Framework aufgerufen, bevor ein Rahmenfenster, das Dokument anzeigen geschlossen wird.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parameter

*pFrame*<br/>
Zeigt auf das Rahmenfenster des eine Ansicht, die dem Dokument zugeordnet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn es sicher ist, schließen Sie das Rahmenfenster ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung überprüft, ob andere Rahmenfenster, das Dokument anzeigen. Wenn das angegebene Rahmenfenster das letzte, in dem das Dokument angezeigt ist, die Funktion der Benutzer aufgefordert, das Dokument zu speichern, wenn es geändert wurde. Überschreiben Sie diese Funktion, sollten Sie durchführen, besondere Bearbeitung, wenn ein Rahmenfenster geschlossen wird. Dies ist ein fortschrittlicher überschreibbar.

##  <a name="cdocument"></a>  CDocument::CDocument

Erstellt ein `CDocument`-Objekt.

```
CDocument();
```

### <a name="remarks"></a>Hinweise

Das Framework verarbeitet die dokumenterstellung für Sie. Überschreiben der [OnNewDocument](#onnewdocument) Memberfunktion für die Initialisierung pro pro-Dokument ein; Dies ist besonders wichtig, in einzelnen Dokument Interface (SDI) Anwendungen.

##  <a name="clearchunklist"></a>  CDocument::ClearChunkList

Löscht die Blockliste an.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Hinweise

##  <a name="clearpathname"></a>  CDocument::ClearPathName

Löscht den Pfad des das Document-Objekt.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Hinweise

Löschen den Pfad aus einem `CDocument` Objekt bewirkt, dass die Anwendung den Benutzer auffordern, wenn Sie als Nächstes das Dokument gespeichert wird. Dadurch wird eine **speichern** Befehl Verhalten sich wie ein **speichern** Befehl.

##  <a name="deletecontents"></a>  CDocument::DeleteContents

Wird aufgerufen, durch das Framework So löschen Sie die Daten des Dokuments ohne zu zerstören der `CDocument` Objekt selbst.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Hinweise

Sie wird aufgerufen, kurz bevor das Dokument ist, zerstört werden soll. Sie wird auch aufgerufen, um sicherzustellen, dass ein Dokument leer ist, bevor er wiederverwendet werden. Dies ist besonders wichtig für eine SDI-Anwendung, die nur ein Dokument verwendet. das Dokument wird wiederverwendet, wenn der Benutzer erstellt oder ein anderes Dokument öffnet. Rufen Sie diese Funktion zur Implementierung einer "Bearbeiten Alle löschen" oder einen ähnlichen Befehl, der alle Daten des Dokuments werden gelöscht. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um die Daten in Ihrem Dokument zu löschen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>  CDocument::FindChunk

Sucht nach einem Block mit einer angegebenen GUID.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parameter

*guid*<br/>
Gibt die GUID eines Blocks gefunden.

*pid*<br/>
Gibt an, eine PID eines Blocks gefunden.

### <a name="return-value"></a>Rückgabewert

Die Position in der internen integritätszustandsblock-Liste, wenn erfolgreich. Andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="getadapter"></a>  CDocument::GetAdapter

Gibt einen Zeiger auf ein Objekt, das die `IDocument` Schnittstelle.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Objekt, das die `IDocument` Schnittstelle.

### <a name="remarks"></a>Hinweise

##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate

Rufen Sie diese Funktion zum Abrufen eines Zeigers auf die Dokumentvorlage für diesen Dokumenttyp an.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Dokumentvorlage für diesen Dokumenttyp oder NULL, wenn das Dokument nicht von einer Dokumentvorlage verwaltet wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>  CDocument::GetFile

Rufen Sie diese Memberfunktion, um einen Zeiger auf eine `CFile` Objekt.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Parameter

*lpszFileName*<br/>
Eine Zeichenfolge, die den Pfad zur gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.

*pError*<br/>
Ein Zeiger auf eine vorhandene Datei-Ausnahme-Objekt, das den Abschlussstatus des Vorgangs angibt.

*nOpenFlags*<br/>
Gemeinsame Nutzung und Zugriffsmodus. Gibt die Aktion an, der beim Öffnen der Datei an. Können Sie in der CFile-Konstruktor angegebenen Optionen kombinieren [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) mit dem bitweisen OR (&#124;) Operator. Ein zugriffsberechtigungseintrag und ein Freigabe-Option sind erforderlich. die `modeCreate` und `modeNoInherit` Modi sind optional.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CFile` -Objekt.

##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition

Rufen Sie diese Funktion rufen Sie die Position der ersten Sicht in der Liste der Ansichten, die dem Dokument zugeordnet.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Positionswert, der für die Iteration mit der verwendet werden kann die [GetNextView](#getnextview) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>  CDocument::GetNextView

Rufen Sie diese Funktion zum Durchlaufen aller die Ansichten des Dokuments.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parameter

*rPosition*<br/>
Ein Verweis auf einen Positionswert zurückgegeben wird, durch einen vorherigen Aufruf der `GetNextView` oder [Sie GetFirstViewPosition](#getfirstviewposition) Memberfunktionen. Dieser Wert darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Ansicht identifizierte *rposition zurück*.

### <a name="remarks"></a>Hinweise

Die Funktion gibt die Sicht identifizierte *rposition zurück* und legt dann *rposition zurück* auf den Wert der POSITION der Sicht in der Liste weiter. Wenn die abgerufenen Ansicht der letzte in der Liste aus, klicken Sie dann *rposition zurück* auf NULL festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>  CDocument::GetPathName

Rufen Sie diese Funktion rufen Sie den vollqualifizierten Pfad der Datenträger-Datei des Dokuments ab.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Rückgabewert

Das Dokument der voll gekennzeichnete Pfad. Diese Zeichenfolge ist leer, wenn das Dokument nicht gespeichert wurde oder verfügt nicht über die Datei auf einem Datenträger zugeordnet.

##  <a name="getthumbnail"></a>  CDocument::GetThumbnail

Erstellt eine Bitmap, die von den Miniaturansicht-Provider verwendet werden, um die Miniaturansicht anzuzeigen.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Parameter

*cx*<br/>
Gibt die Breite und Höhe der Bitmap.

*phbmp*<br/>
Enthält ein Handle für eine Bitmap, wenn die Funktion wurde erfolgreich zurückgegeben.

*pdwAlpha*<br/>
Enthält ein DWORD, das den alpha-Kanal angibt, wenn die Funktion wurde erfolgreich zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn eine Bitmap für die Miniaturansicht wurde erfolgreich erstellt. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="gettitle"></a>  CDocument::GetTitle

Rufen Sie diese Funktion rufen Sie den Titel des Dokuments, die von dem Dateinamen des Dokuments in der Regel abgeleitet ist.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Der Titel eines Dokuments.

##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent

Wird aufgerufen, um Search-Inhalte für den Search-Handler zu initialisieren.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse Inhalt durchsuchen initialisiert werden. Der Inhalt muss eine Zeichenfolge mit Elementen getrennt durch ";". Beispielsweise "zeigen; Rechteck OLE-Element".

##  <a name="ismodified"></a>  CDocument::IsModified

Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument geändert wurde, seit es zuletzt gespeichert wurde.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Dokument seit der letzten Speicherung geändert wurde; andernfalls 0.

##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler

Informiert, ob diese Instanz von `CDocument` erstellt wurde, für den Ereignishandler suchen und organisieren.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn diese Instanz von `CDocument` erstellt wurde, für den Ereignishandler suchen und organisieren.

### <a name="remarks"></a>Hinweise

Derzeit gibt diese Funktion "true" nur für Rich-Vorschauhandler in einer Out-of Process-Server implementiert. Sie können den geeigneten Flags (M_bPreviewHandlerMode, M_bSearchMode M_bGetThumbnailMode) festlegen, auf der Anwendungsebene zu dieser Funktion "true" zurückgeben.

##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream

Wird aufgerufen, um das Laden von Dokumentendaten aus einem Stream.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
Ein Zeiger auf einen Stream. Dieser Datenstrom wird von der Shell bereitgestellt.

*dwGrfMode*<br/>
Der Zugriffsmodus in den Stream.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der Ladevorgang erfolgreich ist, andernfalls HRESULT mit einem Fehlercode.

### <a name="remarks"></a>Hinweise

Sie können diese Methode in einer abgeleiteten Klasse zum Laden von Daten aus dem Stream anpassen überschreiben.

##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode

Gibt an, dass die `CDocument` Objekt durch Dllhost für Miniaturansichten erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Hinweise

`TRUE` Gibt an, dass das Dokument mit Dllhost für Miniaturansichten erstellt wurde.

##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode

Gibt an, dass die `CDocument` Objekt durch Prevhost for Rich Preview erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Hinweise

TRUE gibt an, dass das Dokument mit Prevhost for Rich Preview erstellt wurde.

##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode

Gibt an, dass die `CDocument` Objekt erstellt wurde, Indexer oder von einer anderen Search-Anwendung.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Hinweise

`TRUE` Gibt an, dass das Dokument, Indexer oder von einer anderen Search-Anwendung erstellt wurde.

##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor

Gibt die Hintergrundfarbe des Fensters umfassende Vorschau an. Diese Farbe wird vom Host festgelegt.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor

Gibt die Vordergrundfarbe des Fensters umfassende Vorschau an. Diese Farbe wird vom Host festgelegt.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont

Gibt die Schriftart für das Vorschaufenster mit Rich Text an. Diese Schriftartinformationen wird vom Host festgelegt.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Hinweise

##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged

Wird aufgerufen, bevor die umfassende Vorschau Schriftart geändert wird.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Hinweise

##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList

Vom Framework aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion überprüft, ob die letzte Ansicht entfernt wird, und wenn dies der Fall ist, das Dokument löscht. Überschreiben Sie diese Funktion, wenn durchführen, besondere Bearbeitung, wenn das Framework hinzufügt oder eine Sicht entfernt werden sollen. Z. B. wenn ein Dokument geöffnet bleiben, selbst wenn es keine Sichten, die angefügt sind werden soll, überschreiben Sie diese Funktion.

##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument

Vom Framework aufgerufen, wenn das Dokument, in der Regel als Teil der Datei Close-Befehl geschlossen wird.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion löscht alle Frames für die Anzeige des Dokuments verwendet, schließt die Ansicht, die Inhalte des Dokuments bereinigt und ruft dann die [DeleteContents](#deletecontents) Memberfunktion, um das Löschen des Dokuments Daten.

Überschreiben Sie diese Funktion, wenn Sie möchten Verarbeitungsschritte spezielle Bereinigung ausführen, wenn das Framework ein Dokument geschlossen wird. Z. B. wenn das Dokument einen Datensatz in einer Datenbank darstellt, können Sie dieser Funktion können Sie die Datenbank schließen überschreiben möchten. Sie sollten die Basisklassenversion dieser Funktion aus der Überschreibung aufrufen.

##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame

Vom Framework aufgerufen, wenn sie eine Vorschauframe for Rich Preview erstellen muss.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Frame erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent

Wird aufgerufen, durch das Framework als Reaktion auf ein Dokumentereignis.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Parameter

*deEvent*<br/>
[in] Ein Aufzählungsdatentyp, der den Typ des Ereignisses beschreibt.

### <a name="remarks"></a>Hinweise

Dokumentereignisse können mehrere Klassen auswirken. Diese Methode ist verantwortlich für die Behandlung von Ereignissen, die Klassen außer Auswirkungen auf die [CDocument-Klasse](../../mfc/reference/cdocument-class.md). Derzeit die einzige Klasse, die auf Dokumentereignisse reagieren muss, ist die [CDataRecoveryHandler-Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Die `CDocument` -Klasse verfügt über andere überschreibbare Methoden, die verantwortlich für die Behandlung der Auswirkungen auf die `CDocument`.

Die folgende Tabelle enthält die möglichen Werte für *deEvent* und die Ereignisse, die diese entsprechen.

|Wert|Entsprechendes Ereignis|
|-----------|-------------------------|
|`onAfterNewDocument`|Es wurde ein neues Dokument erstellt.|
|`onAfterOpenDocument`|Ein neues Dokument geöffnet wurde.|
|`onAfterSaveDocument`|Das Dokument wurde gespeichert.|
|`onAfterCloseDocument`|Das Dokument wurde geschlossen.|

##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail

Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Miniaturansicht zu zeichnen.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Parameter

*dc*<br/>
Ein Verweis auf einen Gerätekontext.

*lprcBounds*<br/>
Gibt ein umschließende Rechteck des Bereichs, in dem die Miniaturansicht gezeichnet werden soll.

### <a name="remarks"></a>Hinweise

##  <a name="onfilesendmail"></a>  CDocument:: OnFileSendMail

Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.

```
void OnFileSendMail();
```

### <a name="remarks"></a>Hinweise

`OnFileSendMail` Aufrufe [OnSaveDocument](#onsavedocument) (Speichern) ohne Titel und geänderte Dokumente in eine temporäre Datei serialisiert werden soll, klicken Sie dann über e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei ist nicht erforderlich; die ursprüngliche wird gesendet. `OnFileSendMail` Lädt MAPI32 an. DLL, wenn es nicht bereits geladen wurde.

Eine besondere Implementierung von `OnFileSendMail` für [COleDocument](../../mfc/reference/coledocument-class.md) Verbunddateien ordnungsgemäß behandelt.

`CDocument` unterstützt das das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream

Vom Framework aufgerufen, wenn die Dokumentendaten aus einem Datenstrom geladen werden muss.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
Ein Zeiger auf einen eingehenden Datenstream.

*grfMode*<br/>
Der Zugriffsmodus in den Stream.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der Ladevorgang erfolgreich ist; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="onnewdocument"></a>  CDocument::OnNewDocument

Wird aufgerufen, durch das Framework als Teil des Befehls Datei neu.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Dokument erfolgreich initialisiert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung dieser Funktion die [DeleteContents](#deletecontents) Member-Funktion, um sicherzustellen, dass das Dokument leer ist, und anschließend das neue Dokument als bereinigen markiert. Überschreiben Sie diese Funktion, um die Datenstruktur für ein neues Dokument zu initialisieren. Sie sollten die Basisklassenversion dieser Funktion aus der Überschreibung aufrufen.

Wenn der Benutzer die Datei neuer Befehl in einer SDI-Anwendung auswählt, verwendet das Framework diese Funktion zum erneuten Initialisieren der vorhandenen Dokument, anstatt einen neuen zu erstellen. Wenn der Benutzer neue Datei in eine Anwendung der multiple Document Interface (MDI), wird das Framework erstellt ein neues Dokument jedes Mal, und klicken Sie dann Aufrufe dieser Funktion können Sie sie initialisieren. Sie müssen diese Funktion statt des im Konstruktor für die neue Datei Befehl aus, um effektiv SDI-Anwendungen den Initialisierungscode versehen.

Beachten Sie, dass es Fälle, in denen `OnNewDocument` wird zweimal aufgerufen. Dies tritt auf, wenn das Dokument als Server ActiveX-Dokument eingebettet ist. Die Funktion wird zuerst aufgerufen werden, indem die `CreateInstance` Methode (verfügbar gemacht werden, indem die `COleObjectFactory`-abgeleitete Klasse) und ein zweites Mal von der `InitNew` Methode (verfügbar gemacht werden, indem die `COleServerDoc`-abgeleitete Klasse).

### <a name="example"></a>Beispiel

Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren eines Dokumentobjekts.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>  Funktionen

Wird aufgerufen, durch das Framework als Teil des Befehls Datei öffnen.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Zeigt auf den Pfad des Dokuments, das geöffnet werden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Dokument erfolgreich geladen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion öffnet die angegebene Datei, Aufrufe der [DeleteContents](#deletecontents) Memberfunktion, um sicherzustellen, dass das Dokument leer ist, ruft [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) zum Lesen der Datei Inhalt und markiert anschließend das Dokument als bereinigen. Überschreiben Sie diese Funktion, wenn Sie als der Archiv-Mechanismus oder der dateimechanismus verwenden möchten. Beispielsweise können Sie eine Anwendung schreiben, in denen Darstellung von Dokumenten auf Datensätze in einer Datenbank statt in separaten Dateien.

Wenn der Benutzer die Datei öffnen-Befehl in einer SDI-Anwendung auswählt, verwendet das Framework diese Funktion zum erneuten Initialisieren der vorhandenen `CDocument` Objekt statt einen neuen zu erstellen. Wenn der Benutzer in einer MDI-Anwendung öffnen Datei auswählt, erstellt das Framework eine neue `CDocument` Objekt jedes Mal, und klicken Sie dann Aufrufe dieser Funktion können Sie sie initialisieren. Sie müssen diese Funktion statt des im Konstruktor für die Datei öffnen Befehl aus, um effektiv SDI-Anwendungen den Initialisierungscode versehen.

### <a name="example"></a>Beispiel

Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren eines Dokumentobjekts.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus

Weist den Vorschauhandler zurück, das HWND abgerufen wird, durch den Aufruf der `GetFocus` Funktion.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Parameter

*phwnd*<br/>
[out] Bei der Rückgabe dieser Methode enthält einen Zeiger auf das vom Aufruf zurückgegebene HWND der `GetFocus` -Funktion aus dem Vorschauhandler Vordergrundthread.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn erfolgreich; oder einen Fehlerwert, die andernfalls.

### <a name="remarks"></a>Hinweise

##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator

Weist den Vorschauhandler verarbeitet eine Tastatureingabe nach oben übergeben wird, aus dem Nachrichtensystem des Prozesses in der der Vorschauhandler ausgeführt wird.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Parameter

*pmsg*<br/>
[in] Ein Zeiger auf eine fenstermeldung.

### <a name="return-value"></a>Rückgabewert

Wenn die Tastatureingabe-Nachricht, die von den Vorschauhandler verarbeitet werden kann, wird der Handler verarbeitet diese und gibt S_OK zurück. Wenn der Vorschauhandler die Tastatureingabe-Nachricht nicht verarbeiten kann, bietet es an dem Host über `IPreviewHandlerFrame::TranslateAccelerator`. Diese Methode gibt S_OK zurück, wenn der Host die Nachricht verarbeitet. Diese Methode gibt S_FALSE zurück, wenn der Host die Nachricht nicht verarbeitet.

### <a name="remarks"></a>Hinweise

##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged

Wird aufgerufen, wenn die Hintergrundfarbe für die umfassende Vorschau geändert wurde.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Hinweise

##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged

Wird aufgerufen, wenn es sich bei der erweiterten Vorschau Schriftart geändert hat.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Hinweise

##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged

Wird aufgerufen, wenn es sich bei der Rich Preview-Standorts geändert hat.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Hinweise

##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged

Aufgerufen, wenn die Textfarbe für die umfassende Vorschau geändert wurde.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Hinweise

##  <a name="onsavedocument"></a>  CDocument::OnSaveDocument

Wird aufgerufen, durch das Framework als Teil der Datei zu speichern oder Datei speichern unter-Befehl.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Verweist auf den vollqualifizierten Pfad zu dem die Datei gespeichert werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Dokument erfolgreich gespeichert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion öffnet die angegebene Datei, Aufrufe [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) zum Schreiben von Daten des Dokuments, um die Datei, und klicken Sie dann ein Dokument als bereinigen. Überschreiben Sie diese Funktion, sollten Sie durchführen, besondere Bearbeitung, wenn das Framework ein Dokument speichert. Beispielsweise können Sie eine Anwendung schreiben, in denen Darstellung von Dokumenten auf Datensätze in einer Datenbank statt in separaten Dateien.

##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler

Vom Framework aufgerufen, wenn der Vorschauhandler entladen wird.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Hinweise

##  <a name="onupdatefilesendmail"></a>  CDocument:: OnUpdateFileSendMail

Können den ID_FILE_SEND_MAIL-Befehl aus, wenn e-Mail-Unterstützung (MAPI) vorhanden ist.

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*pCmdUI*<br/>
Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt, mit dem Befehl ID_FILE_SEND_MAIL verknüpft ist.

### <a name="remarks"></a>Hinweise

Andernfalls entfernt die Funktion der ID_FILE_SEND_MAIL-Befehl im Menü, einschließlich der Trennzeichen, über oder unter dem Menüelement, das nach Bedarf. MAPI wird aktiviert, wenn MAPI32. DLL ist vorhanden, in den Pfad und im Abschnitt [Mail] der weißheit letzter Schluss. INI-Datei, MAPI = 1. Die meisten Anwendungen fügen Sie diesen Befehl im Menü Datei.

`CDocument` unterstützt das das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="precloseframe"></a>  CDocument::PreCloseFrame

Diese Memberfunktion wird von Framework aufgerufen, bevor das Rahmenfenster zerstört wird.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parameter

*pFrame*<br/>
Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) , enthält das zugeordnete `CDocument` Objekt.

### <a name="remarks"></a>Hinweise

Sie können überschrieben werden, geben Sie benutzerdefinierte cleanupstrategien, jedoch müssen Sie auch die Basisklasse aufrufen.

Die Standardeinstellung `PreCloseFrame` nichts `CDocument`. Die `CDocument`-abgeleitete Klassen [COleDocument](../../mfc/reference/coledocument-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) verwenden Sie diese Memberfunktion auf.

##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue

Liest den nächsten Block-Wert.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Parameter

*ppValue*<br/>
[out] Wenn die Funktion zurückgibt, *PpValue* enthält den Wert an, das gelesen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

##  <a name="releasefile"></a>  CDocument::ReleaseFile

Diese Memberfunktion wird von dem Framework, Version eine Datei, und somit zur Verwendung von anderen Anwendungen aufgerufen.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Parameter

*pFile*<br/>
Ein Zeiger auf das CFile-Objekt, das freigegeben werden.

*bAbort*<br/>
Gibt an, ob die Datei freigegeben werden, indem Sie entweder `CFile::Close` oder `CFile::Abort`. "False", wenn die Datei freigegeben werden, mithilfe von [CFile::Close](../../mfc/reference/cfile-class.md#close); TRUE, wenn die Datei freigegeben werden, mithilfe von [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Hinweise

Wenn *bAbort* ist "true", `ReleaseFile` Aufrufe `CFile::Abort`, und die Datei wird freigegeben. `CFile::Abort` löst eine Ausnahme nicht.

Wenn *bAbort* ist "false", `ReleaseFile` Aufrufe `CFile::Close` und die Datei wird freigegeben.

Überschreiben Sie diese Memberfunktion, um eine Aktion durch den Benutzer erfordern, bevor die Datei freigegeben wird.

##  <a name="removechunk"></a>  CDocument::RemoveChunk

Entfernt ein Segment mit der angegebenen GUID.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parameter

*Guid*<br/>
Gibt die GUID eines Blocks entfernt werden soll.

*Pid*<br/>
Gibt an, die PID eines Blocks entfernt werden soll.

### <a name="remarks"></a>Hinweise

##  <a name="removeview"></a>  CDocument::RemoveView

Rufen Sie diese Funktion, um eine Ansicht aus einem Dokument zu trennen.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Parameter

*pView*<br/>
Verweist auf die Ansicht entfernt wird.

### <a name="remarks"></a>Hinweise

Diese Funktion entfernt die angegebene Ansicht aus der Liste der Ansichten, die mit dem Dokument verknüpfte; Außerdem wird die Ansicht des Dokuments Zeiger auf NULL festgelegt. Diese Funktion wird vom Framework aufgerufen, wenn ein Rahmenfenster geschlossen ist, oder ein Bereich eines unterteilten Fensters geschlossen wird.

Rufen Sie diese Funktion nur, wenn Sie eine Ansicht manuell getrennt sind. In der Regel können Sie das Framework durch Definieren von Dokumenten und Ansichten trennen eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt, das eine "Document"-Klasse Ansichtsklasse und Rahmenfenster (Klasse) zuordnen.

Siehe das Beispiel unter [AddView](#addview) eine beispielimplementierung.

##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException

Wird aufgerufen, wenn eine Ausnahme ausgelöst wird (in der Regel eine [CFileException](../../mfc/reference/cfileexception-class.md) oder [CArchiveException](../../mfc/reference/carchiveexception-class.md)) beim Speichern oder Laden des Dokuments.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Verweist auf den Namen des Dokuments, das wurde gespeichert oder geladen wird.

*e*<br/>
Verweist auf die Ausnahme, die ausgelöst wurde. NULL kann sein.

*bSaving*<br/>
Flag zum angeben, welcher Vorgang ausgeführt wurde; ungleich NULL, wenn das Dokument wurde gespeichert, 0, wenn das Dokument geladen wird, wurde.

*nIDPDefault*<br/>
Bezeichner, der die Fehlermeldung, die angezeigt werden, wenn die Funktion keine eine spezifischere angibt.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung des Ausnahmeobjekts untersucht und sucht nach eine Fehlermeldung angezeigt, die speziell auf die Fehlerursache beschreibt. Wenn eine bestimmte Nachricht nicht gefunden wird oder wenn *e* NULL ist, die allgemein von angegebene Nachricht die *nIDPDefault* Parameter wird verwendet. Die Funktion zeigt ein Meldungsfeld mit der Fehlermeldung. Überschreiben Sie diese Funktion, wenn Sie zusätzliche, benutzerdefinierte Fehlermeldungen bereitstellen möchten. Dies ist ein fortschrittlicher überschreibbar.

##  <a name="savemodified"></a>  SaveModified

Vom Framework aufgerufen, bevor ein modifiziertes Dokument geschlossen wird.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist dies sicher, um fortzufahren, und schließen Sie das Dokument; 0, wenn das Dokument nicht geschlossen werden soll.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung dieser Funktion zeigt ein Meldungsfeld der Benutzer gefragt wird, ob zum Speichern der Änderungen auf das Dokument, wenn alle vorgenommen wurden. Überschreiben Sie diese Funktion, wenn das Programm eine andere aufgefordert wird Prozedur erfordert. Dies ist ein fortschrittlicher überschreibbar.

##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue

Legt einen Block-Wert.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Gibt einen Block-Wert festlegen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag

Rufen Sie diese Funktion, nachdem Sie Änderungen an das Dokument vorgenommen haben.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parameter

*bModified*<br/>
Flag zum angeben, ob das Dokument geändert wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion durchgängig aufzurufen, stellen Sie sicher, dass das Framework der Benutzer Änderungen speichern, bevor ein Dokument schließen kann. In der Regel sollten Sie den Standardwert für "true" Verwenden der *bModified* Parameter. Rufen Sie diese Funktion mit dem Wert "false", um ein Dokument wie bereinigen (unverändert) zu markieren.

##  <a name="setpathname"></a>  CDocument::SetPathName

Rufen Sie diese Funktion, um den vollqualifizierten Pfad der Datenträger-Datei des Dokuments angeben.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Verweist auf die Zeichenfolge, die als Pfad für das Dokument verwendet werden.

*bAddToMRU*<br/>
Bestimmt, ob der Dateinamen hinzugefügt wird am häufigsten vor kurzem Dateiliste (MRU) verwendet. True gibt an, der Dateiname wird hinzugefügt. False gibt an, wird er nicht hinzugefügt.

### <a name="remarks"></a>Hinweise

Abhängig vom Wert *bAddToMRU* der Pfad hinzugefügt wird oder nicht hinzugefügt werden, zu der MRU-Liste, die von der Anwendung verwaltet. Beachten Sie, dass einige Dokumente keiner Datei auf einem Datenträger zugeordnet sind. Rufen Sie diese Funktion nur, wenn Sie die standardmäßige Implementierung für das Öffnen und Speichern von Dateien, die vom Framework verwendete überschreiben.

##  <a name="settitle"></a>  CDocument::SetTitle

Mit dieser Funktion können Geben Sie den Titel des Dokuments (die Zeichenfolge, die in der Titelleiste eines Fensters Frame angezeigt).

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parameter

*lpszTitle*<br/>
Verweist auf die Zeichenfolge, die als Titel des Dokuments verwendet werden.

### <a name="remarks"></a>Hinweise

Das Aufrufen dieser Funktion aktualisiert die Titel aller Frame-Fenster, in denen das Dokument angezeigt.

##  <a name="updateallviews"></a>  UpdateAllViews

Rufen Sie diese Funktion aus, nachdem das Dokument geändert wurde.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Parameter

*pSender*<br/>
Verweist auf die Ansicht, die das Dokument, geändert oder NULL, wenn alle Ansichten werden aktualisiert werden.

*lHint*<br/>
Enthält Informationen über die Änderung.

*pHint*<br/>
Verweist auf ein Objekt, das Informationen über die Änderung zu speichern.

### <a name="remarks"></a>Hinweise

Sie sollten diese Funktion aufrufen, nach dem Aufrufen der [SetModifiedFlag](#setmodifiedflag) Member-Funktion. Diese Funktion informiert jede Ansicht, die an das Dokument, mit Ausnahme der Ansicht anhand des angefügten *pSender*, die das Dokument geändert wurde. Sie rufen in der Regel dieser Funktion aus Ihrer Ansichtsklasse, nachdem der Benutzer das Dokument über eine Sicht geändert hat.

Diese Funktion ruft die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Memberfunktion für jede der Ansichten mit Ausnahme von das Senden des Dokuments anzuzeigen, übergeben *pHint* und *lHint*. Verwenden Sie diese Parameter, um Informationen zu den Ansichten zu Änderungen an das Dokument zu übergeben. Können Sie mit codieren *lHint* und/oder können Sie definieren eine [CObject](../../mfc/reference/cobject-class.md)-abgeleitete Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt dieser Klasse mit *pHint*. Überschreiben der `CView::OnUpdate` Member-Funktion in Ihrer [CView](../../mfc/reference/cview-class.md)-abgeleitete Klasse, um die Aktualisierung von der Ansicht angezeigt, die basierend auf der übergebenen Informationen zu optimieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)
