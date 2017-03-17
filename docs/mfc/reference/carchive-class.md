---
title: CArchive-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], archiving objects
- CArchive class
- serialization [C++], CArchive class
- storage [C++], CArchive class
- data storage [C++], CArchive class
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
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
ms.openlocfilehash: 501b365678a45148aabe638ff341f3ae995e4ab5
ms.lasthandoff: 02/24/2017

---
# <a name="carchive-class"></a>CArchive-Klasse
Können Sie ein komplexes Netzwerk von Objekten in einer permanenten binären Form (normalerweise in Festplattenspeicher) zu speichern, die erhalten bleibt, nachdem diese Objekte gelöscht werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CArchive  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|Erstellt ein `CArchive`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|Schließt ein Archiv ohne eine Ausnahme auszulösen.|  
|[CArchive::Close](#close)|Leert geleerten Daten und trennt die `CFile`.|  
|[CArchive::Flush](#flush)|Leert geleerten Daten aus dem Archiv-Puffer.|  
|[CArchive::GetFile](#getfile)|Ruft die `CFile` Objektzeiger für dieses Archiv.|  
|[CArchive::GetObjectSchema](#getobjectschema)|Aufgerufen von der `Serialize` Funktion, um die Version des Objekts zu ermitteln, die deserialisiert wird.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Bestimmt, ob der Puffer während der Windows Sockets geleert wurde verarbeiten.|  
|[CArchive::IsLoading](#isloading)|Bestimmt, ob das Archiv geladen wird.|  
|[CArchive::IsStoring](#isstoring)|Bestimmt, ob das Archiv gespeichert werden.|  
|[CArchive::MapObject](#mapobject)|Fügt Objekte in der Zuordnung, die nicht in die Datei serialisiert, die jedoch für Unterobjekte zu verweisen.|  
|[CArchive:: Read](#read)|Liest die unformatierten Bytes.|  
|[CArchive::ReadClass](#readclass)|Verweis auf eine Klasse, die zuvor mit gespeichert werden Lesevorgänge `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Ruft ein Objekt `Serialize` Funktion zum Laden.|  
|[CArchive::ReadString](#readstring)|Liest eine Textzeile an.|  
|[CArchive::SerializeClass](#serializeclass)|Liest oder schreibt den Klassenverweis auf die `CArchive` Objekt abhängig von der Richtung des der `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|Legt die Größe des Load-Arrays dar. Muss aufgerufen werden, bevor ein Objekt geladen wird oder bevor `MapObject` oder `ReadObject` aufgerufen wird.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Legt das Objektschema in das Archivobjekt gespeichert.|  
|[CArchive::SetStoreParams](#setstoreparams)|Legt die Größe des Hash-Tabelle und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.|  
|[CArchive::Write](#write)|Schreibt die unformatierten Bytes.|  
|[CArchive::WriteClass](#writeclass)|Schreibt einen Verweis auf die `CRuntimeClass` auf der `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Ruft ein Objekt `Serialize` Funktion zum Speichern.|  
|[CArchive::WriteString](#writestring)|Schreibt eine einzelne Textzeile.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::operator&lt;&lt;](#operator_lt_lt)|Speichert Objekte und primitive Datentypen in das Archiv.|  
|[CArchive::operator&gt;&gt;](#operator_gt_gt)|Lädt Objekte und primitive Datentypen aus dem Archiv.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Hinweise  
 `CArchive`eine Basisklasse keinen.  
  
 Später können Sie die Objekte aus dem permanenten Speicher laden rekonstruieren im Arbeitsspeicher. Dieser Prozess zum Bereitstellen von Daten persistent heißt "Serialisierung".  
  
 Sie können ein Archivobjekt als eine Art von binären Datenstrom vorstellen. Wie ein e/a-Stream ein Archiv ist mit einer Datei verknüpft und ermöglicht die gepufferten schreiben und Lesen von Daten aus dem Speicher. Ein e/a-Stream verarbeitet Sequenzen von ASCII-Zeichen, aber ein Archiv verarbeitet binäres Objektdaten in einem effizienten, nicht redundante-Format.  
  
 Müssen Sie erstellen ein [CFile](../../mfc/reference/cfile-class.md) Objekt vor der Erstellung einer `CArchive` Objekt. Darüber hinaus müssen Sie sicherstellen, dass das Archiv Laden/Speichern Status mit dem Öffnen der Datei-Modus kompatibel ist. Sie sind auf ein aktives Archiv pro Datei beschränkt.  
  
 Bei der Erstellung einer `CArchive` -Objekts können Sie ein Objekt der Klasse anhängen `CFile` (oder einer abgeleiteten Klasse), die eine offene Datei darstellt. Auch angeben, ob das Archiv zum Laden oder Speichern von verwendet wird. Ein `CArchive` Objekte kann nicht nur primitive Typen, sondern auch Objekte verarbeiten [CObject](../../mfc/reference/cobject-class.md)-abgeleitete Klassen, die für die Serialisierung vorgesehen. Eine serialisierbare Klasse hat normalerweise eine `Serialize` -Memberfunktion, und es in der Regel verwendet die [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makros, wie beschrieben unter Klasse `CObject`.  
  
 Die überladenen Extraktion ( ** >> **) und die Einfügemarke ( ** << **) Operatoren sind praktische Archiv Programmierschnittstellen, die sowohl primitiven Typen unterstützen und `CObject`-abgeleitete Klassen.  
  
 `CArchive`Außerdem unterstützt das Programmieren mit der Windows Sockets in MFC-Klassen [CSocket](../../mfc/reference/csocket-class.md) und [CSocketFile](../../mfc/reference/csocketfile-class.md). Die [IsBufferEmpty](#isbufferempty) Memberfunktion unterstützt diese Verwendung.  
  
 Weitere Informationen zu `CArchive`, finden Sie in den Artikeln [Serialisierung](../../mfc/serialization-in-mfc.md) und [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CArchive`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="abort"></a>CArchive::Abort  
 Rufen Sie diese Funktion, um das Archiv zu schließen, ohne eine Ausnahme auszulösen.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Hinweise  
 Die **CArchive** Destruktor ruft normalerweise **schließen**, die wegschreibt alle Daten, die nicht gespeichert wurde an die zugeordnete `CFile` Objekt. Dies kann dazu führen, dass Ausnahmen.  
  
 Wenn diese Ausnahmen abfangen, ist es eine gute Idee, verwenden Sie **Abort**, so dass destructing die `CArchive` Objekt keine weiteren Ausnahmen führen. Beim Verarbeiten von Ausnahmen, `CArchive::Abort` wird nicht auf Fehler eine Ausnahme auslösen, da im Gegensatz zu [CArchive::Close](#close), **Abort** Fehler ignoriert.  
  
 Wenn Sie verwendet **neue** Zuweisen der `CArchive` -Objekt im Heap, Sie nach dem Schließen der Datei gelöscht werden müssen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).  
  
##  <a name="carchive"></a>CArchive::CArchive  
 Erstellt ein `CArchive` -Objekt und gibt an, ob er zum Laden oder Speichern von Objekten verwendet wird.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf die `CFile` -Objekt, das die ultimative Quelle oder das Ziel der permanenten Daten ist.  
  
 `nMode`  
 Ein Flag, das angibt, ob Objekte aus geladen oder in das Archiv gespeichert werden. Die `nMode` Parameter muss einen der folgenden Werte aufweisen:  
  
- **CArchive::load** lädt Daten aus dem Archiv. Erfordert nur `CFile` read-Berechtigung.  
  
- **CArchive::store** speichert Daten in das Archiv. Erfordert `CFile` Schreibberechtigungen verfügen.  
  
- **CArchive::bNoFlushOnDelete** verhindert, dass das Archiv automatisch aufrufen `Flush` Wenn der Archiv-Destruktor aufgerufen wird. Wenn dieses Flag festgelegt wird, sind Sie verantwortlich für explizites Aufrufen von **schließen** bevor der Destruktor aufgerufen wird. Wenn Sie dies nicht tun, werden Ihre Daten beschädigt werden.  
  
 `nBufSize`  
 Eine ganze Zahl, die die Größe des internen Puffers in Bytes angibt. Beachten Sie, dass die standardmäßige Puffergröße 4.096 Bytes ist. Wenn Sie große Objekte regelmäßig archivieren, werden Sie die Leistung verbessern, wenn Sie einen größeren Puffer verwenden, der ein Vielfaches der Größe der Puffer ist.  
  
 `lpBuf`  
 Ein optionaler Zeiger auf einen Benutzer bereitgestellte Puffer der Größe `nBufSize`. Wenn Sie diesen Parameter nicht angeben, wird das Archiv einen Puffer vom lokalen Heap reserviert und freigegeben, wenn das Objekt zerstört wird. Das Archiv gibt einen Benutzer bereitgestellte Puffer nicht frei.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Spezifikation nicht ändern, nachdem Sie das Archiv erstellt haben.  
  
 Sie können keine `CFile` Vorgänge, den Status der Datei zu ändern, bis Sie das Archiv geschlossen haben. Jeder dieser Vorgang wird die Integrität des Archivs beschädigen. Sie können die Position des Dateizeigers zu einem beliebigen Zeitpunkt während der Serialisierung zugreifen, indem Sie die File-Objekt aus dem Archiv Abrufen der [GetFile](#getfile) -Memberfunktion und dann mithilfe der [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) Funktion. Rufen Sie [CArchive::Flush](#flush) bevor Sie die Position des Dateizeigers abrufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#12;](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>CArchive::Close  
 Löscht alle Daten im Puffer bleibt, schließt das Archiv, und trennt das Archiv aus der Datei.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Es sind keine weiteren Vorgänge im Archiv zulässig. Nachdem Sie ein Archiv geschlossen haben, können Sie ein weiteres Archiv für dieselbe Datei erstellen oder können Sie die Datei schließen.  
  
 Die Memberfunktion **schließen** wird sichergestellt, dass alle Daten aus dem Archiv in die Datei übertragen werden, und es das Archiv nicht verfügbar macht. Sie müssen zuerst verwenden, um die Übertragung aus der Datei auf dem Speichermedium abzuschließen, [CFile::Close](../../mfc/reference/cfile-class.md#close) und löschen Sie dann die `CFile` Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteString](#writestring).  
  
##  <a name="flush"></a>CArchive::Flush  
 Erzwingt, dass alle verbleibenden im Archiv Puffer in die Datei geschrieben werden.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `Flush` wird sichergestellt, dass alle Daten aus dem Archiv in die Datei übertragen wird. Sie müssen Aufrufen [CFile::Close](../../mfc/reference/cfile-class.md#close) um die Übertragung aus der Datei auf dem Speichermedium abzuschließen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#13;](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>CArchive::GetFile  
 Ruft die `CFile` Objektzeiger für dieses Archiv.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Konstanter Zeiger auf die `CFile` Objekt verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen das Archiv vor der Verwendung von leeren `GetFile`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&14;](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>CArchive::GetObjectSchema  
 Mit dieser Funktion wird von der `Serialize` Funktion, um die Version des Objekts zu bestimmen, die gerade deserialisiert wird.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Während der Deserialisierung wird die Version des Objekts gelesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Funktion ist nur gültig, wenn die `CArchive` Objekt geladen wird ( [CArchive::IsLoading](#isloading) gibt einen Wert ungleich null). Es sollte der erste Aufruf in der `Serialize` -Funktion und nur ein Mal aufgerufen. Der Rückgabewert ( **UINT**) –&1; gibt an, dass die Versionsnummer nicht bekannt ist.  
  
 Ein `CObject`-abgeleitete Klasse verwenden kann **VERSIONABLE_SCHEMA** kombiniert (bitweiser mit `OR`) mit der Schemaversion selbst (in der `IMPLEMENT_SERIAL` Makro) zum Erstellen einer "einsetzbarer Object", also ein Objekt, dessen `Serialize` Member-Funktion kann mehrere Versionen lesen. Die Standard-Framework-Funktionalität (ohne **VERSIONABLE_SCHEMA**) ist eine Ausnahme ausgelöst, wenn die Version nicht übereinstimmt, ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#15;](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>CArchive::IsBufferEmpty  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Archivobjekt internen Puffer leer ist.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv Puffer leer ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird bereitgestellt, um die Unterstützung der Programmierung mit der Windows Sockets in MFC-Klasse `CSocketFile`. Sie müssen nicht für ein Archiv zugeordneten verwendet ein `CFile` Objekt.  
  
 Der Grund für die Verwendung von `IsBufferEmpty` mit einem zugeordneten Archiv ein `CSocketFile` Objekt ist, dass das Archiv Puffer mehr als eine Nachricht oder einen Datensatz enthält. Verwenden Sie nach dem Empfang einer Nachricht, `IsBufferEmpty` zum Steuern einer Schleife, die weiterhin Daten empfangen, bis der Puffer leer ist. Weitere Informationen finden Sie unter der [empfangen](../../mfc/reference/casyncsocket-class.md#receive) -Memberfunktion der Klasse `CAsyncSocket`, die zeigt, wie `IsBufferEmpty`.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isloading"></a>CArchive::IsLoading  
 Bestimmt, ob das Archiv Daten lädt.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv für das Laden von derzeit verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, durch die `Serialize` Funktionen der archivierten Klassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization Nr.&16;](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>CArchive::IsStoring  
 Bestimmt, ob das Archiv Daten gespeichert werden.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv zum Speichern von momentan verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, durch die `Serialize` Funktionen der archivierten Klassen.  
  
 Wenn die `IsStoring` Status eines Archivs ist ungleich NULL ist, und klicken Sie dann die `IsLoading` Status gleich 0 ist, und umgekehrt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&17;](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>CArchive::MapObject  
 Rufen Sie diese Memberfunktion zum Platzieren von Objekten in der Zuordnung, die nicht wirklich auf die Datei serialisiert werden, jedoch werden Unterobjekte zu verweisen.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein konstanter Zeiger auf das Objekt gespeichert wird.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise können Sie ein Dokument nicht serialisieren, aber würden Sie die Elemente, die Teil des Dokuments serialisieren. Durch Aufrufen von `MapObject`, Sie können diese Elemente oder dar, auf das Dokument zu verweisen. Darüber hinaus serialisierten Unterelemente serialisieren können ihre `m_pDocument` Zeiger zurück.  
  
 Rufen Sie `MapObject` Wenn Sie zum Speichern und Laden Sie aus der `CArchive` Objekt. `MapObject`Fügt das angegebene Objekt auf die internen Datenstrukturen, die von verwaltet die `CArchive` Objekt während der Serialisierung und Deserialisierung, aber im Gegensatz zu [ReadObject](#readobject) und [WriteObject](#writeobject)**,** wird nicht aufgerufen für das Objekt zu serialisieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&18;](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization Nr.&19;](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization&20;](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization&21;](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>CArchive::m_pDocument  
 Legen Sie auf **NULL** standardmäßig ist dieser Zeiger auf eine **CDocument** kann festgelegt werden auf den Benutzer die `CArchive` -Instanz möchte.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine häufige Verwendung des this-Zeigers werden zusätzliche Informationen über den Serialisierungsprozess auf alle serialisierten Objekte übermitteln. Dies erfolgt durch die Initialisierung des Zeigers mit dem Dokument (ein **CDocument**-abgeleiteten Klasse), werden serialisiert, so, dass Objekte innerhalb des Dokuments, das Dokument ggf. zugreifen können. Dieser Zeiger wird auch vom verwendet `COleClientItem` Objekte während der Serialisierung.  
  
 Das Framework legt `m_pDocument` dem Dokument serialisiert werden, wenn ein Benutzer eine Datei ausgibt öffnen oder speichern (Befehl). Wenn Sie ein Object Linking and Embedding (OLE) Containerdokument Gründen als Datei öffnen oder Speichern Serialisieren, müssen Sie explizit festlegen `m_pDocument`. Beispielsweise würden Sie dazu beim Serialisieren eines Containerdokuments in die Zwischenablage.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#35;](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>CArchive::operator&lt;&lt;  
 Speichert das angegebene Objekt oder die primitiven Typs in das Archiv.  
  
```  
friend CArchive& operator<<(
    CArchive& ar,  
    const CObject* pOb);

 
throw(
    CArchiveException*, 
    CFileException*);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,  
    StringTraits>& str);  
  
CArchive& operator<<(BYTE by); 
CArchive& operator<<(WORD w); 
CArchive& operator<<(LONG l); 
CArchive& operator<<(DWORD dw); 
CArchive& operator<<(float f); 
CArchive& operator<<(double d); 
CArchive& operator<<(int i); 
CArchive& operator<<(short w); 
CArchive& operator<<(char ch); 
CArchive& operator<<(wchar_t ch); 
CArchive& operator<<(unsigned u); 
CArchive& operator<<(bool b); 
CArchive& operator<<(ULONGLONG dwdw); 
CArchive& operator<<(LONGLONG dwdw);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CArchive` -Verweis, der mehrere Insertion-Operatoren in einer einzelnen Zeile ermöglicht.  
  
### <a name="remarks"></a>Hinweise  
 Die letzten beiden Versionen oben sind speziell für das Speichern von 64-Bit-Ganzzahlen.  
  
 Wenn Sie verwendet die `IMPLEMENT_SERIAL` Makro in Ihrer Implementierung der Klasse, und klicken Sie dann auf den Operator zum Einfügen für überladen `CObject` wird die geschützte **WriteObject**. Diese Funktion wiederum ruft die `Serialize` -Funktion der Klasse.  
  
 Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) einfügen-Operator ()<) supports diagnostic dumping and storing to an archive. supports="" diagnostic="" dumping="" and="" storing="" to="" an=""></) supports diagnostic dumping and storing to an archive.>  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Operator zum Einfügen des < with="" the=""> `int` und `long` Typen.  
  
 [!code-cpp[NVC_MFCSerialization&#31;](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel 2 veranschaulicht die Verwendung von der `CArchive` Operator zum Einfügen des < with="" the=""> `CStringT` Typ.  
  
 [!code-cpp[NVC_MFCSerialization&#32;](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>CArchive::operator&gt;&gt;  
 Lädt die angegebenen primitiven Typ aus dem Archiv.  
  
```  
friend CArchive& operator>>(
    CArchive& ar,  
    CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
friend CArchive& operator>>(
    CArchive& ar,  
    const CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType, 
    StringTraits>& str);  
  
CArchive& operator>>(BYTE& by);    
CArchive& operator>>(WORD& w);    
CArchive& operator>>(int& i);    
CArchive& operator>>(LONG& l);    
CArchive& operator>>(DWORD& dw);    
CArchive& operator>>(float& f);    
CArchive& operator>>(double& d);    
CArchive& operator>>(short& w);    
CArchive& operator>>(char& ch);    
CArchive& operator>>(wchar_t& ch);    
CArchive& operator>>(unsigned& u);    
CArchive& operator>>(bool& b);    
CArchive& operator>>(ULONGLONG& dwdw);   
CArchive& operator>>(LONGLONG& dwdw);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CArchive` -Verweis, der in einer einzigen Zeile mehrere Extraktionsoperatoren ermöglicht.  
  
### <a name="remarks"></a>Hinweise  
 Die letzten beiden Versionen oben sind speziell für das Laden von 64-Bit-Ganzzahlen.  
  
 Wenn Sie verwendet die `IMPLEMENT_SERIAL` Makro in Ihrer Implementierung der Klasse, und klicken Sie dann auf die Extraktionsoperatoren überladen für `CObject` aufrufen, die geschützte **ReadObject** Funktion (mit einem Wert ungleich NULL Laufzeitklasse-Zeiger). Diese Funktion wiederum ruft die `Serialize` -Funktion der Klasse.  
  
 Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Extraktionsoperator (>) unterstützt das Laden aus einem Archiv.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Extraktionsoperator >> mit den `int` Typ.  
  
 [!code-cpp[NVC_MFCSerialization&33;](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Einfügung und Extraktion Operatoren \< und >> mit den `CStringT` Typ.  
  
 [!code-cpp[NVC_MFCSerialization&#34;](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>CArchive:: Read  
 Liest eine angegebene Anzahl von Bytes aus dem Archiv.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf einen Benutzer bereitgestellte Puffer zum Empfangen der Daten aus dem Archiv lesen.  
  
 `nMax`  
 Ganze Zahl ohne Vorzeichen angeben der Anzahl von Bytes aus dem Archiv gelesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl ohne Vorzeichen mit der Anzahl der tatsächlich gelesenen Bytes. Wenn der Rückgabewert kleiner als die angeforderte Anzahl ist, wurde das Ende der Datei erreicht. Die End-of-File-Bedingung wird keine Ausnahme ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Das Archiv kann die Bytes nicht interpretieren.  
  
 Können Sie die **lesen** Memberfunktion innerhalb Ihrer `Serialize` Funktion zum Lesen der normaler Strukturen, die in den Objekten enthalten sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#24;](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>CArchive::ReadClass  
 Rufen Sie diese Memberfunktion, um einen Verweis auf eine Klasse, die zuvor mit gespeicherten lesen [WriteClass](#writeclass).  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pClassRefRequested`  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die die angeforderte Klassenreferenz entspricht. Kann **NULL**.  
  
 `pSchema`  
 Ein Zeiger auf ein Schema der zuvor gespeicherten Laufzeit-Klasse.  
  
 `pObTag`  
 Eine Zahl, die auf eindeutigen Tag ein Objekt verweist. Wird intern verwendet, durch die Implementierung von [ReadObject](#readobject). Für die Erweiterte Programmierung bereitgestellt werden; `pObTag` normalerweise sollte **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pClassRefRequested` nicht **NULL**, `ReadClass` stellt sicher, dass die archivierten Informationen mit der Common Language Runtime-Klasse kompatibel ist. Ist er nicht kompatibel ist, `ReadClass` löst ein [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), andernfalls `ReadClass` löst ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Wenn `pSchema` ist **NULL**, das Schema der gespeicherten Klasse abgerufen werden kann, durch Aufrufen von [CArchive::GetObjectSchema](#getobjectschema), andernfalls ** \* ** `pSchema` enthält das Schema der Laufzeit-Klasse, die zuvor gespeichert wurde.  
  
 Sie können [SerializeClass](#serializeclass) anstelle von `ReadClass`, lesen und Schreiben des Klassenverweises behandelt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).  
  
##  <a name="readobject"></a>CArchive::ReadObject  
 Liest Daten aus dem Archiv, und erstellt ein Objekt des entsprechenden Typs.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parameter  
 `pClass`  
 Konstanter Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die dem Objekt entspricht gelesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CObject](../../mfc/reference/cobject-class.md) Zeiger, der problemlos in den richtigen umgewandelt werden, muss abgeleitete Klasse mit [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, indem die `CArchive` extrahieren ( ** >> **) Operator überladen für eine [CObject](../../mfc/reference/cobject-class.md) Zeiger. **ReadObject**, wiederum die `Serialize` -Funktion der archivierten Klasse.  
  
 Wenn Sie einen Wert ungleich NULL angeben `pClass` -Parameter, der von abgerufen werden die [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) -Makro, und klicken Sie dann auf die Funktion überprüft die Laufzeitklasse des archivierten-Objekts. Dabei wird angenommen, Sie verwendet haben, die `IMPLEMENT_SERIAL` Makro in der Implementierung der Klasse.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteObject](#writeobject).  
  
##  <a name="readstring"></a>CArchive::ReadString  
 Rufen Sie diese Memberfunktion zum Lesen von Textdaten in einen Puffer aus der Datei zugeordneten der `CArchive` Objekt.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `rString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die resultierende Zeichenfolge nach dem Lesen aus der Datei, die dem CArchive-Objekt zugeordnet ist.  
  
 `lpsz`  
 Gibt einen Zeiger auf einen Benutzer bereitgestellte Puffer, der eine Null-terminierte Zeichenfolge erhalten.  
  
 `nMax`  
 Gibt die maximale Anzahl der zu lesenden Zeichen. Sollte eine kleiner als die Größe der *Lpsz* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 In der Version, die zurückgibt **BOOL**, **TRUE** bei Erfolg; **FALSE** andernfalls.  
  
 In der Version, die gibt eine `LPTSTR`, einen Zeiger auf den Puffer mit Daten aus der Textdatei; **NULL** Ende der Datei erreicht wurde.  
  
### <a name="remarks"></a>Hinweise  
 In der Version der Memberfunktion mit dem `nMax` -Parameter, der Puffer enthält von bis zu einem `nMax` - 1 Zeichen. Lesen wird durch einen Wagenrücklauf Return-Zeilenvorschub beendet. Nachfolgende neue Zeilenumbruchzeichen werden immer entfernt. In beiden Fällen wird ein Null-Zeichen ('\0') angefügt.  
  
 [CArchive:: Read](#read) steht auch für Textmodus-Eingabe, sondern es wird auf eine Carriage Return-Zeilenvorschub nicht beendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteString](#writestring).  
  
##  <a name="serializeclass"></a>CArchive::SerializeClass  
 Rufen Sie diese Memberfunktion auf, wenn Sie verwenden möchten, speichern und laden die Versionsinformationen für eine Basisklasse.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parameter  
 `pClassRef`  
 Ein Zeiger auf ein Objekt zur Laufzeit-Klasse für die Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 `SerializeClass`liest oder schreibt den Verweis auf eine Klasse, die `CArchive` -Objekt, abhängig von der Richtung des der `CArchive`. Verwendung `SerializeClass` anstelle von [ReadClass](#readclass) und [WriteClass](#writeclass) als eine bequeme Möglichkeit zum Serialisieren von Objekten der Basisklasse; `SerializeClass` erfordert weniger Code und weniger Parameter.  
  
 Wie `ReadClass`, `SerializeClass` stellt sicher, dass die archivierten Informationen mit der Common Language Runtime-Klasse kompatibel ist. Ist er nicht kompatibel ist, `SerializeClass` löst ein [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), andernfalls `SerializeClass` löst ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Verwenden der [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) Makro zum Abrufen des Werts für die `pRuntimeClass` Parameter. Die Basisklasse muss haben verwendet die [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#25;](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>CArchive::SetLoadParams  
 Rufen Sie `SetLoadParams` Wenn man eine große Anzahl von lesen `CObject`-abgeleitete Objekte aus dem Archiv.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Parameter  
 `nGrowBy`  
 Die minimale Anzahl der Element-Steckplätze zuordnen, wenn eine Erhöhung erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 `CArchive`verwendet ein Array laden zum Auflösen von Verweisen auf Objekte, die im Archiv gespeichert. `SetLoadParams`können Sie zum Festlegen der Größe der Load-Array dar.  
  
 Sie müssen nicht aufrufen, `SetLoadParams` jedes Objekt geladen wird oder nach [MapObject](#mapobject) oder [ReadObject](#readobject) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>CArchive::SetObjectSchema  
 Rufen Sie diese Memberfunktion zum Festlegen der Objektschema in das Archiv zu gespeicherten `nSchema`.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Parameter  
 `nSchema`  
 Gibt das Objekt Schema.  
  
### <a name="remarks"></a>Hinweise  
 Der nächste Aufruf von [GetObjectSchema](#getobjectschema) ergibt den Wert in gespeicherten `nSchema`.  
  
 Verwendung `SetObjectSchema` für die erweiterte Versionskontrolle, z. B. Wenn Sie eine bestimmte Version in lesen erzwingen möchten eine `Serialize` einer abgeleiteten Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#27;](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>CArchive::SetStoreParams  
 Verwendung `SetStoreParams` beim Speichern eine große Anzahl von `CObject`-abgeleiteten Objekte in ein Archiv.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Parameter  
 *nHashSize*  
 Die Größe der Hashtabelle für Schnittstellenzeiger zugeordnet wird. Sollte eine Primzahl.  
  
 `nBlockSize`  
 Gibt die Granularität der Reservierung von Speicher für die Erweiterung der Parameter an. Sollte eine Potenz von 2 für die beste Leistung.  
  
### <a name="remarks"></a>Hinweise  
 `SetStoreParams`ermöglicht das Festlegen der Größe der Hash-Tabelle und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.  
  
 Sie müssen nicht aufrufen, `SetStoreParams` Objekte gespeichert werden oder nach [MapObject](#mapobject) oder [WriteObject](#writeobject) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>CArchive::Write  
 Schreibt eine angegebene Anzahl von Bytes in das Archiv.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf einen Benutzer bereitgestellte Puffer mit den Daten in das Archiv geschrieben werden.  
  
 `nMax`  
 Eine ganze Zahl, die Anzahl der Bytes in das Archiv geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Archiv formatiert die Bytes nicht.  
  
 Können Sie die **schreiben** Memberfunktion innerhalb Ihrer `Serialize` -Funktion schreiben gewöhnliche Datenstrukturen, die in den Objekten enthalten sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&23;](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>CArchive::WriteClass  
 Verwendung `WriteClass` zum Speichern der Klasse Informationen zu Version und einer Basisklasse während der Serialisierung der abgeleiteten Klasse.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parameter  
 `pClassRef`  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die die angeforderte Klassenreferenz entspricht.  
  
### <a name="remarks"></a>Hinweise  
 `WriteClass`Schreibt einen Verweis auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) für die Basisklasse, die `CArchive`. Verwendung [CArchive::ReadClass](#readclass) den Verweis abrufen.  
  
 `WriteClass`überprüft, ob die archivierten Klasseninformationen kompatibel mit der Common Language Runtime-Klasse. Ist er nicht kompatibel ist, `WriteClass` löst ein [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), andernfalls `WriteClass` löst ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Sie können [SerializeClass](#serializeclass) anstelle von `WriteClass`, lesen und Schreiben des Klassenverweises behandelt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#28;](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>CArchive::WriteObject  
 Speichert den angegebenen `CObject` in das Archiv.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein konstanter Zeiger auf das Objekt gespeichert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, indem die `CArchive` einfügen ( ** << **) Operator überladen für `CObject`. **WriteObject**, wiederum die `Serialize` -Funktion der archivierten Klasse.  
  
 Verwenden Sie die `IMPLEMENT_SERIAL` Makro Archivierung zu aktivieren. **WriteObject** schreibt die ASCII-Klasse in das Archiv. Der Klassenname wird später während des Ladevorgangs überprüft. Eine spezielle Codierungsschema verhindert, dass unnötige Verdoppelungen von der Klassenname für mehrere Objekte der Klasse. Dieses Schema wird auch verhindert, dass redundanten Speicher von Objekten, die Ziele von mehr als einen Zeiger handelt.  
  
 Genaue das Objekt encoding-Methode (einschließlich das Vorhandensein der ASCII-Klassenname) ist ein Implementierungsdetail, und kann in zukünftigen Versionen der Bibliothek ändern.  
  
> [!NOTE]
>  Beenden Sie erstellen, löschen und aktualisieren alle Objekte, bevor Sie beginnen, zu archivieren. Ihr Archiv wird beschädigt, wenn Sie kombinieren Archivierung mit Objekt ändern.  
  
### <a name="example"></a>Beispiel  
 Eine Definition der Klasse `CAge`, finden Sie im Beispiel [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization&#29;](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>CArchive::WriteString  
 Verwenden Sie diese Memberfunktion zum Schreiben von Daten aus einem Puffer auf die Datei mit den `CArchive` Objekt.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Puffer mit Null endende Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Das abschließende Nullzeichen ('\0') wird nicht in die Datei geschrieben; noch ein Zeilenumbruch automatisch geschrieben.  
  
 `WriteString`löst eine Ausnahme als Reaktion auf verschiedene Faktoren, beispielsweise die voll.  
  
 **Schreiben von** ist ebenfalls verfügbar, aber statt auf ein Null-Zeichen beendet, schreibt er die angeforderte Anzahl von Bytes in der Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization&#30;](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)

