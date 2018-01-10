---
title: COleServerItem Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
dev_langs: C++
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd64d6a2cf4fe36e62f5c6599521780c4ee002ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coleserveritem-class"></a>COleServerItem-Klasse
Stellt die Serverschnittstelle zu OLE-Elementen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|Erstellt ein `COleServerItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Setzt die Präsentations- und Konvertierung von Formaten in eine `COleDataSource` Objekt.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Kopiert das Element in die Zwischenablage.|  
|[COleServerItem:: DoDragDrop](#dodragdrop)|Führt einen Drag-and-Drop-Vorgang.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|Ruft die Datenquelle für die Verwendung bei der Datenübertragung (Drag & Drop oder Zwischenablage) ab.|  
|[COleServerItem::GetDocument](#getdocument)|Gibt zurück, das Serverdokument, das das Element enthält.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Ruft die **CF_EMBEDSOURCE** Daten für ein OLE-Element.|  
|[COleServerItem::GetItemName](#getitemname)|Gibt den Namen des Elements zurück. Für verknüpfte Elemente nur verwendet werden.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Ruft die `CF_LINKSOURCE` Daten für ein OLE-Element.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Ruft die **CF_OBJECTDESCRIPTOR** Daten für ein OLE-Element.|  
|[COleServerItem::IsConnected](#isconnected)|Gibt an, ob das Element mit einem aktiven Container derzeit zugeordnet ist.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|Gibt an, ob das Element ein verknüpftes OLE-Element darstellt.|  
|[COleServerItem::NotifyChanged](#notifychanged)|Aktualisiert alle Container mit Update automatische Verknüpfung an.|  
|[COleServerItem::OnDoVerb](#ondoverb)|Wird aufgerufen, um ein Verb auszuführen.|  
|[COleServerItem:: OnDraw](#ondraw)|Wird aufgerufen, wenn der Container zum Zeichnen des Elements fordert; die Implementierung erforderlich sind.|  
|[COleServerItem::OnDrawEx](#ondrawex)|Wird aufgerufen, für das spezielle Element zeichnen.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Wird aufgerufen, durch das Framework zum Abrufen der Daten, die in die Zwischenablage kopiert werden würde.|  
|[COleServerItem::OnGetExtent](#ongetextent)|Wird aufgerufen, durch das Framework die Größe des OLE-Elements abgerufen.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|Vom Framework aufgerufen wird, initialisieren ein OLE-Element mit dem Inhalt des Daten-Transfer-Objekt angegeben.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Wird aufgerufen, um festzustellen, ob alle verknüpften Elemente aktualisiert werden müssen.|  
|[COleServerItem::OnRenderData](#onrenderdata)|Ruft die Daten als Teil der verzögerte Rendering ab.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in einem `CFile` Objekt als Teil des verzögerte Rendering.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Abrufen von Daten in eine `HGLOBAL` im Rahmen des verzögerte Rendering.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Wird aufgerufen, um Farbschemas für das Element festzulegen.|  
|[COleServerItem::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten des festzulegen.|  
|[COleServerItem::OnSetExtent](#onsetextent)|Vom Framework aufgerufen wird, legen Sie die Größe des OLE-Elements.|  
|[COleServerItem::OnUpdate](#onupdate)|Wird aufgerufen, wird Wenn ein Teil des Dokuments das Element gehört geändert.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|Wird aufgerufen, um den Cache Darstellung aller Elemente im Serverdokument aktualisieren.|  
|[COleServerItem::SetItemName](#setitemname)|Legt den Namen des Elements. Für verknüpfte Elemente nur verwendet werden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|Ruft das Objekt zum Speichern von konvertierungsformate verwendet.|  
|[COleServerItem::OnHide](#onhide)|Vom Framework aufgerufen, die das OLE-Element auszublenden.|  
|[COleServerItem::OnOpen](#onopen)|Wird aufgerufen, durch das Framework das OLE-Element in einem eigenen Fenster der obersten Ebene angezeigt.|  
|[COleServerItem::OnShow](#onshow)|Wird aufgerufen, wenn der Container anfordert, um das Element anzuzeigen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Wird der Server über wie viel des OLE-Elements sichtbar ist.|  
  
## <a name="remarks"></a>Hinweise  
 Ein verknüpftes Element kann es sich um einiger oder aller Serverdokument darstellen. Ein eingebettetes Element stellt immer eine gesamte Serverdokument dar.  
  
 Die `COleServerItem` Klasse definiert mehrere überschreibbare Memberfunktionen, die vom OLE-System Dynamic Link Libraries (DLLs), aufgerufen werden, in der Regel als Antwort auf Anforderungen aus dem Steuerelementcontainer-Anwendung. Diese Memberfunktionen ermöglichen die Steuerelementcontainer-Anwendung auf das Element indirekt auf verschiedene Weise, wie z. B. zu bearbeiten, indem Sie anzeigen, die Verben ausführen oder Abrufen der Daten in verschiedenen Formaten.  
  
 Mit `COleServerItem`, eine Klasse ableiten und Implementieren der [OnDraw](#ondraw) und [Serialize](../../mfc/reference/cobject-class.md#serialize) Memberfunktionen. Die `OnDraw` -Funktion bietet die Metadateidarstellung eines Elements, sodass er angezeigt wird, wenn eine Steuerelementcontainer-Anwendung ein Verbunddokument geöffnet wird. Die `Serialize` Funktion `CObject` stellt die systemeigene Darstellung eines Elements, sodass ein eingebettetes Element zwischen Server und-Container Anwendungen übertragen werden. [OnGetExtent](#ongetextent) natürliche Größe des Elements, das den Container, aktivieren den Container an die Größe des Elements enthält.  
  
 Weitere Informationen zu Servern und verwandten Themen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md) und "Erstellen einer Container/Server-Anwendung" im Artikel [Container: Erweiterte Funktionen](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 Mit dieser Funktion können Sie die Präsentations- und Konvertierung Formate für die OLE-Element im angegebenen platzieren `COleDataSource` Objekt.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataSource`  
 Zeiger auf die `COleDataSource` -Objekt in dem die Daten platziert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Muss implementiert haben die [OnDraw](#ondraw) Memberfunktion der Präsentationsformat (ein Metadateibild) für das Element bereitstellen. Unterstützung von anderen konvertierungsformate, registrieren Sie ihn mithilfe der [COleDataSource](../../mfc/reference/coledatasource-class.md) zurückgegebenes Objekt [GetDataSource](#getdatasource) und überschreiben die [OnRenderData](#onrenderdata) Memberfunktion Geben Sie die Daten in den Formaten, die Sie unterstützen möchten.  
  
##  <a name="coleserveritem"></a>COleServerItem::COleServerItem  
 Erstellt ein `COleServerItem` -Objekt und fügt es der Serverdokument Auflistung von Dokumentelemente hinzu.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 `pServerDoc`  
 Ein Zeiger auf das Dokument, das das neue Element enthalten soll.  
  
 `bAutoDelete`  
 Ein Flag, der angibt, ob das Objekt gelöscht werden kann, wenn ein Link zu ihr losgelassen wird. Legen Sie **"false"** Wenn die `COleServerItem` Objekt ist ein wesentlicher Bestandteil des Dokuments-Daten, die Sie löschen müssen. Legen Sie **"true"** , wenn das Objekt ist eine sekundäre Struktur verwendet, um einen Bereich in Ihr Dokument Daten zu identifizieren, die vom Framework gelöscht werden kann.  
  
##  <a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 Mit dieser Funktion können Sie OLE-Element in die Zwischenablage zu kopieren.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 Legen Sie **"true"** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie **"false"** Wenn Ihre Serveranwendung Links nicht unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die Funktion die [OnGetClipboardData](#ongetclipboarddata) Memberfunktion zum Erstellen einer [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt mit der OLE-Element-Daten in den Formaten unterstützt. Klicken Sie dann die Funktion setzt die `COleDataSource` Objekt in der Zwischenablage mit der [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Die `COleDataSource` Objekt enthält, systemeigene Daten für das Element und dessen Darstellung in `CF_METAFILEPICT` Format sowie Daten in alle konvertierungsformate, die Sie unterstützen möchten. Sie implementiert haben müssen [Serialize](../../mfc/reference/cobject-class.md#serialize) und [OnDraw](#ondraw) für diese Memberfunktion arbeiten.  
  
##  <a name="dodragdrop"></a>COleServerItem:: DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion versucht, einen Drag-and-Drop-Vorgang auszuführen.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectItem*  
 Das Element Rechteck auf dem Bildschirm in Pixel relativ zum Clientbereich.  
  
 `ptOffset`  
 Der Offset vom `lpItemRect` , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.  
  
 `bIncludeLink`  
 Legen Sie **"true"** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie es auf **"false"** Wenn Links von die Anwendung nicht unterstützt wird.  
  
 `dwEffects`  
 Bestimmt die Effekte, die in den Ziehvorgang (eine Kombination aus kopieren, verschieben und Link) die Quelle des Ziehvorgangs ermöglichen.  
  
 `lpRectStartDrag`  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT`-Enumeration. Ist er `DROPEFFECT_MOVE`, sollte die ursprünglichen Daten entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Drag-and-Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor auf das Rechteck, angegeben durch verlässt `lpRectStartDrag` oder bis eine angegebene Anzahl von Millisekunden erfolgreich abgeschlossen wurden. Wenn `lpRectStartDrag` ist **NULL**, ein Standardrechteck wird verwendet, sodass der Ziehvorgang beginnt, wenn der Mauszeiger ein Pixel verschoben.  
  
 Die Verzögerung wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit werden wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version der WIN gespeichert. INI.  
  
 Für Weitere Informationen ziehen wird Verzögerung Informationen gespeichert, in der Registrierung oder der. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) im Windows SDK.  
  
##  <a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 Mit dieser Funktion können Sie den angegebenen füllen [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt mit allen Daten, die in die Zwischenablage kopiert werden würde, wenn Sie aufgerufen [CopyToClipboard](#copytoclipboard) (die gleichen Daten würde auch übertragen werden, wenn Sie wird aufgerufen, [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataSource`  
 Zeiger auf die `COleDataSource` -Objekt, das die OLE-Element-Daten in allen unterstützten Formaten empfangen wird.  
  
 `bIncludeLink`  
 **"True"** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. **"False"** Wenn Ihre Serveranwendung Links nicht unterstützt.  
  
 `lpOffset`  
 Der Offset in Pixel, der den Cursor vom Ursprung des Objekts.  
  
 `lpSize`  
 Die Größe des Objekts in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [GetEmbedSourceData](#getembedsourcedata) Member-Funktion zum Abrufen der systemeigenen Daten für die OLE-Element und ruft die [AddOtherClipboardData](#addotherclipboarddata) zum Abrufen der Präsentationsformat und einer Memberfunktion konvertierungsformate wird unterstützt. Wenn `bIncludeLink` ist **"true"**, ruft die Funktion auch [GetLinkSourceData](#getlinksourcedata) die Link-Daten für das Element abgerufen werden.  
  
 Überschreiben Sie diese Funktion, wenn in den Formaten versetzt werden soll eine `COleDataSource` -Objekt vor oder nach diesen Formaten, die vom `CopyToClipboard`.  
  
##  <a name="getdatasource"></a>COleServerItem::GetDataSource  
 Mit dieser Funktion wird zum Abrufen der [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, mit dem der konvertierungsformate zu speichern, die die Serveranwendung unterstützt.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `COleDataSource` Objekt, das zum Speichern der konvertierungsformate verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Server-Anwendung Daten in einer Vielzahl von Formaten beim Übertragen von Daten Vorgänge anbieten möchten, registrieren Sie diesen Formaten mit der `COleDataSource` Objekt, das von dieser Funktion zurückgegeben. Angenommen, Sie möchten eine **HIERSVR** Darstellung des OLE-Elements für Zwischenablage- oder Drag & Drop-Operationen, würden Sie das Format mit Registrieren der `COleDataSource` -Objekt gibt diese Funktion zurück, und klicken Sie dann überschreiben die  **OnRenderXxxData** Member-Funktion, um die Daten bereitzustellen.  
  
##  <a name="getdocument"></a>COleServerItem::GetDocument  
 Mit dieser Funktion wird zum Abrufen eines Zeigers auf das Dokument, das das Element enthält.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht den Zugriff auf das Serverdokument, das Sie als Argument zu übergeben der `COleServerItem` Konstruktor.  
  
##  <a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 Mit dieser Funktion wird zum Abrufen der **CF_EMBEDSOURCE** Daten für ein OLE-Element.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStgMedium`  
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhält die **CF_EMBEDSOURCE** Daten für das OLE-Element.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Format schließt die systemeigenen Elementdaten. Sie implementiert haben müssen die `Serialize` Memberfunktion für diese Funktion ordnungsgemäß funktioniert.  
  
 Das Ergebnis kann anschließend an eine Datenquelle hinzugefügt werden, mithilfe von [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion wird automatisch vom [COleServerItem::OnGetClipboardData](#ongetclipboarddata).  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) im Windows SDK.  
  
##  <a name="getitemname"></a>COleServerItem::GetItemName  
 Mit dieser Funktion wird zum Abrufen des Namens des Elements.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Name des Elements.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion nur für verknüpfte Elemente.  
  
##  <a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 Mit dieser Funktion wird zum Abrufen der `CF_LINKSOURCE` Daten für ein OLE-Element.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStgMedium`  
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhält die `CF_LINKSOURCE` Daten für das OLE-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Format schließt die CLSID, beschreibt den Typ des OLE-Element und die benötigten Informationen zum Suchen Sie des Dokuments, das OLE-Element enthält.  
  
 Das Ergebnis kann anschließend hinzugefügt werden, um eine Datenquelle mit [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion wird automatisch vom [OnGetClipboardData](#ongetclipboarddata).  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) im Windows SDK.  
  
##  <a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 Mit dieser Funktion wird zum Abrufen der **CF_OBJECTDESCRIPTOR** Daten für ein OLE-Element.  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpOffset`  
 Offset der Maus klicken Sie auf der linken oberen Ecke des OLE-Elements. Kann **NULL**.  
  
 `lpSize`  
 Die Größe des OLE-Elements. Kann **NULL**.  
  
 `lpStgMedium`  
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhält die **CF_OBJECTDESCRIPTOR** Daten für das OLE-Element.  
  
### <a name="remarks"></a>Hinweise  
 Kopiert die Informationen in den **STGMEDIUM** Struktur verweist `lpStgMedium`. Dieses Format schließt für das Dialogfeld "Inhalte einfügen" erforderlichen Informationen.  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) im Windows SDK.  
  
##  <a name="isconnected"></a>COleServerItem::IsConnected  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element verbunden ist.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element verbunden ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein OLE-Element gilt verbunden, wenn eine oder mehrere Container Verweise auf das Element. Ein Element verbunden ist, wenn sein Verweiszähler größer als 0 ist oder wenn es sich um ein eingebettetes Element ist.  
  
##  <a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element ein verknüpftes Element ist.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element ein verknüpftes Element ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Element verknüpft ist, wenn das Element ungültig ist und wird nicht in das Dokument der Liste der eingebetteten Elemente zurückgegeben. Ein verknüpftes Element kann oder möglicherweise nicht zu einem Container verbunden werden.  
  
 Es ist üblich, derselben Klasse für verknüpfte oder eingebettete Elemente verwenden. `IsLinkedItem`können Sie verknüpfte Elemente verhalten sich anders als eingebettete Elemente stellen zwar häufig im Code.  
  
##  <a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 Bei diesem Member weist den Server, wie viel des Objekts im Containerdokument sichtbar ist.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des [OnSetExtent](#onsetextent) legt dieses Elements.  
  
##  <a name="notifychanged"></a>COleServerItem::NotifyChanged  
 Mit dieser Funktion werden, nachdem das verknüpfte Element geändert wurde.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT` Enumeration, der angibt, welcher Aspekt der OLE-Element geändert wurde. Dieser Parameter kann eine der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Containerelement, das Dokument mit einer automatischen Verknüpfung verknüpft ist, wird das Element aktualisiert, um die Änderungen wiederzugeben. In containeranwendungen unter Verwendung der Microsoft Foundation Class-Bibliothek geschrieben [COleClientItem:: OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Reaktion aufgerufen wird.  
  
##  <a name="ondoverb"></a>COleServerItem::OnDoVerb  
 Vom Framework aufgerufen wird, führen Sie das angegebene Verb.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Gibt das Verb ausgeführt. Es kann einer der folgenden sein:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|1|Sekundäre verb|(Keine)|  
|- 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|- 2|Element in separaten Fenster bearbeiten|`OLEIVERB_OPEN`|  
|- 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert-1 ist in der Regel ein Alias für einen anderen Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie – 1. Weitere Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) Memberfunktion der entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die Standardimplementierung Ruft die [OnShow](#onshow) Memberfunktion, wenn die primäres Verb oder `OLEIVERB_SHOW` angegeben wird, [OnOpen](#onopen) Wenn sekundäre Verb oder `OLEIVERB_OPEN` angegeben wird, und [OnHide](#onhide) Wenn `OLEIVERB_HIDE` angegeben ist. Die Standardimplementierung ruft `OnShow` Wenn `iVerb` ist keiner der oben aufgeführten Verben.  
  
 Überschreiben Sie diese Funktion, wenn das Element nicht von Ihr primäre Verb angezeigt wird. Beispielsweise, wenn das Element ein sound aufzeichnen ist und dessen primäre Verb wiedergeben, müssten nicht Sie die Serveranwendung die Wiedergabe des Elements angezeigt.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
##  <a name="ondraw"></a>COleServerItem:: OnDraw  
 Wird aufgerufen, durch das Framework zum Rendern des OLE-Elements in einer Metadatei.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, für das zum Zeichnen des Elements. Der Anzeigekontext wird automatisch dann mit den Anzeigekontext Attribut verbunden, damit Sie Attribut-Funktion aufrufen können, obwohl dies also die Metadatei gerätespezifischen machen würden.  
  
 `rSize`  
 Die Größe, in **HIMETRIC** Einheiten, in dem die Metadatei gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element erfolgreich gezeichnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Metadateidarstellung des OLE-Elements wird verwendet, um das Element in der containeranwendung anzuzeigen. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird von die Metadatei verwendet die [zeichnen](../../mfc/reference/coleclientitem-class.md#draw) Memberfunktion der entsprechenden [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekt. Es ist keine Standardimplementierung vorhanden. Sie müssen diese Funktion zum Zeichnen des Elements in den angegebenen Gerätekontext überschreiben.  
  
##  <a name="ondrawex"></a>COleServerItem::OnDrawEx  
 Wird aufgerufen, durch das Framework für alle zeichnen.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, für das zum Zeichnen des Elements. Der Domänencontroller ist automatisch verbunden mit dem Attribut DC damit Attribut-Funktionen aufgerufen werden kann, obwohl dies also die Metadatei gerätespezifischen machen würden.  
  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann eine der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
 `rSize`  
 Größe des Elements im **HIMETRIC** Einheiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element erfolgreich gezeichnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `OnDraw` Wenn `DVASPECT` gleich `DVASPECT_CONTENT`; andernfalls ein Fehler auftritt.  
  
 Überschreiben Sie diese Funktion, um Aspekte außer Präsentationsdaten verliehen `DVASPECT_CONTENT`, wie z. B. `DVASPECT_ICON` oder `DVASPECT_THUMBNAIL`.  
  
##  <a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 Wird aufgerufen, durch das Framework zum Abrufen einer `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) Memberfunktion.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 Legen Sie **"true"** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie **"false"** Wenn Ihre Serveranwendung Links nicht unterstützt.  
  
 `lpOffset`  
 Der Offset des Mauszeigers vom Ursprung des Objekts in Pixel.  
  
 `lpSize`  
 Die Größe des Objekts in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, das Daten aus der Zwischenablage enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetextent"></a>COleServerItem::OnGetExtent  
 Wird aufgerufen, durch das Framework zum Abrufen der Größe in **HIMETRIC** Einheiten, die OLE-Element.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen werden abgerufen werden sollen. Dieser Parameter kann eine der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
 `rSize`  
 Ein Verweis auf eine `CSize` -Objekt, das die Größe des OLE-Element erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) Memberfunktion der entsprechenden `COleClientItem` -Objekts aufgerufen wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen es selbst implementieren. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung ausführen, bei der Verarbeitung einer Anforderung für die Größe des OLE-Element von möchten.  
  
##  <a name="onhide"></a>COleServerItem::OnHide  
 Vom Framework aufgerufen, die das OLE-Element auszublenden.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige **COleServerDoc::OnShowDocument (FALSE)**. Die Funktion benachrichtigt, dass das OLE-Element ausgeblendet wurde auch dem Container. Überschreiben Sie diese Funktion, wenn spezielle Verarbeitung ausführen, wenn ein OLE-Element ausgeblendet werden sollen.  
  
##  <a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 Wird aufgerufen, durch das Framework zum Initialisieren von einem OLE-Element mit dem Inhalt des `pDataObject`.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Ein Zeiger auf ein OLE-Datenobjekt, das Daten in unterschiedlichen Formaten zum Initialisieren der OLE-Element enthält.  
  
 `bCreation`  
 **"True"** , wenn die Funktion aufgerufen wird, initialisieren Sie ein OLE-Element, das durch eine Steuerelementcontainer-Anwendung neu erstellt wird. **"False"** , wenn die Funktion aufgerufen wird, um den Inhalt von einem bereits vorhandenen OLE-Element zu ersetzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bCreation` ist **"true"**, diese Funktion wird aufgerufen, wenn ein Container neue Objekt einfügen basierend auf der aktuellen Auswahl implementiert. Die ausgewählten Daten werden verwendet, wenn die neue OLE-Element zu erstellen. Z. B. wenn einen Zellbereich in einem Tabellenkalkulationsprogramm auswählen und dann das neue Objekt einfügen zum Erstellen eines Diagramms der Werte in den ausgewählten Bereich anhand. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben von dieser Funktion können Sie wählen ein ungültiges Format von den `pDataObject` und initialisieren Sie das OLE-Element, das basierend auf den bereitgestellten Daten. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) im Windows SDK.  
  
##  <a name="onopen"></a>COleServerItem::OnOpen  
 Wird aufgerufen, durch das Framework zum Anzeigen des OLE-Elements in eine separate Instanz des Server-Anwendung und nicht vorhanden.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert das erste Rahmenfenster anzeigen das Dokument, das OLE-Element enthält. Wenn die Anwendung eine Miniserver ist, zeigt die standardmäßige Implementierung im Hauptfenster. Die Funktion benachrichtigt auch dem Container, dass das OLE-Element geöffnet wurde.  
  
 Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung ausführen, wenn Sie ein OLE-Element zu öffnen möchten. Dies ist besonders häufig bei der verknüpften Elemente, in dem Sie die Auswahl auf den Link festgelegt wird, beim öffnen möchten.  
  
 Weitere Informationen finden Sie unter [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) im Windows SDK.  
  
##  <a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 Wird aufgerufen, durch das Framework ermitteln, ob alle verknüpften Elemente im aktuellen Serverdokument veraltet sind.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument über Elemente, die Updates erfordern besitzt; 0, wenn alle Elemente auf dem neuesten Stand sind.  
  
### <a name="remarks"></a>Hinweise  
 Ein Element ist veraltet, wenn seine Quelldokument wurde geändert, aber das verknüpfte Element wurde nicht entsprechend den Änderungen im Dokument aktualisiert.  
  
##  <a name="onrenderdata"></a>COleServerItem::OnRenderData  
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
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) oder [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Memberfunktion für das verzögerte Rendering. Ruft die standardmäßige Implementierung dieser Funktion [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata)bzw. das angegebene Speichermedium ist eine Datei oder einen Speicher. Wenn keines der folgenden Formate angegeben wird, wird die standardmäßige Implementierung gibt 0 zurück und wird keine Aktion ausgeführt.  
  
 Wenn `lpStgMedium` ->  *Tymed* ist **TYMED_NULL**, **STGMEDIUM** sollten reserviert und entsprechend den Angaben von gefüllt *LpFormatEtc -> TYMED*. Wenn dies nicht der **TYMED_NULL**, **STGMEDIUM** direkt mit den Daten ausgefüllt werden soll.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten können Sie eine der anderen Versionen dieser Funktion stattdessen überschreiben möchten. Wenn Ihre Daten klein und fester Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), und [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) im Windows SDK.  
  
##  <a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das Speichermedium eine Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format, in dem Informationen angefordert, angibt.  
  
 `pFile`  
 Verweist auf ein `CFile` Objekt, in dem die Daten gerendert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Memberfunktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion gibt einfach auftragsantwortnachrichten zurück **"false"**.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Je nach Ihrer Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
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
 Verweist auf ein Handle für den globalen Arbeitsspeicher, in dem die Daten zurückgegeben werden. Dieser Parameter kann sein, wenn kein Arbeitsspeicher belegt wurde, **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Memberfunktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion gibt einfach auftragsantwortnachrichten zurück **"false"**.  
  
 Wenn `phGlobal` ist **NULL**, klicken Sie dann ein neues `HGLOBAL` reserviert und in zurückgegeben werden soll `phGlobal`. Andernfalls die `HGLOBAL` gemäß `phGlobal` mit Daten gefüllt werden soll. Die Menge der Daten platziert werden, der `HGLOBAL` darf sich nicht auf die aktuelle Größe des Speicherblocks. Darüber hinaus kann nicht der Block auf eine Größe neu zugeordnet werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten können Sie eine der anderen Versionen dieser Funktion stattdessen überschreiben möchten. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei ist oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 Vom Framework aufgerufen wird, geben Sie eine Farbpalette beim Bearbeiten von OLE-Element verwendet werden soll.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogPalette`  
 Zeiger auf ein Windows [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Farbpalette verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Funktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Gibt die standardmäßige Implementierung **"false"**. Überschreiben Sie diese Funktion, wenn Sie die empfohlene Palette verwenden möchten. Die Server-Anwendung ist nicht erforderlich, die empfohlene Palette verwenden.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) im Windows SDK.  
  
##  <a name="onsetdata"></a>COleServerItem::OnSetData  
 Wird aufgerufen, durch das Framework das OLE-Element-Daten mit den angegebenen Daten ersetzt.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das Format der Daten angibt.  
  
 `lpStgMedium`  
 Zeiger auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in dem sich die Daten befinden.  
  
 `bRelease`  
 Gibt an, wer das Speichermedium nach Abschluss des Funktionsaufrufs hat. Der Aufrufer entscheidet, die für die Freigabe der Ressourcen für das Speichermedium zuständig ist. Der Aufrufer geschieht durch Festlegen von `bRelease`. Wenn `bRelease` ist ungleich NULL ist, das Serverelement übernimmt den Besitz, das Medium freigeben, wenn er abgeschlossen ist, verwenden. Wenn `bRelease` ist 0, der Aufrufer besitzt und das Serverelement kann das Speichermedium verwenden, nur für die Dauer des Aufrufs.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Serverelement nimmt nicht die Daten, bis er erfolgreich abgerufen hat. Es ist, also nicht den Besitz übernehmen, wenn sie "0" zurück. Wenn Sie den Besitz die Datenquelle ausgeführt wird, werden durch Aufrufen von Speichermedium freigibt der [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Funktion.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion zum Ersetzen der OLE-Element-Daten mit den angegebenen Daten. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), und [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) im Windows SDK.  
  
##  <a name="onsetextent"></a>COleServerItem::OnSetExtent  
 Wird aufgerufen, durch das Framework dem OLE-Element zu informieren, wie viel Speicherplatz im Containerdokument verfügbar ist.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Gibt an, die Teil der OLE-Element, dessen Grenzen angegeben werden. Dieser Parameter kann eine der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
 `size`  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Struktur, die die neue Größe des OLE-Elements angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) Memberfunktion der entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die standardmäßige Implementierung legt den [M_sizeExtent](#m_sizeextent) Mitglied der angegebenen Größe Wenn `nDrawAspect` ist `DVASPECT_CONTENT`; andernfalls wird 0 zurückgegeben. Überschreiben Sie diese Funktion zum Ausführen der besonderen Verarbeitung, wenn Sie die Größe des Elements ändern.  
  
##  <a name="onshow"></a>COleServerItem::OnShow  
 Vom Framework aufgerufen wird, weisen Sie die Server-Anwendung zum Anzeigen des OLE-Elements vorhanden.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion in der Regel aufgerufen wird, wenn der Benutzer die containeranwendung ein Element erstellt oder ein Verb, z. B. bearbeiten führt, erfordert, dass das Element angezeigt werden. Die standardmäßige Implementierung versucht, direkte Aktivierung. Wenn dies fehlschlägt, ruft die Funktion die `OnOpen` Memberfunktion versucht, die OLE-Element in einem separaten Fenster angezeigt.  
  
 Überschreiben Sie diese Funktion, wenn Ausführen spezieller Verarbeitung, wenn ein OLE-Element angezeigt wird.  
  
##  <a name="onupdate"></a>COleServerItem::OnUpdate  
 Vom Framework aufgerufen, wenn ein Element geändert wurde.  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Ein Zeiger auf das Element, das das Dokument geändert. Kann **NULL**.  
  
 `lHint`  
 Enthält Informationen über die Änderung.  
  
 `pHint`  
 Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [NotifyChanged](#notifychanged)unabhängig von den oder die Sender.  
  
##  <a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 Wird aufgerufen, durch das Framework, um alle Elemente im Serverdokument zu aktualisieren.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) für alle `COleClientItem` Objekte im Dokument.  
  
##  <a name="setitemname"></a>COleServerItem::SetItemName  
 Rufen Sie diese Funktion, bei der Erstellung eines verknüpften Elements, dessen Namen festzulegen.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Ein Zeiger auf den neuen Namen des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss innerhalb des Dokuments eindeutig sein. Wenn eine Serveranwendung aufgerufen wird, um ein verknüpftes Element zu bearbeiten, verwendet die Anwendung diesen Namen, um das Element zu suchen. Sie müssen nicht diese Funktion für eingebettete Elemente aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
