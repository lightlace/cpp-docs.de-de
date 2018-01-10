---
title: COleDataSource-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ce9abdccba549e0b0fd3c55bfb7fbaee6a11e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CacheData](#cachedata)|Bietet die Daten in einem angegebenen Format mithilfe einer **STGMEDIUM** Struktur.|  
|[COleDataSource:: CacheGlobalData](#cacheglobaldata)|Bietet die Daten in einem angegebenen Format mithilfe einer `HGLOBAL`.|  
|[:: DelayRenderData](#delayrenderdata)|Stellt Daten in einem angegebenen Format mit verzögertem Rendering.|  
|[DelayRenderFileData](#delayrenderfiledata)|Bietet die Daten in einem angegebenen Format in eine `CFile` Zeiger.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Wird aufgerufen, für jedes Format, das unterstützt wird `OnSetData`.|  
|[Oledatasource](#dodragdrop)|Führt Drag-and-Drop-Vorgänge mit einer Datenquelle.|  
|[COleDataSource::Empty](#empty)|Leert die `COleDataSource` Objekt der Daten.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Rendert alle Daten in der Zwischenablage.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Überprüft, ob die Daten in der Zwischenablage platziert noch vorhanden ist.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Ruft die Daten als Teil der verzögerte Rendering ab.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in eine `CFile` im Rahmen des verzögerte Rendering.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Abrufen von Daten in eine `HGLOBAL` im Rahmen des verzögerte Rendering.|  
|[COleDataSource::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten im Ersetzen der `COleDataSource` Objekt.|  
|[COleDataSource](#setclipboard)|Stellen ein `COleDataSource` Objekt in die Zwischenablage.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die OLE-Datenquellen direkt erstellen. Klicken Sie alternativ die [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md) Klassen erstellen OLE-Datenquellen als Antwort auf ihre `CopyToClipboard` und `DoDragDrop` Memberfunktionen. Finden Sie unter [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) für eine kurze Beschreibung. Überschreiben Sie die `OnGetClipboardData` Memberfunktion Ihrer Client-Element oder Server-Element-Klasse hinzufügen Weitere Zwischenablageformate auf die Daten in der OLE-Datenquelle erstellt wird, für die `CopyToClipboard` oder `DoDragDrop` Memberfunktion.  
  
 Wenn Sie Daten für eine Übertragung vorbereiten möchten, sollten Sie ein Objekt dieser Klasse erstellen und füllen Sie es mit Ihren Daten, die am besten geeignete Methode für Ihre Daten mit. Die Möglichkeit, die in einer Datenquelle eingefügt wird direkt betroffen, ob die Daten sofort bereitgestellt werden (sofortige Rendering) oder bei Bedarf (verzögertes rendering). Für jedes Format der Zwischenablage in die Daten durch übergeben das Format der Zwischenablage zu verwendende bereitgestellt (und optional [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur), rufen Sie [DelayRenderData](#delayrenderdata).  
  
 Weitere Informationen zu Datenquellen und die Datenübertragung, finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Darüber hinaus den Artikel [Zwischenablage Themen](../../mfc/clipboard.md) des OLE-zwischenablagemechanismus beschreibt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="cachedata"></a>CacheData  
 Mit dieser Funktion wird zum Festlegen eines Formats, in dem Daten während der Daten Vorgänge angeboten werden.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablage-Format, in dem die Daten zur Verfügung gestellt werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, die die Daten im angegebenen Format enthält.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem die Daten zur Verfügung gestellt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen die Daten angeben, da diese Funktion bietet sofortigen Rendering mit. Die Daten werden zwischengespeichert, bis Sie benötigt.  
  
 Geben Sie die Daten mithilfe einer [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur. Sie können auch die `CacheGlobalData` Memberfunktion, wenn die Menge der Daten, die Sie angegeben haben, ist klein genug für effizient übertragen werden eine `HGLOBAL`.  
  
 Nach dem Aufruf von `CacheData` der **Ptd** Mitglied `lpFormatEtc` und den Inhalt der `lpStgMedium` werden, gehören das Datenobjekt, nicht durch den Aufrufer.  
  
 Rufen Sie zum Verwenden von verzögertem Rendering der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Memberfunktion. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Strukturen im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="cacheglobaldata"></a>COleDataSource:: CacheGlobalData  
 Mit dieser Funktion wird zum Festlegen eines Formats, in dem Daten während der Daten Vorgänge angeboten werden.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablage-Format, in dem die Daten zur Verfügung gestellt werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 *hGlobal*  
 Handle für den globalen Speicherblock, der Daten im angegebenen Format enthält.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem die Daten zur Verfügung gestellt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet, die Daten mit sofortige rendern, sodass Sie die Daten angeben müssen, wenn die Funktion aufgerufen wird; die Daten werden zwischengespeichert, bis Sie benötigt. Verwenden der `CacheData` Memberfunktion, wenn Sie eine große Menge an Daten oder wenn Sie eine strukturierte Speichermedium benötigen angegeben haben.  
  
 Rufen Sie zum Verwenden von verzögertem Rendering der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Memberfunktion. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="coledatasource"></a>COleDataSource::COleDataSource  
 Erstellt ein `COleDataSource`-Objekt.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>:: DelayRenderData  
 Mit dieser Funktion wird zum Festlegen eines Formats, in dem Daten während der Daten Vorgänge angeboten werden.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablage-Format, in dem die Daten zur Verfügung gestellt werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem die Daten zur Verfügung gestellt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet die Daten mit verzögerte rendering, damit die Daten nicht direkt bereitgestellt werden. Die [OnRenderData](#onrenderdata) oder [OnRenderGlobalData](#onrenderglobaldata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie nicht beabsichtigen, Ihre Daten durch Angeben einer `CFile` Objekt. Wenn Sie beabsichtigen, die Daten durch Angeben einer `CFile` -Objekt, rufen Sie die [DelayRenderFileData](#delayrenderfiledata) Memberfunktion. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Rufen Sie zum sofortigen Rendering verwenden die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Memberfunktion.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="delayrenderfiledata"></a>DelayRenderFileData  
 Mit dieser Funktion wird zum Festlegen eines Formats, in dem Daten während der Daten Vorgänge angeboten werden.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablage-Format, in dem die Daten zur Verfügung gestellt werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem die Daten zur Verfügung gestellt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet die Daten mit verzögerte rendering, damit die Daten nicht direkt bereitgestellt werden. Die [OnRenderFileData](#onrenderfiledata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie beabsichtigen, mit einem `CFile` die Daten zu verwendendes Objekt. Wenn Sie nicht vorhaben, verwenden Sie eine `CFile` -Objekt, rufen Sie die [DelayRenderData](#delayrenderdata) Memberfunktion. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Rufen Sie zum sofortigen Rendering verwenden die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Memberfunktion.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="delaysetdata"></a>COleDataSource::DelaySetData  
 Mit dieser Funktion können Sie ändern den Inhalt der Datenquelle unterstützt.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format der Zwischenablage, in dem die Daten abgelegt werden soll. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem die Daten ersetzt werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 [OnSetData](#onsetdata) wird vom Framework aufgerufen, wenn dies geschieht. Dies wird nur verwendet, wenn das Framework gibt die Datenquelle aus [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Wenn `DelaySetData` nicht aufgerufen wird, Ihre `OnSetData` Funktion wird nie aufgerufen werden. `DelaySetData`sollte für jede Zwischenablage aufgerufen werden oder **FORMATETC** Format, die Sie unterstützen.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="dodragdrop"></a>Oledatasource  
 Rufen Sie die `DoDragDrop` Memberfunktion versucht, in der Regel führen Sie einen Drag-and-Drop-Vorgang für diese Datenquelle in eine [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) Handler.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwEffects`  
 Drag & Drop-Vorgänge, die zulässig sind für diese Datenquelle. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_COPY`Ein Vorgang zum Kopieren konnte ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Es konnte ein Verschiebevorgang ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten konnte hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass es sich bei Auftreten ein Ziehvorgangs ein Bildlauf.  
  
 `lpRectStartDrag`  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
 *pDropSource*  
 Verweist auf eine Drop-Quelle. Wenn **NULL** klicken Sie dann eine Standardimplementierung von [COleDropSource](../../mfc/reference/coledropsource-class.md) verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Löschen Sie die Auswirkungen von dem Drag-and-Drop-Vorgang generierte; andernfalls `DROPEFFECT_NONE` , wenn der Vorgang nie gestartet werden, da der Benutzer die Maustaste losgelassen, vor dem Verlassen des angegebenen Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Die Drag-and-Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor auf das Rechteck, angegeben durch verlässt `lpRectStartDrag` oder bis eine angegebene Anzahl von Millisekunden erfolgreich abgeschlossen wurden. Wenn `lpRectStartDrag` ist **NULL**, die Größe des Rechtecks beträgt ein Pixel.  
  
 Die Verzögerung wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit werden wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version der WIN gespeichert. INI.  
  
 Für Weitere Informationen ziehen wird Verzögerung Informationen gespeichert, in der Registrierung oder der. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) im Windows SDK.  
  
 Weitere Informationen finden Sie im Artikel [Drag & Drop: Implementieren einer Drag & Drop Quelle](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="empty"></a>COleDataSource::Empty  
 Rufen Sie diese Funktion einen leeren der `COleDataSource` Objekt der Daten.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Hinweise  
 Beide zwischengespeichert und Verzögerung renderingformate werden geleert, sodass sie wiederverwendet werden können.  
  
 Weitere Informationen finden Sie unter [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) im Windows SDK.  
  
##  <a name="flushclipboard"></a>COleDataSource::FlushClipboard  
 Rendert die Daten, die in die Zwischenablage, und dann können Sie die Daten aus der Zwischenablage einfügen, nachdem die Anwendung beendet wird.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [SetClipboard](#setclipboard) , die Daten in die Zwischenablage zu speichern.  
  
##  <a name="getclipboardowner"></a>COleDataSource::GetClipboardOwner  
 Bestimmt, ob die Daten in der Zwischenablage, seit geändert hat [SetClipboard](#setclipboard) zuletzt aufgerufen wurde, und wenn dies der Fall ist, identifiziert den aktuellen Besitzer.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datenquelle derzeit in der Zwischenablage oder **NULL** Wenn nichts in die Zwischenablage, oder wenn die Zwischenablage nicht von der aufrufenden Anwendung gehört.  
  
##  <a name="onrenderdata"></a>COleDataSource::OnRenderData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in dem die Daten zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Memberfunktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion rufen [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata) Wenn das angegebene Speichermedium eine Datei oder einen Arbeitsspeicher ist. Wenn keines dieser Formate angegeben werden, wird die standardmäßige Implementierung gibt 0 zurück und Unternehmen Sie nichts. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Wenn `lpStgMedium` ->  *Tymed* ist **TYMED_NULL**, **STGMEDIUM** reserviert und entsprechend den Angaben von gefüllt werden soll *LpFormatEtc -> TYMED*. Ist er nicht **TYMED_NULL**, **STGMEDIUM** direkt mit den Daten ausgefüllt werden soll.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten können Sie eine der anderen Versionen dieser Funktion stattdessen überschreiben möchten. Wenn Ihre Daten klein und fester Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Strukturen, die [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Enumerationstyp und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) im Windows SDK.  
  
##  <a name="onrenderfiledata"></a>COleDataSource::OnRenderFileData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das Speichermedium für die angegebene Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 `pFile`  
 Verweist auf eine [CFile](../../mfc/reference/cfile-class.md) Objekt, in dem die Daten gerendert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Memberfunktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion gibt einfach auftragsantwortnachrichten zurück **"false"**.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Je nach Ihrer Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben `OnRenderFileData`. Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) im Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das angegebene Speichermedium globaler Speicher ist.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 `phGlobal`  
 Verweist auf ein Handle für den globalen Arbeitsspeicher, in dem die Daten zurückgegeben werden. Dieser Parameter kann sein, wenn eine noch nicht belegt wurde, **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Memberfunktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion gibt einfach auftragsantwortnachrichten zurück **"false"**.  
  
 Wenn `phGlobal` ist **NULL**, klicken Sie dann ein neues `HGLOBAL` reserviert und in zurückgegeben werden soll `phGlobal`. Andernfalls die `HGLOBAL` gemäß `phGlobal` mit Daten gefüllt werden soll. Die Menge der Daten platziert werden, der `HGLOBAL` darf sich nicht auf die aktuelle Größe des Speicherblocks. Darüber hinaus kann nicht der Block auf eine Größe neu zugeordnet werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten können Sie eine der anderen Versionen dieser Funktion stattdessen überschreiben möchten. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata). Weitere Informationen für das verzögerte Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) im Windows SDK.  
  
##  <a name="onsetdata"></a>COleDataSource::OnSetData  
 Wird aufgerufen, durch das Framework festlegen oder Ersetzen Sie die Daten in der `COleDataSource` Objekt im angegebenen Format.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format, in dem Daten ausgetauscht werden, angibt.  
  
 `lpStgMedium`  
 Verweist auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur mit den Daten, die dem aktuellen Inhalt zu ersetzen, werden die `COleDataSource` Objekt.  
  
 `bRelease`  
 Gibt an, wer das Speichermedium nach Abschluss des Funktionsaufrufs hat. Der Aufrufer entscheidet, die für die Freigabe der Ressourcen für das Speichermedium zuständig ist. Der Aufrufer geschieht durch Festlegen von `bRelease`. Wenn `bRelease` ist ungleich NULL ist, die Datenquelle übernimmt den Besitz, das Medium freigeben, wenn er abgeschlossen ist, verwenden. Wenn `bRelease` ist 0, der Aufrufer besitzt und die Datenquelle kann das Speichermedium nur für die Dauer des Aufrufs verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquelle nimmt nicht die Daten, bis er erfolgreich abgerufen hat. D. h. es ist nicht den Besitz übernehmen Wenn `OnSetData` gibt 0 zurück. Wenn Sie den Besitz die Datenquelle ausgeführt wird, werden durch Aufrufen von Speichermedium freigibt der [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Funktion.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion zum Ersetzen der Daten im angegebenen Format. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Strukturen und die [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Funktionen im Windows SDK.  
  
##  <a name="setclipboard"></a>COleDataSource  
 Legt die Daten in der `COleDataSource` Objekt in der Zwischenablage nach dem Aufrufen einer der folgenden Funktionen: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), oder [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataObject-Klasse](../../mfc/reference/coledataobject-class.md)
