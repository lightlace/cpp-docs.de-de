---
title: CMemFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CMemFile class
- temporary files, memory files
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
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
ms.openlocfilehash: 9851e050b05ac129e5e498c7ea99dfedddc79e54
ms.lasthandoff: 02/24/2017

---
# <a name="cmemfile-class"></a>CMemFile-Klasse
Die [CFile](../../mfc/reference/cfile-class.md)-abgeleitete Klasse, die arbeitsspeicherdateien unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Erstellt ein Speicherobjekt für die Datei.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Fügt einen Speicherblock zu `CMemFile`.|  
|[CMemFile::Detach](#detach)|Trennt den Speicherblock aus `CMemFile` und gibt einen Zeiger auf den Speicherblock, getrennt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Überschreiben Sie, um das Zuordnungsverhalten Arbeitsspeicher ändern.|  
|[CMemFile::Free](#free)|Überschreiben Sie, um Arbeitsspeicher belegen Verhalten zu ändern.|  
|[CMemFile::GrowFile](#growfile)|Überschreiben Sie, um das Verhalten zu ändern, wenn eine Datei vergrößert.|  
|[CMemFile::Memcpy](#memcpy)|Überschreiben Sie, um Speicher Kopierverhalten beim Lesen und Schreiben von Dateien zu ändern.|  
|[CMemFile::Realloc](#realloc)|Überschreiben Sie, um Arbeitsspeicher Neubelegung Verhalten zu ändern.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Dateien Verhalten sich wie Dateien, mit der Ausnahme, dass die Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert ist. Eine Datei ist hilfreich beim schnellen temporären Speicher und zum Übertragen von unformatierten Bytes oder serialisierten Objekten zwischen voneinander unabhängige Prozesse.  
  
 `CMemFile`Objekte können ihre eigenen Speicher automatisch oder anfügen, die Ihre eigenen Speicherblock, der die `CMemFile` -Objekt durch Aufrufen von [Anfügen](#attach). In beiden Fällen wird im Speicher für die Speicherdatei automatisch vergrößern reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht&0; (null).  
  
 Der Speicherblock automatisch gelöscht, auf die Zerstörung von der `CMemFile` Objekt, wenn der Arbeitsspeicher von ursprünglich belegt wurde die `CMemFile` Objekt; andernfalls sind Sie verantwortlich für das Freigeben von Arbeitsspeicher, die Sie an das Objekt angefügt.  
  
 Sie können den Speicherblock zugreifen, über den Zeiger angegeben, wenn Sie von getrennt den `CMemFile` -Objekt durch Aufrufen von [trennen](#detach).  
  
 Die häufigste Verwendung von `CMemFile` ist die Erstellung einer `CMemFile` Objekt, und verwenden Sie es durch Aufrufen von [CFile](../../mfc/reference/cfile-class.md) Memberfunktionen. Beachten Sie, dass das Erstellen einer `CMemFile` wird automatisch geöffnet: Rufen Sie [CFile::Open](../../mfc/reference/cfile-class.md#open), die nur für Dateien verwendet wird. Da `CMemFile` eine Datenträgerdatei, die dem Datenmember verwendet nicht `CFile::m_hFile` wird nicht verwendet.  
  
 Die `CFile` Memberfunktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) nicht implementiert sind `CMemFile`. Wenn Sie diese Funktionen aufrufen, die sich auf eine `CMemFile` -Objekt erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile`verwendet die Funktionen der Laufzeitbibliothek [Malloc](../../c-runtime-library/reference/malloc.md), [Realloc](../../c-runtime-library/reference/realloc.md), und [freien](../../c-runtime-library/reference/free.md) um zuzuordnen, neu zuordnen und Freigeben von Arbeitsspeicher, und die systeminterne Funktion [Memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) Block Kopie Arbeitsspeicher beim Lesen und schreiben. Wenn Sie dieses Verhalten oder das Verhalten ändern möchten wenn `CMemFile` wächst eine Datei leiten Sie eine eigene Klasse von `CMemFile` und die entsprechenden Funktionen überschreiben.  
  
 Weitere Informationen zu `CMemFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Speicher-Management (MFC)](../../mfc/memory-management.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="alloc"></a>CMemFile::Alloc  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Anzahl der Bytes im Speicher zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock, der belegt wurde, oder **NULL** Wenn die Verteilung fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um benutzerdefinierte speicherbelegung implementieren. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [frei](#free) und [Realloc](#realloc) ebenfalls.  
  
 Die standardmäßige Implementierung verwendet die Funktion der Laufzeitbibliothek [Malloc](../../c-runtime-library/reference/malloc.md) Arbeitsspeicher zugeordnet werden.  
  
##  <a name="attach"></a>CMemFile::Attach  
 Rufen Sie diese Funktion zum Anfügen eines Speicherblocks auf `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuffer`  
 Zeiger auf den Puffer an `CMemFile`.  
  
 `nBufferSize`  
 Eine ganze Zahl, die die Größe des Puffers in Bytes angibt.  
  
 `nGrowBytes`  
 Die Schrittweite Zuordnung für Arbeitsspeicher in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass `CMemFile` den Speicherblock als Datei für den Speicher zu verwenden.  
  
 Wenn `nGrowBytes` ist 0, `CMemFile` wird festgelegt, die Dateilänge mit `nBufferSize`. Dies bedeutet, dass die Daten in den Speicherblock, bevor er angefügt war `CMemFile` wie die Datei verwendet werden. Auf diese Weise erstellte Dateien können nicht vergrößert werden.  
  
 Da die Datei vergrößert werden kann, werden nicht dazu führen, dass `CMemFile` für den Versuch, die Datei vergrößert werden. Zum Beispiel nicht aufrufen, die `CMemFile` überschreibt der [CFile:Write](../../mfc/reference/cfile-class.md#write) , hinter dem Ende schreiben, oder rufen Sie nicht [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) mit einer Länge von mehr als `nBufferSize`.  
  
 Wenn `nGrowBytes` ist größer als 0, `CMemFile` ignoriert den Inhalt des Speicherblocks, das Sie angefügt haben. Sie müssen den Inhalt der Datei für den Speicher vollständig neuen Schreiben der `CMemFile` das Außerkraftsetzen der `CFile::Write`. Wenn Sie versuchen, nach dem Ende der Datei schreiben oder vergrößern die Datei durch Aufrufen der `CMemFile` das Außerkraftsetzen der `CFile::SetLength`, `CMemFile` wächst die speicherbelegung in Schritten von `nGrowBytes`. Wächst die Speicherzuordnungs schlägt fehl, wenn der Speicherblock an Sie übergeben **Anfügen** wurde nicht mit einer Methode kompatibel mit zugeordneten [Alloc](#alloc). Für die Kompatibilität mit der Standardimplementierung des `Alloc`, müssen Sie den Speicher mit der Funktion der Laufzeitbibliothek reservieren [Malloc](../../c-runtime-library/reference/malloc.md) oder [Calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>CMemFile::CMemFile  
 Die erste Überladung wird eine leerer Speicher-Datei geöffnet.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nGrowBytes`  
 Die Schrittweite Zuordnung für Arbeitsspeicher in Bytes.  
  
 *LpBuffe*r  
 Zeiger auf einen Puffer, der Informationen der Größe empfängt `nBufferSize`.  
  
 `nBufferSize`  
 Eine ganze Zahl, die die Größe des Dateipuffers in Bytes angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Datei, durch den Konstruktor geöffnet wird und Sie nicht rufen [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 Die zweite Überladung entspricht das Verhalten, als ob Sie sofort aufgerufen und den ersten Konstruktor verwendet [Anfügen](#attach) mit denselben Parametern. Finden Sie unter **Anfügen** Details.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles Nr.&36;](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>CMemFile::Detach  
 Rufen Sie diese Funktion, um einen Zeiger auf den Speicherblock, der vom verwendeten `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock, der den Inhalt der Datei für den Speicher enthält.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Funktion schließt auch die `CMemFile`. Sie können den Speicherblock Anfügen `CMemFile` durch Aufrufen von [Anfügen](#attach). Wenn Sie die Datei anfügen und die Daten darin möchten, sollten Sie aufrufen [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) zum Abrufen der Länge der Datei vor dem Aufruf von **trennen**. Beachten Sie, dass, wenn Sie einen Speicherblock auf Anfügen `CMemFile` , damit Sie die Daten verwenden können ( `nGrowBytes` == 0), und klicken Sie dann die Arbeitsspeicherdatei vergrößert werden können.  
  
##  <a name="free"></a>CMemFile::Free  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMem`  
 Zeiger auf den Speicher freigegeben werden *.*  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um benutzerdefinierte Speicherfreigabe implementieren. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [Zuordnungseinheits](#alloc) und [Realloc](#realloc) ebenfalls.  
  
##  <a name="growfile"></a>CMemFile::GrowFile  
 Diese Funktion wird aufgerufen, von einigen der `CMemFile` Member-Funktionen.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewLen`  
 Neue Größe der Datei für den Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Sie können es überschreiben, wenn Sie ändern möchten wie `CMemFile` die Datei wächst. Die standardmäßige Implementierung ruft [Realloc](#realloc) einen vorhandenen Block wachsen (oder [Alloc](#alloc) einen Speicherblock zu erstellen), beim Zuweisen von Speicher in Vielfachen von der `nGrowBytes` im Konstruktor angegebene Wert oder [Anfügen](#attach) aufrufen.  
  
##  <a name="memcpy"></a>CMemFile::Memcpy  
 Diese Funktion wird aufgerufen, indem die `CMemFile` überschreibt der [CFile:: Read](../../mfc/reference/cfile-class.md#read) und [CFile::Write](../../mfc/reference/cfile-class.md#write) zum Übertragen von Daten in und aus dem Arbeitsspeicher.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMemTarget`  
 Zeiger auf den Speicherblock, der, den Quelle Speicher kopiert werden sollen.  
  
 `lpMemSource`  
 Zeiger auf den Speicherblock Quelle.  
  
 `nBytes`  
 Anzahl der zu kopierenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie des `lpMemTarget`es.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie die Art ändern möchten, die `CMemFile` diese Speicher kopiert wird.  
  
##  <a name="realloc"></a>CMemFile::Realloc  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMem`  
 Ein Zeiger auf den Speicherblock, verschoben werden.  
  
 `nBytes`  
 Neue Größe für den Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock, der neu zugeordnet (und möglicherweise verschoben), oder **NULL** fehlgeschlagenem überlegen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um benutzerdefinierte neuzuordnung implementieren. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [Zuordnungseinheits](#alloc) und [frei](#free) sowie.  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




