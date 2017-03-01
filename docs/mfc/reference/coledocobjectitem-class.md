---
title: COleDocObjectItem-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocObjectItem
dev_langs:
- C++
helpviewer_keywords:
- COleDocObjectItem class
- document object containment
- containment
- containment, doc object
- doc object containment
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0815454fa4b194e97a2d16a621cfc25da61d5fd0
ms.lasthandoff: 02/24/2017

---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem-Klasse
Implementiert "Active Document Containment".  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Erstellt ein `COleDocObject` Element.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DoDefaultPrinting](#dodefaultprinting)|Wird der Container-Anwendung-Dokument mit den Standardeinstellungen für den Drucker gedruckt.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Führt den Befehl vom Benutzer angegeben.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Ruft die aktive Ansicht des Dokuments ab.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten in der Container-Anwendung Dokument ab.|  
|[COleDocObjectItem:: OnPreparePrinting](#onprepareprinting)|Wird der Container-Anwendung-Dokument für das Drucken vorbereitet.|  
|[COleDocObjectItem](#onprint)|Wird der Container-Anwendung Dokument gedruckt.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|  
|[COleDocObjectItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei und wieder geschlossen, wenn er geöffnet war. Die Client-Element wird nicht zerstört werden.|  
  
## <a name="remarks"></a>Hinweise  
 In MFC wird ein aktives Dokument ähnlich behandelt, um eine reguläre, direkte bearbeitbaren einbetten, mit den folgenden unterschieden:  
  
-   Die `COleDocument`-abgeleiteten Klasse verwaltet eine Liste der momentan eingebetteten Elemente nach wie vor; allerdings sind diese Elemente möglicherweise `COleDocObjectItem`-abgeleiteten Elemente.  
  
-   Wenn ein active Document aktiv ist, belegt den gesamten Clientbereich der Ansicht, wenn es direkt aktiv ist.  
  
-   Active Document-Container verfügt über Vollzugriff auf die **Hilfe** Menü.  
  
-   Die **Hilfe** Menü enthält Menüelemente für Active Document-Container und Server.  
  
 Active Document-Container besitzt die **Hilfe** im Menü der Container ist dafür verantwortlich, Server **Hilfe** Menü Nachrichten an den Server. Diese Integration erfolgt über `COleDocObjectItem`.  
  
 Weitere Informationen über das Zusammenführen von Menüs und Active Document-Aktivierung finden Sie unter Übersicht über die [Active Document-Container](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-namecoledocobjectitema--coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Rufen Sie diese Memberfunktion zum Initialisieren der `COleDocObjectItem` Objekt.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pContainerDoc`  
 Ein Zeiger auf die `COleDocument` Objekt fungiert als active Document-Container. Dieser Parameter muss **NULL** aktivieren **IMPLEMENT_SERIALIZE**. Normalerweise werden OLE-Elemente mit einem nicht-erstellt **NULL** Dokument Zeiger.  
  
##  <a name="a-namedodefaultprintinga--coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a>DoDefaultPrinting  
 Aufgerufen, um ein Dokument mit den Standardeinstellungen.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl gesendet wird.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden.  
  
##  <a name="a-nameexeccommanda--coledocobjectitemexeccommand"></a><a name="execcommand"></a>COleDocObjectItem::ExecCommand  
 Rufen Sie diese Memberfunktion zum Ausführen des Befehls, der vom Benutzer angegeben.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nCmdID`  
 Der Bezeichner des auszuführenden Befehls. Muss in der identifizierten Gruppe `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Gibt die Ausführung des Befehls Optionen. Standardmäßig festgelegt, um den Befehl auszuführen, ohne den Benutzer aufzufordern. Finden Sie unter [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) für eine Liste von Werten.  
  
 `pguidCmdGroup`  
 Eindeutiger Bezeichner der Befehlsgruppe. In der Standardeinstellung **NULL**, gibt die Gruppe an. Der Befehl übergebenen `nCmdID` müssen der Gruppe angehören.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` Wenn erfolgreich, andernfalls wird eine der folgenden Fehlercodes.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Unerwarteter Fehler aufgetreten.|  
|**E_FAIL**|Es ist ein Fehler aufgetreten.|  
|**E_NOTIMPL**|Gibt an MFC selbst sollten versuchen, übersetzen und verteilen den Befehl.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`ist ungleich **NULL** , aber eine Gruppe bekannter Befehl angeben.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`wird nicht als gültiger Befehl in der Gruppe pGroup erkannt.|  
|**OLECMDERR_DISABLED**|Der Befehl identifizierten `nCmdID` ist deaktiviert und kann nicht ausgeführt werden.|  
|**OLECMDERR_NOHELP**|Aufrufer aufgefordert Hilfe zum Befehl identifizierten `nCmdID` , aber es ist keine Hilfe verfügbar.|  
|**OLECMDERR_CANCELLED**|Die Ausführung wurde vom Benutzer abgebrochen.|  
  
### <a name="remarks"></a>Hinweise  
 Die `pguidCmdGroup` und `nCmdID` Parameter zusammen aufzurufenden Befehls eindeutig zu identifizieren. Die `nCmdExecOpt` Parameter gibt die genaue auszuführende Aktion an.  
  
##  <a name="a-namegetactiveviewa--coledocobjectitemgetactiveview"></a><a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die `IOleDocumentView` Schnittstelle, die derzeit aktive Ansicht.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) Schnittstelle, die derzeit aktive Ansicht. Wenn keine aktuelle Ansicht vorhanden ist, wird **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Der Verweiszähler für das zurückgegebene `IOleDocumentView` Zeiger wird nicht erhöht, bevor sie die von dieser Funktion zurückgegeben wird.  
  
##  <a name="a-namegetpagecounta--coledocobjectitemgetpagecount"></a><a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Seiten im Dokument ab.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>Parameter  
 *pnFirstPage*  
 Ein Zeiger auf die Anzahl der ersten Seite des Dokuments. Kann **NULL**, gibt der Aufrufer an diese Nummer brauchen nicht.  
  
 *pcPages*  
 Ein Zeiger auf die Gesamtanzahl der Seiten im Dokument. Kann **NULL**, gibt der Aufrufer an diese Nummer brauchen nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-nameonprepareprintinga--coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a>COleDocObjectItem:: OnPreparePrinting  
 Diese Memberfunktion heißt vom Framework an ein Dokument für den Druck vorzubereiten.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl gesendet wird.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden.  
  
 `bPrintAll`  
 Gibt an, ob das gesamte Dokument gedruckt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-nameonprinta--coledocobjectitemonprint"></a><a name="onprint"></a>COleDocObjectItem  
 Diese Member-Funktion wird vom Framework zum Drucken eines Dokuments aufgerufen.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pCaller`  
 Ein Zeiger auf ein CView-Objekt, das den Druckbefehl gesendet wird.  
  
 `pInfo`  
 Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden.  
  
 `bPrintAll`  
 Gibt an, ob das gesamte Dokument gedruckt werden soll.  
  
##  <a name="a-namequerycommanda--coledocobjectitemquerycommand"></a><a name="querycommand"></a>COleDocObjectItem::QueryCommand  
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
 Zeiger auf eine [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) Struktur in der Name und Status eines einzelnen Befehls zurückgegeben. Kann **NULL** an, dass der Aufrufer diese Informationen nicht benötigt.  
  
 `pguidCmdGroup`  
 Eindeutiger Bezeichner der Befehlsgruppe. kann **NULL** der Standardgruppe angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine vollständige Liste von Werten, finden Sie unter [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) -Methode auf, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereleasea--coledocobjectitemrelease"></a><a name="release"></a>COleDocObjectItem::Release  
 Die Verbindung mit einer OLE-Element verknüpfte frei und wieder geschlossen, wenn er geöffnet war. Die Client-Element wird nicht zerstört werden.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCloseOption`  
 Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Eine Liste der möglichen Werte finden Sie unter [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Hinweise  
 Die Client-Element wird nicht zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)

