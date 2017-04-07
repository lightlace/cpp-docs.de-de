---
title: CDataRecoveryHandler Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler class
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 26e36977a2e18dcaa4a76b201f9543e200f2d276
ms.lasthandoff: 03/31/2017

---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler-Klasse
Die `CDataRecoveryHandler` speichert Dokumente automatisch und stellt sie wieder her, wenn eine Anwendung unerwartet beendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Erstellt ein `CDataRecoveryHandler`-Objekt.|  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Jede Datei mit registrierten speichert die `CDataRecoveryHandler` Klasse.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Speichert das angegebene Dokument.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Fügt ein Dokument in die Liste der geöffneten Dokumente.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Löscht die aktuellen automatisch gespeicherte Dateien.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Löscht die angegebene automatisch gespeicherte Datei.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Generiert den Namen für eine Sicherungsdatei, die den Dateinamen des angegebenen Dokument zugeordnet.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Gibt das Intervall zwischen AutoSpeichern versucht zurück.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Gibt den Pfad der Dateien automatisch gespeichert.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Ruft den Namen des Dokuments aus einer `CDocument` Objekt.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Ruft den normalen Titel für das angegebene Dokument ab.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Erstellt und gibt den Titel für das wiederhergestellte Dokument.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Ruft den Neustart des eindeutigen Bezeichner für die Anwendung.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Gibt an, ob der Neustart-Manager die zum Beenden der Anwendung verursacht.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Initialisiert das `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer das Dokument automatisch wiederherstellen möchte.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Lädt die Liste der geöffneten Dokument aus der Registrierung.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Öffnet die zuvor geöffneten Dokumente.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Stellt Sie automatisch gespeicherte Dokumente basierend auf Benutzereingaben wieder her.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Speichert die aktuelle Liste der geöffneten Dokumente zur Windows-Registrierung.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Legt die Zeit zwischen AutoSpeichern Zyklen in Millisekunden fest.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Legt das Verzeichnis, in dem Dateien automatisch gespeichert werden.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Legt fest, ob die `CDataRecoveryHandler` , speichert die geöffneten Dokumentinformationen zur Windows-Registrierung während der aktuellen im Leerlauf Zyklus.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Legt fest, ob es sich bei der vorherigen Beenden der Anwendung vom Neustart-Manager verursacht wurde.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Aktualisiert die Informationen für ein Dokument an, da der Benutzer es gespeichert.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Gibt an, ob es sich bei der Wiederherstellung Datenhandler zuvor geöffneten Dokumente eröffnet.|  
|m_bSaveDocumentInfoOnIdle|Gibt an, ob die Data Recovery Ereignishandler speichert auf der nächsten Leerlaufschleife dokumentiert.|  
|m_bShutdownByRestartManager|Gibt an, ob der Neustart-Manager bewirkt, die Anwendung dass zu beenden.|  
|m_dwRestartManagerSupportFlags|Flags, die angeben, was die Neustart-Manager unterstützt enthält für die Anwendung.|  
|m_lstAutosavesToDelete|Eine Liste der Dateien automatisch, die nicht gelöscht wurden, wenn die ursprünglichen Dokumente geschlossen wurden. Beim Beenden der Anwendung, der Neustart-Manager Wiederholungen, die die Dateien zu löschen.|  
|m_mapDocNameToAutosaveName|Eine Zuordnung der Dokumentnamen auf die Dateinamen automatisch gespeichert.|  
|m_mapDocNameToDocumentPtr|Eine Zuordnung der Dokumentnamen, um die [CDocument](../../mfc/reference/cdocument-class.md) Zeiger.|  
|m_mapDocNameToRestoreBool|Eine Zuordnung der Dokumentnamen zu einem booleschen Parameter, der angibt, ob das Dokument automatisch wiederhergestellt werden soll.|  
|m_mapDocumentPtrToDocName|Eine Übersicht über die `CDocument` Zeiger auf den Dokumentnamen.|  
|m_mapDocumentPtrToDocTitle|Eine Übersicht über die `CDocument` Zeiger auf den Dokumenttitel. Dieser Titel werden zum Speichern von Dateien verwendet.|  
|m_nAutosaveInterval|Die Zeit in Millisekunden zwischen speichert.|  
|m_nTimerID|Der Bezeichner für den Timer AutoSpeichern.|  
|m_strAutosavePath|Der Speicherort, in dem die automatisch gespeicherte Dokumente gespeichert werden.|  
|m_strRestartIdentifier|Die Zeichenfolgendarstellung einer GUID für den Neustart-Manager.|  
  
## <a name="remarks"></a>Hinweise  
 Der Neustart-Manager verwendet die `CDataRecoveryHandler` Klasse zu verfolgen aller geöffneten Dokumente und AutoSpeichern nach Bedarf. Verwenden Sie zum Aktivieren von AutoSpeichern die [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) Methode. Diese Methode leitet den `CDataRecoveryHandler` ein AutoSpeichern auf der nächsten Leerlaufschleife ausführen. Die Neustart-Manager ruft `SetSaveDocumentInfoOnIdle` bei der `CDataRecoveryHandler` sollten eine AutoSpeichern ausführen.  
  
 Alle Methoden von der `CDataRecoveryHandler` Klasse sind virtuell. Überschreiben Sie die Methoden in dieser Klasse, um eine eigene benutzerdefinierte Datenhandler für die Wiederherstellung zu erstellen. Instanziieren Sie ein CDataRecoveryHandler nicht, es sei denn, Sie Ihre eigenen Datenhandler für die Wiederherstellung erstellen oder-Manager Neustart. Die [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md) erstellt eine `CDataRecoveryHandler` Objekt, wie es erforderlich ist.  
  
 Vor der Verwendung einer `CDataRecoveryHandler` -Objekt, rufen Sie [CDataRecoveryHandler::Initialize](#initialize).  
  
 Da die `CDataRecoveryHandler` Klasse eng verbunden ist, um den Neustart-Manager `CDataRecoveryHandler` hängt von der globalen Parameter `m_dwRestartManagerSupportFlags`. Dieser Parameter bestimmt, welche Berechtigungen, die der Neustart-Manager hat und wie sie mit der Anwendung interagiert. Um den Neustart-Manager in einer vorhandenen Anwendung zu integrieren, müssen Sie weisen `m_dwRestartManagerSupportFlags` den entsprechenden Wert im Konstruktor der Ihre hauptanwendung. Weitere Informationen zur Verwendung den Neustart-Manager finden Sie unter [Vorgehensweise: Neustart-Manager-Unterstützung hinzufügen](../../mfc/how-to-add-restart-manager-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 Jede Datei mit registrierten speichert die `CDataRecoveryHandler` Klasse.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CDataRecoveryHandler` gespeicherten alle Dokumente; `FALSE` , wenn ein Dokument nicht gespeichert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` Wenn es sind keine Dokumente, die gespeichert werden müssen. Sie gibt überdies `TRUE` ohne speichern alle Dokumente aus, wenn das Abrufen der `CWinApp` oder `CDocManager` für die Anwendung einen Fehler generiert.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. Finden Sie unter [M_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) für Weitere Informationen.  
  
##  <a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
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
|[in] `pDocument`|Ein Zeiger auf die `CDocument` zu speichern.|  
|[in] `bResetModifiedFlag`|`TRUE`Gibt an, dass die `CDataRecoveryHandler` betrachtet `pDocument` geändert werden; `FALSE` gibt an, dass das Framework berücksichtigt `pDocument` nicht geändert werden. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu den Auswirkungen dieses Flags.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die entsprechenden Flags festgelegt sind und `pDocument` ist ein gültiger `CDocument` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Jedes `CDocument` Objekt verfügt über ein Flag, das angibt, ob es sich seit der letzten Speicherung geändert hat. Verwendung [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) zum Ermitteln des Status dieses Flags. Wenn eine `CDocument` wurde nicht geändert, seit der letzten Speicherung `AutosaveDocumentInfo` löscht alle Dateien automatisch für das Dokument. Wenn ein Dokument seit der letzten Speicherung geändert wurde, fordert das Schließen den Benutzer das Dokument vor dem Schließen zu speichern.  
  
> [!NOTE]
>  Mithilfe von `bResetModifiedFlag` so ändern Sie den Status des Dokuments auf unmodified können dazu führen, dass den Benutzer nicht gespeicherte Daten verloren gehen. Wenn das Framework, ein Dokument unverändert bleiben sollen berücksichtigt, einen schließen fordert nicht vom Benutzer zu speichern.  
  
 Diese Methode löst eine Ausnahme mit der [ASSERT](diagnostic-services.md#assert) Makro Wenn `pDocument` ist kein gültiger `CDocument` Objekt.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
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
|[in] `dwRestartManagerSupportFlags`|Gibt an, welche Optionen für den Neustart-Manager unterstützt werden.|  
|[in] `nAutosaveInterval`|Die Zeit zwischen speichert. Dieser Parameter ist in Millisekunden.|  
  
### <a name="remarks"></a>Hinweise  
 Das MFC-Framework erstellt automatisch eine `CDataRecoveryHandler` Objekt für die Anwendung bei Verwendung der **neues Projekt** Assistenten. Wenn Sie das Wiederherstellungsverhalten Daten oder der Neustart-Manager anpassen, sollten Sie keine erstellen eine `CDataRecoveryHandler` Objekt.  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 Fügt ein Dokument in die Liste der geöffneten Dokumente.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`. Diese Methode erstellt die Dokumentinformationen dafür `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, ob `pDocument` ist bereits in der Liste der Dokumente, bevor das Dokument hinzugefügt. Wenn `pDocument` befindet Sie sich bereits in der Liste, diese Methode löscht die Datei automatisch zugeordnet `pDocument`.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` oder `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. 
  
##  <a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 Löscht die aktuellen automatisch gespeicherte Dateien.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die standardmäßige Implementierung immer `TRUE`.  
  
##  <a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 Löscht die angegebene automatisch gespeicherte Datei.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strAutosavedFile`|Eine Zeichenfolge, die automatisch gespeicherte Dateiname enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung immer return `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode automatisch gespeicherte Datei löschen kann, wird der Name der Datei in einer Liste gespeichert. Der Destruktor für die `CDataRecoveryHandler` versucht, jede automatisch gespeicherte Datei angegeben, in der Liste zu löschen.  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 Generiert den Namen für eine Sicherungsdatei, die den Dateinamen des angegebenen Dokument zugeordnet.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDocumentName`  
 Eine Zeichenfolge, die den Namen des Dokuments enthält. `GenerateAutosaveFileName`verwendet diese Dokument zum Generieren eines entsprechenden AutoSpeichern Datei namens.  
  
### <a name="return-value"></a>Rückgabewert  
 Der AutoSpeichern Dateiname generiert `strDocumentName`.  
  
### <a name="remarks"></a>Hinweise  
 Jedes der Dokumentname hat eine Zuordnung mit einem Dateinamen AutoSpeichern  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 Gibt das Intervall zwischen AutoSpeichern versucht zurück.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Millisekunden zwischen AutoSpeichern versucht.  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 Gibt den Pfad der Dateien automatisch gespeichert.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Speicherort, in dem die automatisch gespeicherte Dokumente gespeichert werden.  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 Ruft den Namen des Dokuments aus einer `CDocument` Objekt.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`. `GetDocumentListName`Ruft den Namen des Dokuments aus diesem `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Den Namen des Dokuments aus `pDocument`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CDataRecoveryHandler` verwendet den Namen des Dokuments als Schlüssel bei `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, und `m_mapDocNameToRestoreBool`. Aktivieren Sie diese Parameter dem `CDataRecoveryHandler` Überwachen `CDocument` Objekte, die AutoSpeichern-Dateiname und die AutoSpeichern-Einstellungen.  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 Ruft den normalen Titel für das angegebene Dokument ab.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf eine `CDocument`.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der normale Titel für das angegebene Dokument.  
  
### <a name="remarks"></a>Hinweise  
 Der normale Titel eines Dokuments ist normalerweise der Dateiname des Dokuments ohne Pfad. Dies ist der Titel in der **Dateiname** Feld der **speichern unter** (Dialogfeld).  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Erstellt und gibt den Titel für das wiederhergestellte Dokument.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strDocumentTitle`  
 Der normale Titel für das Dokument.  
  
### <a name="return-value"></a>Rückgabewert  
 Der wiederhergestellte Dokument-Titel.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist der wiederhergestellte Titel eines Dokuments der normalen Titel mit **[wiederhergestellt]** angefügt ist. Der wiederhergestellte Titel wird angezeigt, für den Benutzer bei der `CDataRecoveryHandler` fragt den Benutzer automatisch gespeicherte Dokumente wiederherstellen.  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 Ruft den Neustart des eindeutigen Bezeichner für die Anwendung.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Neustart des eindeutigen Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Die Neustart-Bezeichner ist eindeutig für jede Ausführung der Anwendung.  
  
 Die `CDataRecoveryHandler` speichert Informationen in der Registrierung über die derzeit geöffneten Dokumente. Wenn der Neustart-Manager eine Anwendung beendet und neu gestartet, stellt den Neustart-Bezeichner, der die `CDataRecoveryHandler`. Die `CDataRecoveryHandler` verwendet den Neustart-Bezeichner zum Abrufen der Liste der zuvor geöffneten Dokumente. Dies ermöglicht die `CDataRecoveryHandler` zu dem Versuch, suchen und Wiederherstellen von Dateien automatisch gespeichert.  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Gibt an, ob die `CDataRecoveryHandler` führt eine automatische Speicherung auf der aktuellen Leerlaufschleife.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, die `CDataRecoveryHandler` speichert auf der aktuellen Leerlaufschleife; `FALSE` gibt an, dies nicht der Fall.  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 Gibt an, ob der Neustart-Manager die zum Beenden der Anwendung verursacht.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass der Neustart-Manager die zum Beenden der Anwendung verursacht. `FALSE` gibt an, es war nicht der Fall.  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 Initialisiert das `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Initialisierung erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Initialisierungsprozess lädt den Pfad zum Speichern von AutoSpeichern-Dateien aus der Registrierung. Wenn die `Initialize` Methode dieses Verzeichnis kann nicht gefunden werden oder wenn der Pfad ist `NULL`, `Initialize` schlägt fehl, und gibt `FALSE`.  
  
 Verwendung [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) AutoSpeichern-Pfad zu ändern, nachdem die Anwendung initialisiert den `CDataRecoveryHandler`.  
  
 Die `Initialize` Methode wird ein Timer zu überwachen, den nächsten AutoSpeichern tritt auf, die auch gestartet. Verwendung [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) das Intervall für die automatische Speicherung zu ändern, nachdem Ihre Anwendung initialisiert den `CDataRecoveryHandler`.  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Zeigt ein Dialogfeld für den Benutzer an, für jedes Dokument, das die `CDataRecoveryHandler` automatisch gespeichert. Das Dialogfeld bestimmt, ob der Benutzer das Dokument automatisch wiederherstellen möchte.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung Unicode ist, zeigt diese Methode eine [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) für den Benutzer. Andernfalls verwendet das Framework [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) um vom Benutzer abzufragen.  
  
 Nach dem `QueryRestoreAutosavedDocuments` sammelt alle Antworten des Benutzers speichert die Informationen in die Membervariable `m_mapDocNameToRestoreBool`. Diese Methode ist die automatisch gespeicherte Dokumente nicht wiederherstellen.  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 Lädt die Liste der geöffneten Dokument aus der Registrierung.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass `ReadOpenDocumentList` die Informationen für mindestens ein Dokument aus der Registrierung geladen `FALSE` gibt an, keine Informationen im Dokument geladen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion lädt die geöffneten Dokumentinformationen aus der Registrierung und speichert ihn in die Membervariable `m_mapDocNameToAutosaveName`.  
  
 Nach dem `ReadOpenDocumentList` lädt alle Daten, die Dokumentinformationen werden aus der Registrierung gelöscht.  
  
##  <a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 Entfernt das angegebene Dokument aus der Liste der geöffneten Dokument.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf das Dokument zu entfernen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pDocument` entfernt wurde, aus der Liste. `FALSE` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer ein Dokument geschlossen wird, verwendet das Framework diese Methode so entfernen Sie es aus der Liste der geöffneten Dokumente.  
  
 Wenn `RemoveDocumentInfo` wurde nicht gefunden `pDocument` in der Liste der geöffneten Dokumente, es wird keine Aktion ausgeführt, und gibt `TRUE`.  
  
 Diese Methode verwendet `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 Öffnet die zuvor geöffneten Dokumente.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn mindestens ein Dokument geöffnet wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird dem letzten Speichern des zuvor geöffneten Dokumente geöffnet. Wenn ein Dokument wurde nicht gespeichert oder automatisch, `ReopenPreviousDocuments` wird ein leeres Dokument basierend auf der Vorlage für diesen Dateityp geöffnet.  
  
 Diese Methode verwendet `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`. Wenn dieser Parameter nicht festgelegt ist, `ReopenPreviousDocuments` keine Aktion aus und gibt `FALSE`.  
  
 Wenn es keine Dokumente, die in der Liste der zuvor geöffneten Dokumenten gespeichert sind `ReopenPreviousDocuments` keine Aktion aus und gibt `FALSE`.  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 Stellt Sie automatisch gespeicherte Dokumente basierend auf Benutzereingaben wieder her.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich Dokumente wiederherstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) um zu bestimmen, die den Benutzer Dokumente wiederherstellen möchte. Wenn ein Benutzer kein Dokument automatisch wiederherstellen `RestoreAutosavedDocuments` löscht die Sicherungsdatei. Andernfalls `RestoreAutosavedDocuments` das geöffnete Dokument durch die automatisch gespeicherte Version ersetzt.  
  
 Verwenden Sie diese Methode entweder `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` oder `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 Speichert die aktuelle Liste der geöffneten Dokumente zur Windows-Registrierung.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es keine offenen Dokumente sind zu speichern oder sie wurden erfolgreich gespeichert wurden. `FALSE`Wenn Dokumente in der Registrierung gespeichert sind, aber sie nicht gespeichert wurden, da ein Fehler aufgetreten ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Neustart-Manager ruft `SaveOpenDocumentList` bei die Anwendung unerwartet beendet wird oder wenn er für ein Upgrade beendet wird. Wenn die Anwendung neu gestartet wird, verwendet er [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) beim Abrufen der Liste der geöffneten Dokumente.  
  
 Diese Methode speichert nur die Liste der geöffneten Dokumente. Die Methode [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) ist verantwortlich für das Speichern der Dokumente selbst.  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 Legt die Zeit zwischen AutoSpeichern Zyklen in Millisekunden fest.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nAutosaveInterval`  
 Das neue AutoSpeichern Intervall in Millisekunden.  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 Legt das Verzeichnis, in dem Dateien automatisch gespeichert werden.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strAutosavePath`|Der Pfad, in dem AutoSpeichern-Dateien gespeichert sind.|  
  
### <a name="remarks"></a>Hinweise  
 Ändern das Verzeichnis AutoSpeichern verschoben nicht derzeit automatisch gespeicherte Dateien.  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 Den Neustart des eindeutigen Bezeichner für diese Instanz von legt die `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `strRestartIdentifier`|Der eindeutige Bezeichner für den Neustart-Manager.|  
  
### <a name="remarks"></a>Hinweise  
 Der Neustart-Manager zeichnet folgende Informationen über die offenen Dokumente in der Registrierung. Diese Informationen werden mit dem Neustart des eindeutigen Bezeichner als Schlüssel gespeichert. Da die Neustart-Bezeichner für jede Instanz einer Anwendung eindeutig ist, mehrere Instanzen einer Anwendung möglicherweise unerwartet beendet und der Neustart-Manager wiederhergestellt werden kann jede von ihnen.  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Legt fest, ob die `CDataRecoveryHandler` , speichert die geöffneten Dokumentinformationen zur Windows-Registrierung während der aktuellen im Leerlauf Zyklus.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bSaveOnIdle`|`TRUE`Um Dokumentinformationen während der aktuellen im Leerlauf Zyklus zu speichern. `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 Legt fest, ob es sich bei der vorherigen Beenden der Anwendung vom Neustart-Manager verursacht wurde.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `bShutdownByRestartManager`|`TRUE`um anzugeben, dass der Neustart-Manager die zum Beenden der Anwendung verursacht. `FALSE` , um anzugeben, dass die Anwendung aus einem anderen Grund beendet wurde.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verhält sich anders basierend auf, ob das vorherige Exit unerwartet war, oder gibt an, ob es von den Neustart-Manager initiiert wurde.  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 Aktualisiert die Informationen für ein Dokument an, da der Benutzer es gespeichert.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDocument`|Ein Zeiger auf das gespeicherte Dokument.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode das Dokument automatisch gelöscht, und die Dokumentinformationen aktualisiert; `FALSE` bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer ein Dokument speichert, entfernt die Anwendung die Datei automatisch, da es nicht mehr benötigt wird. `UpdateDocumentInfo`Löscht die Datei automatisch durch den Aufruf [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`fügt dann die Informationen aus `pDocument` zur Liste der derzeit geöffneten Dokumente da `RemoveDocumentInfo` löscht diese Informationen verwendet werden soll, sondern das gespeicherte Dokument noch geöffnet ist.  
  
 Diese Methode verwendet `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` muss festgelegt werden, `m_dwRestartManagerSupportFlags`.   
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Vorgehensweise: Hinzufügen von Unterstützung für den Neustart-Manager](../../mfc/how-to-add-restart-manager-support.md)


