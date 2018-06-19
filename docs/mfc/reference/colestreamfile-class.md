---
title: COleStreamFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 805c32145d844cc1103cab7c4987c0595ff5935f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371389"
---
# <a name="colestreamfile-class"></a>COleStreamFile-Klasse
Stellt einen Datenstream ( `IStream`) in einer Verbunddatei als Teil des OLE Structured Storage.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Erstellt ein `COleStreamFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Ordnet einen Stream mit dem Objekt.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Erstellt einen Datenstrom aus dem globalen Arbeitsspeicher, und ordnet es dem Objekt.|  
|[COleStreamFile::CreateStream](#createstream)|Erstellt einen Datenstrom und ordnet es dem Objekt.|  
|[COleStreamFile::Detach](#detach)|Hebt die Zuordnung des Streams, aus dem Objekt.|  
|[COleStreamFile::GetStream](#getstream)|Gibt den aktuellen Stream zurück.|  
|[COleStreamFile::OpenStream](#openstream)|Öffnet einen Datenstrom zum sicheren und ordnet es dem Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `IStorage` Objekt muss vorhanden sein, bevor der Stream geöffnet oder erstellt, wenn es sich um einen Speicherstream ist werden kann.  
  
 `COleStreamFile` Objekte bearbeitet werden, genau so wie [CFile](../../mfc/reference/cfile-class.md) Objekte.  
  
 Weitere Informationen zum Bearbeiten von Datenströmen und speichern können, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="attach"></a>  COleStreamFile::Attach  
 Ordnet die angegebene OLE-Stream mit der `COleStreamFile` Objekt.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStream`  
 Verweist auf die OLE-Streams ( `IStream`) mit dem Objekt zugeordnet werden soll. Nicht mit **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt darf nicht bereits ein OLE-Datenstrom zugeordnet sein.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) im Windows SDK.  
  
##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile  
 Erstellt ein `COleStreamFile`-Objekt.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStream`  
 Zeiger auf den OLE-Stream mit dem Objekt zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `lpStream` ist **NULL**, das Objekt ist nicht mit einem OLE-Datenstrom verknüpft, das Objekt ist, andernfalls das angegebene OLE-Datenstrom zugeordnet.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) im Windows SDK.  
  
##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream  
 Sicher erstellt einen neuen Stream nicht genügend globale, freigegebenen Arbeitsspeicher, in dem ein Fehler für eine normale, erwartete Bedingung ist.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL** , der den Abschlussstatus des Vorgangs erstellen angibt. Geben Sie diesen Parameter, wenn Sie mögliche Ausnahmen generiert, wird versucht, den Datenstrom erstellen überwachen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Datenstrom erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Arbeitsspeicher wird vom OLE-Subsystem zugeordnet.  
  
 Weitere Informationen finden Sie unter [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) im Windows SDK.  
  
##  <a name="createstream"></a>  COleStreamFile::CreateStream  
 Sicher erstellt einen neuen Stream in dem bereitgestellten Speicher-Objekt, in dem ein Fehler für eine normale, erwartete Bedingung ist.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStorage`  
 Verweist auf das OLE-Speicherobjekt, das den zu erstellenden Datenstroms enthält. Nicht mit **NULL**.  
  
 `lpszStreamName`  
 Der Name des zu erstellenden Datenstroms. Nicht mit **NULL**.  
  
 `nOpenFlags`  
 Der Zugriffsmodus zu verwenden, wenn der Stream geöffnet. Exklusive, Lese-/Schreibzugriff und erstellen Sie die Modi werden standardmäßig verwendet. Eine vollständige Liste der verfügbaren Modi finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL**. Geben Sie diesen Parameter, wenn Sie mögliche Ausnahmen generiert, wird versucht, den Datenstrom erstellen überwachen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Datenstrom erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei-Ausnahme wird ausgelöst, wenn die Open schlägt fehl und `pError` nicht **NULL**.  
  
 Weitere Informationen finden Sie unter [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) im Windows SDK.  
  
##  <a name="detach"></a>  COleStreamFile::Detach  
 Hebt die Zuordnung des Streams, aus dem Objekt ohne das Schließen des Streams.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Datenstrom ( `IStream`), die dem Objekt zugeordnet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der Stream muss auf irgendeine andere geschlossen werden, bevor das Programm beendet wird.  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) im Windows SDK.  
  
##  <a name="getstream"></a>  COleStreamFile::GetStream  
 Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Stream zurückzugeben.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Stream-Schnittstelle ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>  COleStreamFile::OpenStream  
 Öffnet einen vorhandenen Datenstrom.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpStorage`  
 Verweist auf das OLE-Speicherobjekt, das den Datenstrom geöffnet werden. Nicht mit **NULL**.  
  
 `lpszStreamName`  
 Der Name des Datenstroms geöffnet werden. Nicht mit **NULL**.  
  
 `nOpenFlags`  
 Der Zugriffsmodus zu verwenden, wenn der Stream geöffnet. Exklusive und Lese-/Schreibzugriff Modi werden standardmäßig verwendet. Die vollständige Liste der verfügbaren Modi, finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder **NULL**. Geben Sie diesen Parameter, wenn mögliche, wird versucht, den Stream geöffnet generierte Ausnahmen überwacht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Stream wurde erfolgreich geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei-Ausnahme wird ausgelöst, wenn die Open schlägt fehl und `pError` nicht **NULL**.  
  
 Weitere Informationen finden Sie unter [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



