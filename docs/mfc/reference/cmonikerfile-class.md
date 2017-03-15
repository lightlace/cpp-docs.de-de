---
title: CMonikerFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
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
ms.openlocfilehash: 4668672af1b33170ece1cb4d449ed5a20f6040e7
ms.lasthandoff: 02/24/2017

---
# <a name="cmonikerfile-class"></a>CMonikerFile-Klasse
Stellt einen Datenstrom ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) mit dem Namen durch ein [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Erstellt ein `CMonikerFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Trennt und gibt den Stream und den Moniker frei.|  
|[CMonikerFile::Detach](#detach)|Trennt die `IMoniker` aus diesem `CMonikerFile` Objekt.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Gibt den aktuellen Moniker.|  
|[CMonikerFile::Open](#open)|Öffnet die angegebene Datei, um einen Datenstrom abzurufen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Ruft den Bindungskontext ab oder erstellt einen Bindungskontext standardmäßig initialisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Moniker enthält Informationen, ähnlich wie ein Pfadname in eine Datei. Wenn Sie einen Zeiger auf ein monikerobjekt haben `IMoniker` -Schnittstelle können Sie Zugriff auf die angegebene Datei abrufen, ohne andere spezifische Informationen über, in dem die Datei tatsächlich gespeichert ist.  
  
 Abgeleitet von `COleStreamFile`, `CMonikerFile` nimmt einen Moniker oder eine String-Darstellung in ein Moniker erleichtern können, und in den Stream für die den Moniker einen Namen stellt bindet. Sie können dann lesen und Schreiben in den Stream. Dem eigentlichen Zweck `CMonikerFile` einfachen Zugriff auf `IStream`s mit dem Namen `IMoniker`, damit Sie keinen in einen Datenstrom selbst binden noch besitzen `CFile` Funktionen in den Stream.  
  
 `CMonikerFile`kann zum Binden an etwas anderes als einen Datenstrom verwendet werden. Wenn Sie auf Speicher oder ein Objekt binden möchten, müssen Sie verwenden die `IMoniker` -Schnittstelle direkt.  
  
 Weitere Informationen über Datenströme und Moniker, finden Sie unter [COleStreamFile](../../mfc/reference/colestreamfile-class.md) in der *MFC-Referenz* und [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-nameclosea--cmonikerfileclose"></a><a name="close"></a>CMonikerFile::Close  
 Rufen Sie diese Funktion zu trennen, und lassen Sie den Stream und den Moniker freizugeben.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Kann auf geöffnete oder bereits geschlossene Streams aufgerufen werden.  
  
##  <a name="a-namecmonikerfilea--cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 Erstellt ein `CMonikerFile`-Objekt.  
  
```  
CMonikerFile();
```  
  
##  <a name="a-namecreatebindcontexta--cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 Rufen Sie diese Funktion zum Erstellen einer Bindungskontext standardmäßig initialisiert.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Parameter  
 `pError`  
 Ein Zeiger auf eine Datei ausgelöst. Falls ein Fehler auftritt wird es auf die Ursache festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bindungskontext [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) zum Binden, wenn erfolgreich, andernfalls **NULL**. Wenn die Instanz geöffnet wurde ein `IBindHost` -Schnittstelle, aus dem Bindungskontext abgerufen wird die `IBindHost`. Es ist keine `IBindHost` oder der Schnittstelle ein Fehler auftritt, eine Bindungskontext zurückgeben, einen Bindungskontext wird erstellt. Eine Beschreibung der [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) Benutzeroberfläche, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Eine Bindungskontext ist ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang gespeichert. Sie können diese Funktion, um einen benutzerdefinierten Kontext bereitzustellen, überschreiben.  
  
##  <a name="a-namedetacha--cmonikerfiledetach"></a><a name="detach"></a>CMonikerFile::Detach  
 Rufen Sie diese Funktion, um den Stream zu schließen.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pError`  
 Ein Zeiger auf eine Datei ausgelöst. Falls ein Fehler auftritt wird es auf die Ursache festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namegetmonikera--cmonikerfilegetmoniker"></a><a name="getmoniker"></a>CMonikerFile::GetMoniker  
 Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Moniker abzurufen.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktuelle Moniker-Schnittstelle ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Hinweise  
 Da `CMonikerFile` ist keine Schnittstelle, erhöht sich der zurückgegebene Zeiger nicht den Verweiszähler (über [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), und der Moniker freigegeben wird bei der `CMonikerFile` Objekt freigegeben. Wenn Sie auf den Moniker enthalten ist, oder selbst freigeben möchten, müssen Sie `AddRef` es.  
  
##  <a name="a-nameopena--cmonikerfileopen"></a><a name="open"></a>CMonikerFile::Open  
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
 `lpszURL`  
 Eine URL oder der Dateiname der Datei geöffnet werden.  
  
 `pError`  
 Ein Zeiger auf eine Datei ausgelöst. Falls ein Fehler auftritt wird es auf die Ursache festgelegt werden.  
  
 `pMoniker`  
 Ein Zeiger auf die Schnittstelle Moniker `IMoniker` verwendet werden, um einen Datenstrom abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszURL` Parameter auf einem Macintosh-Computer verwendet werden kann. Nur die `pMoniker` Form **öffnen** auf einem Macintosh-Computer verwendet werden können.  
  
 Sie können eine URL oder einen Dateinamen für die `lpszURL` Parameter. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCWinInet&6;](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 – oder –  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [COleStreamFile-Klasse](../../mfc/reference/colestreamfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)

