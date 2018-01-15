---
title: COleDocObjectItem-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
dev_langs: C++
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 246c645dad5ed11fb5428e2f90ed9b9574696417
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem-Klasse
Implementiert "Active Document Containment".  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Erstellt eine `COleDocObject` Element.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DoDefaultPrinting](#dodefaultprinting)|Druckt die containeranwendung-Dokument mit den Standardeinstellungen für den Drucker.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Führt den Befehl, der vom Benutzer angegeben wird.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Ruft die aktive Ansicht des Dokuments ab.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten in der containeranwendung-Dokument ab.|  
|[COleDocObjectItem:: OnPreparePrinting](#onprepareprinting)|Bereitet die containeranwendung Dokument für den Druck.|  
|[COleDocObjectItem](#onprint)|Die containeranwendung Dokument gedruckt.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|  
|[COleDocObjectItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, falls er geöffnet ist. Die Client-Element wird nicht zerstört werden.|  
  
## <a name="remarks"></a>Hinweise  
 In MFC wird auf ähnliche Weise ein aktiven Dokuments behandelt, für das ein regulärer, direkte bearbeitbaren einbetten, in folgender Hinsicht:  
  
-   Die `COleDocument`-abgeleitete Klasse weiterhin verwaltet eine Liste der momentan eingebetteten Elemente; allerdings sind diese Elemente möglicherweise `COleDocObjectItem`-Elemente abgeleitet.  
  
-   Wenn ein aktiven Dokuments aktiv ist, belegt den gesamten Clientbereich der Ansicht, wenn es sich um in-Place aktiv ist.  
  
-   Active Document-Container verfügt über Vollzugriff auf die **Hilfe** Menü.  
  
-   Die **Hilfe** Menü enthält Menüelemente für die Active Document-Container und Server.  
  
 Da Active Document-Container besitzt die **Hilfe** im Menü der Container ist verantwortlich für Server weiterleiten **Hilfe** Menü Nachrichten an den Server. Diese Integration erfolgt durch `COleDocObjectItem`.  
  
 Weitere Informationen zur das Zusammenführen von Menüs und aktive Dokument Aktivierung finden Sie unter Übersicht [Active Document-Container](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Rufen Sie diese Memberfunktion zum Initialisieren der `COleDocObjectItem` Objekt.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pContainerDoc`  
 Ein Zeiger auf die `COleDocument` Objekt fungiert als active Document-Container. Dieser Parameter muss **NULL** aktivieren **IMPLEMENT_SERIALIZE**. Normalerweise werden OLE-Elementen erstellt, mit einem nicht- **NULL** Dokument Zeiger.  
  
##  <a name="dodefaultprinting"></a>DoDefaultPrinting  
 Vom Framework aufgerufen wird, ein Dokument mit den Standardeinstellungen.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl sendet.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Objekt, das den Auftrag zu druckende beschreibt.  
  
##  <a name="execcommand"></a>COleDocObjectItem::ExecCommand  
 Rufen Sie diese Memberfunktion zum Ausführen des Befehls, der vom Benutzer angegeben wird.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdID`  
 Der Bezeichner für den auszuführenden Befehl. Muss in der identifizierten Gruppe `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Gibt die befehlsausführung Optionen. Standardmäßig festgelegt, um den Befehl auszuführen, ohne den Benutzer aufzufordern. Finden Sie unter [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) für eine Liste von Werten.  
  
 `pguidCmdGroup`  
 Eindeutiger Bezeichner der Befehlsgruppe. Standardmäßig **NULL**, gibt die standard-Gruppe. Übergeben Sie der Befehl `nCmdID` müssen der Gruppe angehören.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` Wenn erfolgreich, andernfalls wird eine der folgenden Fehlercodes.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Unerwarteter Fehler ist aufgetreten.|  
|**E_FAIL**|Es ist ein Fehler aufgetreten.|  
|**E_NOTIMPL**|Gibt an MFC selbst sollten versuchen, übersetzen und verteilen den Befehl.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`ist ungleich **NULL** aber nicht an eine Gruppe Befehl erkannt.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`wird nicht als gültiger Befehl in der Gruppe pGroup erkannt.|  
|**OLECMDERR_DISABLED**|Der Befehl identifizierte `nCmdID` ist deaktiviert und kann nicht ausgeführt werden.|  
|**OLECMDERR_NOHELP**|Aufrufer aufgefordert Hilfe zum Befehl "identifizierte" `nCmdID` , aber es ist keine Hilfe verfügbar.|  
|**OLECMDERR_CANCELLED**|Die Ausführung wurde vom Benutzer abgebrochen.|  
  
### <a name="remarks"></a>Hinweise  
 Die `pguidCmdGroup` und `nCmdID` Parameter zusammen eindeutig identifizieren den Befehl zum Aufrufen. Die `nCmdExecOpt` Parameter gibt die genaue zu ergreifende Maßnahme.  
  
##  <a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die `IOleDocumentView` Schnittstelle, die derzeit aktive Ansicht.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) Schnittstelle, die derzeit aktive Ansicht. Wenn keine aktuelle Ansicht vorhanden ist, gibt es **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Der Verweiszähler für das zurückgegebene `IOleDocumentView` Zeiger wird nicht erhöht werden, bevor sie von dieser Funktion zurückgegeben werden.  
  
##  <a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Seiten, die im Dokument.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>Parameter  
 *pnFirstPage*  
 Ein Zeiger auf die Anzahl der ersten Seite des Dokuments. Kann **NULL**, dies bedeutet, dass den Aufrufer benötigt diese Zahl.  
  
 *pcPages*  
 Ein Zeiger auf die Gesamtanzahl der Seiten im Dokument. Kann **NULL**, dies bedeutet, dass den Aufrufer benötigt diese Zahl.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="onprepareprinting"></a>COleDocObjectItem:: OnPreparePrinting  
 Diese Memberfunktion wird durch das Framework für das Drucken ein Dokuments vorbereiten aufgerufen.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl sendet.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Objekt, das den Auftrag zu druckende beschreibt.  
  
 `bPrintAll`  
 Gibt an, ob das gesamte Dokument gedruckt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="onprint"></a>COleDocObjectItem  
 Diese Memberfunktion wird vom Framework zum Drucken eines Dokuments aufgerufen.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf ein CView-Objekt, das den Druckbefehl sendet.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) Objekt, das den Auftrag zu druckende beschreibt.  
  
 `bPrintAll`  
 Gibt an, ob das gesamte Dokument gedruckt werden soll.  
  
##  <a name="querycommand"></a>COleDocObjectItem::QueryCommand  
 Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdID`  
 Der Bezeichner des Befehls abgefragt wird.  
  
 `pdwStatus`  
 Ein Zeiger auf die Flags, die als Ergebnis der Abfrage zurückgegeben wurden. Eine Liste der möglichen Werte finden Sie unter [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237).  
  
 `pCmdText`  
 Zeiger auf eine [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) Struktur in den Namen und den Status der Informationen eines einzelnen Befehls zurückgegeben. Kann **NULL** um anzugeben, dass der Aufrufer diese Informationen nicht benötigt.  
  
 `pguidCmdGroup`  
 Eindeutiger Bezeichner der Befehlsgruppe; kann **NULL** der Standardgruppe angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine vollständige Liste von Werten, finden Sie unter [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) -Methode, wie im Windows SDK beschrieben.  
  
##  <a name="release"></a>COleDocObjectItem::Release  
 Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, falls er geöffnet ist. Die Client-Element wird nicht zerstört werden.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCloseOption`  
 Kennzeichen, das angibt, unter welchen Umständen der OLE-Element gespeichert wird, wenn er in den geladenen Zustand zurückversetzt. Eine Liste der möglichen Werte finden Sie unter [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Hinweise  
 Die Client-Element wird nicht zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)
