---
title: COleDataSource-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDataSource
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject, MFC encapsulation
- data transfer [C++], OLE
- COleDataSource class
- OLE data transfer [C++]
- uniform data transfer, OLE
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd8f30c3edd7d26b254e7f4a6f153ab0b2fc96da
ms.lasthandoff: 02/24/2017

---
# <a name="coledatasource-class"></a>COleDataSource-Klasse
Dient als Cache, in den eine Anwendung die Daten für Datenübertragungsoperationen ablegt, beispielsweise bei Zwischenablage- oder Drag & Drop-Operationen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Erstellt ein `COleDataSource`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CacheData](#cachedata)|Stellt Daten in einem angegebenen Format mithilfe einer **STGMEDIUM** Struktur.|  
|[COleDataSource:: CacheGlobalData](#cacheglobaldata)|Stellt Daten in einem angegebenen Format mithilfe einer `HGLOBAL`.|  
|[:: DelayRenderData](#delayrenderdata)|Stellt Daten in einem angegebenen Format verzögerte Rendering verwenden.|  
|[DelayRenderFileData](#delayrenderfiledata)|Stellt Daten in einem angegebenen Format in eine `CFile` Zeiger.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Für jedes Format, das unterstützt wird aufgerufen, `OnSetData`.|  
|[Ablagequellenobjekt](#dodragdrop)|Führt Drag & Drop-Operationen mit einer Datenquelle.|  
|[COleDataSource::Empty](#empty)|Leert den `COleDataSource` Daten.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Rendert alle Daten in der Zwischenablage.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Überprüft, ob die Daten in der Zwischenablage platziert noch vorhanden ist.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Ruft die Daten als Teil der verzögerte Rendering.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in einem `CFile` als Teil der verzögerte Rendering.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Abrufen von Daten in eine `HGLOBAL` als Teil der verzögerte Rendering.|  
|[COleDataSource::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten im Ersetzen der `COleDataSource` Objekt.|  
|[COleDataSource](#setclipboard)|Stellen ein `COleDataSource` Objekt in die Zwischenablage.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können OLE-Datenquellen direkt erstellen. Auch die [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md) Klassen erstellen OLE-Datenquellen als Antwort auf ihre `CopyToClipboard` und `DoDragDrop` Memberfunktionen. Finden Sie unter [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) eine kurze Beschreibung. Überschreiben der `OnGetClipboardData` Memberfunktion Ihrer Client-Element oder Server-Element-Klasse zusätzliche Zwischenablageformate auf die Daten in der OLE-Datenquelle hinzufügen erstellt wird, für die `CopyToClipboard` oder `DoDragDrop` -Memberfunktion.  
  
 Daten für die Übertragung vorbereiten möchten, sollten Sie ein Objekt dieser Klasse erstellen und füllen Sie es mit Ihren Daten mithilfe der am besten geeigneten Methode für Ihre Daten. Die Möglichkeit, die in einer Datenquelle eingefügt wird direkt betroffen, ob die Daten sofort bereitgestellt werden (unmittelbares Rendern) oder nach Bedarf (verzögertes Rendern). Für jedes Format der Zwischenablage in die Geben Sie Daten durch das Zwischenablageformat zu verwendende übergeben (und eine optionale [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur), rufen Sie [DelayRenderData](#delayrenderdata).  
  
 Weitere Informationen über Datenquellen und Übertragung von Daten finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Darüber hinaus Artikel [Zwischenablage](../../mfc/clipboard.md) des OLE-zwischenablagemechanismus beschrieben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-namecachedataa--coledatasourcecachedata"></a><a name="cachedata"></a>CacheData  
 Rufen Sie diese Funktion, um ein Format anzugeben, in dem Daten während Daten übertragen angeboten werden.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die Daten im angegebenen Format enthält.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Da diese Funktion bietet mithilfe von unmittelbares rendern, müssen Sie die Daten angeben. Die Daten werden zwischengespeichert, bis Sie benötigt.  
  
 Geben Sie die Daten mithilfe einer [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur. Sie können auch die `CacheGlobalData` Member-Funktion, wenn die Menge der Daten, die Sie bereitstellen, ist klein genug, um effizient mit übertragen werden eine `HGLOBAL`.  
  
 Nach dem Aufruf von `CacheData` der **Ptd** Mitglied `lpFormatEtc` und den Inhalt der `lpStgMedium` das Datenobjekt nicht vom Aufrufer gehören.  
  
 Rufen Sie zum Verwenden der verzögerten Rendering der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecacheglobaldataa--coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataSource:: CacheGlobalData  
 Rufen Sie diese Funktion, um ein Format anzugeben, in dem Daten während Daten übertragen angeboten werden.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 *hGlobal*  
 Handle für den globalen Speicherblock, der Daten im angegebenen Format enthält.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bereit, die Daten mit sofort gerendert wird, damit Sie die Daten angeben müssen, wenn die Funktion aufgerufen wird; die Daten werden zwischengespeichert, bis Sie benötigt. Verwenden der `CacheData` Member-Funktion, wenn Sie eine große Menge von Daten oder wenn Sie eine strukturierte Speichermedium bereitstellen.  
  
 Rufen Sie zum Verwenden der verzögerten Rendering der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecoledatasourcea--coledatasourcecoledatasource"></a><a name="coledatasource"></a>COleDataSource::COleDataSource  
 Erstellt ein `COleDataSource`-Objekt.  
  
```  
COleDataSource();
```  
  
##  <a name="a-namedelayrenderdataa--coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>:: DelayRenderData  
 Rufen Sie diese Funktion, um ein Format anzugeben, in dem Daten während Daten übertragen angeboten werden.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bereit, die Daten mit verzögerte rendering, sodass die Daten nicht sofort bereitgestellt werden. Die [OnRenderData](#onrenderdata) oder [OnRenderGlobalData](#onrenderglobaldata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie nicht beabsichtigen, Ihre Daten durch Angeben einer `CFile` Objekt. Wenn Sie beabsichtigen, geben Sie die Daten über eine `CFile` -Objekt, rufen Sie die [DelayRenderFileData](#delayrenderfiledata) Member-Funktion. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Rufen Sie zum sofortigen Rendering verwenden die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Member-Funktion.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedelayrenderfiledataa--coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>DelayRenderFileData  
 Rufen Sie diese Funktion, um ein Format anzugeben, in dem Daten während Daten übertragen angeboten werden.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablageformat, in dem die Daten angeboten werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format, in dem die Daten angeboten werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bereit, die Daten mit verzögerte rendering, sodass die Daten nicht sofort bereitgestellt werden. Die [OnRenderFileData](#onrenderfiledata) Member-Funktion wird aufgerufen, um die Daten anfordern.  
  
 Verwenden Sie diese Funktion, wenn Sie beabsichtigen, verwenden Sie ein `CFile` -Objekt, der die Daten bereitstellt. Wenn Sie nicht beabsichtigen, verwenden Sie eine `CFile` Objekt, rufen Sie die [DelayRenderData](#delayrenderdata) Member-Funktion. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Rufen Sie zum sofortigen Rendering verwenden die [CacheData](#cachedata) oder [CacheGlobalData](#cacheglobaldata) Member-Funktion.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedelaysetdataa--coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>COleDataSource::DelaySetData  
 Rufen Sie diese Funktion, um den Inhalt der Datenquelle ändern zu unterstützen.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Zwischenablageformat, in dem die Daten platziert werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format, in dem die Daten ersetzt werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 [OnSetData](#onsetdata) wird vom Framework aufgerufen, wenn dies geschieht. Wird nur verwendet, wenn das Framework die Datenquelle gibt [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Wenn `DelaySetData` nicht aufgerufen wird, die `OnSetData` Funktion wird nie aufgerufen werden. `DelaySetData`für jede Zwischenablage aufgerufen werden soll oder **FORMATETC** Format, die Sie unterstützen.  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedodragdropa--coledatasourcedodragdrop"></a><a name="dodragdrop"></a>Ablagequellenobjekt  
 Rufen Sie die `DoDragDrop` Memberfunktion, um einen Drag & Drop-Vorgang für diese Datenquelle führen in der Regel in einer [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) Handler.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwEffects`  
 Drag & Drop-Vorgänge, die zulässig sind für diese Datenquelle. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_COPY`Es konnte ein Kopiervorgang ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Es konnte ein Verschiebevorgang ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung zwischen der abgelegten Daten und die ursprünglichen Daten konnte hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass es sich bei Auftreten ein Ziehvorgangs ein Bildlauf.  
  
 `lpRectStartDrag`  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
 *pDropSource*  
 Verweist auf ein Drop-Quelle. Wenn **NULL** dann eine Standardimplementierung der [COleDropSource](../../mfc/reference/coledropsource-class.md) verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Löschen Sie wirksam, die von der Drag & Drop-Vorgang generiert. andernfalls `DROPEFFECT_NONE` , wenn der Vorgang nie gestartet werden, da der Benutzer die Maustaste losgelassen, vor dem Verlassen des angegebenen Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Der Drag & Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor die durch angegebene Rechteck verlässt `lpRectStartDrag` oder eine angegebene Anzahl an Millisekunden verstrichen sind. Wenn `lpRectStartDrag` ist **NULL**, die Größe des Rechtecks beträgt ein Pixel.  
  
 Die Verzögerungszeit wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerung ändern, durch Aufrufen von [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie nicht die Verzögerung angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Windows 95/98 Drag-Verzögerungszeit wird in eine zwischengespeicherte Version der Windows-Taste gespeichert. INI.  
  
 Für Weitere Informationen ziehen ist Verzögerung Informationen in der Registrierung gespeicherten oder. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie im Artikel [per Drag & Drop: Implementieren einer Drop-Quelle](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="a-nameemptya--coledatasourceempty"></a><a name="empty"></a>COleDataSource::Empty  
 Rufen Sie diese Funktion zum Leeren der `COleDataSource` Daten.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Hinweise  
 Beide zwischengespeichert und Verzögerung Render-Formate werden geleert, sodass sie wiederverwendet werden können.  
  
 Weitere Informationen finden Sie unter [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameflushclipboarda--coledatasourceflushclipboard"></a><a name="flushclipboard"></a>COleDataSource::FlushClipboard  
 Werden Daten, die in die Zwischenablage kopieren und dann können Sie die Daten aus der Zwischenablage einfügen, nachdem die Anwendung beendet.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [SetClipboard](#setclipboard) zum Einfügen von Daten in die Zwischenablage.  
  
##  <a name="a-namegetclipboardownera--coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>COleDataSource::GetClipboardOwner  
 Bestimmt, ob die Daten in die Zwischenablage, seit geändert hat [SetClipboard](#setclipboard) zuletzt aufgerufen wurde, und wenn dies der Fall ist, identifiziert den aktuellen Besitzer.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datenquelle, die derzeit in der Zwischenablage oder **NULL** Wenn nichts in die Zwischenablage kopieren oder die Zwischenablage nicht von der aufrufenden Anwendung gehört.  
  
##  <a name="a-nameonrenderdataa--coledatasourceonrenderdata"></a><a name="onrenderdata"></a>COleDataSource::OnRenderData  
 Vom Framework aufgerufen wird zum Abrufen von Daten im angegebenen Format.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in der die Daten zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) oder [DelayRenderFileData](#delayrenderfiledata) Member-Funktion für das verzögerte Rendering. Ruft die standardmäßige Implementierung dieser Funktion [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata) Wenn das angegebene Speichermedium eine Datei oder einen Speicher ist. Wenn keines dieser Formate angegeben werden, wird die standardmäßige Implementierung gibt 0 zurück, und nichts. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Wenn `lpStgMedium` ->  *Tymed* ist **TYMED_NULL**, **STGMEDIUM** zugeordnet und entsprechend den Angaben von gefüllt werden *LpFormatEtc-> Tymed*. Ist er nicht **TYMED_NULL**, **STGMEDIUM** mit Daten ausgefüllt werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Ihre Daten klein und feste Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Strukturen, die [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Enumerationstyp und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonrenderfiledataa--coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>COleDataSource::OnRenderFileData  
 Aufgerufen, um Daten im angegebenen Format abzurufen, wenn das angegebene Speichermedium eine Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `pFile`  
 Verweist auf eine [CFile](../../mfc/reference/cfile-class.md) Objekt, in dem die Daten gerendert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten empfiehlt es sich, eine der anderen Versionen dieser Funktion stattdessen überschreiben. Wenn Sie mehrere Medien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`. Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonrenderglobaldataa--coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData  
 Aufgerufen, um Daten im angegebenen Format abzurufen, wird das angegebene Speichermedium globalen Arbeitsspeicher.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `phGlobal`  
 Verweist auf ein Handle für den globalen Arbeitsspeicher, in dem die Daten zurückgegeben werden. Wenn Sie eine noch nicht belegt wurde, kann dieser Parameter **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Wenn `phGlobal` ist **NULL**, ein neues `HGLOBAL` zugeordnet und in zurückgegeben werden sollte `phGlobal`. Andernfalls die `HGLOBAL` angegebene `phGlobal` mit Daten gefüllt werden soll. Die Datenmenge der `HGLOBAL` darf sich nicht auf die aktuelle Größe des Speicherblocks. Der Block kann nicht darüber hinaus auf eine größere Größe neu zugewiesen werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Sie mehrere Medien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata). Weitere Informationen zum verzögerten Rendering von MFC als behandelt, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonsetdataa--coledatasourceonsetdata"></a><a name="onsetdata"></a>COleDataSource::OnSetData  
 Aufgerufen, um festzulegen, oder Ersetzen Sie die Daten in der `COleDataSource` Objekt im angegebenen Format.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Daten ersetzt werden.  
  
 `lpStgMedium`  
 Verweist auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur mit den Daten, die den aktuellen Inhalt des ersetzt, die `COleDataSource` Objekt.  
  
 `bRelease`  
 Gibt an, wer das Speichermedium nach Abschluss des Funktionsaufrufs hat. Der Aufrufer entscheidet, die verantwortlich für die Freigabe der Ressourcen für das Speichermedium zugewiesen ist. Der Aufrufer wird `bRelease`. Wenn `bRelease` ist ungleich NULL ist, die Datenquelle übernimmt den Besitz, das Medium freigeben, wenn Verwendung er beendet wurde. Wenn `bRelease` ist 0, der Aufrufer besitzt und die Datenquelle kann das Speichermedium nur für die Dauer des Aufrufs verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Datenquelle nimmt keine Besitzer der Daten, bis er erfolgreich abgerufen hat. D. h., es übernimmt keinen Besitz Wenn `OnSetData` gibt 0 zurück. Wenn die Datenquelle den Besitz übernimmt, werden durch Aufrufen von Speichermedium freigibt der [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Funktion.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um die Daten im angegebenen Format zu ersetzen. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Strukturen und [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) und [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) -Funktionen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-namesetclipboarda--coledatasourcesetclipboard"></a><a name="setclipboard"></a>COleDataSource  
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

