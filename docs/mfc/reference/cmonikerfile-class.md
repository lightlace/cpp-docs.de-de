---
title: CMonikerFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cd166cac7d6d2cddbc12b3cbaa14b28d00c1357
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037268"
---
# <a name="cmonikerfile-class"></a>CMonikerFile-Klasse
Stellt einen Datenstream ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) benannt, indem ein [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Erstellt ein `CMonikerFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Trennt und Streams frei, und den Moniker frei.|  
|[CMonikerFile::Detach](#detach)|Trennt die `IMoniker` aus diesem `CMonikerFile` Objekt.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Gibt den aktuellen Moniker zurück.|  
|[CMonikerFile::Open](#open)|Öffnet die angegebene Datei aus, um einen Datenstrom abzurufen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Ruft den Bindungskontext oder erstellt einen Bindungskontext standardmäßig initialisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Moniker enthält Informationen, ähnlich wie ein Pfadname einer Datei. Wenn Sie einen Zeiger auf ein monikerobjekt haben `IMoniker` -Schnittstelle, Sie können den Zugriff auf die identifizierte Datei abrufen, ohne spezielle Informationen darüber, an die Datei tatsächlich befindet.  
  
 Abgeleitet von `COleStreamFile`, `CMonikerFile` nimmt ein Moniker oder eine Zeichenfolgendarstellung in ein Moniker erleichtern können und bindet Sie in den Stream, der für die ist der Moniker einen Namen. Sie können dann lesen und Schreiben in diesem Datenstrom. Der echte Zweck `CMonikerFile` besteht darin, den einfachen Zugriff auf bereitzustellen `IStream`s mit dem Namen von `IMoniker`s, damit Sie nicht in einen Datenstrom selbst binden verfügen noch nicht `CFile` Funktionalität in den Stream.  
  
 `CMonikerFile` kann zum Binden an etwas anderes als ein Datenstrom verwendet werden. Wenn Sie in Speicher oder ein Objekt binden möchten, müssen Sie verwenden die `IMoniker` -Schnittstelle direkt.  
  
 Weitere Informationen zu Streams und der Moniker, finden Sie unter [COleStreamFile](../../mfc/reference/colestreamfile-class.md) in der *MFC-Referenz* und [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) in der Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="close"></a>  CMonikerFile::Close  
 Mit dieser Funktion werden zum Trennen und Freigeben des Streams und den Moniker freizugeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Kann auf geöffnete oder bereits geschlossen Streams aufgerufen werden.  
  
##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile  
 Erstellt ein `CMonikerFile`-Objekt.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext  
 Mit dieser Funktion wird zum Erstellen einer Bindungskontext standardmäßig initialisiert.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Parameter  
 *pError*  
 Ein Zeiger auf eine Datei-Ausnahme. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bindungskontext [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) mit gebunden werden soll, wenn erfolgreich; andernfalls **NULL**. Wenn Sie mit die Instanz geöffnet wurde ein `IBindHost` -Schnittstelle, aus dem Bindungskontext abgerufen wird die `IBindHost`. Es ist keine `IBindHost` oder der Schnittstelle ein Fehler auftritt, eine Bindungskontext zurückgegeben, eine Bindungskontext wird erstellt. Eine Beschreibung der [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) Schnittstelle, finden Sie im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Eine Bindungskontext ist ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang speichert. Sie können dieser Funktion können Sie einen benutzerdefinierten Kontext bereitzustellen, überschreiben.  
  
##  <a name="detach"></a>  CMonikerFile::Detach  
 Mit dieser Funktion wird zum Schließen des Streams.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pError*  
 Ein Zeiger auf eine Datei-Ausnahme. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker  
 Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Moniker abzurufen.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle Moniker-Schnittstelle ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Hinweise  
 Seit `CMonikerFile` ist keine Schnittstelle, der zurückgegebene Zeiger nicht inkrementiert den Verweiszähler dieser Planergruppe (über [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), und der Moniker wird freigegeben, wenn der `CMonikerFile` Objekt freigegeben. Wenn Sie daran Festhalten des Monikers oder selbst freigeben möchten, müssen Sie `AddRef` es.  
  
##  <a name="open"></a>  CMonikerFile::Open  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei oder Moniker-Objekts.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszURL*  
 Eine URL oder der Dateiname der Datei geöffnet werden.  
  
 *pError*  
 Ein Zeiger auf eine Datei-Ausnahme. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.  
  
 *pMoniker*  
 Ein Zeiger auf die Schnittstelle Moniker `IMoniker` verwendet werden, kein Stream abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die *LpszURL* Parameter kann nicht auf einem Macintosh-Computer verwendet werden. Nur die *pMoniker* Form **öffnen** kann auf einem Macintosh-Computer verwendet werden.  
  
 Sie können eine URL oder einen Dateinamen für die *LpszURL* Parameter. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - ODER  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [COleStreamFile-Klasse](../../mfc/reference/colestreamfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)
