---
title: COleDataObject-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67a4f03db6a7c4cf37e59e05464865016d836097
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215007"
---
# <a name="coledataobject-class"></a>COleDataObject-Klasse
Wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|Erstellt ein `COleDataObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|Fügt das angegebene Objekt der OLE-Daten in die `COleDataObject`.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|Fügt das Datenobjekt, das in der Zwischenablage befindet.|  
|[BeginEnumFormats](#beginenumformats)|Vorbereitet für ein oder mehr nachfolgende `GetNextFormat` aufrufen.|  
|[COleDataObject::Detach](#detach)|Trennt die zugeordnete `IDataObject` Objekt.|  
|[COleDataObject::GetData](#getdata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in einem angegebenen Format.|  
|[COleDataObject::GetFileData](#getfiledata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in einem `CFile` Zeiger im angegebenen Format.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in eine `HGLOBAL` im angegebenen Format.|  
|[COleDataObject::GetNextFormat](#getnextformat)|Gibt das nächste Datenformat zurück.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|Überprüft, ob die Daten in einem angegebenen Format verfügbar sind.|  
|[COleDataObject::Release](#release)|Trennt und die zugeordnete frei `IDataObject` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDataObject` eine Basisklasse keinen.  
  
 Diese Arten von Datenübertragungen enthalten eine Quelle und Ziel. Die Datenquelle wird als ein Objekt implementiert die [COleDataSource](../../mfc/reference/coledatasource-class.md) Klasse. Jedes Mal, wenn eine Zielanwendung Daten darin gelöscht wurde oder wird gebeten, führen Sie einen Einfügevorgang aus der Zwischenablage, ein Objekt der `COleDataObject` Klasse erstellt werden muss.  
  
 Diese Klasse ermöglicht Ihnen, zu bestimmen, ob die Daten in einem angegebenen Format vorhanden sind. Auch Auflisten der verfügbaren Datenformate oder Überprüfen Sie, ob es sich bei ein bestimmtes Format verfügbar ist, und klicken Sie dann die Daten in das bevorzugte Format abzurufen. Abrufen von Objekten kann erreicht werden, auf verschiedene Arten, einschließlich der Verwendung von einer [CFile](../../mfc/reference/cfile-class.md), ein HGLOBAL oder ein `STGMEDIUM` Struktur.  
  
 Weitere Informationen finden Sie unter den [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur im Windows SDK.  
  
 Weitere Informationen zur Verwendung von Datenobjekten in Ihrer Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `COleDataObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="attach"></a>  COleDataObject::Attach  
 Mit dieser Funktion wird zum Zuordnen der `COleDataObject` Objekt mit Daten OLE-Objekt.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDataObject*  
 Verweist auf ein OLE-Datenobjekt.  
  
 *bAutoRelease*  
 TRUE, wenn das OLE-Objekt werden sollte freigegeben, wenn die `COleDataObject` Objekt wird zerstört; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) im Windows SDK.  
  
##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard  
 Mit dieser Funktion können Sie das Datenobjekt, das Anfügen, die derzeit in der Zwischenablage befinden, wird die `COleDataObject` Objekt.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Aufrufen dieser Funktion sperrt die Zwischenablage, bis dieses Datenobjekt freigegeben wird. Das Objekt wird freigegeben, in der Destruktor für die `COleDataObject`. Weitere Informationen finden Sie unter [OpenClipboard](/windows/desktop/api/winuser/nf-winuser-openclipboard) und [CloseClipboard](/windows/desktop/api/winuser/nf-winuser-closeclipboard) in der Win32-Dokumentation.  
  
##  <a name="beginenumformats"></a>  BeginEnumFormats  
 Mit dieser Funktion wird für nachfolgende Aufrufe vorbereiten `GetNextFormat` zum Abrufen einer Liste von Datenformaten aus dem Element.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von `BeginEnumFormats`, befindet sich die Position des ersten Formats von diesem Datenobjekt unterstützt werden. Aufeinander folgende Aufrufe von `GetNextFormat` Listet die Liste der verfügbaren Formate im Datenobjekt.  
  
 Verwenden Sie zum Überprüfen auf die Verfügbarkeit von Daten in einem bestimmten Format [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) im Windows SDK.  
  
##  <a name="coledataobject"></a>  COleDataObject::COleDataObject  
 Erstellt ein `COleDataObject`-Objekt.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Aufruf von [COleDataObject::Attach](#attach) oder [COleDataObject::AttachClipboard](#attachclipboard) muss vor dem Aufruf von anderen erfolgen `COleDataObject` Funktionen.  
  
> [!NOTE]
>  Da einer der Parameter an die Drag & Drop-Handler ist, dass ein Zeiger auf eine `COleDataObject`, besteht keine Notwendigkeit zum Aufrufen dieses Konstruktors zur Unterstützung von Drag & Drop.  
  
##  <a name="detach"></a>  COleDataObject::Detach  
 Mit dieser Funktion wird beim Trennen der `COleDataObject` Objekt von dem zugeordneten Objekt der OLE-Daten ohne das Objekt freigeben.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die OLE-Datenobjekt, das getrennt wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdata"></a>  COleDataObject::GetData  
 Rufen Sie diese Funktion zum Abrufen von Daten aus dem Element im angegebenen Format.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Format, in dem Daten sind, zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpStgMedium*  
 Verweist auf eine [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) -Struktur, die Daten empfangen werden.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in der Daten sind, zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden die Standardwerte für die anderen Felder in verwendet die `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="getfiledata"></a>  COleDataObject::GetFileData  
 Mit dieser Funktion wird zum Erstellen einer `CFile` oder `CFile`-abgeleitete Objekt und zum Abrufen von Daten im angegebenen Format in eine `CFile` Zeiger.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Format, in dem Daten sind, zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in der Daten sind, zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden die Standardwerte für die anderen Felder in verwendet die `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf den neuen `CFile` oder `CFile`-abgeleitetes Objekt, die Daten enthält, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig von dem Medium sich die Daten in befindet der tatsächliche Typ verweist der zurückgegebene Wert möglicherweise `CFile`, `CSharedFile`, oder `COleStreamFile`.  
  
> [!NOTE]
>  Die `CFile` Objekt zugegriffen wird, durch den Rückgabewert dieser Funktion ist im Besitz des Aufrufers. Es liegt in der Verantwortung des Aufrufers, **löschen** der `CFile` -Objekt, und Schließen der Datei.  
  
 Weitere Informationen finden Sie unter [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData  
 Rufen Sie diese Funktion, die einen globalen Speicherblock zuzuweisen und die Daten im angegebenen Format in HGLOBAL abzurufen.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Das Format, in dem Daten sind, zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, beschreibt das Format, in der Daten sind, zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter *CfFormat*. Wenn es NULL ist, werden die Standardwerte für die anderen Felder in verwendet die `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des globalen Speicherblocks mit den Daten, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat  
 Rufen Sie diese Funktion, um alle Formate zum Abrufen von Daten aus dem Element zu erhalten.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Parameter  
 *lpFormatEtc*  
 Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die Informationen über das empfängt, wenn der Funktionsaufruf zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn ein anderes Format verfügbar ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von [BeginEnumFormats](#beginenumformats), befindet sich die Position des ersten Formats von diesem Datenobjekt unterstützt werden. Aufeinander folgende Aufrufe von `GetNextFormat` Listet die Liste der verfügbaren Formate im Datenobjekt. Verwenden Sie diese Funktionen, um die verfügbaren Formate aufzulisten.  
  
 Rufen Sie zum Überprüfen der Verfügbarkeit von einem bestimmten Format [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) im Windows SDK.  
  
##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein bestimmtes Format für das Abrufen von Daten aus der OLE-Element verfügbar ist.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *cfFormat*  
 Zwischenablage-Datenformats, die in der Struktur verwendet werden auf die von *LpFormatEtc*. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Funktion.  
  
 *lpFormatEtc*  
 Verweist auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das gewünschte Format beschreibt. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn es NULL ist, werden die Standardwerte für die anderen Felder in verwendet die `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Daten im angegebenen Format verfügbar sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist hilfreich, vor dem Aufruf `GetData`, `GetFileData`, oder `GetGlobalData`.  
  
 Weitere Informationen finden Sie unter [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>  COleDataObject::Release  
 Mit dieser Funktion können Sie den Besitz des wieder die [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) -Objekt, das zuvor zugeordnet war die `COleDataObject` Objekt.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `IDataObject` zugeordnet wurde die `COleDataObject` durch Aufrufen von `Attach` oder `AttachClipboard` explizit oder durch das Framework. Wenn die *bAutoRelease* Parameter `Attach` ist "false", die `IDataObject` Objekt wird nicht freigegeben werden. In diesem Fall der Aufrufer ist verantwortlich für die Freigabe der `IDataObject` durch Aufrufen von [IUnknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataSource-Klasse](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
