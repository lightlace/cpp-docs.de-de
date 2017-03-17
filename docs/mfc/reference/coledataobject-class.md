---
title: COleDataObject Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject interface, MFC encapsulation
- data transfer [C++]
- data transfer [C++], OLE
- OLE data transfer [C++]
- COleDataObject class
- uniform data transfer, OLE
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
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
ms.openlocfilehash: f30ca208252fe81f1e47d9e8f817cb9137656540
ms.lasthandoff: 02/24/2017

---
# <a name="coledataobject-class"></a>COleDataObject-Klasse
Wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|Erstellt ein `COleDataObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|Fügt das angegebene Objekt der OLE-Daten in der `COleDataObject`.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|Fügt das Datenobjekt, das in der Zwischenablage ist.|  
|[BeginEnumFormats](#beginenumformats)|Vorbereitet für ein oder mehr nachfolgende `GetNextFormat` aufrufen.|  
|[COleDataObject::Detach](#detach)|Trennt die zugeordnete `IDataObject` Objekt.|  
|[COleDataObject::GetData](#getdata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in einem angegebenen Format.|  
|[COleDataObject::GetFileData](#getfiledata)|Kopiert Daten aus der angefügten Daten OLE-Objekts in einem `CFile` Zeiger im angegebenen Format.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|Kopiert Daten aus der angefügten Daten OLE-Objekts in ein `HGLOBAL` im angegebenen Format.|  
|[COleDataObject::GetNextFormat](#getnextformat)|Gibt das nächste Datenformat zurück.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|Überprüft, ob die Daten in einem angegebenen Format verfügbar sind.|  
|[COleDataObject::Release](#release)|Trennt und die zugeordnete frei `IDataObject` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDataObject`eine Basisklasse keinen.  
  
 Diese Arten von Datenübertragungen enthalten eine Quelle und ein Ziel. Die Datenquelle wird als ein Objekt implementiert die [COleDataSource](../../mfc/reference/coledatasource-class.md) Klasse. Jedes Mal, wenn eine Zielanwendung enthält Daten, die Sie gelöscht oder dazu aufgefordert wird, führen Sie einen Einfügevorgang aus der Zwischenablage ein Objekt der `COleDataObject` Klasse erstellt werden muss.  
  
 Dieser Klasse können Sie bestimmen, ob die Daten in einem angegebenen Format vorhanden. Auch Auflisten der verfügbaren Datenformaten oder Überprüfen Sie, ob ein bestimmtes Format verfügbar ist, und dann die Daten im gewünschten Format abrufen. Abrufen von Objekten kann auf verschiedene Arten, einschließlich der Verwendung von erreicht werden eine [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, oder ein **STGMEDIUM** Struktur.  
  
 Weitere Informationen finden Sie unter der [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zur Verwendung von Datenobjekten in Ihrer Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `COleDataObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="attach"></a>COleDataObject::Attach  
 Mit dieser Funktion wird zum Zuordnen der `COleDataObject` Objekt mit Daten OLE-Objekt.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDataObject*  
 Verweist auf ein Objekt für die Daten.  
  
 `bAutoRelease`  
 **True,** , wenn das OLE-Objekt sein sollte freigegeben, wenn die `COleDataObject` Objekt wird zerstört; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 Rufen Sie diese Funktion, um das Objekt anzufügen, die derzeit in der Zwischenablage an der `COleDataObject` Objekt.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Aufrufen dieser Funktion sperrt die Zwischenablage bis zur Veröffentlichung dieses Datenobjekt. Das Objekt wird freigegeben, in der Destruktor für die `COleDataObject`. Weitere Informationen finden Sie unter [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) und [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) in der Win32-Dokumentation.  
  
##  <a name="beginenumformats"></a>BeginEnumFormats  
 Rufen Sie diese Funktion für die vorzubereitende für nachfolgende Aufrufe von `GetNextFormat` für das Abrufen einer Liste von Datenformaten aus dem Element.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von `BeginEnumFormats`, die Position des ersten Formats von diesem Datenobjekt unterstützt wird gespeichert. Aufeinander folgende Aufrufe von `GetNextFormat` wird die Liste der verfügbaren Formate in das Objekt auflisten.  
  
 Verwenden Sie zum Überprüfen auf die Verfügbarkeit der Daten in einem bestimmten Format [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="coledataobject"></a>COleDataObject::COleDataObject  
 Erstellt ein `COleDataObject`-Objekt.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Aufruf von [COleDataObject::Attach](#attach) oder [COleDataObject::AttachClipboard](#attachclipboard) erfolgen muss vor dem Aufruf von anderen `COleDataObject` Funktionen.  
  
> [!NOTE]
>  Da der Parameter der Drag & Drop-Handler ist ein Zeiger auf eine `COleDataObject`, besteht keine Notwendigkeit zur Unterstützung von Drag & Drop-Konstruktor aufgerufen.  
  
##  <a name="detach"></a>COleDataObject::Detach  
 Rufen Sie diese Funktion zum Trennen der `COleDataObject` Objekt aus seiner zugeordneten OLE-Datenobjekte ohne Freigabe des Datenobjekts.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die OLE-Datenobjekte, die getrennt wurde.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdata"></a>COleDataObject::GetData  
 Rufen Sie diese Funktion zum Abrufen von Daten aus dem Element im angegebenen Format.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format der Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpStgMedium`  
 Verweist auf eine [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) -Struktur, die Daten empfängt.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format der Daten zurückgegeben werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, die Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getfiledata"></a>COleDataObject::GetFileData  
 Rufen Sie diese Funktion zum Erstellen einer `CFile` oder `CFile`-abgeleitete Objekt und Abrufen von Daten im angegebenen Format in eine `CFile` Zeiger.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format der Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format der Daten zurückgegeben werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, die Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue `CFile` oder `CFile`-abgeleitetes Objekt, das Daten enthält, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig von dem Medium sich die Daten in befindet der tatsächliche Typ, auf den der Rückgabewert möglicherweise `CFile`, `CSharedFile`, oder `COleStreamFile`.  
  
> [!NOTE]
>  Das `CFile` Objekt zugegriffen, indem der Rückgabewert dieser Funktion ist im Besitz des Aufrufers. Es liegt in der Verantwortung des Aufrufers, **löschen** der `CFile` -Objekt, damit die Datei geschlossen.  
  
 Weitere Informationen finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 Mit dieser Funktion wird einen globale Speicherblock zuordnen und Abrufen von Daten im angegebenen Format in ein `HGLOBAL`.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Das Format der Daten zurückgegeben werden. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur beschreibt das Format der Daten zurückgegeben werden. Wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten, geben Sie einen Wert für diesen Parameter `cfFormat`. Ist dies **NULL**, die Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des globalen Speicherblocks mit den Daten, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnextformat"></a>COleDataObject::GetNextFormat  
 Mit dieser Funktion wird wiederholt, um alle Formate zum Abrufen von Daten von einem Element zu erhalten.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFormatEtc`  
 Verweist auf die [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur, die Informationen empfängt, gibt der Aufruf der Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein anderes Format verfügbar ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Nach einem Aufruf von [BeginEnumFormats](#beginenumformats), die Position des ersten Formats von diesem Datenobjekt unterstützt wird gespeichert. Aufeinander folgende Aufrufe von `GetNextFormat` wird die Liste der verfügbaren Formate in das Objekt auflisten. Verwenden Sie diese Funktionen, um die verfügbaren Formate aufzulisten.  
  
 Rufen Sie zum Überprüfen der Verfügbarkeit von einem bestimmten Format [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Weitere Informationen finden Sie unter [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein bestimmtes Format für das Abrufen von Daten aus der OLE-Element verfügbar ist.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cfFormat`  
 Zwischenablage-Datenformats in der Struktur verwendet werden auf die von `lpFormatEtc`. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von systemeigenen Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion.  
  
 `lpFormatEtc`  
 Verweist auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur, die das gewünschte Format beschreibt. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Ist dies **NULL**, die Standardwerte werden verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Daten im angegebenen Format verfügbar sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion eignet sich vor dem Aufruf von `GetData`, `GetFileData`, oder `GetGlobalData`.  
  
 Weitere Informationen finden Sie unter [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>COleDataObject::Release  
 Mit dieser Funktion können Sie den Besitz des wieder der [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) -Objekt, das zuvor zugeordnet war die `COleDataObject` Objekt.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `IDataObject` zugeordnet wurde der `COleDataObject` durch Aufrufen von **Anfügen** oder `AttachClipboard` explizit oder durch das Framework. Wenn die `bAutoRelease` Parameter der **Anfügen** ist **FALSE**der `IDataObject` Objekt wird nicht freigegeben werden. In diesem Fall der Aufrufer ist verantwortlich für das Freigeben der `IDataObject` durch Aufrufen von [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataSource-Klasse](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)

