---
title: CDocTemplate-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
dev_langs:
- C++
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd7e80d3c01cf84080ba2b5851da99584122ec4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023942"
---
# <a name="cdoctemplate-class"></a>CDocTemplate-Klasse
Eine abstrakte Basisklasse, die die grundlegende Funktionalität für Dokumentvorlagen definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Erstellt ein `CDocTemplate`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|Ein Dokument hinzugefügt in eine Vorlage.|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Schließt alle Dokumente mit dieser Vorlage verknüpft ist.|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Erstellt ein neues Dokument.|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|Erstellt ein neues Rahmenfensterobjekt, enthält ein Dokument und Ansicht.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|Erstellt ein OLE-fähige Rahmenfenster.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Erstellt eine Child-Rahmen, die für die umfassende Vorschau verwendet.|  
|[CDocTemplate::GetDocString](#getdocstring)|Ruft eine Zeichenfolge, die mit dem Dokument verknüpft ist.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Ruft ein Dokument und die Position des nächsten ab.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Initialisiert das Rahmenfenster und optional macht es sichtbar.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Lädt die Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Bestimmt das Maß an Vertrauen der Übereinstimmung zwischen einem Dokument und diese Vorlage an.|  
|[CDocTemplate:: OpenDocumentFile](#opendocumentfile)|Öffnet eine Datei, die durch ein Pfadname angegeben.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Entfernt ein Dokument aus einer Vorlage.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Speichert alle Dokumente mit dieser Vorlage verknüpft die geändert wurden.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Bestimmt die Ressourcen für OLE-Container an, wenn ein OLE-Element für ein direktes Bearbeiten.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Zeigt den Standardtitel in der Titelleiste des Dokumentfensters an.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Installationen außerhalb des Prozesses Vorschau Handler.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Wenn das Serverdokument eingebettet ist, oder für ein direktes bearbeitet die Ressourcen und Klassen bestimmt werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Sie erstellen eine oder mehrere Dokumentvorlagen in der Regel in der Implementierung von Ihrer Anwendungsverzeichnis `InitInstance` Funktion. Eine Dokumentvorlage definiert die Beziehungen zwischen den drei Arten von Klassen:  
  
-   Eine Dokumentenklasse, die Sie von abgeleitet werden `CDocument`.  
  
-   Eine Ansichtsklasse, die Daten aus der Dokumentenklasse, die oben aufgeführten anzeigt. Sie können diese Klasse von ableiten `CView`, `CScrollView`, `CFormView`, oder `CEditView`. (Sie können auch `CEditView` direkt.)  
  
-   Ein Frame Fenster-Klasse, die die Sicht enthält. Für ein einzelnes Dokument Interface (SDI)-Anwendung, leiten Sie diese Klasse von `CFrameWnd`. Für eine Anwendung multiple Document Interface (MDI), leiten Sie diese Klasse von `CMDIChildWnd`. Wenn Sie nicht das Verhalten des Rahmenfensters anpassen müssen, können Sie `CFrameWnd` oder `CMDIChildWnd` direkt, ohne eine eigene Klasse ableiten.  
  
 Ihre Anwendung verfügt über eine Vorlage für Dokumente für jeden Typ von Dokument, das es unterstützt. Wenn Ihre Anwendung sowohl Tabellen als auch Text unterstützt, muss die Anwendung z. B. zwei Objekte der Dokument-Vorlage. Jede Dokumentvorlage dient zum Erstellen und verwalten alle Dokumente dieses Typs.  
  
 Die Dokumentvorlage speichert Zeiger zu der `CRuntimeClass` Objekte für das Dokument anzeigen und Klassen für Rahmenfenster. Diese `CRuntimeClass` Objekte werden angegeben, wenn Sie eine Dokumentvorlage erstellen.  
  
 Die Dokumentvorlage enthält, die ID der Ressourcen, die mit den Dokumenttyp (z. B. Menüs, Symbol oder tabellenressourcen Accelerator) verwendet wird. Die Dokumentvorlage verfügt auch über Zeichenfolgen, das zusätzliche Informationen zu den Dokumenttyp enthält. Dazu gehören der Name des Dokumenttyps (z. B. "Arbeitsblatt") und der Dateierweiterung (z. B. ".xls"). Optional können sie andere Zeichenfolgen, die von der Benutzeroberfläche der Anwendung, die Windows-Manager für Dateiserver und Object Linking and Embedding (OLE)-Unterstützung verwendet enthalten.  
  
 Wenn Ihre Anwendung ein OLE-Container und/oder Server ist, definiert die Dokumentvorlage auch die ID des Menüs während der direkten Aktivierung verwendet. Wenn Ihre Anwendung einen OLE-Server ist, definiert die Dokumentvorlage die ID des der Symbolleiste und die direkte Aktivierung verwendet. Angabe von diesen zusätzlichen OLE-Ressourcen durch Aufrufen von `SetContainerInfo` und `SetServerInfo`.  
  
 Da `CDocTemplate` ist eine abstrakte Klasse, Sie können die Klasse nicht direkt verwenden. Eine typische Anwendung verwendet einen der beiden `CDocTemplate`-abgeleitete Klassen, die von der Microsoft Foundation Class-Bibliothek bereitgestellt: `CSingleDocTemplate`, SDI, implementiert und `CMultiDocTemplate`, MDI implementiert. Finden Sie diese Klassen für Weitere Informationen zur Verwendung von Dokumentvorlagen.  
  
 Wenn Ihre Anwendung ein UI-Paradigma, die grundlegend von SDI- oder MDI-ist erfordert, können Sie eine eigene Klasse von ableiten `CDocTemplate`.  
  
 Weitere Informationen zu `CDocTemplate`, finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="adddocument"></a>  CDocTemplate::AddDocument  
 Verwenden Sie diese Funktion, um ein Dokument in eine Vorlage hinzufügen.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *pDoc*  
 Ein Zeiger auf das Dokument hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) und [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) überschreiben Sie diese Funktion. Wenn Sie Ihre eigenen Dokumentvorlagen-Klasse aus ableiten `CDocTemplate`, überschreiben Sie die abgeleitete Klasse muss diese Funktion.  
  
##  <a name="cdoctemplate"></a>  CDocTemplate::CDocTemplate  
 Erstellt ein `CDocTemplate`-Objekt.  
  
```  
CDocTemplate (
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDResource*  
 Gibt die ID der mit dem Dokument verwendeten Ressourcen. Dies kann im Menü "," Symbol "," Zugriffstastentabelle "und" Zeichenfolgenressourcen enthalten.  
  
 Die Zeichenfolgenressource besteht aus bis zu sieben Teilzeichenfolgen, die durch das Zeichen '\n' getrennte (das Zeichen '\n' wird als Platzhalter benötigt, wenn eine untergeordnete Zeichenfolge nicht enthalten ist; nachfolgende '\n'-Zeichen sind jedoch nicht erforderlich); Diese Teilzeichenfolgen beschreiben den Dokumenttyp an. Weitere Informationen dazu, das die Teilzeichenfolgen, finden Sie unter [GetDocString](#getdocstring). Diese Zeichenfolgenressource in die Ressourcendatei der Anwendung gefunden. Zum Beispiel:  

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

 Beachten Sie, dass die Zeichenfolge mit einem '\n'-Zeichen beginnt. Dies ist, da die erste Teilzeichenfolge nicht für MDI-Anwendungen verwendet wird und daher nicht enthalten ist. Sie können diese Zeichenfolge, die mit den Zeichenfolgen-Editor bearbeiten. die gesamte Zeichenfolge wird als einzelner Eintrag in den Editor für Zeichenfolgen, nicht als sieben separate Einträge angezeigt.  
  
 *pDocClass*  
 Verweist auf die `CRuntimeClass` Objekt der Document-Klasse. Diese Klasse ist eine `CDocument`-abgeleitete Klasse, die Sie definieren, um die Darstellung von Dokumenten.  
  
 *pFrameClass*  
 Verweist auf die `CRuntimeClass` Objekt das Rahmenfenster (Klasse). Diese Klasse kann sein, eine `CFrameWnd`-abgeleitete Klasse, oder es kann sein `CFrameWnd` selbst, wenn Sie Standardverhalten für das Hauptrahmenfenster verwenden möchten.  
  
 *pViewClass*  
 Verweist auf die `CRuntimeClass` Objekt der Klasse anzeigen. Diese Klasse ist eine `CView`-abgeleitete Klasse, die Sie definieren, um die Anzeige von Dokumenten.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion zum Erstellen einer `CDocTemplate` Objekt. Dynamisch Zuordnen einer `CDocTemplate` -Objekt und übergeben es an [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aus der `InitInstance` Memberfunktion der Anwendungsklasse.  
  
##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments  
 Rufen Sie diese Memberfunktion, um alle geöffneten Dokumente zu schließen.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parameter  
 *bEndSession*  
 Nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird in der Regel als Teil des Datei-beenden-Befehls verwendet. Ruft die standardmäßige Implementierung dieser Funktion die [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) Memberfunktion, um das Löschen des Dokuments Daten und schließt dann die Frame-Fensters für alle Ansichten, die an das Dokument angefügten.  
  
 Überschreiben Sie diese Funktion, sollten Sie, dass der Benutzer Verarbeitungsschritte spezielle Bereinigung ausführen, bevor das Dokument geschlossen wird. Z. B. wenn das Dokument einen Datensatz in einer Datenbank darstellt, können Sie dieser Funktion können Sie die Datenbank schließen überschreiben möchten.  
  
##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument  
 Rufen Sie diese Memberfunktion zum Erstellen eines neuen Dokuments, der den Typ dieser Dokumentvorlage zugeordnet.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neu erstellten Dokument, oder NULL, wenn ein Fehler auftritt.  
  
##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame  
 Erstellt ein neues Rahmenfensterobjekt, enthält ein Dokument und Ansicht.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Parameter  
 *pDoc*  
 Das Dokument, das neue Rahmenfenster verweisen soll. NULL kann sein.  
  
 *pOther*  
 Das Rahmenfenster, das auf dem das neue Rahmenfenster ist, basieren soll. NULL kann sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Rahmenfenster oder NULL, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `CreateNewFrame` verwendet die `CRuntimeClass` Objekte an den Konstruktor übergeben, erstellen ein neues Rahmenfensterobjekt mit einer Ansicht und das Dokument angefügt. Wenn die *pDoc* Parameter NULL ist, das Framework eine ablaufverfolgungsnachricht ausgibt.  
  
 Die *pOther* Parameter wird verwendet, um das neue Fenster Befehl zu implementieren. Es bietet ein Rahmenfenster, das neue Rahmenfenster zu modellieren. Das neue Rahmenfenster wird in der Regel nicht sichtbar erstellt. Mit dieser Funktion können Rahmenfenster außerhalb der standard Framework-Implementierung, Datei öffnen und neue Datei erstellen.  
  
##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame  
 Erstellt ein OLE-Rahmenfenster.  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf die übergeordnete Fenster des Frames.  
  
 *pDoc*  
 Ein Zeiger auf das Dokument, das neue OLE-Rahmenfenster verweisen soll.  
  
 *bCreateView*  
 Bestimmt, ob eine Sicht zusammen mit dem Frame erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Rahmenfenster, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bCreateView* ist 0 (null), ein leerer Frame wird erstellt.  
  
##  <a name="getdocstring"></a>  CDocTemplate::GetDocString  
 Ruft eine Zeichenfolge, die mit dem Dokument verknüpft ist.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rString*  
 Ein Verweis auf eine `CString` -Objekt, das die Zeichenfolge enthalten soll, wenn die Funktion zurückgibt.  
  
 *index*  
 Ein Index, der die Teilzeichenfolge aus der Zeichenfolge, die den Dokumenttyp beschreibt abgerufen wird. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `CDocTemplate::windowTitle` Der Name, der in das Anwendungsfenster, Titelleiste (z. B. "Microsoft Excel") angezeigt wird. Stellen Sie nur in die Dokumentvorlage für SDI-Anwendungen.  
  
- `CDocTemplate::docName` Stammzertifikate für die der Name des Standarddokuments (z. B. "Anmeldeformular"). Dieses Stammverzeichnis sowie eine Zahl ist, wird für den Standardnamen, der ein neues Dokument dieses Typs verwendet, wenn der Benutzer den neuen Befehl (z. B. "Arbeitsblatt1" oder "Sheet2") im Menü "Datei" auswählt. Wenn nicht angegeben ist, wird "Unbenannt" als Standard verwendet.  
  
- `CDocTemplate::fileNewName` Der Name für diesen Dokumenttyp. Wenn die Anwendung mehr als einen Typ des Dokuments unterstützt, wird diese Zeichenfolge in das Dialogfeld neue Datei (z. B. "Arbeitsblatt") angezeigt. Wenn nicht angegeben, ist der Dokumenttyp kann nicht zugegriffen werden mit dem Befehl neue Datei.  
  
- `CDocTemplate::filterName` Beschreibung des Dokumenttyps und einen Platzhalterfilter übereinstimmenden Dokumente dieses Typs. Diese Zeichenfolge wird in der Liste Dateityp Dropdown-Liste im Dialogfeld Datei öffnen (z. B. "Arbeitsblätter (*.xls)") angezeigt. Wenn nicht angegeben, ist der Dokumenttyp kann nicht zugegriffen werden mithilfe des Befehls Datei öffnen.  
  
- `CDocTemplate::filterExt` Erweiterung für Dokumente dieses Typs (z. B. ".xls"). Wenn nicht angegeben, ist der Dokumenttyp kann nicht zugegriffen werden mithilfe des Befehls Datei öffnen.  
  
- `CDocTemplate::regFileTypeId` Der Bezeichner für den Dokumenttyp in der Registrierungsdatenbank, die von Windows verwaltet gespeichert werden. Diese Zeichenkette ist nur zur internen Verwendung (z. B. "ExcelWorksheet"). Wenn nicht angegeben ist, kann nicht den Typ der Dokumente mit dem Windows-Datei-Manager registriert werden.  
  
- `CDocTemplate::regFileTypeName` Name des Dokumenttyps an, in der Registrierungsdatenbank gespeichert werden. Diese Zeichenfolge kann in Dialogfeldern von Anwendungen angezeigt werden, die Zugriff auf die Registrierungsdatenbank (z. B. "Microsoft Excel-Arbeitsblatt").  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei die angegebene Teilzeichenfolge gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen der einer bestimmten Teilzeichenfolge, die den Dokumenttyp beschreibt. Die Zeichenfolge, enthält diese Teilzeichenfolgen werden Dokumente gespeichert, und es ergibt sich aus einer Zeichenfolge in der Ressourcendatei für die Anwendung. Das Framework ruft diese Funktion rufen Sie die Zeichenfolgen, die sie für die Benutzeroberfläche der Anwendung benötigt. Wenn Sie eine Dateinamenerweiterung für die Dokumente Ihrer Anwendung angegeben haben, ruft das Framework auch diese Funktion beim Hinzufügen eines Eintrags in der Datenbank der Windows-Registrierung; Dadurch können Dokumente aus dem Windows-Datei-Manager geöffnet werden.  
  
 Rufen Sie diese Funktion nur, wenn Sie eine eigene Klasse von ableiten, werden `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition  
 Ruft die Position des ersten dieser Vorlage zugeordneten Dokuments ab.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Positionswert, der zum iterieren durch die Liste der Dokumente dieser Dokumentvorlage zugeordneten verwendet werden kann. oder NULL, wenn die Liste leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Position des ersten Dokuments in der Liste der Dokumente dieser Vorlage zugeordneten abzurufen. Verwenden Sie als Argument an den-Positionswerts [CDocTemplate::GetNextDoc](#getnextdoc) zum iterieren durch die Liste der Dokumente, die der Vorlage zugeordnet.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) und [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) sowohl diese rein virtuelle Funktion außer Kraft setzen. Jede Klasse, die Sie eine von Ableitung `CDocTemplate` müssen diese Funktion auch überschreiben.  
  
##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc  
 Ruft ab, das List-Element identifizierte *rPos*, legt dann *RPOs von bis zu* auf den Wert für die POSITION des nächsten Eintrag in der Liste.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Dokument in der Liste der Dokumente, die mit dieser Vorlage verknüpft ist.  
  
### <a name="parameters"></a>Parameter  
 *RPOs von bis zu*  
 Ein Verweis auf eine Positionswert, der von einem vorherigen Aufruf zurückgegebene [GetFirstDocPosition](#getfirstdocposition) oder `GetNextDoc`.  
  
### <a name="remarks"></a>Hinweise  
 Ist das abgerufene Element das letzte Element in der Liste aus, klicken Sie dann den neuen Wert des *rPos* auf NULL festgelegt ist.  
  
 Sie können `GetNextDoc` in einer Schleife Vorwärtsiteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten [GetFirstDocPosition](#getfirstdocposition).  
  
 Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame  
 Initialisiert das Rahmenfenster und optional macht es sichtbar.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrame*  
 Das Rahmenfenster, das die erste Aktualisierung benötigt.  
  
 *pDoc*  
 Das Dokument, das der Frame zugeordnet ist. NULL kann sein.  
  
 *bMakeVisible*  
 Gibt an, ob der Rahmen sichtbar und aktiv werden sollten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `IntitialUpdateFrame` nach dem Erstellen eines neuen Frames mit `CreateNewFrame`. Das Aufrufen dieser Funktion führt dazu, dass die Ansichten in diesem Frame-Fenster zum Empfangen von ihren `OnInitialUpdate` aufrufen. Darüber hinaus war es nicht bereits eine aktive Ansicht, die primäre Ansicht des Rahmenfensters active erfolgt; die primäre Ansicht ist eine Ansicht mit einem untergeordneten Element-ID des AFX_IDW_PANE_FIRST. Zum Schluss das Rahmenfenster sichtbar gemacht wird Wenn *bMakeVisible* ungleich NULL ist. Wenn *bMakeVisible* ist 0 (null), die aktueller Fokus und sichtbare Zustand des Rahmenfensters bleiben unverändert.  
  
 Es ist nicht notwendig, diese Funktion aufrufen, wenn mit der Implementierung des Frameworks neue Datei und die Datei öffnen.  
  
##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate  
 Lädt die Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, durch das Framework beim Laden von Ressourcen für einen bestimmten `CDocTemplate` oder eine abgeleitete Klasse. Normalerweise wird sie während der Erstellung, außer aufgerufen, wenn global die Vorlage erstellt wird. In diesem Fall wird der Aufruf von `LoadTemplate` wird verzögert, bis [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) aufgerufen wird.  
  
##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType  
 Bestimmt das Maß an Vertrauen der Übereinstimmung zwischen einem Dokument und diese Vorlage an.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPathName*  
 Der Pfadname der Datei an, dessen Typ bestimmt werden soll.  
  
 *rpDocMatch*  
 Zeiger auf ein Dokument, das das entsprechende Dokument zugewiesen wird, wenn die Datei durch angegeben *LpszPathName* ist bereits geöffnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der **vertrauen** -Enumeration, die wie folgt definiert ist:  
  
```  
enum Confidence  
    {  
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um den Typ der Dokumentvorlage, verwenden Sie zum Öffnen einer Datei bestimmen. Wenn Ihre Anwendung mehrere Dateitypen unterstützt, z. B. können diese Funktion um zu bestimmen, welche der verfügbaren Dokumentationsvorlagen für eine bestimmte Datei durch Aufrufen von `MatchDocType` für jede Vorlage im aktivieren, und wählen eine Vorlage gemäß der Wert für die Zuverlässigkeit zurückgegeben.  
  
 Wenn die Datei durch angegeben *LpszPathName* ist bereits geöffnet ist, gibt diese Funktion `CDocTemplate::yesAlreadyOpen` und kopiert die Datei `CDocument` Objekt in das Objekt am *RpDocMatch*.  
  
 Ist die Datei nicht geöffnet ist, aber die Erweiterung in *LpszPathName* entspricht die Erweiterung gemäß `CDocTemplate::filterExt`, diese Funktion gibt `CDocTemplate::yesAttemptNative` und *RpDocMatch* auf NULL. Weitere Informationen zu `CDocTemplate::filterExt`, finden Sie unter [CDocTemplate::GetDocString](#getdocstring).  
  
 Wenn keiner der beiden Fälle zutrifft, gibt die Funktion `CDocTemplate::yesAttemptForeign`.  
  
 Die Standardimplementierung gibt keine zurück `CDocTemplate::maybeAttemptForeign` oder `CDocTemplate::maybeAttemptNative`. Überschreiben Sie diese Funktion zur Implementierung typübereinstimmung Logik, die auf Ihre Anwendung, z. B. durch Verwenden dieser beiden Werte aus der **vertrauen** Enumeration.  
  
##  <a name="opendocumentfile"></a>  CDocTemplate:: OpenDocumentFile  
 Öffnet eine Datei, die durch einen Pfad angegeben.  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
*lpszPathName*<br/>
[in] Zeiger auf den Pfad der Datei, die mit dem Dokument geöffnet werden soll.  
  
*bAddToMRU*<br/>
[in] TRUE gibt an, dass das Dokument eine von der zuletzt verwendeten Dateien ist; FALSE gibt an, dass das Dokument nicht die zuletzt verwendeten Dateien ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, dessen Datei wird dem Namen *LpszPathName*; NULL, wenn der Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Öffnet die Datei, deren Pfad, indem angegeben wird *LpszPathName*. Wenn *LpszPathName* NULL ist, wird eine neue Datei, die ein Dokument mit den Typ dieser Vorlage zugeordneten enthält erstellt.  
  
##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument  
 Entfernt das Dokument verweist *pDoc* aus der Liste der Dokumente, die mit dieser Vorlage verknüpft ist.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *pDoc*  
 Zeiger auf das Dokument entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die abgeleiteten Klassen `CMultiDocTemplate` und `CSingleDocTemplate` überschreiben Sie diese Funktion. Wenn Sie Ihre eigenen Dokumentvorlagen-Klasse aus ableiten `CDocTemplate`, überschreiben Sie die abgeleitete Klasse muss diese Funktion.  
  
##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified  
 Speichert alle Dokumente, die geändert wurden.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich; andernfalls 0.  
  
##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo  
 Bestimmt die Ressourcen für OLE-Container an, wenn ein OLE-Element für ein direktes Bearbeiten.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDOleInPlaceContainer*  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt aktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie legen für die Ressourcen verwendet werden, wenn ein OLE-Objekt direkt aktiviert ist. Diese Ressourcen gehören möglicherweise die Menüs und Zugriffstastentabellen. Diese Funktion wird in der Regel aufgerufen, der [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Funktion Ihrer Anwendung.  
  
 Klicken Sie im Menü zugeordneten *nIDOleInPlaceContainer* Trennzeichen, die Sie im Menü des aktivierten direktes Elements, das Zusammenführen mit dem Menü der Container-Anwendung zu ermöglichen. Weitere Informationen zum Zusammenführen von Menüs für Server und den Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle  
 Rufen Sie diese Funktion zum Laden des Dokuments Standardtitel und zeigt sie auf der Titelleiste des Dokuments ab.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *pDocument*  
 Zeiger auf das Dokument, dessen Titel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu den Standardtitel, finden Sie unter der Beschreibung der `CDocTemplate::docName` in [CDocTemplate::GetDocString](#getdocstring).  
  
##  <a name="setserverinfo"></a>  CDocTemplate::SetServerInfo  
 Wenn das Serverdokument eingebettet ist, oder für ein direktes bearbeitet die Ressourcen und Klassen bestimmt werden soll.  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDOleEmbedding*  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt in einem separaten Fenster geöffnet wird.  
  
 *nIDOleInPlaceServer*  
 Die ID der Ressourcen verwendet, wenn ein eingebettetes Objekt aktiviert direkt.  
  
 *pOleFrameClass*  
 Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur, die Klasseninformationen für die Frame-Window-Objekt erstellt, wenn die Aktivierung des direktes enthält.  
  
 *pOleViewClass*  
 Zeiger auf eine `CRuntimeClass` Struktur, die Klasseninformationen für das Objekt erstellt, wenn die Aktivierung des direktes enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Identifizieren von Ressourcen, die von der Serveranwendung verwendet wird, wenn der Benutzer die Aktivierung von einem eingebetteten Objekt anfordert. Diese Ressourcen bestehen aus Menüs und Zugriffstastentabellen. Diese Funktion wird in der Regel aufgerufen, der `InitInstance` Ihrer Anwendung.  
  
 Klicken Sie im Menü zugeordneten *nIDOleInPlaceServer* Trennzeichen, mit denen im Menü "Server" zum Zusammenführen mit dem Menü des Containers enthält. Weitere Informationen zum Zusammenführen von Menüs für Server und den Container finden Sie im Artikel [Menüs und Ressourcen (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame  
 Erstellt eine Child-Rahmen, die für die umfassende Vorschau verwendet.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf ein übergeordnetes Fenster (in der Regel von der Shell bereitgestellt).  
  
 *pDoc*  
 Ein Zeiger auf ein Document-Objekt, dessen Inhalt werden in der Vorschau angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf eine `CFrameWnd` Objekt, oder NULL, wenn die Datenbankerstellung fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo  
 Legt fest, um die Out-of-Vorschauhandler Prozess.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDPreviewFrame*  
 Gibt eine Ressourcen-ID, der den Vorschauframe an.  
  
 *pPreviewFrameClass*  
 Gibt einen Zeiger auf eine Struktur für Common Language Runtime-Klasse von den Vorschauframe.  
  
 *pPreviewViewClass*  
 Gibt einen Zeiger auf eine Common Language Runtime-Klasse Informationsstruktur der Vorschau an.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate-Klasse](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate-Klasse](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)   
 [CEditView-Klasse](../../mfc/reference/ceditview-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd-Klasse](../../mfc/reference/cmdichildwnd-class.md)
