---
title: COleDataSource-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
dev_langs:
- C++
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d67165d3869ffdd60eff86fa8c33abf275e070b4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209776"
---
# <a name="coledatasource-class"></a>COleDataSource-Klasse
Dient als Cache, in den eine Anwendung die Daten für Datenübertragungsoperationen ablegt, beispielsweise bei Zwischenablage- oder Drag & Drop-Operationen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Erstellt ein `COleDataSource`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CacheData](#cachedata)|Stellt Daten in einem angegebenen Format mithilfe einer `STGMEDIUM` Struktur.|  
|[COleDataSource:: CacheGlobalData](#cacheglobaldata)|Stellt Daten in einem angegebenen Format HGLOBAL verwenden.|  
|[:: DelayRenderData](#delayrenderdata)|Stellt Daten in einem angegebenen Format mit verzögertem Rendering.|  
|[DelayRenderFileData](#delayrenderfiledata)|Stellt Daten in einem angegebenen Format in eine `CFile` Zeiger.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Wird aufgerufen, für jedes Format, das unterstützt wird `OnSetData`.|  
|[Oledatasource:: DoDragDrop](#dodragdrop)|Führt Drag & Drop-Vorgänge mit einer Datenquelle.|  
|[COleDataSource::Empty](#empty)|Leert den `COleDataSource` Datenobjekts.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Rendert alle Daten in der Zwischenablage.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Überprüft, ob die Daten in der Zwischenablage platziert immer noch vorhanden ist.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Ruft die Daten im Rahmen der verzögerte Rendering ab.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in einem `CFile` als Teil des verzögerte Rendering.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Ruft die Daten in HGLOBAL als Teil des verzögerte Rendering ab.|  
|[COleDataSource::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten im Ersetzen der `COleDataSource` Objekt.|  
|[COleDataSource](#setclipboard)|Stellen eine `COleDataSource` Objekt in der Zwischenablage.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die OLE-Datenquellen direkt erstellen. Klicken Sie alternativ die [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md) Klassen erstellen OLE-Datenquellen als Reaktion auf ihre `CopyToClipboard` und `DoDragDrop` Memberfunktionen. Finden Sie unter [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) für eine kurze Beschreibung. Überschreiben der `OnGetClipboardData` Memberfunktion Ihrer Client-Element oder Server-Element-Klasse zum Hinzufügen von zusätzlicher Zwischenablageformaten auf die Daten in der OLE-Datenquelle erstellt wird, für die `CopyToClipboard` oder `DoDragDrop` Member-Funktion.  
  
 Nach Wunsch zur Vorbereitung von Daten für die Übertragung, sollten Sie ein Objekt dieser Klasse erstellen und über die am besten geeignete Methode für Ihre Daten mit Ihren Daten füllen. Die Möglichkeit, die in einer Datenquelle eingefügt wird direkt betroffen, ob die Daten sofort bereitgestellt werden (unmittelbares Rendern) als auch bedarfsgesteuert (verzögertes rendering). Für jedes Zwischenablageformat, in dem Sie Daten durch übergeben das Format der Zwischenablage zu verwendende bereitstellen (und optional [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur), rufen Sie [DelayRenderData](#delayrenderdata).  
  
 Weitere Informationen zu Datenquellen und die Datenübertragung, finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Darüber hinaus den Artikel [Zwischenablage Themen](../../mfc/clipboard.md) des OLE-zwischenablagemechanismus beschreibt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="cachedata"></a>  CacheData  
 Rufen Sie diese Funktion um ein Format anzugeben, in denen Daten bei datentransfervorgänge angeboten werden.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpStgMedium*  
 Verweist auf eine [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur, die die Daten im angegebenen Format enthält.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen die Daten angeben, da diese Funktion, die sie mithilfe der unmittelbaren Rendering bereitstellt. Die Daten werden zwischengespeichert, bis Sie benötigt.  
  
 Geben Sie die Daten mithilfe einer [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur. Sie können auch die `CacheGlobalData` Memberfunktion, wenn die Menge der Daten, die Sie angegeben haben, ist klein genug, um effizient mit HGLOBAL übertragen werden.  
  
 Nach dem Aufruf von `CacheData` der `ptd` Mitglied `lpFormatEtc` und den Inhalt der *LpStgMedium* werden, gehören das Datenobjekt nicht durch den Aufrufer.  
  
 Um verzögerte Rendering zu verwenden, rufen die [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter den [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Strukturen im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="cacheglobaldata"></a>  COleDataSource:: CacheGlobalData  
 Rufen Sie diese Funktion um ein Format anzugeben, in denen Daten bei datentransfervorgänge angeboten werden.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *hGlobal*  
 Handle für den globalen Speicherblock, der die Daten im angegebenen Format enthält.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet, die Daten mithilfe von sofort zu rendern, damit Sie die Daten angeben müssen, wenn die Funktion aufgerufen wird; die Daten werden zwischengespeichert, bis Sie benötigt. Verwenden der `CacheData` Memberfunktion, wenn Sie eine große Menge an Daten oder wenn Sie einem strukturierten Speichermedium benötigen angeben.  
  
 Um verzögerte Rendering zu verwenden, rufen die [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="coledatasource"></a>  COleDataSource::COleDataSource  
 Erstellt ein `COleDataSource`-Objekt.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>  :: DelayRenderData  
 Rufen Sie diese Funktion um ein Format anzugeben, in denen Daten bei datentransfervorgänge angeboten werden.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet es sich um die Daten mit verzögerte rendering, damit die Daten nicht direkt bereitgestellt werden. Die [OnRenderData](#onrenderdata) oder [OnRenderGlobalData](#onrenderglobaldata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie nicht beabsichtigen, Ihre Daten durch Angeben einer `CFile` Objekt. Wenn Sie beabsichtigen, die Daten durch Angeben einer `CFile` Objekt, rufen Sie die [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Um sofortige Rendering zu verwenden, rufen die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Member-Funktion.  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="delayrenderfiledata"></a>  DelayRenderFileData  
 Rufen Sie diese Funktion um ein Format anzugeben, in denen Daten bei datentransfervorgänge angeboten werden.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet es sich um die Daten mit verzögerte rendering, damit die Daten nicht direkt bereitgestellt werden. Die [OnRenderFileData](#onrenderfiledata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie beabsichtigen, verwenden Sie eine `CFile` Objekt, das die Daten angeben. Wenn Sie nicht beabsichtigen, mit einer `CFile` Objekt, rufen Sie die [DelayRenderData](#delayrenderdata) Member-Funktion. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Um sofortige Rendering zu verwenden, rufen die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Member-Funktion.  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData  
 Mit dieser Funktion können Sie ändern den Inhalt der Datenquelle unterstützt.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Zwischenablageformat, in dem die Daten ist, platziert werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in dem die Daten sind, ersetzt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 [OnSetData](#onsetdata) wird vom Framework aufgerufen, wenn dies geschieht. Wird nur verwendet, wenn das Framework die Datenquelle gibt [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Wenn `DelaySetData` nicht aufgerufen wird, Ihre `OnSetData` Funktion wird nie aufgerufen werden. `DelaySetData` für jede Zwischenablage aufgerufen werden soll oder `FORMATETC` Format, die Sie unterstützen.  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="dodragdrop"></a>  Oledatasource:: DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion versucht, die in der Regel führen Sie einen Drag & Drop-Vorgang für diese Datenquelle in eine [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) Handler.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Parameter  
*dwEffects*  
Drag & Drop-Vorgänge, die zulässig sind für diese Datenquelle. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
 - Es konnte DROPEFFECT_COPY ein Kopiervorgang ausgeführt werden.  
      
 - Es konnte DROPEFFECT_MOVE ein Verschiebevorgang ausgeführt werden.  
      
 - DROPEFFECT_LINK ein Link von der abgelegten Daten auf die Originaldaten konnte hergestellt werden.  
      
 - DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für das Scrollen auftreten können.  
  
*lpRectStartDrag*  
Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang tatsächlich gestartet. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
*pDropSource*  
Verweist auf eine Drop-Quelle. Wenn NULL, dann eine Standardimplementierung der [COleDropSource](../../mfc/reference/coledropsource-class.md) verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Löschen Sie die Auswirkungen, die von dem Drag & Drop-Vorgang generierte; andernfalls DROPEFFECT_NONE, wenn der Vorgang nicht gestartet, da der Benutzer die Maustaste losgelassen, vor dem Verlassen des angegebenen Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Der Drag & Drop-Vorgang wird nicht sofort gestartet. Er wartet, bis der Mauszeiger das durch angegebene Rechteck verlässt *LpRectStartDrag* oder eine angegebene Anzahl von Millisekunden verstrichen sind. Wenn *LpRectStartDrag* NULL ist, die Größe des Rechtecks ist 1 Pixel.  
  
 Die Verzögerungszeit wird durch eine registrierungsschlüsseleinstellung angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der Windows-Taste gespeichert. INI-Datei unter dem [Windows}-Abschnitt.  
  
-   Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version des Windows-Taste gespeichert. INI.  
  
 Für Weitere Informationen ziehen wird der Informationen in der Registrierung gespeichert oder. INI-Datei finden Sie unter [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) im Windows SDK.  
  
 Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren einer Drop-Quelle](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="empty"></a>  COleDataSource::Empty  
 Mit dieser Funktion wird zum Leeren der `COleDataSource` Datenobjekts.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Hinweise  
 Beide zwischengespeichert und Verzögerung renderingformate werden geleert, sodass sie wiederverwendet werden können.  
  
 Weitere Informationen finden Sie unter [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) im Windows SDK.  
  
##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard  
 Rendert die Daten, die in der Zwischenablage, und klicken Sie dann können Sie die Daten aus der Zwischenablage einfügen, nachdem die Anwendung beendet.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [SetClipboard](#setclipboard) zum Einfügen von Daten in die Zwischenablage.  
  
##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner  
 Bestimmt, ob die Daten in der Zwischenablage, seit geändert hat [SetClipboard](#setclipboard) zuletzt aufgerufen wurde, und, wenn dies der Fall ist, identifiziert den aktuellen Besitzer.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datenquelle derzeit in der Zwischenablage, oder NULL zurück, wenn es keine Werte in die Zwischenablage, oder wenn die Zwischenablage nicht von der aufrufenden Anwendung gehört.  
  
##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 *lpFormatEtc*  
 Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 *lpStgMedium*  
 Verweist auf eine [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur, in dem die Daten zurückgegeben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion für das verzögerte Rendering. Ruft die standardmäßige Implementierung dieser Funktion [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata) Wenn das angegebene Speichermedium eine Datei oder einen Speicher ist. Wenn keines dieser Formate angegeben werden, wird die Standardimplementierung gibt 0 zurück, und keine Aktion durchführen. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Wenn *LpStgMedium*-> *Tymed* TYMED_NULL, ist die `STGMEDIUM` zugeordnet, und laut gefüllt werden soll *LpFormatEtc -> Tymed*. Wenn es sich nicht um TYMED_NULL, ist die `STGMEDIUM` mit Daten ausgefüllt werden.  
  
 Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Ihre Daten kleine und fester Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter den [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Strukturen, die [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) Enumerationstyp ist, und [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) in der Windows SDK.  
  
##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das angegebene Speichermedium eine Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 *lpFormatEtc*  
 Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 *pFile-Datei*  
 Verweist auf eine [CFile](../../mfc/reference/cfile-class.md) Objekt, in dem die Daten gerendert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die Standardimplementierung dieser Funktion gibt einfach "false" zurück.  
  
 Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`. Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur und [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) im Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das angegebene Speichermedium globaler Speicher ist.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parameter  
 *lpFormatEtc*  
 Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 *phGlobal*  
 Verweist auf ein Handle für den globalen Arbeitsspeicher, die in der die Daten sind, zurückgegeben werden. Wenn eine noch nicht belegt wurde, kann dieser Parameter NULL sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die Standardimplementierung dieser Funktion gibt einfach "false" zurück.  
  
 Wenn *PhGlobal* NULL ist, und klicken Sie dann eine neue HGLOBAL zugeordnet und in zurückgegeben werden soll *PhGlobal*. Andernfalls anhand der HGLOBAL *PhGlobal* mit Daten gefüllt werden soll. Die Menge der Daten, die in der HGLOBAL platziert darf die aktuelle Größe des Speicherblocks nicht überschreiten. Darüber hinaus kann nicht der Block auf einen größeren verschoben werden.  
  
 Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata). Weitere Informationen zum verzögerten Rendern von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur und [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) im Windows SDK.  
  
##  <a name="onsetdata"></a>  COleDataSource::OnSetData  
 Wird aufgerufen, durch das Framework zum Festlegen oder ersetzen die Daten in die `COleDataSource` Objekt im angegebenen Format.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 *lpFormatEtc*  
 Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) -Struktur gibt das Format, in dem Daten ausgetauscht werden.  
  
 *lpStgMedium*  
 Verweist auf die [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur, die mit den Daten, die den aktuellen Inhalt des ersetzt die `COleDataSource` Objekt.  
  
 *bRelease*  
 Gibt an, die das Speichermedium nach Abschluss des Funktionsaufrufs ist. Der Aufrufer entscheidet, die verantwortlich für die Freigabe der Ressourcen, die für das Speichermedium zugeordnet ist. Der Aufrufer wird durch Festlegen von *bRelease*. Wenn *bRelease* ist ungleich NULL ist, die die Datenquelle übernimmt die Besitzrechte, Freigeben des Mediums, wenn es abgeschlossen ist, verwenden. Wenn *bRelease* ist 0, der Aufrufer besitzt und die Datenquelle kann das Speichermedium nur für die Dauer des Aufrufs verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquelle wird nicht den Besitz der Daten, bis er erfolgreich abgerufen hat. D. h. es wird nicht den Besitz übernehmen Wenn `OnSetData` gibt 0 zurück. Wenn die Datenquelle den Besitz übernimmt, werden durch Aufrufen von das Speichermedium freigibt der [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Funktion.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion zum Ersetzen der Daten im angegebenen Format. Dies ist ein fortschrittlicher überschreibbar.  
  
 Weitere Informationen finden Sie unter den [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Strukturen und [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) und [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) die Funktionen im Windows SDK.  
  
##  <a name="setclipboard"></a>  COleDataSource  
 Legt die Daten in die `COleDataSource` Objekt in der Zwischenablage nach dem Aufrufen einer der folgenden Funktionen: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), oder [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataObject-Klasse](../../mfc/reference/coledataobject-class.md)
