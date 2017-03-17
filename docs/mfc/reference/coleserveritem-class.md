---
title: COleServerItem-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- servers, OLE
- OLE server applications, managing server documents
- OLE server applications, server interfaces
- OLE server documents
- COleServerItem class
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
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
ms.openlocfilehash: 49dd8cc258ebf96c91ac8ff1190f9a830b6bb5ec
ms.lasthandoff: 02/24/2017

---
# <a name="coleserveritem-class"></a>COleServerItem-Klasse
Stellt die Serverschnittstelle zu OLE-Elementen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|Erstellt ein `COleServerItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Fügt der Präsentation und Konvertierung von Formaten in einem `COleDataSource` Objekt.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Das Element kopiert in die Zwischenablage.|  
|[COleServerItem:: DoDragDrop](#dodragdrop)|Führt eine Drag & Drop-Operation.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|Ruft die Datenquelle für die Verwendung in Datenübertragung (Drag & Drop oder Zwischenablage) ab.|  
|[COleServerItem::GetDocument](#getdocument)|Gibt das Serverdokument, das das Element enthält.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Ruft die **CF_EMBEDSOURCE** Daten für ein OLE-Element.|  
|[COleServerItem::GetItemName](#getitemname)|Gibt den Namen des Elements zurück. Für nur verknüpfte Elemente verwendet.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Ruft die `CF_LINKSOURCE` Daten für ein OLE-Element.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Ruft die **CF_OBJECTDESCRIPTOR** Daten für ein OLE-Element.|  
|[COleServerItem::IsConnected](#isconnected)|Gibt an, ob das Element derzeit ein aktiver Container zugeordnet ist.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|Gibt an, ob das Element ein verknüpftes OLE-Element darstellt.|  
|[COleServerItem::NotifyChanged](#notifychanged)|Aktualisiert alle Container mit automatischen Verknüpfung aktualisieren.|  
|[COleServerItem::OnDoVerb](#ondoverb)|Wird aufgerufen, um eine Aktion ausführen.|  
|[COleServerItem:: OnDraw](#ondraw)|Aufgerufen, wenn der Container zum Zeichnen des Elements anfordert. die Implementierung erforderlich sind.|  
|[COleServerItem::OnDrawEx](#ondrawex)|Für spezielle zeichnen aufgerufen.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Aufgerufen, um die Daten abzurufen, die in die Zwischenablage kopiert würden.|  
|[COleServerItem::OnGetExtent](#ongetextent)|Aufgerufen, um die Größe des OLE-Elements abzurufen.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|Aufgerufen, um ein OLE-Element mit dem Inhalt des angegebenen Objekts Übertragung initialisieren.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Wird aufgerufen, um festzustellen, ob verknüpfte Elemente aktualisiert werden müssen.|  
|[COleServerItem::OnRenderData](#onrenderdata)|Ruft die Daten als Teil der verzögerte Rendering.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in ein `CFile` Objekt als Teil der verzögerte Rendering.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Abrufen von Daten in eine `HGLOBAL` als Teil der verzögerte Rendering.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Wird aufgerufen, um das Farbschema für das Element festgelegt.|  
|[COleServerItem::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten des festzulegen.|  
|[COleServerItem::OnSetExtent](#onsetextent)|Aufgerufen, um die Größe des OLE-Elements festgelegt.|  
|[COleServerItem::OnUpdate](#onupdate)|Aufgerufen, wird Wenn ein Teil des Dokuments das Element gehört geändert.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|Aufgerufen, um den Cache Darstellung aller Elemente im Dokument zu aktualisieren.|  
|[COleServerItem::SetItemName](#setitemname)|Legt den Namen des Elements. Für nur verknüpfte Elemente verwendet.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|Ruft das Objekt zum Speichern von konvertierungsformate verwendet.|  
|[COleServerItem::OnHide](#onhide)|Aufgerufen, um das OLE-Element auszublenden.|  
|[COleServerItem::OnOpen](#onopen)|Aufgerufen, um das OLE-Element in einem eigenen Fenster der obersten Ebene anzuzeigen.|  
|[COleServerItem::OnShow](#onshow)|Wird aufgerufen, wenn der Container anfordert, um das Element anzuzeigen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Teilt dem Server zu wie viel des OLE-Elements sichtbar ist.|  
  
## <a name="remarks"></a>Hinweise  
 Ein verknüpftes Element kann einige oder alle der Serverdokument darstellen. Ein eingebettetes Element stellt immer eine ganze Serverdokument dar.  
  
 Die `COleServerItem` -Klasse definiert mehrere überschreibbare Memberfunktionen, die vom OLE-System Dynamic Link Libraries (DLLs), aufgerufen werden, in der Regel als Antwort auf Anforderungen von der Container-Anwendung. Diese Memberfunktionen ermöglichen die containeranwendung, das Element indirekt auf verschiedene Art und Weise, wie z. B. bearbeiten anzeigen, die Verben ausführen oder Abrufen von Daten in verschiedenen Formaten.  
  
 Mit `COleServerItem`, eine Klasse ableiten und Implementieren der [OnDraw](#ondraw) und [Serialize](../../mfc/reference/cobject-class.md#serialize) Memberfunktionen. Die `OnDraw` -Funktion bietet die Metadateidarstellung eines Elements, wodurch angezeigt wird, wenn eine Steuerelementcontainer-Anwendung ein Verbunddokument wird geöffnet. Die `Serialize` Funktion der `CObject` stellt die systemeigene Darstellung eines Elements, sodass ein eingebettetes Element zwischen dem Server und Container übertragen werden. [OnGetExtent](#ongetextent) der natürliche Größe des Elements, das den Container, aktivieren den Container die Größe des Elements enthält.  
  
 Weitere Informationen zu Server und verwandten Themen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md) und "Erstellen einer Container/Server-Anwendung" im Artikel [Container: Erweiterte Features](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 Mit dieser Funktion können Sie die Präsentation und Konvertierung Formate für das OLE-Element in der angegebenen platzieren `COleDataSource` Objekt.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataSource`  
 Zeiger auf die `COleDataSource` -Objekt in die Daten eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Sie implementiert haben müssen die [OnDraw](#ondraw) Memberfunktion, die das Presentation-Format (ein Metadateibild) für das Element bereitzustellen. Unterstützung von anderen Konvertierungsformaten, registrieren Sie sie mithilfe der [COleDataSource](../../mfc/reference/coledatasource-class.md) zurückgegebene Objekt [GetDataSource](#getdatasource) und überschreiben die [OnRenderData](#onrenderdata) Memberfunktion, die Daten in den Formaten bereitstellen, unterstützen soll.  
  
##  <a name="coleserveritem"></a>COleServerItem::COleServerItem  
 Erstellt ein `COleServerItem` -Objekt und fügt dieses der Serverdokument Auflistung von Dokumentelementen.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 `pServerDoc`  
 Ein Zeiger auf das Dokument, das das neue Element enthalten soll.  
  
 `bAutoDelete`  
 Ein Flag, der angibt, ob das Objekt gelöscht werden kann, wenn ein Link freigegeben wird. Legen Sie den **FALSE** Wenn das `COleServerItem` Objekt ist ein wesentlicher Bestandteil Ihres Dokuments-Daten, die Sie löschen müssen. Legen Sie den **TRUE** Wenn das Objekt eine sekundäre Struktur verwendet, um einen Bereich in die Daten des Dokuments zu identifizieren, die vom Framework gelöscht werden können.  
  
##  <a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 Rufen Sie diese Funktion, um das OLE-Element in die Zwischenablage zu kopieren.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 Legen Sie den **TRUE** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden soll. Legen Sie den **FALSE** Wenn die Server-Anwendung Links nicht unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die Funktion die [OnGetClipboardData](#ongetclipboarddata) Member-Funktion zum Erstellen einer [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, das das OLE-Element-Daten in unterstützten Formaten enthält. Die Funktion setzt dann die `COleDataSource` Objekt in der Zwischenablage mit der [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Die `COleDataSource` Objekt enthält die Daten des systemeigenen und seine Darstellung im `CF_METAFILEPICT` -Format als auch Daten in alle Konvertierungsformaten, die Sie unterstützen möchten. Sie müssen implementiert haben [Serialize](../../mfc/reference/cobject-class.md#serialize) und [OnDraw](#ondraw) für diese Memberfunktion funktioniert.  
  
##  <a name="dodragdrop"></a>COleServerItem:: DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion zum Ausführen einer Drag & Drop-Operation.  
  
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
 Das Element Rechteck auf dem Bildschirm, in Pixel relativ zum Clientbereich.  
  
 `ptOffset`  
 Der Offset vom `lpItemRect` , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.  
  
 `bIncludeLink`  
 Legen Sie den **TRUE** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden soll. Legen Sie es auf **FALSE** Wenn Ihre Anwendung Links nicht unterstützt.  
  
 `dwEffects`  
 Bestimmt die Effekte, die die Quelle des Ziehvorgangs des Ziehvorgangs (eine Kombination aus kopieren, verschieben und Link) zugelassen werden.  
  
 `lpRectStartDrag`  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DROPEFFECT`-Enumeration. Es ist `DROPEFFECT_MOVE`, die ursprünglichen Daten entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Drag & Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor die durch angegebene Rechteck verlässt `lpRectStartDrag` oder eine angegebene Anzahl an Millisekunden verstrichen sind. Wenn `lpRectStartDrag` ist **NULL**, ein Standardrechteck wird verwendet, sodass das Ziehen beginnt, wenn der Mauszeiger ein Pixel verschoben.  
  
 Die Verzögerungszeit wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerung ändern, durch Aufrufen von [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie nicht die Verzögerung angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Windows 95/98 Drag-Verzögerungszeit wird in eine zwischengespeicherte Version der Windows-Taste gespeichert. INI.  
  
 Für Weitere Informationen ziehen ist Verzögerung Informationen in der Registrierung gespeicherten oder. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 Mit dieser Funktion können Sie den angegebenen füllen [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt mit allen Daten, die in die Zwischenablage kopiert werden würde, wenn Sie aufgerufen [CopyToClipboard](#copytoclipboard) (die gleichen Daten würden auch übertragen werden, wenn Sie aufgerufen [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataSource`  
 Zeiger auf die `COleDataSource` -Objekt, das das OLE-Element-Daten in allen unterstützten Formaten empfängt.  
  
 `bIncludeLink`  
 **TRUE** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden soll. **FALSE** Wenn die Server-Anwendung Links nicht unterstützt.  
  
 `lpOffset`  
 Der Offset in Pixel, der den Cursor vom Ursprung des Objekts.  
  
 `lpSize`  
 Die Größe des Objekts in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [GetEmbedSourceData](#getembedsourcedata) Member-Funktion zum Abrufen der systemeigenen Daten für die OLE-Element und ruft die [AddOtherClipboardData](#addotherclipboarddata) Memberfunktion Präsentationsformat und eine konvertierungsformate unterstützt. Wenn `bIncludeLink` ist **TRUE**, ruft die Funktion auch [GetLinkSourceData](#getlinksourcedata) die Link-Daten für das Element abgerufen werden.  
  
 Überschreiben Sie diese Funktion, wenn Formaten sollen eine `COleDataSource` Objekt vor oder nach diesen Formaten, die vom `CopyToClipboard`.  
  
##  <a name="getdatasource"></a>COleServerItem::GetDataSource  
 Rufen Sie diese Funktion zum Abrufen der [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt verwendet, um die konvertierungsformate zu speichern, die die Server-Anwendung unterstützt.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `COleDataSource` Objekt verwendet, um die konvertierungsformate zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Server-Anwendung Daten in einer Vielzahl von Formaten während der Datenübertragung Vorgänge anbieten möchten, registrieren Sie diesen Formaten mit den `COleDataSource` von dieser Funktion zurückgegebene Objekt. Angenommen, Sie möchten eine **CF_TEXT** Darstellung des OLE-Elements für die Zwischenablage oder Drag & Drop-Vorgänge, registrieren Sie das Format mit der `COleDataSource` Objekt diese Funktion gibt zurück, und klicken Sie dann überschreiben die **OnRenderXxxData** Memberfunktion, die die Daten.  
  
##  <a name="getdocument"></a>COleServerItem::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf das Dokument, das das Element enthält.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht den Zugriff auf die Server-Dokument, das Sie als Argument übergeben der `COleServerItem` Konstruktor.  
  
##  <a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 Rufen Sie diese Funktion zum Abrufen der **CF_EMBEDSOURCE** Daten für ein OLE-Element.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStgMedium`  
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhalten die **CF_EMBEDSOURCE** Daten für das OLE-Element.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Format enthält die Daten des systemeigenen. Sie müssen implementiert haben die `Serialize` Memberfunktion für diese Funktion ordnungsgemäß funktioniert.  
  
 Das Ergebnis kann anschließend an eine Datenquelle hinzugefügt werden, mithilfe von [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion wird automatisch aufgerufen [COleServerItem::OnGetClipboardData](#ongetclipboarddata).  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemname"></a>COleServerItem::GetItemName  
 Rufen Sie diese Funktion zum Abrufen des Namens des Elements.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Name des Elements.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion nur für verknüpfte Elemente.  
  
##  <a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 Rufen Sie diese Funktion zum Abrufen der `CF_LINKSOURCE` Daten für ein OLE-Element.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStgMedium`  
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhalten die `CF_LINKSOURCE` Daten für das OLE-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Format schließt die CLSID, die den Typ des OLE-Elements und die Informationen, die erforderlich sind, um das Dokument mit der OLE-Element beschreibt.  
  
 Das Ergebnis kann anschließend hinzugefügt werden, um eine Datenquelle mit [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion wird automatisch aufgerufen [OnGetClipboardData](#ongetclipboarddata).  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 Rufen Sie diese Funktion zum Abrufen der **CF_OBJECTDESCRIPTOR** Daten für ein OLE-Element.  
  
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
 Zeiger auf die [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die erhalten die **CF_OBJECTDESCRIPTOR** Daten für das OLE-Element.  
  
### <a name="remarks"></a>Hinweise  
 Kopiert die Informationen in der **STGMEDIUM** Struktur verweist `lpStgMedium`. Dieses Format enthält, die für das Dialogfeld "Inhalte einfügen" benötigten Informationen.  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isconnected"></a>COleServerItem::IsConnected  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element verbunden ist.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element verbunden ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein OLE-Element gilt als verbunden, wenn eine oder mehrere Container Verweise auf das Element. Ein Element verbunden ist, wenn der Verweiszähler größer als 0 ist oder ein eingebettetes Element ist.  
  
##  <a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element ein verknüpftes Element ist.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element ein verknüpftes Element ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Element ist verknüpft, wenn das Element gültig ist und nicht in das Dokument der Liste der eingebetteten Elemente zurückgegeben. Ein verknüpftes Element möglicherweise oder ist nicht in einen Container verbunden.  
  
 Es ist üblich, die gleiche Klasse für verknüpfte und eingebettete Elemente verwenden. `IsLinkedItem`können Sie verknüpfte Elemente verhalten sich anders als eingebettete Elemente stellen zwar oft der Code.  
  
##  <a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 Dieses Element weist den Server wie viel des Objekts im Containerdokument sichtbar ist.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des [OnSetExtent](#onsetextent) legt dieses Element fest.  
  
##  <a name="notifychanged"></a>COleServerItem::NotifyChanged  
 Rufen Sie diese Funktion aus, nachdem das verknüpfte Element geändert wurde.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT` -Enumeration, der angibt, welche Aspekte des OLE-Elements geändert hat. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Containerelement mit automatischen Verknüpfung mit dem Dokument verknüpft ist, wird das Element die Änderungen entsprechend aktualisiert. In Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben [COleClientItem:: OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Reaktion aufgerufen wird.  
  
##  <a name="ondoverb"></a>COleServerItem::OnDoVerb  
 Aufgerufen, um das angegebene Verb aufzurufen.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>Parameter  
 `iVerb`  
 Gibt das Verb ausführen. Es kann eine der folgenden sein:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|1|Sekundäre verb|(Keine)|  
|– 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|– 2|Bearbeiten des Konfigurationselements in separaten Fenster|`OLEIVERB_OPEN`|  
|– 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert –&1; ist in der Regel ein Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat –&2; die gleiche Auswirkung wie –&1;. Zusätzliche Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die standardmäßige Implementierung ruft die [OnShow](#onshow) Memberfunktion, wenn das primäre Verb oder `OLEIVERB_SHOW` angegeben ist, [OnOpen](#onopen) Wenn Verbs sekundäre oder `OLEIVERB_OPEN` angegeben ist, und [OnHide](#onhide) Wenn `OLEIVERB_HIDE` angegeben wird. Die standardmäßige Implementierung ruft `OnShow` Wenn `iVerb` ist keiner der oben aufgeführten Verben.  
  
 Überschreiben Sie diese Funktion, wenn Ihr primäre Verb nicht das Element angezeigt wird. Z. B. wenn das Element einer Tonaufnahme und seine primäre Verb Play ist, müssten nicht Sie die Server-Anwendung, um die Wiedergabe des Elements angezeigt.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondraw"></a>COleServerItem:: OnDraw  
 Wird von Framework aufgerufen, um das OLE-Element in einer Metadatei zu rendern.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt auf der das Element gezeichnet werden soll. Anzeigekontext wird automatisch dann an den Kontext der Attribut-Anzeige verbunden, damit Attribut-Funktionen aufgerufen werden kann, obwohl dies also die Metadatei gerätespezifische machen würden.  
  
 `rSize`  
 Größe in **HIMETRIC** Einheiten, in dem die Metadatei gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element erfolgreich gezeichnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Metadateidarstellung des OLE-Elements wird verwendet, um das Element in der Container-Anwendung anzuzeigen. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird von die Metadatei verwendet die [zeichnen](../../mfc/reference/coleclientitem-class.md#draw) -Memberfunktion des entsprechenden [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekt. Es ist keine Standardimplementierung vorhanden. Sie müssen diese Funktion zum Zeichnen des Elements den angegebenen Gerätekontext überschreiben.  
  
##  <a name="ondrawex"></a>COleServerItem::OnDrawEx  
 Vom Framework aufgerufen wird für alle zeichnen.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt auf der das Element gezeichnet werden soll. Der Domänencontroller wird automatisch verbunden dem DC-Attribut damit Attribut-Funktionen aufgerufen werden kann, obwohl dies also die Metadatei gerätespezifische machen würden.  
  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
 `rSize`  
 Größe des Elements im **HIMETRIC** Einheiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Element erfolgreich gezeichnet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `OnDraw` Wenn `DVASPECT` gleich `DVASPECT_CONTENT`; andernfalls schlägt fehl.  
  
 Überschreiben Sie diese Funktion zum Bereitstellen von Präsentationsdaten für Aspekte außer `DVASPECT_CONTENT`, wie z. B. `DVASPECT_ICON` oder `DVASPECT_THUMBNAIL`.  
  
##  <a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 Aufgerufen, zum Abrufen einer `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) Member-Funktion.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 Legen Sie den **TRUE** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden soll. Legen Sie den **FALSE** Wenn die Server-Anwendung Links nicht unterstützt.  
  
 `lpOffset`  
 Der Offset des Mauszeigers auf den Ursprung des-Objekts in Pixeln.  
  
 `lpSize`  
 Die Größe des Objekts in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, das Daten in der Zwischenablage enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetextent"></a>COleServerItem::OnGetExtent  
 Aufgerufen, zum Abrufen der Größe in **HIMETRIC** Einheiten des OLE-Elements.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen abgerufen werden sollen. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
 `rSize`  
 Ein Verweis auf ein `CSize` -Objekt, das die Größe des OLE-Elements erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen es selbst implementieren. Überschreiben Sie diese Funktion, wenn speziellen Verarbeitung ausführen, wenn eine Anforderung für die Größe des OLE-Elements verwendet werden soll.  
  
##  <a name="onhide"></a>COleServerItem::OnHide  
 Aufgerufen, um das OLE-Element auszublenden.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standard-Aufrufe **COleServerDoc::OnShowDocument (FALSE)**. Die Funktion benachrichtigt, dass das OLE-Element ausgeblendet wurde auch die Container. Überschreiben Sie diese Funktion, wenn speziellen Verarbeitung auszuführen, wenn ein OLE-Element ausgeblendet werden soll.  
  
##  <a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 Aufgerufen, um ein OLE-Element mit dem Inhalt des initialisieren `pDataObject`.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Ein Zeiger auf ein OLE-Objekt, Daten, die Daten in verschiedene Formate für das OLE-Element zu initialisieren.  
  
 `bCreation`  
 **True,** , wenn die Funktion aufgerufen wird, initialisieren Sie ein OLE-Element, das durch eine Container-Anwendung neu erstellt wird. **FALSE** , wenn die Funktion aufgerufen wird, um den Inhalt von einem bereits vorhandenen OLE-Element ersetzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bCreation` ist **TRUE**, diese Funktion wird aufgerufen, wenn ein Container neues Objekt einfügen basierend auf der aktuellen Auswahl implementiert. Die ausgewählten Daten werden verwendet, wenn das neue OLE-Element zu erstellen. Zum Beispiel wenn markieren einen Zellbereich in ein Tabellenkalkulationsprogramm und neues Objekt einfügen zum Erstellen eines Diagramms mithilfe der Werte im ausgewählten Bereich anhand. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um Wählen Sie ein ungültiges Format von den `pDataObject` und initialisieren Sie das OLE-Element, das basierend auf den angegebenen Daten. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onopen"></a>COleServerItem::OnOpen  
 Aufgerufen, um das OLE-Element in eine separate Instanz der Server-Anwendung und nicht an Ort anzuzeigen.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung aktiviert den ersten Frame-Fenster das Dokument, das OLE-Element enthält. Wenn die Anwendung eines Mini-Servers ist, zeigt die standardmäßige Implementierung im Hauptfenster. Die Funktion benachrichtigt auch dem Container, dass das OLE-Element geöffnet wurde.  
  
 Überschreiben Sie diese Funktion, wenn Sie speziellen Verarbeitung ausführen, wenn Sie ein OLE-Element zu öffnen möchten. Dies ist besonders mit verknüpften Elementen soll die Auswahl auf den Link festgelegt wird, wenn sie geöffnet ist.  
  
 Weitere Informationen finden Sie unter [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 Aufgerufen, um festzustellen, ob verknüpfte Elemente im aktuellen Dokument nicht mehr aktuell sind.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, verfügt das Dokument Elemente Updates sind erforderlich; 0, wenn alle Elemente auf dem neuesten Stand sind.  
  
### <a name="remarks"></a>Hinweise  
 Ein Element ist veraltet, wenn dem Quelldokument geändert wurde, aber das verknüpfte Element entsprechend die Änderungen im Dokument nicht aktualisiert wurde.  
  
##  <a name="onrenderdata"></a>COleServerItem::OnRenderData  
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
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) oder [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Member-Funktion für das verzögerte Rendering. Ruft die standardmäßige Implementierung dieser Funktion [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata), wenn das angegebene Speichermedium eine Datei oder einen Speicher ist. Wenn keines der folgenden Formate angegeben wird, wird die standardmäßige Implementierung gibt 0 zurück und führt keine Aktion.  
  
 Wenn `lpStgMedium` ->  *Tymed* ist **TYMED_NULL**, **STGMEDIUM** sollte zugeordnet und entsprechend den Angaben von gefüllt *LpFormatEtc-> Tymed*. Wenn dies nicht **TYMED_NULL**, **STGMEDIUM** mit Daten ausgefüllt werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Ihre Daten klein und feste Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), und [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 Aufgerufen, um die Daten im angegebenen Format abgerufen, wenn das Speichermedium eine Datei ist.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die Angabe des Formats, in dem Informationen angefordert.  
  
 `pFile`  
 Verweist auf ein `CFile` Objekt, in dem die Daten gerendert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten empfiehlt es sich, eine der anderen Versionen dieser Funktion stattdessen überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
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
 Verweist auf ein Handle für den globalen Arbeitsspeicher, in dem die Daten zurückgegeben werden. Wenn kein Speicher zugewiesen wurde, kann dieser Parameter **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Format ist eines der zuvor platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die standardmäßige Implementierung dieser Funktion einfach gibt **FALSE**.  
  
 Wenn `phGlobal` ist **NULL**, ein neues `HGLOBAL` zugeordnet und in zurückgegeben werden sollte `phGlobal`. Andernfalls die `HGLOBAL` angegebene `phGlobal` mit Daten gefüllt werden soll. Die Datenmenge der `HGLOBAL` darf sich nicht auf die aktuelle Größe des Speicherblocks. Der Block kann nicht darüber hinaus auf eine größere Größe neu zugewiesen werden.  
  
 Dies ist eine erweiterte überschrieben. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihrer Daten sollten Sie stattdessen eine der anderen Versionen dieser Funktion zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).  
  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 Vom Framework aufgerufen wird, geben Sie eine Farbpalette verwendet werden, wenn das OLE-Element zu bearbeiten.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogPalette`  
 Zeiger auf eine Windows [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Farbpalette verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Funktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die standardmäßige Implementierung gibt **FALSE**. Überschreiben Sie diese Funktion, wenn Sie die empfohlene Palette verwenden möchten. Die Server-Anwendung ist nicht erforderlich, die vorgeschlagene Palette verwenden.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetdata"></a>COleServerItem::OnSetData  
 Aufgerufen, um das OLE-Element-Daten mit den angegebenen Daten zu ersetzen.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur, die das Format der Daten angibt.  
  
 `lpStgMedium`  
 Zeiger auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur, in dem sich die Daten befinden.  
  
 `bRelease`  
 Gibt an, wer das Speichermedium nach Abschluss des Funktionsaufrufs hat. Der Aufrufer entscheidet, die verantwortlich für die Freigabe der Ressourcen für das Speichermedium zugewiesen ist. Der Aufrufer wird `bRelease`. Wenn `bRelease` ist ungleich NULL ist, das Serverelement übernimmt den Besitz, Freigeben von das Medium nach der Verwendung. Wenn `bRelease` ist 0, der Aufrufer besitzt und das Serverelement kann das Speichermedium nur für die Dauer des Aufrufs.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Server-Element wird nicht die Daten verwendet, bis er erfolgreich abgerufen hat. D. h. dauert nicht den Besitz es 0 zurück. Wenn die Datenquelle den Besitz übernimmt, werden durch Aufrufen von Speichermedium freigibt der [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Funktion.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das OLE-Element-Daten mit den angegebenen Daten zu ersetzen. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), und [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetextent"></a>COleServerItem::OnSetExtent  
 Aufgerufen, um dem OLE-Element mitzuteilen, wie viel Speicherplatz im Containerdokument verfügbar ist.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen angegeben sind. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
 `size`  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Struktur, die die neue Größe des OLE-Elements angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die standardmäßige Implementierung legt die [M_sizeExtent](#m_sizeextent) Element in die angegebene Größe Wenn `nDrawAspect` ist `DVASPECT_CONTENT`; andernfalls wird 0 zurückgegeben. Überschreiben Sie diese Funktion zum Ausführen der besonderen Verarbeitung, wenn Sie die Größe des Elements ändern.  
  
##  <a name="onshow"></a>COleServerItem::OnShow  
 Vom Framework aufgerufen wird, weisen Sie die Server-Anwendung zum Anzeigen des OLE-Elements an.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion in der Regel aufgerufen wird, wenn der Benutzer von der Container-Anwendung ein Element erstellt oder ein Verb, z. B. bearbeiten, erfordert, dass das Element angezeigt werden. Die standardmäßige Implementierung versucht, die direkte Aktivierung. Wenn dies fehlschlägt, ruft die Funktion die `OnOpen` Memberfunktion, die das OLE-Element in einem separaten Fenster angezeigt.  
  
 Überschreiben Sie diese Funktion ggf. spezielle Verarbeitungsschritte gleichzeitig ausführen, wenn ein OLE-Element angezeigt wird.  
  
##  <a name="onupdate"></a>COleServerItem::OnUpdate  
 Wird vom Framework aufgerufen, wenn ein Element geändert wurde.  
  
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
 Ein Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann einer der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft [NotifyChanged](#notifychanged), unabhängig von den Hinweis oder die Absender.  
  
##  <a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 Aufgerufen, um alle Elemente im Serverdokument zu aktualisieren.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) für alle `COleClientItem` Objekte im Dokument.  
  
##  <a name="setitemname"></a>COleServerItem::SetItemName  
 Rufen Sie diese Funktion, wenn Sie ein verknüpftes Element, legen Sie seinen Namen erstellen.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Ein Zeiger auf den neuen Namen des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss innerhalb des Dokuments eindeutig sein. Wenn eine Server-Anwendung aufgerufen wird, um ein verknüpftes Element zu bearbeiten, verwendet die Anwendung diesen Namen nach dem Element suchen. Sie müssen nicht zum Aufrufen dieser Funktion für eingebettete Elemente.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)

