---
title: COleDataObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f85a1e6992e8d679401f4e0f97080efcf991446
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[COleDataObject::Attach](#attach)|Fügt das angegebene OLE-Datenobjekt, das `COleDataObject`.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|Fügt das Datenobjekt, das in die Zwischenablage kopiert wird.|  
|[BeginEnumFormats](#beginenumformats)|Bereitet für ein oder mehr nachfolgende `GetNextFormat` aufrufen.|  
|[COleDataObject::Detach](#detach)|Trennt die zugeordnete `IDataObject` Objekt.|  
|[COleDataObject::GetData](#getdata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in einem angegebenen Format.|  
|[COleDataObject::GetFileData](#getfiledata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in eine `CFile` Zeiger im angegebenen Format.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in eine `HGLOBAL` im angegebenen Format.|  
|[COleDataObject::GetNextFormat](#getnextformat)|Gibt das nächste Datenformat zurück.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|Überprüft, ob die Daten in einem angegebenen Format verfügbar sind.|  
|[COleDataObject::Release](#release)|Trennt und die zugeordnete frei `IDataObject` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDataObject`eine Basisklasse verfügt nicht über.  
  
 Diese Arten von Datenübertragungen enthalten eine Quelle und ein Ziel. Die Datenquelle wird als ein Objekt des implementiert die [COleDataSource](../../mfc/reference/coledatasource-class.md) Klasse. Wenn eine Zielanwendung Daten darin gelöscht wurde oder wird zum Einfügen aus der Zwischenablage, ein Objekt des Vorgangs aufgefordert die `COleDataObject` Klasse erstellt werden muss.  
  
 Diese Klasse können Sie bestimmen, ob die Daten in einem angegebenen Format vorhanden ist. Auch Auflisten der verfügbaren Datenformate oder Überprüfen Sie, ob ein bestimmtes Format verfügbar ist, und klicken Sie dann die Daten in das bevorzugte Format abrufen. Abrufen von Objekten auf verschiedene Weise, einschließlich der Verwendung von erfolgen eine [CFile](../../mfc/reference/cfile-class.md), wird ein `HGLOBAL`, oder ein **STGMEDIUM** Struktur.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Struktur im Windows SDK.  
  
 Weitere Informationen zur Verwendung von Datenobjekten in Ihrer Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `COleDataObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="attach"></a>COleDataObject::Attach  
 Mit dieser Funktion wird zum Zuordnen der `COleDataObject` Objekt mit einer OLE-Datenobjekt.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDataObject*  
 Verweist auf eine OLE-Datenobjekt.  
  
 `bAutoRelease`  
 **"True"** , wenn das OLE-Datenobjekt sein sollte freigegeben, wenn die `COleDataObject` Objekt wird zerstört; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) im Windows SDK.  
  
##  <a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 Mit dieser Funktion können Sie das Datenobjekt anfügen, die derzeit in der Zwischenablage ist die `COleDataObject` Objekt.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Aufrufen dieser Funktion sperrt die Zwischenablage, bis dieses Datenobjekt aufgehoben wird. Das Datenobjekt wird freigegeben, in der Destruktor für die `COleDataObject`. Weitere Informationen finden Sie unter [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) und [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) in der Win32-Dokumentation.  
  
##  <a name="beginenumformats"></a>BeginEnumFormats  
 Mit dieser Funktion wird für nachfolgende Aufrufe vorbereiten `GetNextFormat` zum Abrufen einer Liste von Datenformaten vom Element.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von `BeginEnumFormats`, befindet sich die Position des ersten Formats von dieses Datenobjekt unterstützt. Aufeinander folgende Aufrufe von `GetNextFormat` Listet die Liste der verfügbaren Formate in das Datenobjekt.  
  
 Verwenden Sie zum Überprüfen auf die Verfügbarkeit von Daten in einem bestimmten Format [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) im Windows SDK.  
  
##  <a name="coledataobject"></a>COleDataObject::COleDataObject  
 Erstellt ein `COleDataObject`-Objekt.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Aufruf von [COleDataObject::Attach](#attach) oder [COleDataObject::AttachClipboard](#attachclipboard) muss vor dem Aufruf von anderen erfolgen `COleDataObject` Funktionen.  
  
> [!NOTE]
>  Da einer der Parameter, die Drag & Drop-Handler ist, dass ein Zeiger auf eine `COleDataObject`, besteht keine Notwendigkeit zum Aufrufen dieses Konstruktors zur Unterstützung von Drag & Drop.  
  
##  <a name="detach"></a>COleDataObject::Detach  
 Mit dieser Funktion werden zum Trennen der `COleDataObject` Objekt aus seiner zugeordneten OLE-Datenobjekt nicht das Objekt freigegeben.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die OLE-Datenobjekt, das getrennt wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdata"></a>COleDataObject::GetData  
 Mit dieser Funktion wird zum Abrufen von Daten aus dem Element im angegebenen Format.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format, in dem Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die Daten erhält.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem Daten zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, die Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="getfiledata"></a>COleDataObject::GetFileData  
 Mit dieser Funktion wird zum Erstellen einer `CFile` oder `CFile`-abgeleitete Objekt und zum Abrufen von Daten im angegebenen Format in eine `CFile` Zeiger.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format, in dem Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem Daten zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, die Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue `CFile` oder `CFile`-abgeleitete Objekt, das Daten enthält, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig von der "Mittel" die Daten in gespeichert ist, ist der tatsächliche Typ verweist, zu der Rückgabewert möglicherweise `CFile`, `CSharedFile`, oder `COleStreamFile`.  
  
> [!NOTE]
>  Die `CFile` Besitzer des Objekts zugegriffen werden, den der Rückgabewert dieser Funktion durch den Aufrufer. Es liegt in der Verantwortung des Aufrufers, **löschen** der `CFile` -Objekt, und Schließen der Datei.  
  
 Weitere Informationen finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 Mit dieser Funktion wird einen globale Speicherblock zuordnen und zum Abrufen von Daten im angegebenen Format in ein `HGLOBAL`.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format, in dem Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die beschreibt des Format, in dem Daten zurückgegeben werden. Wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist er **NULL**, die Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des globalen Speicherblocks mit den Daten, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
##  <a name="getnextformat"></a>COleDataObject::GetNextFormat  
 Mit dieser Funktion wird wiederholt, um alle Formate zum Abrufen von Daten aus dem Element abzurufen.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur, die Informationen über das empfängt, wenn der Funktionsaufruf zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein anderes Format verfügbar ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von [BeginEnumFormats](#beginenumformats), befindet sich die Position des ersten Formats von dieses Datenobjekt unterstützt. Aufeinander folgende Aufrufe von `GetNextFormat` Listet die Liste der verfügbaren Formate in das Datenobjekt. Verwenden Sie diese Funktionen, um die verfügbaren Formate aufzulisten.  
  
 Rufen Sie zum Überprüfen der Verfügbarkeit eines bestimmten Formats [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) im Windows SDK.  
  
##  <a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein bestimmtes Format für das Abrufen von Daten aus der OLE-Element verfügbar ist.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Datenformat der Zwischenablage in die Struktur zu verwendende verweist `lpFormatEtc`. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von der systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das gewünschte Format beschreibt. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten `cfFormat`. Ist er **NULL**, die Standardwerte für die anderen Felder dienen der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Daten in das angegebene Format verfügbar sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion eignet sich vor dem Aufruf `GetData`, `GetFileData`, oder `GetGlobalData`.  
  
 Weitere Informationen finden Sie unter [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>COleDataObject::Release  
 Mit dieser Funktion können Sie den Besitz von Freigeben der ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) Objekt, das zuvor zugeordnet wurde die `COleDataObject` Objekt.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `IDataObject` zugeordnet wurde die `COleDataObject` durch Aufrufen von **Anfügen** oder `AttachClipboard` explizit oder durch das Framework. Wenn die `bAutoRelease` Parameter **Anfügen** ist **"false"**die `IDataObject` Objekt wird nicht freigegeben werden. In diesem Fall der Aufrufer ist verantwortlich für die Freigabe der `IDataObject` durch Aufrufen von [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataSource-Klasse](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
