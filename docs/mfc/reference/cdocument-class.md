---
title: CDocument-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6cfe4dc779fb4ad50f2171ef8811785f48275a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdocument-class"></a>CDocument-Klasse
Stellt die grundlegende Funktionalität für benutzerdefinierte Dokumentklassen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|Erstellt ein `CDocument`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument:: AddView](#addview)|Fügt eine Sicht auf das Dokument an.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|Initialisiert in Blöcken lesen.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Erweiterte überschreibbare; wird aufgerufen, vor dem Schließen eines Rahmenfensters dieses Dokument anzeigen.|  
|[CDocument::ClearChunkList](#clearchunklist)|Löscht die Liste der Block.|  
|[CDocument::ClearPathName](#clearpathname)|Löscht den Pfad der Document-Objekt.|  
|[CDocument::DeleteContents](#deletecontents)|Wird aufgerufen, um die Bereinigung des Dokuments durchführen.|  
|[CDocument::FindChunk](#findchunk)|Sucht ein Block mit der angegebenen GUID.|  
|[CDocument::GetAdapter](#getadapter)|Gibt einen Zeiger auf das Objekt, durch `IDocument` Schnittstelle.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Gibt einen Zeiger zur Dokumentvorlage, die den Typ des Dokuments beschreibt.|  
|[CDocument::GetFile](#getfile)|Gibt einen Zeiger auf die gewünschte `CFile` Objekt.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Gibt die Position des ersten in der Liste der Sichten; verwendet, um die Iteration starten.|  
|[CDocument::GetNextView](#getnextview)|Durchläuft die Liste der Ansichten, die dem Dokument zugeordnet.|  
|[CDocument::GetPathName](#getpathname)|Gibt den Pfad des Dokuments-Datendatei.|  
|[CDocument::GetThumbnail](#getthumbnail)|Wird aufgerufen, um eine Bitmap von Miniaturansichten Anbieter verwendet werden, zum Anzeigen der Miniaturansicht zu erstellen.|  
|[CDocument::GetTitle](#gettitle)|Gibt den Titel des Dokuments zurück.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Wird aufgerufen, um Inhalte durchsuchen für Suche Handler zu initialisieren.|  
|[CDocument::IsModified](#ismodified)|Gibt an, ob das Dokument seit der letzten Speicherung geändert wurde.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Informiert, ob diese Instanz von `CDocument` Objekt zu suchen und Organisieren Handler erstellt wurde.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Wird aufgerufen, um die Dokumentdaten aus Stream laden.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Wird aufgerufen, bevor Rich Preview Schriftart geändert wird.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Wird aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Wird aufgerufen, um das Dokument zu schließen.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Vom Framework aufgerufen, wenn sie einen Frame Preview for Rich Preview erstellen muss.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Wird aufgerufen, durch das Framework in Reaktion auf ein Dokumentereignis.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Überschreiben Sie diese Methode in einer abgeleiteten Klasse Inhalt der Miniaturansicht gezeichnet werden soll.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Vom Framework aufgerufen, wenn die Daten aus Stream geladen werden müssen.|  
|[CDocument::OnNewDocument](#onnewdocument)|Wird aufgerufen, um ein neues Dokument erstellen.|  
|[Funktionen](#onopendocument)|Wird aufgerufen, um ein vorhandenes Dokument zu öffnen.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Weist den Preview-Handler, der das HWND des Aufrufs der Funktion GetFocus zurückgeben.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Weist den Vorschauhandler behandelt eine Tastenkombination, die nach oben übergeben wird, aus dem Nachrichtensystem des Prozesses, in dem der Preview-Handler ausgeführt wird.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Wird aufgerufen, wenn umfangreiche Vorschau Background-Farbe geändert hat.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Wird aufgerufen, wenn umfangreiche Vorschau Schriftart geändert hat.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Wird aufgerufen, wenn Rich Preview-Standort geändert hat.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Wird aufgerufen, wenn umfangreiche Vorschau Textfarbe geändert hat.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Wird aufgerufen, um das Dokument auf den Datenträger zu speichern.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Vom Framework aufgerufen, wenn der Handler Preview entladen wird.|  
|[CDocument::PreCloseFrame](#precloseframe)|Wird aufgerufen, bevor das Rahmenfenster geschlossen wird.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Liest die nächsten Block-Wert.|  
|[CDocument::ReleaseFile](#releasefile)|Gibt eine Datei aus, um ihn von anderen Anwendungen für die Verwendung verfügbar zu machen.|  
|[CDocument::RemoveChunk](#removechunk)|Entfernt ein Block mit der angegebenen GUID.|  
|[CDocument::RemoveView](#removeview)|Trennt eine Sicht aus dem Dokument.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Erweiterte überschreibbare; wird aufgerufen, wenn ein offenes oder Speichervorgang kann nicht aufgrund einer Ausnahme abgeschlossen werden.|  
|[SaveModified](#savemodified)|Erweiterte überschreibbare; wird aufgerufen, um den Benutzer auffordern, gibt an, ob das Dokument gespeichert werden soll.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Legt einen Block-Wert.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Setzt ein Flag gibt an, dass Sie das Dokument geändert haben, seit es zuletzt gespeichert wurde.|  
|[CDocument::SetPathName](#setpathname)|Legt den Pfad der Datendatei verwendet, die für das Dokument fest.|  
|[CDocument::SetTitle](#settitle)|Legt den Titel des Dokuments.|  
|[UpdateAllViews](#updateallviews)|Benachrichtigt alle Ansichten das Dokument geändert wurde.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument:: OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|  
|[CDocument:: OnUpdateFileSendMail](#onupdatefilesendmail)|Können den Befehl E-Mail senden, wenn e-Mail-Unterstützung vorhanden ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Gibt an, dass `CDocument` Objekt durch Dllhost für Miniaturansichten erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Gibt an, dass `CDocument` -Objekt wurde erstellt, indem Prevhost für `Rich Preview`. Sollte aktiviert sein, `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Gibt an, dass `CDocument` Objekt erstellt wurde, durch den Indexer oder eine andere Suchanwendung.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Gibt die Hintergrundfarbe des Fensters Rich Preview. Diese Farbe wird vom Host festgelegt.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Gibt die Vordergrundfarbe von Rich-Vorschaufenster. Diese Farbe wird vom Host festgelegt.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Gibt für Rich-Vorschaufenster Schriftart an. Diese Schriftartinformationen wird vom Host festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Dokument stellt die Dateneinheit, die der Benutzer in der Regel mit dem Befehl Datei öffnen wird geöffnet und mit dem Befehl Speichern speichert.  
  
 **CDocument** unterstützt Standardvorgänge wie z. B. ein Dokument zu erstellen, laden und speichern. Das Framework bearbeitet, Dokumente, die mithilfe der Benutzeroberfläche von definierten **CDocument**.  
  
 Eine Anwendung kann mehr als einen Typ von Dokument unterstützen; eine Anwendung könnte z. B. Kalkulationstabellen und Textdokumente unterstützen. Jeder Typ von Dokument verfügt über eine zugeordnete Dokumentvorlage; die Dokumentvorlage gibt an, welche Ressourcen (z. B. Menüs, Symbol oder Accelerator-Tabelle) für diesen Dokumenttyp verwendet werden. Jedes Dokument enthält einen Zeiger auf die zugehörigen `CDocTemplate` Objekt.  
  
 Benutzer interagieren mit einem Dokument über die [CView](../../mfc/reference/cview-class.md) Objekte zugeordnet. Eine Ansicht rendert ein Bild des Dokuments in einem Rahmenfenster und Benutzereingaben als Vorgänge des Dokuments interpretiert. Ein Dokument kann mehrere Ansichten zugeordnet haben. Wenn der Benutzer ein Fenster für ein Dokument öffnet, wird das Framework eine Sicht erstellt, und fügt ihn in das Dokument. Die Dokumentvorlage gibt an, welche Art von Ansicht- und Frame-Fensters werden verwendet, um jeden Typ von Dokument anzuzeigen.  
  
 Dokumente sind Teil der Framework-Standards Befehl routing und daher empfangen von Befehlen aus standardmäßigen Benutzeroberflächen-Komponenten (z. B. das Menüelement Datei zu speichern). Ein Dokument empfängt, Befehle, die von der aktiven Ansicht weitergeleitet wird. Wenn das Dokument keinen bestimmten Befehl behandelt, wird der Befehl aus, um das Dokumentvorlage, die er verwaltet weitergeleitet.  
  
 Wenn die Daten eines Dokuments geändert werden, muss jedes der zugehörigen Ansichten diese Änderungen widerspiegeln. **CDocument** bietet die [UpdateAllViews](#updateallviews) Memberfunktion für die Sie die Ansichten der solche Änderungen benachrichtigen, damit die Ansichten selbst nach Bedarf neu gezeichnet werden können. Das Framework auch der Benutzer aufgefordert, eine geänderte Datei vor dem Schließen zu speichern.  
  
 Um Dokumente in einer typischen Anwendung zu implementieren, müssen Sie Folgendes ausführen:  
  
-   Leiten Sie eine Klasse von **CDocument** für jeden Typ des Dokuments.  
  
-   Hinzufügen von Membervariablen zum Speichern von Daten für jedes Dokument.  
  
-   Memberfunktionen für das Lesen und Ändern von Daten für das Dokument zu implementieren. Die Ansichten des Dokuments sind die wichtigsten Benutzer diese Memberfunktionen.  
  
-   Überschreiben Sie die [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) Memberfunktion in der Dokumentklasse, die Daten des Dokuments zum und vom Datenträger gelesen und geschrieben.  
  
 **CDocument** unterstützt das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Weitere Informationen zu **CDocument**, finden Sie unter [Serialisierung](../../mfc/serialization-in-mfc.md), [Dokument-/Ansichtarchitektur-Cloudarchitektur – Themen](../../mfc/document-view-architecture.md), und [Dokument-/Ansichtarchitektur Erstellung](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="addview"></a>CDocument:: AddView  
 Rufen Sie diese Funktion, um eine Sicht auf das Dokument anfügen.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Verweist auf die Ansicht hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion fügt die angegebene Ansicht der Liste der Ansichten, die dem Dokument zugeordnet; die Funktion setzt auch die Sicht Dokument Zeiger zu diesem Dokument. Das Framework ruft diese Funktion auf, wenn ein neu erstelltes Objekt zu einem Dokument anfügen; Dieser Fehler tritt in der Antwort auf eine neue Datei, neues Fenster oder Datei öffnen-Befehl oder wenn ein unterteiltes Fenster aufgeteilt wird.  
  
 Rufen Sie diese Funktion nur, wenn Sie manuell erstellen und Anfügen eine Ansicht. In der Regel können Sie das Framework Verbinden von Dokumenten und Ansichten durch Definieren einer [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt zuordnen einer Dokumentklasse Ansichtsklasse und Rahmenfenster (Klasse).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 Initialisiert in Blöcken lesen.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cancloseframe"></a>CDocument::CanCloseFrame  
 Vom Framework aufgerufen, bevor ein Rahmenfensters anzeigen das Dokument geschlossen wird.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Verweist auf das Rahmenfenster einer Sicht mit dem Dokument verknüpft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sicher ist, schließen Sie das Rahmenfenster ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird überprüft, ob es andere Rahmenfenster gibt, Dokument anzeigen. Wenn das angegebene Rahmenfenster zum letzten Blatt, die das Dokument anzeigt wird, fordert die Funktion den Benutzer das Dokument zu speichern, wenn er geändert wurde. Überschreiben Sie diese Funktion, wenn Sie besondere Bearbeitung beim Schließen eines Rahmenfensters ausführen möchten. Dies ist eine erweiterte überschrieben.  
  
##  <a name="cdocument"></a>CDocument::CDocument  
 Erstellt eine **CDocument** Objekt.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verarbeitet Erstellen eines Dokuments für Sie. Überschreiben Sie die [OnNewDocument](#onnewdocument) Memberfunktion für die Initialisierung auf einer pro-Dokument-Basis; Dies ist besonders wichtig in einzelnen Document Interface (SDI) Anwendungen.  
  
##  <a name="clearchunklist"></a>CDocument::ClearChunkList  
 Löscht die Liste der Block.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clearpathname"></a>CDocument::ClearPathName  
 Löscht den Pfad der Document-Objekt.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Hinweise  
 Deaktivieren den Pfad aus einem `CDocument` Objekt führt dazu, dass die Anwendung aus, um den Benutzer aufzufordern, wenn das Dokument als Nächstes gespeichert wird. Dadurch wird eine **speichern** Befehl verhält sich wie ein **speichern unter** Befehl.  
  
##  <a name="deletecontents"></a>CDocument::DeleteContents  
 Wird aufgerufen, durch das Framework So löschen Sie die Daten des Dokuments ohne Sie zu zerstören der **CDocument** Objekt selbst.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie wird aufgerufen, kurz bevor das Dokument ist, zerstört werden. Sie wird auch aufgerufen, um sicherzustellen, dass ein Dokument leer ist, bevor er wiederverwendet wird. Dies ist besonders wichtig für eine SDI-Anwendung, die nur in einem Dokument verwendet. das Dokument wird wiederverwendet, wenn der Benutzer erstellt oder ein anderes Dokument öffnet. Mit dieser Funktion wird zum Implementieren einer "Bearbeiten Alle löschen" oder ähnlichen Befehl, mit dem alle Daten für das Dokument gelöscht. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um die Daten in Ihrem Dokument zu löschen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="findchunk"></a>CDocument::FindChunk  
 Sucht ein Block mit einer angegebenen GUID.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parameter  
 `guid`  
 Gibt die GUID der ein Segment zu suchen.  
  
 `pid`  
 Gibt eine PID von einem Block gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Position in der Liste interner Block, wenn erfolgreich. Andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getadapter"></a>CDocument::GetAdapter  
 Gibt einen Zeiger auf ein Objekt, durch die `IDocument` Schnittstelle.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Objekt, durch die `IDocument` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 Mit dieser Funktion wird zum Abrufen eines Zeigers an das Dokumentvorlage für diesen Dokumenttyp.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokumentvorlage für diesen Dokumenttyp oder **NULL** , wenn das Dokument nicht von einem Dokumentvorlage verwaltet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="getfile"></a>CDocument::GetFile  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf ein `CFile` Objekt.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Eine Zeichenfolge, die den Pfad zu der gewünschten Datei ist. Der Pfad kann relativ oder absolut sein.  
  
 `pError`  
 Ein Zeiger auf eine vorhandene Datei-Ausnahme-Objekt, das den Abschlussstatus des Vorgangs angibt.  
  
 `nOpenFlags`  
 Freigabe und Zugriffsmodus. Gibt die zu ergreifende Maßnahme beim Öffnen der Datei an. Sie können die Optionen aufgeführt, die im Konstruktor CFile kombinieren [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) mit den bitweisen OR-Operator (&#124;) Operator. Eine Access-Berechtigung und eine Freigabe Option sind erforderlich. die **ModeCreate** und **ModeNoInherit** Modi sind optional.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CFile` Objekt.  
  
##  <a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 Mit dieser Funktion wird zum Abrufen der Position der ersten Ansicht in der Liste der Ansichten, die dem Dokument zugeordnet.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration mit verwendet werden, kann die [GetNextView](#getnextview) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getnextview"></a>CDocument::GetNextView  
 Mit dieser Funktion wird zum Durchlaufen aller Ansichten des Dokuments.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Ein Verweis auf eine **POSITION** durch einen vorherigen Aufruf zurückgegebene Wert den `GetNextView` oder [Sie GetFirstViewPosition](#getfirstviewposition) Memberfunktionen. Dieser Wert darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Sicht identifizierten `rPosition`.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt die Sicht identifizierten `rPosition` und legt dann `rPosition` auf die **POSITION** Wert des nächsten Ansicht in der Liste. Wenn die abgerufenen Ansicht der letzte in der Liste aus, klicken Sie dann `rPosition` festgelegt ist, um **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getpathname"></a>CDocument::GetPathName  
 Mit dieser Funktion wird zum Abrufen des vollqualifizierten Pfads für Datenträgerdatei für das Dokument.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Dokument den vollqualifizierten Pfad. Diese Zeichenfolge ist leer, wenn das Dokument nicht gespeichert wurde oder verfügt nicht über eine Datenträgerdatei zugeordnet.  
  
##  <a name="getthumbnail"></a>CDocument::GetThumbnail  
 Erstellt eine Bitmap, die von der Miniaturansicht-Anbieter verwendet werden, um die Miniaturansicht anzuzeigen.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Gibt die Breite und Höhe der Bitmap an.  
  
 `phbmp`  
 Enthält ein Handle für ein Bitmuster an, wenn die Funktion erfolgreich ausgeführt wurde.  
  
 `pdwAlpha`  
 Enthält einen DWORD-Wert, der den alpha-Kanal-Wert angeben, wenn die Funktion erfolgreich ausgeführt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` eine Bitmap für die Miniaturansicht erstellt wurde, konnte, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettitle"></a>CDocument::GetTitle  
 Mit dieser Funktion wird der Titel eines Dokuments, abrufen, die dem Dateinamen des Dokuments in der Regel abgeleitet ist.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel eines Dokuments.  
  
##  <a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 Wird aufgerufen, um Inhalte durchsuchen für die Suche Handler zu initialisieren.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um Inhalte durchsuchen zu initialisieren. Der Inhalt muss eine Zeichenfolge mit Teile, getrennt durch ";". Z. B. "zeigen. Rechteck; OLE-Element".  
  
##  <a name="ismodified"></a>CDocument::IsModified  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument seit der letzten Speicherung geändert wurde.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Dokument seit der letzten Speicherung geändert wurde; andernfalls 0.  
  
##  <a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 Informiert, ob diese Instanz von `CDocument` zu suchen und Organisieren-Ereignishandler erstellt wurde.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` Wenn diese Instanz von `CDocument` zu suchen und Organisieren-Ereignishandler erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zurzeit zurück `TRUE` nur für Rich Preview-Handler, die in einer Out-of Process-Server implementiert. Sie können den geeigneten Flags (M_bPreviewHandlerMode, M_bSearchMode, M_bGetThumbnailMode) festlegen, auf der Anwendungsebene vornehmen dieser Funktion `TRUE`.  
  
##  <a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 Wird aufgerufen, um das Laden von Daten aus einem Stream.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf einen Stream. In diesem Datenstrom wird von der Shell bereitgestellt.  
  
 `dwGrfMode`  
 Der Zugriffsmodus in den Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Ladevorgang erfolgreich ist, andernfalls HRESULT mit einem Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse zum Laden von Daten aus dem Stream anpassen überschreiben.  
  
##  <a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 Gibt an, dass die `CDocument` Objekt durch Dllhost für Miniaturansichten erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument vom Dllhost für Miniaturansichten erstellt wurde.  
  
##  <a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 Gibt an, dass die `CDocument` Objekt durch Prevhost for Rich Preview erstellt wurde. Sollte aktiviert sein, `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument durch Prevhost for Rich Preview erstellt wurde.  
  
##  <a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 Gibt an, dass die `CDocument` Objekt erstellt wurde, Indexer oder von einer anderen Anwendung der Suche.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass das Dokument durch Indexer oder eine andere Suche Anwendung erstellt wurde.  
  
##  <a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 Gibt die Hintergrundfarbe des Fensters Rich Preview. Diese Farbe wird vom Host festgelegt.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 Gibt die Vordergrundfarbe des Fensters Rich Preview. Diese Farbe wird vom Host festgelegt.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 Gibt die Schriftart für das Vorschaufenster Rich Text an. Diese Schriftartinformationen wird vom Host festgelegt.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 Wird aufgerufen, bevor die Rich Preview Schriftart geändert wird.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 Vom Framework aufgerufen, nachdem eine Sicht hinzugefügt oder aus dem Dokument entfernt.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion überprüft, ob die letzte Ansicht entfernt wird, und wenn dies der Fall ist, das Dokument löscht. Überschreiben Sie diese Funktion, wenn Sie besondere Bearbeitung, wenn das Framework hinzufügt oder eine Sicht entfernt ausführen möchten. Überschreiben Sie diese Funktion z. B. wenn ein Dokument geöffnet bleiben, selbst wenn es keine Sichten, die angefügt sind werden sollen.  
  
##  <a name="onclosedocument"></a>CDocument::OnCloseDocument  
 Vom Framework aufgerufen, wenn das Dokument, in der Regel als Teil des Befehls Schließen von Dateien geschlossen wird.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion zerstört alle Frames, zum Anzeigen des Dokuments verwendet, schließt die Ansicht, den Inhalt des Dokuments bereinigt und ruft dann die [DeleteContents](#deletecontents) Memberfunktion zum Löschen des Dokuments Daten.  
  
 Überschreiben Sie diese Funktion, wenn Sie möchten Verarbeitungsschritte spezielle Bereinigung ausführen, wenn das Framework ein Dokument geschlossen wird. Wenn das Dokument einen Datensatz in einer Datenbank darstellt, sollten Sie dieser Funktion können Sie die Datenbank schließen, außer Kraft setzen. Sie sollten die Basisklassenversion dieser Funktion aus der Außerkraftsetzung aufrufen.  
  
##  <a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 Vom Framework aufgerufen, wenn sie einen Frame Preview for Rich Preview erstellen muss.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn der Frame, konnte, andernfalls erstellt wird `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 Wird aufgerufen, durch das Framework in Reaktion auf ein Dokumentereignis.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `deEvent`  
 Enumerierten Datentyps, der den Typ des Ereignisses beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Dokumentereignisse können mehrere Klassen auswirken. Diese Methode ist verantwortlich für die Behandlung von Ereignissen, die Klassen außer Auswirkungen auf die [CDocument-Klasse](../../mfc/reference/cdocument-class.md). Derzeit die einzige Klasse, die auf Dokumentereignisse reagieren muss, ist die [CDataRecoveryHandler Klasse](../../mfc/reference/cdatarecoveryhandler-class.md). Die `CDocument` -Klasse verfügt über andere überschreibbare Methoden, die verantwortlich für die Behandlung der Auswirkung auf die `CDocument`.  
  
 Die folgende Tabelle enthält die möglichen Werte für `deEvent` und die Ereignisse, die diese entsprechen.  
  
|Wert|Entsprechende Ereignis|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Es wurde ein neues Dokument erstellt.|  
|`onAfterOpenDocument`|Ein neues Dokument geöffnet wurde.|  
|`onAfterSaveDocument`|Das Dokument wurde gespeichert.|  
|`onAfterCloseDocument`|Das Dokument wurde geschlossen.|  
  
##  <a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Miniaturansicht gezeichnet werden soll.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Ein Verweis zu einem Gerätekontext.  
  
 `lprcBounds`  
 Gibt ein umschließendes Rechteck des Bereichs, in dem die Miniaturansicht gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfilesendmail"></a>CDocument:: OnFileSendMail  
 Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnFileSendMail`Aufrufe [OnSaveDocument](#onsavedocument) (Speichern) neue und geänderte Dokumente in eine temporäre Datei zu serialisieren, die dann per e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei nicht erforderlich. die ursprüngliche wird gesendet. `OnFileSendMail`Lädt MAPI32. DLL, wenn er nicht bereits geladen wurde.  
  
 Eine spezielle Implementierung der `OnFileSendMail` für [COleDocument](../../mfc/reference/coledocument-class.md) Verbunddateien ordnungsgemäß behandelt.  
  
 **CDocument** unterstützt das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 Vom Framework aufgerufen, wenn die Daten aus einem Stream geladen werden müssen.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf einen eingehenden Datenstrom.  
  
 `grfMode`  
 Der Zugriffsmodus in den Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn das Laden erfolgreich ist; andernfalls ein Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onnewdocument"></a>CDocument::OnNewDocument  
 Vom Framework als Teil der Datei neue Befehl aufgerufen wird.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion die [DeleteContents](#deletecontents) Member-Funktion, um sicherzustellen, dass das Dokument leer ist, und klicken Sie dann das neue Dokument als sauber markiert. Überschreiben Sie diese Funktion, um die Datenstruktur für ein neues Dokument zu initialisieren. Sie sollten die Basisklassenversion dieser Funktion aus der Außerkraftsetzung aufrufen.  
  
 Wenn der Benutzer die Datei neuen Befehl in einer SDI-Anwendung auswählt, verwendet das Framework diese Funktion zum erneuten Initialisieren zum vorhandenen Dokument, anstatt ein neues zu erstellen. Wenn der Benutzer in einer Anwendung der multiple Document Interface (MDI) neue Datei auswählt, wird das Framework erstellt ein neues Dokument jedes Mal, und ruft dann diese Funktion, um sie zu initialisieren. Sie müssen diese Funktion statt des im Konstruktor für die neue Datei Befehl funktioniert im SDI-Anwendungen den Initialisierungscode versehen.  
  
 Beachten Sie, dass es Fälle, in denen `OnNewDocument` wird zweimal aufgerufen. Dies tritt auf, wenn das Dokument als ActiveX-Dokument eingebettet ist. Die Funktion zuerst aufgerufen wird der `CreateInstance` Methode (verfügbar gemacht werden, indem Sie die `COleObjectFactory`-abgeleitete Klasse) und ein zweites Mal von der `InitNew` Methode (verfügbar gemacht werden, indem Sie die `COleServerDoc`-abgeleitete Klasse).  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren der Document-Objekt.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="onopendocument"></a>Funktionen  
 Vom Framework als Teil der Datei öffnen-Befehl aufgerufen wird.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den Pfad des Dokuments geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion die angegebene Datei geöffnet, Aufrufe der [DeleteContents](#deletecontents) Member-Funktion, um sicherzustellen, dass das Dokument leer ist, ruft [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) zum Lesen der Datei Inhalt, und klicken Sie dann das Dokument als sauber markiert. Überschreiben Sie diese Funktion, wenn Sie ein Element als der Mechanismus Archiv oder der Datei-Mechanismus verwenden möchten. Beispielsweise können Sie eine Anwendung schreiben, in denen Darstellung von Dokumenten auf Datensätze in einer Datenbank statt in separaten Dateien.  
  
 Wenn der Benutzer die Datei öffnen-Befehl in einer SDI-Anwendung auswählt, verwendet das Framework diese Funktion zum erneuten Initialisieren der vorhandenen **CDocument** -Objekt, anstatt ein neues zu erstellen. Wenn der Benutzer in einer MDI-Anwendung geöffneten Datei auswählt, erstellt das Framework ein neues **CDocument** Objekt jedes Mal ein und ruft dann diese Funktion, um sie zu initialisieren. Sie müssen diese Funktion statt des im Konstruktor für die Datei öffnen Befehl funktioniert im SDI-Anwendungen den Initialisierungscode versehen.  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen die alternative Methoden zum Initialisieren der Document-Objekt.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 Weist den Preview-Handler zurückgegeben, das HWND abgerufen wird, durch den Aufruf der `GetFocus` Funktion.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Parameter  
 `phwnd`  
 [out] Bei der Rückgabe dieser Methode enthält einen Zeiger auf das vom Aufruf zurückgegebene HWND die `GetFocus` Funktion der Preview-Handler Vordergrundthread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK, wenn erfolgreich; oder einen Fehlerwert andernfalls.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 Weist den Vorschauhandler behandelt eine Tastenkombination, die nach oben übergeben wird, aus dem Nachrichtensystem des Prozesses, in dem der Preview-Handler ausgeführt wird.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pmsg`  
 [in] Ein Zeiger auf eine fenstermeldung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Tastatureingabe-Nachricht von der Preview-Handler verarbeitet werden kann, wird der Handler verarbeitet, und gibt S_OK zurück. Wenn der Preview-Handler die Tastatureingabe Nachricht verarbeiten kann, bietet es an dem Host über `IPreviewHandlerFrame::TranslateAccelerator`. Wenn der Host die Nachricht verarbeitet hat, gibt diese Methode S_OK zurück. Wenn der Host die Nachricht nicht verarbeitet werden, gibt diese Methode "S_FALSE" zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 Wird aufgerufen, wenn die Hintergrundfarbe Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 Wird aufgerufen, wenn die Schriftart Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 Wird aufgerufen, wenn die Rich Preview-Standort geändert hat.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 Wird aufgerufen, wenn die Textfarbe Rich Preview geändert hat.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsavedocument"></a>CDocument::OnSaveDocument  
 Vom Framework als Teil des Befehls Datei speichern oder Datei speichern unter aufgerufen.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den vollqualifizierten Pfad zu dem die Datei gespeichert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich gespeichert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion die angegebene Datei geöffnet, Aufrufe [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) Dokumentdaten zum Schreiben der Datei, und markiert das Dokument als bereinigen. Überschreiben Sie diese Funktion, wenn Sie besondere Verarbeitung, wenn das Framework ein Dokument speichert ausführen möchten. Beispielsweise können Sie eine Anwendung schreiben, in denen Darstellung von Dokumenten auf Datensätze in einer Datenbank statt in separaten Dateien.  
  
##  <a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 Vom Framework aufgerufen, wenn der Handler Preview entladen wird.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatefilesendmail"></a>CDocument:: OnUpdateFileSendMail  
 Ermöglicht die **ID_FILE_SEND_MAIL** -Befehl, wenn e-Mail-Unterstützung (MAPI) vorhanden ist.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) zugeordnete Objekt der **ID_FILE_SEND_MAIL** Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion andernfalls entfernt der **ID_FILE_SEND_MAIL** Befehl über das Menü, einschließlich der Trennzeichen oben oder unten im Menü Element nach Bedarf. MAPI wird aktiviert, wenn MAPI32. DLL ist in den Pfad und im Abschnitt [Mail] der WIN vorhanden. INI-Datei MAPI = 1. Die meisten Anwendungen werden mit diesem Befehl im Menü Datei abgelegt.  
  
 **CDocument** unterstützt das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. Finden Sie in den Artikeln [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="precloseframe"></a>CDocument::PreCloseFrame  
 Diese Memberfunktion wird vom Framework aufgerufen, bevor das Rahmenfenster zerstört wird.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrame`  
 Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) , enthält die zugeordnete **CDocument** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können überschrieben werden, um ein benutzerdefinierter Cleanup, nach Belieben Achten Sie darauf, dass Sie auch von der Basisklasse aufgerufen.  
  
 Die Standardeinstellung von `PreCloseFrame` nichts **CDocument**. Die **CDocument**-abgeleitete Klassen [COleDocument](../../mfc/reference/coledocument-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) verwenden Sie diese Memberfunktion auf.  
  
##  <a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 Liest den nächsten Block-Wert.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Parameter  
 `ppValue`  
 [out] Wenn die Funktion zurückgibt, `ppValue` enthält den Wert, der gelesen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="releasefile"></a>CDocument::ReleaseFile  
 Diese Memberfunktion wird vom Framework zum Freigeben einer Datei, die von einer anderen Anwendung für die Verwendung verfügbar machen aufgerufen.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf das CFile-Objekt, das freigegeben werden.  
  
 `bAbort`  
 Gibt an, ob die Datei freigegeben werden, indem Sie entweder `CFile::Close` oder `CFile::Abort`. **"False"** ist die Datei unter Verwendung freigegeben werden [CFile::Close](../../mfc/reference/cfile-class.md#close); **"True"** ist die Datei unter Verwendung freigegeben werden [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAbort` ist **"true"**, `ReleaseFile` Aufrufe `CFile::Abort`, und die Datei freigegeben ist. `CFile::Abort`wird keine Ausnahme auslöst.  
  
 Wenn `bAbort` ist **"false"**, `ReleaseFile` Aufrufe `CFile::Close` und die Datei freigegeben ist.  
  
 Überschreiben Sie diese Memberfunktion, um eine Aktion vom Benutzer erforderlich, bevor die Datei freigegeben ist.  
  
##  <a name="removechunk"></a>CDocument::RemoveChunk  
 Entfernt ein Block mit der angegebenen GUID.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parameter  
 `Guid`  
 Gibt die GUID des ein Segment entfernt werden soll.  
  
 `Pid`  
 Gibt an, die PID von einem beschädigten entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removeview"></a>CDocument::RemoveView  
 Mit dieser Funktion wird eine Sicht aus einem Dokument zu trennen.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Verweist auf die Ansicht entfernt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion entfernt die angegebene Ansicht aus der Liste der Ansichten, die dem Dokument zugeordnet; Zudem wird die Sicht Dokument Zeiger auf **NULL**. Diese Funktion wird vom Framework aufgerufen, wenn ein Framefenster geschlossen wird oder ein Bereich eines unterteilten Fensters geschlossen wird.  
  
 Rufen Sie diese Funktion nur, wenn Sie eine Ansicht manuell trennen sind. In der Regel können Sie das Framework Trennen von Dokumenten und Ansichten durch Definieren einer [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt zuordnen einer Dokumentklasse Ansichtsklasse und Rahmenfenster (Klasse).  
  
 Siehe das Beispiel [AddView](#addview) beispielimplementierung.  
  
##  <a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 Wird aufgerufen, wenn eine Ausnahme ausgelöst wird (in der Regel eine [CFileException](../../mfc/reference/cfileexception-class.md) oder [CArchiveException](../../mfc/reference/carchiveexception-class.md)) beim Speichern oder Laden des Dokuments.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf den Namen des Dokuments, das wurde gespeichert oder geladen wird.  
  
 *e*  
 Verweist auf die ausgelöste Ausnahme. Möglicherweise **NULL**.  
  
 *bSaving*  
 Flag, der angibt, welcher Vorgang ausgeführt wurde; ungleich NULL, wenn das Dokument wurde gespeichert, 0, wenn beim Laden des Dokuments.  
  
 `nIDPDefault`  
 Bezeichner, der die Fehlermeldung, die angezeigt werden, wenn die Funktion keine eine spezifischere angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung untersucht das Ausnahmeobjekt und sucht nach einer Fehlermeldung, die die Ursache im Detail beschreibt. Wenn eine bestimmte Nachricht nicht gefunden wird oder wenn *e* ist **NULL**, die allgemein von angegebene Nachricht die `nIDPDefault` Parameter wird verwendet. Die Funktion zeigt ein Meldungsfeld mit der Fehlermeldung. Überschreiben Sie diese Funktion, wenn Sie zusätzliche, benutzerdefinierte Fehlermeldungen bereitstellen möchten. Dies ist eine erweiterte überschrieben.  
  
##  <a name="savemodified"></a>SaveModified  
 Vom Framework aufgerufen, bevor ein geändertes Dokument wird geschlossen.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sich um den Vorgang fortzusetzen, und schließen Sie das Dokument sicher handelt; 0, wenn das Dokument nicht geschlossen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion zeigt ein Meldungsfeld mit der Benutzer aufgefordert, ob die Änderungen auf das Dokument zu speichern, wenn alle vorgenommen wurden. Überschreiben Sie diese Funktion, wenn das Programm eine andere aufforderungsstufe Prozedur erforderlich ist. Dies ist eine erweiterte überschrieben.  
  
##  <a name="setchunkvalue"></a>CDocument::SetChunkValue  
 Legt einen Block-Wert.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parameter  
 `pValue`  
 Gibt einen Block-Wert festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 Rufen Sie diese Funktion, nachdem Sie das Dokument keine Änderungen vorgenommen haben.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Ein Flag, der angibt, ob das Dokument geändert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Durch das Aufrufen dieser Funktion einheitlich, stellen Sie sicher, dass das Framework den Benutzer um Änderungen zu speichern, bevor Sie ein Dokument schließen auffordert. In der Regel sollten Sie den Standardwert verwenden **"true"** für die `bModified` Parameter. Um ein Dokument wie bereinigen (unverändert) kennzeichnen, rufen Sie diese Funktion mit einem Wert von **"false"**.  
  
##  <a name="setpathname"></a>CDocument::SetPathName  
 Mit dieser Funktion wird zum Angeben des vollqualifizierten Pfads der Datenträgerdatei für das Dokument.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Verweist auf die Zeichenfolge, die als Pfad für das Dokument verwendet werden.  
  
 `bAddToMRU`  
 Bestimmt, ob der Dateiname hinzugefügt wird der zuletzt verwendeten Dateiliste (MRU) verwendete. Wenn **"true"** der Dateiname hinzugefügt; Wenn **"false"**, wird er nicht hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig vom Wert der `bAddToMRU` der Pfad hinzugefügt wird, oder nicht hinzugefügt werden, um die Liste der zuletzt von der Anwendung verwaltet. Beachten Sie, dass einige Dokumente keine Datenträgerdatei zugeordnet sind. Rufen Sie diese Funktion nur, wenn Sie die standardmäßige Implementierung für das Öffnen und Speichern von Dateien, die vom Framework verwendete überschreiben.  
  
##  <a name="settitle"></a>CDocument::SetTitle  
 Mit dieser Funktion wird zum Angeben der Titel eines Dokuments (die Zeichenfolge, die in der Titelleiste Rand eines Rahmenfensters angezeigt).  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 Verweist auf die Zeichenfolge, die als Titel des Dokuments verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Funktion aktualisiert die Titel aller Rahmenfenster, in denen das Dokument angezeigt.  
  
##  <a name="updateallviews"></a>UpdateAllViews  
 Mit dieser Funktion werden, nachdem das Dokument geändert wurde.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Verweist auf die Sicht, die das Dokument geändert oder **NULL** Wenn alle Sichten aktualisiert werden.  
  
 `lHint`  
 Enthält Informationen über die Änderung.  
  
 `pHint`  
 Verweist auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten diese Funktion aufrufen, nach dem Aufruf der [SetModifiedFlag](#setmodifiedflag) Memberfunktion. Diese Funktion informiert, jede Sicht mit dem Dokument, mit Ausnahme von angegebene Ansicht verknüpft `pSender`, die das Dokument geändert wurde. Rufen Sie in der Regel diese Funktion von Ihrer Ansichtsklasse nachdem der Benutzer das Dokument über eine Sicht geändert wurde.  
  
 Diese Funktion ruft die [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) Memberfunktion für die einzelnen Ansichten mit Ausnahme der Versand des Dokuments anzuzeigen, das Übergeben von `pHint` und `lHint`. Verwenden Sie diese Parameter, um Informationen zu den Ansichten über die Änderungen an den das Dokument zu übergeben. Sie können Informationen mit codiert `lHint` und/oder können Sie definieren eine [CObject](../../mfc/reference/cobject-class.md)-abgeleitete Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt der Klasse verwenden `pHint`. Überschreiben der `CView::OnUpdate` Memberfunktion in Ihre [CView](../../mfc/reference/cview-class.md)-abgeleitete Klasse, um das Aktualisieren der Ansicht anzeigen, die anhand der Informationen übergeben zu optimieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel NPP](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)
