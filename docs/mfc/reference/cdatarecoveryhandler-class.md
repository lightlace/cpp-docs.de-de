---
title: CDataRecoveryHandler-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: 88cc4a433c774dc7767efaaa62edc71ce8b904d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273035"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler-Klasse

Die `CDataRecoveryHandler` speichert Dokumente automatisch und stellt diese wieder her, wenn eine Anwendung unerwartet beendet wird.

## <a name="syntax"></a>Syntax

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Erstellt ein `CDataRecoveryHandler`-Objekt.|

### <a name="methods"></a>Methoden

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Speichert, die jeder Datei registriert, mit der `CDataRecoveryHandler` Klasse.|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Speichert das angegebene Dokument.|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Die Liste der geöffneten Dokumente hinzufügt ein Dokument.|
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Löscht die aktuellen automatisch gespeicherte Dateien.|
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Löscht die Datei angegebenen fortlaufend automatisch gespeichert.|
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Generiert die Namen für eine autospeicher-Datei, die den Dateinamen des angegebenen Dokument zugeordnet.|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Gibt das Intervall zwischen Versuche des Autosave zurück.|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Gibt den Pfad der Dateien automatisch gespeichert.|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Ruft den Namen des Dokuments aus einem `CDocument` Objekt.|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Ruft den normalen Titel für das angegebene Dokument ab.|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Erstellt und gibt den Titel für das wiederhergestellte Dokument.|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Ruft den Neustart des eindeutigen Bezeichner für die Anwendung.|
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Gibt an, ob der Neustart-Manager, die zu beendenden Anwendung verursacht.|
|[CDataRecoveryHandler::Initialize](#initialize)|Initialisiert das `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` fortlaufend automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer die automatisch gespeicherte Dokument wiederherstellen möchte.|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Lädt die Liste der geöffneten Dokument aus der Registrierung.|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Öffnet die vorher geöffnete Dokumente.|
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Stellt die automatisch gespeicherte Dokumente auf Grundlage der Benutzereingabe.|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Die aktuelle Liste der geöffneten Dokumente in der Windows-Registrierung gespeichert.|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Legt die Zeit zwischen Autosave Zyklen in Millisekunden fest.|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Legt das Verzeichnis, in dem automatisch gespeicherte Dateien gespeichert werden.|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Legt fest, ob die `CDataRecoveryHandler` , speichert die geöffneten Dokumentinformationen in die Windows-Registrierung bei der aktuellen im Leerlauf befindet.|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Legt fest, ob es sich bei der vorherige Beenden der Anwendung durch den Neustart-Manager verursacht wurde.|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Die Informationen für ein Dokument aktualisiert, da der Benutzer, die sie gespeichert.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|m_bRestoringPreviousOpenDocs|Gibt an, ob es sich bei der Wiederherstellung Datenhandler vorher geöffnete Dokumente erneut öffnet.|
|m_bSaveDocumentInfoOnIdle|Gibt an, ob die Data Recovery Handler speichert auf der nächsten Leerlaufschleife dokumentiert.|
|m_bShutdownByRestartManager|Gibt an, ob der Neustart-Manager führt dazu, die Anwendung dass zu beenden.|
|m_dwRestartManagerSupportFlags|Flags, die angeben, was den Neustart-Manager unterstützen, stellt für die Anwendung bereit.|
|m_lstAutosavesToDelete|Eine Liste der Dateien automatisch gespeichert, die nicht gelöscht wurden, wenn die ursprünglichen Dokumente geschlossen wurden. Wenn die Anwendung, die Neustart-Manager Wiederholungen, löschen Sie die Dateien beendet wird.|
|m_mapDocNameToAutosaveName|Eine Karte mit den Dokumentnamen, die Dateinamen automatisch gespeichert.|
|m_mapDocNameToDocumentPtr|Eine Übersicht über die Namen von Dokumenten, die [CDocument](../../mfc/reference/cdocument-class.md) Zeiger.|
|m_mapDocNameToRestoreBool|Eine Karte mit den Dokumentnamen, einen booleschen Parameter, der angibt, ob das Dokument automatisch gespeicherte wiederhergestellt werden soll.|
|m_mapDocumentPtrToDocName|Eine Übersicht über die `CDocument` Zeiger auf den Dokumentnamen.|
|m_mapDocumentPtrToDocTitle|Eine Übersicht über die `CDocument` Zeiger auf den Dokumenttitel. Dieser Titel werden zum Speichern von Dateien verwendet.|
|m_nAutosaveInterval|Zeit in Millisekunden zwischen speichert.|
|m_nTimerID|Der Bezeichner für den Zeitgeber des Autosave.|
|m_strAutosavePath|Der Speicherort, wo die automatisch gespeicherte Dokumente gespeichert werden.|
|m_strRestartIdentifier|Die Zeichenfolgendarstellung einer GUID für den Neustart-Manager.|

## <a name="remarks"></a>Hinweise

Der Neustart-Manager verwendet die `CDataRecoveryHandler` Klasse zu nachverfolgen und automatisches Speichern aller geöffneten Dokumente können nach Bedarf. Verwenden Sie zum Aktivieren von Autosave den [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) Methode. Diese Methode leitet die `CDataRecoveryHandler` ein Autosave auf der nächsten Leerlaufschleife ausführen. Die Neustart-Manager ruft `SetSaveDocumentInfoOnIdle` bei der `CDataRecoveryHandler` sollte ein automatisches Speichern ausführen.

Alle Methoden von der `CDataRecoveryHandler` Klasse sind virtuell. Überschreiben Sie die Methoden in dieser Klasse, um Ihren eigenen benutzerdefinierten Daten-Recovery-Handler zu erstellen. Es sei denn, Sie Ihre eigenen Data Recovery Ereignishandler erstellen oder-Manager Neustart, instanziieren Sie ein CDataRecoveryHandler nicht. Die [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) erstellt eine `CDataRecoveryHandler` Objekt, wie es erforderlich ist.

Vor der Verwendung einer `CDataRecoveryHandler` Objekt, rufen Sie [CDataRecoveryHandler::Initialize](#initialize).

Da die `CDataRecoveryHandler` Klasse eng verbunden ist, um den Neustart-Manager, `CDataRecoveryHandler` hängt von der globalen Parameters `m_dwRestartManagerSupportFlags`. Dieser Parameter bestimmt, welche Berechtigungen, die der Neustart-Manager hat und wie sie mit der Anwendung interagiert. Um den Neustart-Manager in einer vorhandenen Anwendung zu integrieren, müssen Sie weisen `m_dwRestartManagerSupportFlags` den entsprechenden Wert im Konstruktor der Ihre hauptanwendung. Weitere Informationen dazu, wie Sie den Neustart-Manager verwenden, finden Sie unter [Vorgehensweise: Hinzufügen von Unterstützung für den Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md).

## <a name="requirements"></a>Anforderungen

**Header:** afxdatarecovery.h

##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo

Speichert, die jeder Datei registriert, mit der `CDataRecoveryHandler` Klasse.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die `CDataRecoveryHandler` alle Dokumente; gespeichert "False", wenn ein Dokument nicht gespeichert wurde.

### <a name="remarks"></a>Hinweise

Diese Methode gibt TRUE zurück, wenn es sind keine Dokumente, die gespeichert werden müssen. Außerdem gibt TRUE zurück, ohne speichern alle Dokumente aus, wenn beim Abrufen der `CWinApp` oder `CDocManager` für die Anwendung einen Fehler generiert.

Um diese Methode verwenden zu können, muss entweder AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART oder AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL festgelegt werden `m_dwRestartManagerSupportFlags`. Finden Sie unter [M_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) für Weitere Informationen.

##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo

Speichert das angegebene Dokument.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf die `CDocument` zu speichern.|
|*bResetModifiedFlag*|[in] "True" gibt an, dass die `CDataRecoveryHandler` berücksichtigt *pDocument* geändert werden; FALSE gibt an, dass das Framework berücksichtigt *pDocument* unverändert sein. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu den Auswirkungen dieses Flags.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die entsprechenden Flags festgelegt sind und *pDocument* ist ein gültiger `CDocument` Objekt.

### <a name="remarks"></a>Hinweise

Jede `CDocument` Objekt verfügt über ein Flag, das angibt, ob es seit der letzten Speicherung geändert hat. Verwendung [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) zum Ermitteln des Status dieses Flags. Wenn eine `CDocument` wurde nicht geändert, seit der letzten Speicherung, `AutosaveDocumentInfo` löscht automatisch gespeicherte Dateien für das Dokument. Wenn ein Dokument, die seit dem letzten Speichern geändert wurde, schließen sie die Benutzer aufgefordert, das Dokument vor dem Schließen speichern.

> [!NOTE]
>  Mithilfe von *bResetModifiedFlag* so ändern Sie den Status des Dokuments, unveränderte können dazu führen, dass den Benutzer nicht gespeicherte Daten verloren gehen. Wenn ein Dokument unverändert als das Framework angesehen wird, schließen nicht die Benutzer wird zum Speichern aufgefordert.

Diese Methode löst eine Ausnahme mit der [ASSERT](diagnostic-services.md#assert) Makro Wenn *pDocument* ist kein gültiger `CDocument` Objekt.

Um diese Methode verwenden zu können, muss entweder AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART oder AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL festgelegt werden *M_dwRestartManagerSupportFlags*.

##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler

Erstellt ein `CDataRecoveryHandler`-Objekt.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*dwRestartManagerSupportFlags*|[in] Gibt an, welche Optionen des Neustart-Managers unterstützt werden.|
|*nAutosaveInterval*|[in] Die Zeit zwischen speichert. Dieser Parameter ist in Millisekunden.|

### <a name="remarks"></a>Hinweise

MFC-Framework erstellt automatisch eine `CDataRecoveryHandler` Objekt für Ihre Anwendung bei der Verwendung der **neues Projekt** Assistenten. Es sei denn, Sie der Wiederherstellungsverhalten für Daten oder den Neustart-Manager anpassen, erstellen Sie keine `CDataRecoveryHandler` Objekt.

##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo

Die Liste der geöffneten Dokumente hinzufügt ein Dokument.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf eine `CDocument`. Diese Methode erstellt die Dokumentinformationen für diesen `CDocument`.|

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Methode überprüft, ob *pDocument* ist bereits in der Liste der Dokumente, bevor das Dokument hinzugefügt. Wenn *pDocument* befindet Sie sich bereits in der Liste, diese Methode löscht, die automatisch gespeicherte Datei zugeordneten *pDocument*.

Um diese Methode verwenden zu können, muss entweder AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART oder AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL festgelegt werden *M_dwRestartManagerSupportFlags*.

##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles

Löscht die aktuellen automatisch gespeicherte Dateien.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Rückgabewert

Immer die Standardimplementierung gibt "true" zurück.

##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile

Löscht die Datei angegebenen fortlaufend automatisch gespeichert.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*strAutosavedFile*|[in] Eine Zeichenfolge, die automatisch gespeicherte Dateiname enthält.|

### <a name="return-value"></a>Rückgabewert

Immer die Standardimplementierung gibt WAHR zurück.

### <a name="remarks"></a>Hinweise

Wenn diese Methode, die automatisch gespeicherte Datei löschen kann, speichert es den Namen der Datei in einer Liste. Der Destruktor für die `CDataRecoveryHandler` versucht, jede automatisch gespeicherte Datei angegeben, in der Liste zu löschen.

##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName

Generiert die Namen für eine autospeicher-Datei, die den Dateinamen des angegebenen Dokument zugeordnet.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Parameter

*strDocumentName*<br/>
[in] Eine Zeichenfolge, die den Namen des Dokuments enthält. `GenerateAutosaveFileName` verwendet diese Dokument um einen entsprechenden Namen des Autosave-Datei zu generieren.

### <a name="return-value"></a>Rückgabewert

Generiert aus der Autosave-Dateiname *StrDocumentName*.

### <a name="remarks"></a>Hinweise

Jeder Dokumentname verfügt über eine 1: 1-Zuordnung mit einem Dateinamen des Autosave.

##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval

Gibt das Intervall zwischen Versuche des Autosave zurück.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Millisekunden zwischen Autosave versucht.

##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath

Gibt den Pfad der Dateien automatisch gespeichert.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Rückgabewert

Der Speicherort, wo die automatisch gespeicherte Dokumente gespeichert werden.

##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName

Ruft den Namen des Dokuments aus einem `CDocument` Objekt.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf eine `CDocument`. `GetDocumentListName` Ruft den Namen des Dokuments ab, aus dieser `CDocument`.|

### <a name="return-value"></a>Rückgabewert

Den Namen des Dokuments aus *pDocument*.

### <a name="remarks"></a>Hinweise

Die `CDataRecoveryHandler` verwendet den Namen des Dokuments als Schlüssel in *M_mapDocNameToAutosaveName*, *M_mapDocNameToDocumentPtr*, und *M_mapDocNameToRestoreBool*. Aktivieren Sie diese Parameter der `CDataRecoveryHandler` Überwachen `CDocument` Objekte, den Dateinamen des Autosave und die Einstellungen des Autosave.

##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle

Ruft den normalen Titel für das angegebene Dokument ab.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf eine `CDocument`.|

### <a name="return-value"></a>Rückgabewert

Der normale Titel für das angegebene Dokument.

### <a name="remarks"></a>Hinweise

Die normale Titel eines Dokuments wird in der Regel den Dateinamen des Dokuments ohne Pfad. Dies ist der Titel in der **Dateiname** Feld der **speichern** Dialogfeld.

##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle

Erstellt und gibt den Titel für das wiederhergestellte Dokument.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Parameter

*strDocumentTitle*<br/>
[in] Der normale Titel für das Dokument.

### <a name="return-value"></a>Rückgabewert

Der wiederhergestellte Dokument-Titel.

### <a name="remarks"></a>Hinweise

Standardmäßig ist die wiederhergestellte Titel eines Dokuments den normalen Titel **[wiederhergestellt]** angefügt. Der wiederhergestellte Titel wird angezeigt, für den Benutzer bei der `CDataRecoveryHandler` fragt den Benutzer automatisch gespeicherte Dokumente wiederherstellen.

##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier

Ruft den Neustart des eindeutigen Bezeichner für die Anwendung.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Rückgabewert

Der Neustart des eindeutigen Bezeichner.

### <a name="remarks"></a>Hinweise

Die Neustart-ID ist eindeutig für jede Ausführung der Anwendung.

Die `CDataRecoveryHandler` speichert Informationen in der Registrierung über die aktuell geöffneten Dokumente. Wenn der Neustart-Manager eine Anwendung beendet und startet ihn neu, gibt er den Neustart-Bezeichner, der die `CDataRecoveryHandler`. Die `CDataRecoveryHandler` verwendet die Neustart-ID zum Abrufen der Liste der zuvor geöffneten Dokumente. Dies ermöglicht die `CDataRecoveryHandler` zum Suchen nach und automatisch gespeicherte Dateien wiederherstellen.

##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle

Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" an die `CDataRecoveryHandler` speichert, auf die aktuelle Leerlaufschleife; FALSE gibt an, dass dies nicht der Fall.

##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager

Gibt an, ob der Neustart-Manager, die zu beendenden Anwendung verursacht.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass der Neustart-Manager, die zu beendenden Anwendung verursacht; FALSE gibt an, dass dies nicht der Fall.

##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize

Initialisiert das `CDataRecoveryHandler`.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Initialisierung erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Initialisierungsprozess lädt den Pfad zum Speichern des Autosave-Dateien aus der Registrierung. Wenn die `Initialize` Methode wurde dieses Verzeichnis nicht gefunden, oder wenn der Pfad NULL ist, ist `Initialize` schlägt fehl, und gibt `FALSE`.

Verwendung [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) des Autosave-Pfads zu ändern, nachdem Ihre Anwendung initialisiert den `CDataRecoveryHandler`.

Die `Initialize` Methode startet außerdem einen Zeitgeber, bei der nächsten Autosave tritt auf, zu überwachen. Verwendung [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) des Autosave-Intervalls ändern, nachdem Ihre Anwendung initialisiert den `CDataRecoveryHandler`.

##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments

Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` fortlaufend automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer die automatisch gespeicherte Dokument wiederherstellen möchte.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung Unicode ist, zeigt diese Methode eine ["CTaskDialog"](../../mfc/reference/ctaskdialog-class.md) für den Benutzer. Andernfalls verwendet das Framework [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) um vom Benutzer abzufragen.

Nach dem `QueryRestoreAutosavedDocuments` sammelt alle Antworten des Benutzers, speichert er die Informationen in der Membervariablen *M_mapDocNameToRestoreBool*. Diese Methode die automatisch gespeicherte Dokumente nicht wiederhergestellt werden.

##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList

Lädt die Liste der geöffneten Dokument aus der Registrierung.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Rückgabewert

"True" gibt an, dass `ReadOpenDocumentList` die Informationen für mindestens ein Dokument aus der Registrierung geladen FALSE gibt an, dass kein Dokument geladen wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion lädt die geöffneten Dokumentinformationen aus der Registrierung und speichert sie in der Membervariablen *M_mapDocNameToAutosaveName*.

Nach dem `ReadOpenDocumentList` lädt alle Daten, die Dokumentinformationen werden aus der Registrierung gelöscht.

##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo

Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf das Dokument zu entfernen.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *pDocument* entfernt wurde, aus der Liste. FALSE, wenn ein Fehler aufgetreten ist.

### <a name="remarks"></a>Hinweise

Wenn der Benutzer ein Dokument geschlossen wird, verwendet das Framework diese Methode, die um sie aus der Liste der geöffneten Dokumente zu entfernen.

Wenn `RemoveDocumentInfo` wurde nicht gefunden *pDocument* in der Liste der geöffneten Dokumente, es führt keine Aktion aus, und gibt TRUE zurück.

Zur Verwendung dieser Methode AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES nutno nastavit *M_dwRestartManagerSupportFlags*.

##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments

Öffnet die vorher geöffnete Dokumente.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Rückgabewert

True, wenn mindestens ein Dokument geöffnet wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode öffnet den letzten Speichervorgang der vorher geöffnete Dokumente. Wenn ein Dokument nicht gespeichert wurde oder fortlaufend automatisch gespeichert, `ReopenPreviousDocuments` öffnet ein leeres Dokument basierend auf der Vorlage für diesen Dateityp.

Zur Verwendung dieser Methode AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES nutno nastavit *M_dwRestartManagerSupportFlags*. Wenn dieser Parameter nicht festgelegt ist, `ReopenPreviousDocuments` führt keine Aktion aus und gibt FALSE zurück.

Wenn es keine Dokumente, die in der Liste der zuvor geöffneten Dokumente, gespeicherte sind `ReopenPreviousDocuments` führt keine Aktion aus und gibt FALSE zurück.

##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments

Stellt die automatisch gespeicherte Dokumente auf Grundlage der Benutzereingabe.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn es sich bei dieser Methode werden die Dokumente erfolgreich wiederhergestellt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) um zu bestimmen, die den Benutzer Dokumente wiederherstellen möchte. Wenn ein Benutzer nicht zu einem Dokument automatisch gespeicherte wiederherstellen `RestoreAutosavedDocuments` löscht die autospeicher-Datei. Andernfalls `RestoreAutosavedDocuments` ersetzt das geöffnete Dokument mit der Version fortlaufend automatisch gespeichert.

Um diese Methode verwenden zu können, muss entweder AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES oder AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES festgelegt werden `m_dwRestartManagerSupportFlags`.

##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList

Die aktuelle Liste der geöffneten Dokumente in der Windows-Registrierung gespeichert.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Rückgabewert

"True", wenn es keine geöffneten Dokumente sind speichern oder sie wurden erfolgreich gespeichert wurden. FALSE, wenn Dokumente in der Registrierung gespeichert sind, aber sie nicht gespeichert wurden, da ein Fehler aufgetreten ist.

### <a name="remarks"></a>Hinweise

Die Neustart-Manager ruft `SaveOpenDocumentList` Wenn die Anwendung unerwartet beendet wird oder wenn es bei einem Upgrade beendet wird. Wenn die Anwendung neu gestartet wird, verwendet es [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) zum Abrufen der Liste der geöffneten Dokumente.

Diese Methode speichert nur die Liste der geöffneten Dokumente. Die Methode [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) ist verantwortlich für das die Dokumente selbst zu speichern.

##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval

Legt die Zeit zwischen Autosave Zyklen in Millisekunden fest.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Parameter

*nAutosaveInterval*<br/>
[in] Das neue Autosave Intervall in Millisekunden.

##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath

Legt das Verzeichnis, in dem automatisch gespeicherte Dateien gespeichert werden.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*strAutosavePath*|[in] Der Pfad, in dem Dateien des Autosave gespeichert sind.|

### <a name="remarks"></a>Hinweise

Das Ändern des Autosave-Verzeichnisses verschoben nicht derzeit automatisch gespeicherte Dateien.

##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier

Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*strRestartIdentifier*|[in] Der eindeutige Bezeichner für den Neustart-Manager.|

### <a name="remarks"></a>Hinweise

Der Neustart-Manager zeichnet Informationen zu geöffneten Dokumente in der Registrierung. Diese Informationen werden mit dem Neustart des eindeutigen Bezeichner als Schlüssel gespeichert. Da die Neustart-Bezeichner für jede Instanz einer Anwendung eindeutig ist, mehrere Instanzen einer Anwendung möglicherweise unerwartet beendet und der Neustart-Manager wiederhergestellt werden kann jeweils.

##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle

Legt fest, ob die `CDataRecoveryHandler` , speichert die geöffneten Dokumentinformationen in die Windows-Registrierung bei der aktuellen im Leerlauf befindet.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*bSaveOnIdle*|[in] True, um das Dokumentinformationen bei der aktuellen im Leerlauf zu speichern. FALSE, wenn einen Speichervorgang nicht ausgeführt werden.|

##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager

Legt fest, ob es sich bei der vorherige Beenden der Anwendung durch den Neustart-Manager verursacht wurde.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*bShutdownByRestartManager*|[in] TRUE gibt an, dass der Neustart-Manager, die zu beendenden Anwendung verursacht. "False", um anzugeben, dass die Anwendung aus einem anderen Grund wurde beendet.|

### <a name="remarks"></a>Hinweise

Das Framework verhält sich unterschiedlich basierend auf gibt an, ob die vorherige beenden unerwartet war, oder gibt an, ob es durch den Neustart-Manager initiiert wurde.

##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo

Die Informationen für ein Dokument aktualisiert, da der Benutzer, die sie gespeichert.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pDocument*|[in] Ein Zeiger auf das gespeicherte Dokument.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode automatisch gespeicherte Dokument gelöscht und die Dokumentinformationen aktualisiert; FALSE, wenn ein Fehler aufgetreten ist.

### <a name="remarks"></a>Hinweise

Wenn ein Benutzer ein Dokument speichert, wird die Anwendung die automatisch gespeicherte Datei entfernt, da es nicht mehr benötigt wird. `UpdateDocumentInfo` Löscht die automatisch gespeicherte Datei durch Aufrufen von [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo` fügt dann die Informationen aus *pDocument* zur Liste der derzeit öffnen Dokumente da `RemoveDocumentInfo` löscht diese Informationen, aber die gespeicherten Dokument noch geöffnet ist.

Zur Verwendung dieser Methode AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES nutno nastavit *M_dwRestartManagerSupportFlags*.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Vorgehensweise: Hinzufügen von Unterstützung für Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)
