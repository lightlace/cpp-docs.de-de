---
title: COleStreamFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- data streams [C++]
- streams [C++], OLE
- data streams [C++], OLE
- structured storage in OLE
- OLE structured storage [C++]
- OLE [C++], streams of data
- COleStreamFile class
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
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
ms.openlocfilehash: 0840d365f4179da0ad680256688eaf9484cb3cd8
ms.lasthandoff: 02/24/2017

---
# <a name="colestreamfile-class"></a>COleStreamFile-Klasse
Stellt einen Datenstrom ( `IStream`) in einer Verbunddatei als Teil des OLE Structured Storage.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Erstellt ein `COleStreamFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Ordnet einen Stream mit dem Objekt.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Erstellt einen Datenstrom aus dem globalen Arbeitsspeicher und ordnet dem Objekt.|  
|[COleStreamFile::CreateStream](#createstream)|Erstellt einen Datenstrom und ordnet dem Objekt.|  
|[COleStreamFile::Detach](#detach)|Hebt die Zuordnung des Streams, aus dem Objekt.|  
|[COleStreamFile::GetStream](#getstream)|Gibt den aktuellen Stream zurück.|  
|[COleStreamFile::OpenStream](#openstream)|Sicher öffnet einen Stream, und ordnet es dem Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `IStorage` Objekt muss vorhanden sein, bevor der Stream geöffnet oder erstellt, wenn es sich um einen Speicherstream ist werden kann.  
  
 `COleStreamFile`Objekte werden genau wie bearbeitet [CFile](../../mfc/reference/cfile-class.md) Objekte.  
  
 Weitere Informationen zum Bearbeiten von Datenströmen und speichern können, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="attach"></a>COleStreamFile::Attach  
 Ordnet den angegebenen OLE-Stream mit der `COleStreamFile` Objekt.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStream`  
 Verweist auf die OLE-Datenstrom ( `IStream`) mit dem Objekt zugeordnet werden soll. Nicht **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt darf nicht bereits ein OLE-Datenstrom zugeordnet werden.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 Erstellt ein `COleStreamFile`-Objekt.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStream`  
 Zeiger auf die OLE-Stream mit dem Objekt zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `lpStream` ist **NULL**, das Objekt ist nicht mit ein OLE-Datenstrom verknüpft, das Objekt ist, andernfalls der angegebenen OLE-Datenstrom zugeordnet.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 Sichere erstellt einen neuen Stream nicht genügend globale, gemeinsam genutzte Arbeitsspeicher, in dem ein Fehler für eine normale, erwartete Bedingung ist.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL** , die den Status von den Vorgang angibt. Geben Sie diesen Parameter, wenn Sie Überwachen mögliche Ausnahmen generiert, wird versucht, den Stream erstellen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Stream erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Arbeitsspeicher wird durch das OLE-Subsystem zugeordnet.  
  
 Weitere Informationen finden Sie unter [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstream"></a>COleStreamFile::CreateStream  
 Sichere erstellt einen neuen Stream im angegebenen Speicherobjekt, in dem ein Fehler für eine normale, erwartete Bedingung ist.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStorage`  
 Verweist auf das OLE-Speicher-Objekt, das den zu erstellenden Datenstroms enthält. Nicht **NULL**.  
  
 `lpszStreamName`  
 Der Name des Datenstroms erstellt werden. Nicht **NULL**.  
  
 `nOpenFlags`  
 Der Zugriffsmodus zu verwenden, wenn der Stream geöffnet. Exklusive, Lese-/Schreibzugriff und Erstellen von Modi werden standardmäßig verwendet. Eine vollständige Liste der verfügbaren, finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL**. Geben Sie diesen Parameter, wenn Sie Überwachen mögliche Ausnahmen generiert, wird versucht, den Stream erstellen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Stream erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei-Ausnahme wird ausgelöst, wenn die Open schlägt fehl, und `pError` nicht **NULL**.  
  
 Weitere Informationen finden Sie unter [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="detach"></a>COleStreamFile::Detach  
 Hebt die Zuordnung des Streams, aus das Objekt ohne diesen zu schließen.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Datenstrom ( `IStream`), die dem Objekt zugeordnet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der Stream muss auf eine andere Art geschlossen werden, bevor das Programm beendet wird.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstream"></a>COleStreamFile::GetStream  
 Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Stream zurückzugeben.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Stream-Schnittstelle ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>COleStreamFile::OpenStream  
 Öffnet einen vorhandenen Stream.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStorage`  
 Verweist auf das OLE-Speicher-Objekt, das den Stream geöffnet werden, enthält. Nicht **NULL**.  
  
 `lpszStreamName`  
 Der Name des Datenstroms geöffnet werden. Nicht **NULL**.  
  
 `nOpenFlags`  
 Der Zugriffsmodus zu verwenden, wenn der Stream geöffnet. Exklusive und Lese-/Schreibzugriff Modi werden standardmäßig verwendet. Eine vollständige Liste der verfügbaren Modi finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL**. Geben Sie diesen Parameter, wenn Sie mögliche Ausnahmen generiert, indem Sie versuchen, den Stream geöffnet zu überwachen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Stream erfolgreich geöffnet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei-Ausnahme wird ausgelöst, wenn die Open schlägt fehl, und `pError` nicht **NULL**.  
  
 Weitere Informationen finden Sie unter [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




