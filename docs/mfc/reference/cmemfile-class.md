---
title: CMemFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81421c99623fd3ab0abde20b479ec1ba91c3f936
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368360"
---
# <a name="cmemfile-class"></a>CMemFile-Klasse
Die [CFile](../../mfc/reference/cfile-class.md)-abgeleitete Klasse, die arbeitsspeicherdateien unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Erstellt ein Speicherobjekt für die Datei an.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Fügt einen Speicherblock zu `CMemFile`.|  
|[CMemFile::Detach](#detach)|Trennt den Speicherblock von `CMemFile` und gibt einen Zeiger auf den Speicherblock, der getrennt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Überschreiben Sie, um das Zuordnungsverhalten Arbeitsspeicher ändern.|  
|[CMemFile::Free](#free)|Außer Kraft setzen Sie, um Arbeitsspeicher Aufhebung Verhalten zu ändern.|  
|[CMemFile::GrowFile](#growfile)|Außer Kraft setzen Sie, um das Verhalten zu ändern, wenn eine Datei vergrößert.|  
|[CMemFile::Memcpy](#memcpy)|Außer Kraft setzen Sie, um Speicher Kopierverhalten beim Lesen und Schreiben von Dateien zu ändern.|  
|[CMemFile::Realloc](#realloc)|Außer Kraft setzen Sie, um Arbeitsspeicher neuzuordnungen Verhalten zu ändern.|  
  
## <a name="remarks"></a>Hinweise  
 Diese arbeitsspeicherdateien Verhalten wie Dateien auf Datenträgern, außer dass die Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert wird. Eine Arbeitsspeicherdatei eignet sich für die schnelle temporäre Speicherung oder zum Übertragen von unformatierten Bytes oder serialisiert Objekte zwischen unabhängigen Prozessen.  
  
 `CMemFile` Objekte können automatisch ihre eigenen Speicher zuordnen, oder Sie können eigene Speicherblocks zum Anfügen der `CMemFile` Objekt durch Aufrufen von [Anfügen](#attach). In beiden Fällen wird im Arbeitsspeicher für die Speicherdatei automatisch vergrößern reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht 0 (null).  
  
 Der Speicherblock automatisch gelöscht werden nach der Zerstörung der `CMemFile` Objekt, wenn der Arbeitsspeicher von ursprünglich zugeordnet wurde die `CMemFile` Objekt; andernfalls sind Sie verantwortlich für das Freigeben des Arbeitsspeichers, die Sie an das Objekt angefügt.  
  
 Sie erreichen den Speicherblock über den Zeiger angegeben, wenn Sie von getrennt den `CMemFile` Objekt durch Aufrufen von [trennen](#detach).  
  
 Die häufigste Verwendung von `CMemFile` besteht im Erstellen einer `CMemFile` Objekt, und verwenden Sie es durch den Aufruf [CFile](../../mfc/reference/cfile-class.md) Memberfunktionen. Beachten Sie, dass das Erstellen einer `CMemFile` wird er automatisch geöffnet: Rufen Sie nicht [CFile::Open](../../mfc/reference/cfile-class.md#open), dem wird nur für Dateien auf Datenträgern verwendet. Da `CMemFile` eine Datenträgerdatei Datenmembers verwendet keine `CFile::m_hFile` wird nicht verwendet.  
  
 Die `CFile` Memberfunktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) nicht implementiert werden `CMemFile`. Wenn Sie für diese Funktionen aufrufen einer `CMemFile` -Objekt erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` verwendet die Funktionen der Laufzeit-Bibliothekscode ["malloc"](../../c-runtime-library/reference/malloc.md), [Realloc](../../c-runtime-library/reference/realloc.md), und [freien](../../c-runtime-library/reference/free.md) zuzuordnen, neu zu reservieren und Freigeben von Arbeitsspeicher und die systeminterne Funktion [Memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) Block Kopie Arbeitsspeicher beim Lesen und schreiben. Wenn Sie dieses Verhalten oder das Verhalten ändern möchten bei `CMemFile` vergrößert wird eine Datei, leiten Sie eine eigene Klasse von `CMemFile` und überschreiben Sie die entsprechenden Funktionen.  
  
 Weitere Informationen zu `CMemFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Speicher-Management (MFC)](../../mfc/memory-management.md) und finden Sie unter [Dateibehandlung](../../c-runtime-library/file-handling.md) in der *zur Laufzeit Bibliotheksverweis*.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Anzahl der Bytes an Arbeitsspeicher zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock, der belegt wurde, oder **NULL** Wenn Fehler bei der Zuweisung.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Implementieren von benutzerdefinierten speicherbelegung. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [frei](#free) und [Realloc](#realloc) ebenfalls.  
  
 Die Standardimplementierung verwendet die Funktion der Laufzeitbibliothek ["malloc"](../../c-runtime-library/reference/malloc.md) belegt werden.  
  
##  <a name="attach"></a>  CMemFile::Attach  
 Mit dieser Funktion können Sie einen Speicherblock, der zum Anfügen `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuffer`  
 Zeiger auf den Puffer anzufügenden `CMemFile`.  
  
 `nBufferSize`  
 Eine ganze Zahl, die die Größe des Puffers in Bytes angibt.  
  
 `nGrowBytes`  
 Das Inkrement Zuweisung, Arbeitsspeicher in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass `CMemFile` , die den Speicherblock, der als Datei für den Speicher verwendet.  
  
 Wenn `nGrowBytes` ist 0, `CMemFile` wird festgelegt, der die Dateilänge mit `nBufferSize`. Dies bedeutet, dass die Daten im Speicherblock, bevor er angefügt war `CMemFile` wird die Datei verwendet werden. Arbeitsspeicherdateien erstellt, die auf diese Weise können nicht vergrößert werden.  
  
 Da die Datei vergrößert werden kann, achten Sie darauf, nicht bewirken, dass `CMemFile` versucht, die Datei vergrößert werden. Beispielsweise rufen Sie nicht die `CMemFile` überschreibt der [CFile:Write](../../mfc/reference/cfile-class.md#write) , hinter dem Ende schreiben, oder rufen Sie nicht [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) mit einer Länge von mehr als `nBufferSize`.  
  
 Wenn `nGrowBytes` ist größer als 0 (null) `CMemFile` ignoriert den Inhalt des Speicherblocks, der Sie angefügt haben. Sie müssen den Inhalt der Datei für den Speicher aus mithilfe von Grund auf neu zu schreiben der `CMemFile` Überschreiben von `CFile::Write`. Wenn Sie versuchen, nach dem Ende der Datei schreiben oder die Vergrößerung der das durch Aufrufen der `CMemFile` Überschreiben von `CFile::SetLength`, `CMemFile` wächst die speicherbelegung in Schritten von `nGrowBytes`. Wächst die speicherbelegung schlägt fehl, wenn der Speicherblock an Sie übergeben **Anfügen** wurde nicht mit einer Methode, die kompatibel mit zugeordneten [Alloc](#alloc). Für die Kompatibilität mit die standardmäßige Implementierung des `Alloc`, müssen Sie den Speicher mit der Funktion der Laufzeitbibliothek reservieren ["malloc"](../../c-runtime-library/reference/malloc.md) oder [Calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 Die erste Überladung wird ein leeres Arbeitsspeicherdatei geöffnet.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nGrowBytes`  
 Das Inkrement Zuweisung, Arbeitsspeicher in Bytes.  
  
 *LpBuffe*r  
 Zeiger auf einen Puffer, der Informationen der Größe empfängt `nBufferSize`.  
  
 `nBufferSize`  
 Eine ganze Zahl, die die Größe des Dateipuffers in Bytes angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Datei, die vom Konstruktor geöffnet wird und Sie nicht rufen [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 Die zweite Überladung entspricht das Verhalten, als wäre den ersten Konstruktor verwendet und wird sofort aufgerufen, [Anfügen](#attach) mit denselben Parametern. Finden Sie unter **Anfügen** Details.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 Mit dieser Funktion wird zum Abrufen eines Zeigers auf den Speicherblock, der vom verwendeten `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock mit dem Inhalt der Datei für den Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen dieser Funktion schließt auch die `CMemFile`. Sie können den Speicherblock Anfügen `CMemFile` durch Aufrufen von [Anfügen](#attach). Wenn Sie die Datei anfügen und die Daten darin möchten, sollten Sie aufrufen [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) die Länge der Datei vor dem Aufruf abgerufen **trennen**. Beachten Sie, dass, wenn Sie einen Speicherblock zu Anfügen `CMemFile` , damit Sie ihre Daten verwenden können ( `nGrowBytes` == 0), und Sie können zur Vergrößerung der Arbeitsspeicherdatei nicht.  
  
##  <a name="free"></a>  CMemFile::Free  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMem`  
 Zeiger auf den Speicher freigegeben werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Implementieren von benutzerdefinierten Speicherfreigabe an. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [Alloc](#alloc) und [Realloc](#realloc) ebenfalls.  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 Diese Funktion wird aufgerufen, von mehreren der `CMemFile` Memberfunktionen.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewLen`  
 Neue Größe der Datei für den Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Sie können es überschreiben, wenn Sie ändern möchten wie `CMemFile` lässt die Datei wachsen. Die Standardimplementierung ruft [Realloc](#realloc) einen vorhandenen Block vergrößert (oder [Alloc](#alloc) einen Speicherblock zu erstellen), belegen von Speicher in Vielfachen von der `nGrowBytes` im Konstruktor angegebene Wert oder [Anfügen](#attach) aufrufen.  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 Diese Funktion wird aufgerufen, indem Sie die `CMemFile` überschreibt der [CFile:: Read](../../mfc/reference/cfile-class.md#read) und [CFile::Write](../../mfc/reference/cfile-class.md#write) zum Übertragen von Daten in und aus dem Arbeitsspeicher.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMemTarget`  
 Zeiger zum Speicherblock, der in dem Quelle Speicher kopiert wird.  
  
 `lpMemSource`  
 Zeiger zum Speicherblock Quelle.  
  
 `nBytes`  
 Anzahl der zu kopierenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie des `lpMemTarget`es.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie die Art ändern möchten, `CMemFile` diese Speicher kopiert wird.  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
 Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMem`  
 Ein Zeiger auf den Speicherblock zugewiesen werden.  
  
 `nBytes`  
 Neue Größe für den Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speicherblock, der wurde neu zugewiesen wurde (und möglicherweise verschoben), oder **NULL** Wenn die neuzuordnung fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Implementieren von benutzerdefinierten neuzuordnung. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [Alloc](#alloc) und [frei](#free) ebenfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



