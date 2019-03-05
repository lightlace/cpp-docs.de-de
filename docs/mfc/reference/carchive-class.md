---
title: CArchive-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
ms.openlocfilehash: 8f169964c6a313f37b5ea50a5105af29af7b59b1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266327"
---
# <a name="carchive-class"></a>CArchive-Klasse

Können Sie ein komplexes Netzwerk von Objekten in einer permanenten binären Form (normalerweise in Festplattenspeicher) zu speichern, die erhalten bleibt, nachdem diese Objekte gelöscht wurden.

## <a name="syntax"></a>Syntax

```
class CArchive
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|Erstellt ein `CArchive`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CArchive::Abort](#abort)|Schließen ein Archiv, ohne eine Ausnahme auszulösen.|
|[CArchive::Close](#close)|Schreibt nicht geschriebene Daten Weg, und trennt die `CFile`.|
|[CArchive::Flush](#flush)|Leert nicht geschriebene Daten aus dem Archiv-Puffer.|
|[CArchive::GetFile](#getfile)|Ruft die `CFile` Objektzeiger für dieses Archiv.|
|[CArchive::GetObjectSchema](#getobjectschema)|Wird aufgerufen, von der `Serialize` -Funktion können Sie die Version des Objekts zu ermitteln, die deserialisiert wird.|
|[CArchive::IsBufferEmpty](#isbufferempty)|Bestimmt, ob der Puffer während einer Windows-Sockets geleert wurde verarbeiten.|
|[CArchive::IsLoading](#isloading)|Bestimmt, ob das Archiv geladen wird.|
|[CArchive::IsStoring](#isstoring)|Bestimmt, ob das Archiv gespeichert werden.|
|[CArchive::MapObject](#mapobject)|Fügt Objekte in der Zuordnung auf die Datei nicht serialisiert werden, aber für den untergeordneten Objekte zu verweisen.|
|[CArchive:: Read](#read)|Liest die rohen Bytes.|
|[CArchive::ReadClass](#readclass)|Verweis auf eine Klasse, die zuvor mit gespeichert werden Lesevorgänge `WriteClass`.|
|[CArchive::ReadObject](#readobject)|Ruft ein Objekt des `Serialize` Funktion zum Laden.|
|[CArchive::ReadString](#readstring)|Liest eine Textzeile an.|
|[CArchive::SerializeClass](#serializeclass)|Liest oder schreibt die Klassenverweises an die `CArchive` Objekt abhängig von der Richtung von der `CArchive`.|
|[CArchive::SetLoadParams](#setloadparams)|Legt die Größe, die Load-Array wächst. Muss aufgerufen werden, bevor ein Objekt geladen wird oder vor dem `MapObject` oder `ReadObject` aufgerufen wird.|
|[CArchive::SetObjectSchema](#setobjectschema)|Legt fest, das Objektschema in das Archivobjekt gespeichert.|
|[CArchive::SetStoreParams](#setstoreparams)|Legt fest, die Hashtabellengröße und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.|
|[CArchive::Write](#write)|Schreibt die unformatierten Bytes.|
|[CArchive::WriteClass](#writeclass)|Schreibt einen Verweis auf die `CRuntimeClass` auf die `CArchive`.|
|[CArchive::WriteObject](#writeobject)|Ruft ein Objekt des `Serialize` Funktion zum Speichern von.|
|[CArchive::WriteString](#writestring)|Schreibt eine Textzeile an.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|Speichert Objekte und primitive Datentypen in das Archiv.|
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|Laden die Objekte und primitive Datentypen aus dem Archiv.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Hinweise

`CArchive` eine Basisklasse keinen.

Später können Sie die Objekte aus dem persistenten Speicher laden rekonstruieren im Arbeitsspeicher. Dieser Prozess zum Bereitstellen von persistenten Daten heißt "Serialisierung".

Sie können ein Archivobjekt als eine Art des binären Datenstroms vorstellen. Wie ein e/a-Stream ein Archiv bezieht sich auf eine Datei und ermöglicht die gepufferten schreiben und Lesen von Daten in und aus Storage. Ein Eingabe-/Ausgabestreams verarbeitet Sequenzen von ASCII-Zeichen, aber ein Archiv Datenverarbeitung binäres Objekt in einem effizienten, nicht redundante-Format.

Müssen Sie erstellen eine [CFile](../../mfc/reference/cfile-class.md) Objekt vor der Erstellung einer `CArchive` Objekt. Darüber hinaus müssen Sie sicherstellen, dass das Laden/Speichern der Archivstatus mit den Öffnungsmodus der Datei kompatibel ist. Sie sind auf einem aktiven Archiv pro Datei beschränkt.

Beim Erstellen einer `CArchive` -Objekts können Sie es an ein Objekt der Klasse anfügen `CFile` (oder einer abgeleiteten Klasse), das eine offene Datei darstellt. Sie geben außerdem, ob das Archiv zum Laden oder Speichern von verwendet wird. Ein `CArchive` Objekt verarbeiten kann, nicht nur primitive Typen, sondern auch Objekte [CObject](../../mfc/reference/cobject-class.md)-abgeleitete Klassen, die für die Serialisierung vorgesehen. Eine serialisierbare Klasse in der Regel verfügt über eine `Serialize` Member-Funktion, und in der Regel verwendet der [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makros, wie beschrieben unter Klasse `CObject`.

Die überladenen Extrahierung ( **>>**) und dem Einfügen ( **<<**) Operatoren sind praktische Archiv Programmierschnittstellen, die sowohl primitiven Typen zu unterstützen und `CObject` – abgeleitete Klassen.

`CArchive` Außerdem unterstützt das Programmieren mit den Windows-Sockets MFC-Klassen [CSocket](../../mfc/reference/csocket-class.md) und [CSocketFile](../../mfc/reference/csocketfile-class.md). Die [IsBufferEmpty](#isbufferempty) Member-Funktion unterstützt diese Verwendung.

Weitere Informationen zu `CArchive`, finden Sie in den Artikeln [Serialisierung](../../mfc/serialization-in-mfc.md) und [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CArchive`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="abort"></a>  CArchive::Abort

Rufen Sie diese Funktion aus, um das Archiv zu schließen, ohne eine Ausnahme auszulösen.

```
void Abort ();
```

### <a name="remarks"></a>Hinweise

Die `CArchive` Destruktor ruft normalerweise `Close`, alle Daten, die nicht gespeichert wurde, die wird geleert an die zugeordnete `CFile` Objekt. Dies kann die Ausnahmen verursachen.

Wenn diese Ausnahmen abfangen, ist es eine gute Idee, `Abort`, sodass destructing der `CArchive` Objekt keine weiteren Ausnahmen auslösen. Bei der Behandlung von Ausnahmen, `CArchive::Abort` wird nicht bei Fehlern eine Ausnahme ausgelöst, da im Gegensatz zu [CArchive::Close](#close), `Abort` Fehler ignoriert.

Wenn Sie verwendet **neue** Zuweisen der `CArchive` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).

##  <a name="carchive"></a>  CArchive::CArchive

Erstellt eine `CArchive` Objekt und gibt an, ob er zum Laden oder Speichern von Objekten verwendet wird.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Parameter

*pFile*<br/>
Ein Zeiger auf die `CFile` Objekt, das ist die ultimative Quelle oder das Ziel der permanenten Daten.

*nMode*<br/>
Ein Flag, das angibt, ob die Objekte aus geladen oder in das Archiv gespeichert werden. Die *nMode* Parameter muss einen der folgenden Werte aufweisen:

- `CArchive::load` Lädt Daten aus dem Archiv. Erfordert nur `CFile` read-Berechtigung.

- `CArchive::store` Speichert Daten in das Archiv. Erfordert `CFile` Schreibberechtigungen verfügen.

- `CArchive::bNoFlushOnDelete` Verhindert, dass das Archiv automatisch aufrufen `Flush` bei der Archiv-Destruktor aufgerufen wird. Wenn Sie dieses Flag festlegen, sind Sie verantwortlich für den expliziten Aufruf `Close` , bevor der Destruktor aufgerufen wird. Wenn Sie dies nicht tun, werden Ihre Daten beschädigt werden.

*nBufSize*<br/>
Eine ganze Zahl, die die Größe des internen Puffers in Bytes angibt. Beachten Sie, dass die Standardpuffergröße 4.096 Bytes. Wenn Sie große Objekte routinemäßig archivieren haben, werden Sie bei Verwendung ein größeren Puffers, das ein Vielfaches der Größe der Puffer ist die Leistung verbessert.

*lpBuf*<br/>
Einem optionalen Zeiger auf einen vom Benutzer bereitgestellten Puffer der Größe *nBufSize*. Wenn Sie diesen Parameter nicht angeben, wird das Archiv weist einen Puffer aus dem lokalen Heap und gibt sie frei, wenn das Objekt zerstört wird. Das Archiv gibt einen Benutzer bereitgestellte Puffer nicht frei.

### <a name="remarks"></a>Hinweise

Sie können in dieser Spezifikation nicht ändern, nachdem Sie das Archiv erstellt haben.

Sie können nicht `CFile` Operations, ändern den Status der Datei aus, bis Sie das Archiv geschlossen haben. Solche Vorgänge, die Integrität des Archivs beschädigen. Sie können die Position des Dateizeigers zu einem beliebigen Zeitpunkt während der Serialisierung zugreifen, durch Abrufen des Archivs Objekt "Datei" aus der [GetFile](#getfile) Memberfunktion, und klicken Sie dann mit der [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) Funktion . Rufen Sie [CArchive::Flush](#flush) vor dem Abrufen der Position des Dateizeigers.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>  CArchive::Close

Leert alle Daten, die im Puffer bleibt, schließen das Archiv und trennt die Verbindung des Archivs aus der Datei.

```
void Close();
```

### <a name="remarks"></a>Hinweise

Es sind keine weiteren Vorgänge auf das Archiv zulässig. Nachdem Sie ein Archiv geschlossen haben, können Sie ein weiteres Archiv für dieselbe Datei erstellen, oder können Sie die Datei schließen.

Die Memberfunktion `Close` wird sichergestellt, dass alle Daten aus dem Archiv auf die Datei übertragen wird, und es das Archiv nicht mehr verfügbar ist. Um die Übertragung aus der Datei auf dem Speichermedium abzuschließen, müssen Sie zunächst mithilfe [CFile::Close](../../mfc/reference/cfile-class.md#close) und entfernen Sie dann die `CFile` Objekt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CArchive::WriteString](#writestring).

##  <a name="flush"></a>  CArchive::Flush

Erzwingt, dass alle Daten verbleiben in der Archiv-Puffer, in die Datei geschrieben werden.

```
void Flush();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion `Flush` wird sichergestellt, dass alle Daten aus dem Archiv auf die Datei übertragen wird. Rufen Sie [CFile::Close](../../mfc/reference/cfile-class.md#close) die Übertragung aus der Datei auf dem Speichermedium.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>  CArchive::GetFile

Ruft die `CFile` Objektzeiger für dieses Archiv.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Rückgabewert

Ein konstanter Zeiger auf die `CFile` Objekt verwendet.

### <a name="remarks"></a>Hinweise

Sie müssen das Archiv vor der Verwendung von leeren `GetFile`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema

Mit dieser Funktion wird von der `Serialize` -Funktion können Sie die Version des Objekts zu ermitteln, die gerade deserialisiert wird.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Rückgabewert

Während der Deserialisierung wird die Version des Objekts gelesen wird.

### <a name="remarks"></a>Hinweise

Das Aufrufen dieser Funktion ist nur gültig, wenn die `CArchive` Objekt geladen wird ( [CArchive::IsLoading](#isloading) ungleich NULL zurückgibt). Wird der erste Aufruf in die `Serialize` -Funktion und nur ein Mal aufgerufen. Der Rückgabewert (UINT) – 1 gibt an, dass die Versionsnummer unbekannt ist.

Ein `CObject`-abgeleiteten Klasse können Sie VERSIONABLE_SCHEMA kombiniert (bitweiser mit **oder**) mit der Schemaversion selbst (in der das Makro) zum Erstellen einer "anbietbar Object", also ein Objekt, dessen `Serialize` Member-Funktion kann mehrere Versionen lesen. Die Funktionen des Standard-Frameworks (ohne VERSIONABLE_SCHEMA) ist eine Ausnahme ausgelöst, wenn die Version nicht übereinstimmt, ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty

Rufen Sie diese Memberfunktion, um festzustellen, ob der interne Puffer für das Archivobjekt leer ist.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Rückgabewert

Legen Sie ungleich NULL, wenn es sich bei dem Archiv der Puffer leer ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion wird bereitgestellt, um die Unterstützung der Programmierung mit der Windows-Sockets MFC-Klasse `CSocketFile`. Sie müssen nicht für ein Archiv verwendet eine `CFile` Objekt.

Der Grund für die Verwendung von `IsBufferEmpty` mit einem zugeordneten Archiv eine `CSocketFile` Objekt ist, dass das Archiv der Puffer mehr als eine Nachricht oder Datensatz enthalten kann. Verwenden Sie nach dem Empfang einer Nachricht, `IsBufferEmpty` zum Steuern einer Schleife, die fortgesetzt wird, Empfangen von Daten, bis der Puffer leer ist. Weitere Informationen finden Sie unter den [Receive](../../mfc/reference/casyncsocket-class.md#receive) Memberfunktion der Klasse `CAsyncSocket`, die zeigt, wie `IsBufferEmpty`.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isloading"></a>  CArchive::IsLoading

Bestimmt, ob das Archiv Daten geladen werden.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Archiv für das Laden von derzeit verwendet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, indem die `Serialize` Funktionen der archivierten Klassen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>  CArchive::IsStoring

Bestimmt, ob das Archiv Daten gespeichert werden.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Archiv für die Speicherung von derzeit verwendet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, indem die `Serialize` Funktionen der archivierten Klassen.

Wenn die `IsStoring` Status eines Archivs ungleich NULL ist, und klicken Sie dann die `IsLoading` Status ist 0 (null) und umgekehrt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>  CArchive::MapObject

Rufen Sie diese Memberfunktion zum Platzieren von Objekten in der Zuordnung, die nicht wirklich in die Datei serialisiert werden, aber für den untergeordneten Objekte zu verweisen.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*pOb*<br/>
Ein konstanter Zeiger auf das Objekt gespeichert wird.

### <a name="remarks"></a>Hinweise

Beispielsweise Sie ein Dokument können nicht serialisiert werden, aber Sie würden die Elemente, die Teil des Dokuments serialisieren. Durch Aufrufen von `MapObject`, Sie können diese Elemente oder Unterobjekte, um das Dokument zu referenzieren. Darüber hinaus serialisierten Unterelemente serialisieren können ihre *M_pDocument* Gegenzeiger.

Rufen Sie `MapObject` Wenn Sie zum Speichern und Laden Sie aus der `CArchive` Objekt. `MapObject` Fügt das angegebene Objekt auf die internen Datenstrukturen, die von verwaltet die `CArchive` Objekt während der Serialisierung und Deserialisierung, aber im Gegensatz zu [ReadObject](#readobject) und [WriteObject](#writeobject), wird nicht aufgerufen für das Objekt serialisiert werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>  CArchive::m_pDocument

Auf NULL festgelegt ist, wird standardmäßig dieser Zeiger in einen `CDocument` können festgelegt werden den Benutzer die `CArchive` Instanz benötigt.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Hinweise

Eine häufige Verwendung des this-Zeigers ist zusätzliche Informationen zu den Serialisierungsprozess für alle Objekte, die serialisiert wird übermittelt. Dies erfolgt durch die Initialisierung des Zeigers mit dem Dokument (einem `CDocument`-abgeleitete Klasse), werden serialisiert, so, dass Objekte innerhalb des Dokuments, das Dokument bei Bedarf zugreifen können. This-Zeiger wird auch vom verwendet `COleClientItem` Objekte während der Serialisierung.

Das Framework legt *M_pDocument* auf das Dokument serialisiert wird, wenn ein Benutzer eine Datei ausgibt öffnen oder speichern (Befehl). Wenn Sie eine Containerdokument Object Linking and Embedding (OLE) anderen Gründen als Datei öffnen oder Speichern Serialisieren, müssen Sie explizit festlegen *M_pDocument*. Beispielsweise würden Sie vorgehen beim Serialisieren eines Containerdokuments in die Zwischenablage.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;

Speichert die angegebenen Objekt oder ein primitiver Typ, in das Archiv.

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

Ein `CArchive` -Verweis, der mehrere Einfügeoperatoren in einer einzelnen Zeile ermöglicht.

### <a name="remarks"></a>Hinweise

Die letzten beiden Versionen, die oben genannten sind speziell für das Speichern von 64-Bit-Ganzzahlen.

Wenn Sie das IMPLEMENT_SERIAL-Makro in Ihrer klassenimplementierung verwendet, der Einfügeoperator für überladen `CObject` Ruft die geschützte `WriteObject`. Diese Funktion, wiederum ruft die `Serialize` -Funktion der Klasse.

Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Operator zum Einfügen (<<) unterstützt die Diagnose-Dump-Sicherungen und in ein Archiv speichern.

### <a name="example"></a>Beispiel

Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` einfügungsoperator << mit der **Int** und **lange** Typen.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Beispiel

In diesem Beispiel 2 zeigt die Verwendung von der `CArchive` einfügungsoperator << mit der `CStringT` Typ.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;

Lädt das angegebene Objekt oder ein primitiver Typ, aus dem Archiv.

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

Ein `CArchive` -Verweis, der mehrere Extraktionsoperatoren in einer einzelnen Zeile ermöglicht.

### <a name="remarks"></a>Hinweise

Die letzten beiden Versionen, die oben genannten sind speziell für die 64-Bit-Ganzzahlen werden geladen.

Wenn Sie das IMPLEMENT_SERIAL-Makro in Ihrer klassenimplementierung verwendet, die Extraktionsoperatoren für überladen `CObject` rufen die geschützte `ReadObject` -Funktion (mit Zeiger ungleich NULL Run-Time-Klasse). Diese Funktion, wiederum ruft die `Serialize` -Funktion der Klasse.

Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Extraktionsoperator (>>) unterstützt das Laden aus einem Archiv.

### <a name="example"></a>Beispiel

Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Extraktionsoperator >> mit der **Int** Typ.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Beispiel

Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Einfügung und Extraktion Operatoren <\< und >> mit der `CStringT` Typ.

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>  CArchive:: Read

Liest eine angegebene Anzahl von Bytes aus dem Archiv.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger auf einen Benutzer bereitgestellten Puffer, der zum Empfangen der Daten aus dem Archiv zu lesen ist.

*nMax*<br/>
Ganze Zahl ohne Vorzeichen, die die Anzahl von Bytes angibt, aus dem Archiv gelesen werden.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl ohne Vorzeichen, die die Anzahl der tatsächlich gelesenen Bytes enthält. Wenn der Rückgabewert kleiner als die angeforderte Anzahl ist, wurde das Dateiende erreicht. Nach der End-of-File-Bedingung wird keine Ausnahme ausgelöst.

### <a name="remarks"></a>Hinweise

Das Archiv kann nicht die Bytes interpretieren.

Können Sie die `Read` Memberfunktion innerhalb Ihrer `Serialize` Funktion zum Lesen von normaler Strukturen, die in den Objekten enthalten sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>  CArchive::ReadClass

Rufen Sie diese Memberfunktion zum Lesen von eines Verweis auf eine Klasse, die zuvor mit gespeicherten [WriteClass](#writeclass).

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>Parameter

*pClassRefRequested*<br/>
Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die die angeforderten Klassenreferenz entspricht. NULL kann sein.

*pSchema*<br/>
Ein Zeiger auf ein Schema von der Laufzeit-Klasse, die zuvor gespeichert.

*pObTag*<br/>
Eine Zahl, die auf eine eindeutige Objekttag verweist. Wird intern verwendet, durch die Implementierung von [ReadObject](#readobject). Für die Erweiterte Programmierung verfügbar gemacht; *pObTag* normalerweise sollte NULL sein.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur.

### <a name="remarks"></a>Hinweise

Wenn *pClassRefRequested* ist nicht NULL, `ReadClass` stellt sicher, dass die archivierten Klasseninformationen kompatibel mit der Common Language Runtime-Klasse ist. Wenn er nicht kompatibel ist, ist `ReadClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `ReadClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Wenn *pSchema* NULL ist, kann das Schema der gespeicherten-Klasse abgerufen werden, durch den Aufruf [CArchive::GetObjectSchema](#getobjectschema)ist, andernfalls <strong>\*</strong>  *pSchema* enthält das Schema der Runtime-Klasse, die zuvor gespeichert wurde.

Sie können [SerializeClass](#serializeclass) anstelle von `ReadClass`, lesen und Schreiben des Klassenverweises behandelt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).

##  <a name="readobject"></a>  CArchive::ReadObject

Aus dem Archiv werden Objektdaten gelesen, und erstellt ein Objekt des entsprechenden Typs.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>Parameter

*pClass*<br/>
Ein konstanter Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die dem Objekt entspricht gelesen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein [CObject](../../mfc/reference/cobject-class.md) Zeiger, der problemlos in den richtigen umgewandelt werden, muss abgeleitete Klasse mit [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof).

### <a name="remarks"></a>Hinweise

Diese Funktion wird normalerweise aufgerufen, indem die `CArchive` extrahieren ( **>>**) Operator überladen, für eine [CObject](../../mfc/reference/cobject-class.md) Zeiger. `ReadObject`, wiederum ruft die `Serialize` Funktion der archivierten-Klasse.

Wenn Sie einen Wert ungleich NULL angeben *pClass* -Parameter, der vom abgerufen wird die [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) -Makro, und klicken Sie dann auf die Funktion überprüft die Laufzeit-Klasse des archivierten-Objekts. Dies setzt voraus, dass Sie die IMPLEMENT_SERIAL-Makro in der Implementierung der Klasse verwendet haben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CArchive::WriteObject](#writeobject).

##  <a name="readstring"></a>  CArchive::ReadString

Rufen Sie diese Memberfunktion zum Lesen von Textdaten in einen Puffer aus der Datei zugeordneten der `CArchive` Objekt.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>Parameter

*rString*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die resultierende Zeichenfolge nach dem Lesen aus der Datei, die dem CArchive-Objekt zugeordnet ist.

*lpsz*<br/>
Gibt einen Zeiger zu einem Benutzer bereitgestellten Puffer, der eine Null-terminierte Zeichenfolge empfangen wird.

*nMax*<br/>
Gibt die maximale Anzahl der zu lesenden Zeichen. Muss eine kleiner als die Größe der *Lpsz* Puffer.

### <a name="return-value"></a>Rückgabewert

In der Version, die "bool", "true" bei Erfolg zurückgibt; "False" andernfalls.

In der Version, die zurückgibt ein `LPTSTR`, ein Zeiger auf den Puffer, die die Textdaten enthält. NULL, wenn das Ende der Datei erreicht wurde.

### <a name="remarks"></a>Hinweise

In der Version von der Memberfunktion mit dem *nmax* Parameter, der Puffer enthält sich auf ein Limit von *nmax* - 1 Zeichen. Lesen, wird durch ein Carriage Return-Zeilenvorschub-Paar beendet. Nachfolgende Zeilenumbruchzeichen werden immer entfernt. Ein Null-Zeichen ('\0') wird in beiden Fällen angefügt.

[CArchive:: Read](#read) steht auch für Textmodus-Eingabe, aber es wird ein Carriage Return-Zeilenvorschub-Paar nicht beendet.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CArchive::WriteString](#writestring).

##  <a name="serializeclass"></a>  CArchive::SerializeClass

Rufen Sie diese Memberfunktion auf, wenn Sie möchten, speichern und laden die Versionsinformationen für eine Basisklasse.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parameter

*pClassRef*<br/>
Ein Zeiger auf eine Laufzeitklasse-Objekt, für die Basisklasse.

### <a name="remarks"></a>Hinweise

`SerializeClass` liest oder schreibt Sie den Verweis auf eine Klasse, um die `CArchive` -Objekt, abhängig von der Richtung von der `CArchive`. Verwendung `SerializeClass` anstelle von [ReadClass](#readclass) und [WriteClass](#writeclass) als einfache Möglichkeit zum Serialisieren von Objekten der Basisklasse; `SerializeClass` erfordert weniger Code und weniger Parameter.

Wie `ReadClass`, `SerializeClass` stellt sicher, dass die archivierten Klasseninformationen kompatibel mit der Common Language Runtime-Klasse ist. Wenn er nicht kompatibel ist, ist `SerializeClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `SerializeClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Verwenden der [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) Makro zum Abrufen des Werts für die *pRuntimeClass* Parameter. Die Basisklasse muss hätte die [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makro.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>  CArchive::SetLoadParams

Rufen Sie `SetLoadParams` Wenn Sie eine große Anzahl von lesen spaltendateneinträge `CObject`-abgeleiteten Objekte aus einem Archiv.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Parameter

*nGrowBy*<br/>
Die minimale Anzahl der Element-Slots zugewiesen werden, wenn eine Vergrößerung erforderlich ist.

### <a name="remarks"></a>Hinweise

`CArchive` verwendet ein Array von Load zum Auflösen von Verweisen auf Objekte im Archiv gespeichert. `SetLoadParams` können Sie die Größe festlegen, die das Load-Array wächst.

Sie müssen nicht aufrufen, `SetLoadParams` nach dem ein Objekt geladen wird, oder nach [MapObject](#mapobject) oder [ReadObject](#readobject) aufgerufen wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema

Mit dieser Memberfunktion können Sie das in das Archivobjekt, das gespeicherte Objekt Schemaset *nSchema*.

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Parameter

*nSchema*<br/>
Gibt die Schemanamen des Objekts an.

### <a name="remarks"></a>Hinweise

Beim nächsten Aufruf von [GetObjectSchema](#getobjectschema) ergibt den Wert, der in gespeicherten *nSchema*.

Verwendung `SetObjectSchema` für die erweiterten versionsverwaltung, z. B. Wenn Sie möchten erzwingen, dass eine bestimmte Version im gelesen wird eine `Serialize` Funktion einer abgeleiteten Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>  CArchive::SetStoreParams

Verwendung `SetStoreParams` beim Speichern einer großen Anzahl von `CObject`-abgeleiteten Objekte in ein Archiv.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Parameter

*nHashSize*<br/>
Die Größe der Hashtabelle für Schnittstellenzeiger zugeordnet. Sollte es sich um eine Zahl eine Primzahl sein.

*nBlockSize*<br/>
Gibt die Granularität der speicherbelegung für die Parameter zu erweitern. Sollte eine Potenz von 2 für die beste Leistung.

### <a name="remarks"></a>Hinweise

`SetStoreParams` ermöglicht Ihnen die Hashtabellengröße und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.

Sie müssen nicht aufrufen, `SetStoreParams` nach dem alle Objekte gespeichert werden, oder nach [MapObject](#mapobject) oder [WriteObject](#writeobject) aufgerufen wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>  CArchive::Write

Schreibt eine angegebene Anzahl von Bytes in das Archiv.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Zeiger zu einem Benutzer bereitgestellten Puffer mit den Daten in das Archiv geschrieben werden sollen.

*nMax*<br/>
Eine ganze Zahl, die angibt, die Anzahl der Bytes in das Archiv geschrieben werden sollen.

### <a name="remarks"></a>Hinweise

Das Archiv wird die Bytes nicht formatiert.

Können Sie die `Write` Memberfunktion innerhalb Ihrer `Serialize` Funktion schreiben, normale Strukturen, die in den Objekten enthalten sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>  CArchive::WriteClass

Verwendung `WriteClass` zum Speichern der Version "und"-Klasse Informationen von einer Basisklasse während der Serialisierung der abgeleiteten Klasse.

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parameter

*pClassRef*<br/>
Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die die angeforderten Klassenreferenz entspricht.

### <a name="remarks"></a>Hinweise

`WriteClass` Schreibt einen Verweis auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) für die Basisklasse, die `CArchive`. Verwendung [CArchive::ReadClass](#readclass) um den Verweis abzurufen.

`WriteClass` überprüft, ob die archivierten Klasseninformationen kompatibel mit der Common Language Runtime-Klasse. Wenn er nicht kompatibel ist, ist `WriteClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Die Common Language Runtime-Klasse verwenden muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `WriteClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Sie können [SerializeClass](#serializeclass) anstelle von `WriteClass`, lesen und Schreiben des Klassenverweises behandelt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>  CArchive::WriteObject

Speichert die angegebenen `CObject` in das Archiv.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*pOb*<br/>
Ein konstanter Zeiger auf das Objekt gespeichert wird.

### <a name="remarks"></a>Hinweise

Diese Funktion wird normalerweise aufgerufen, indem die `CArchive` einfügen ( **<<**) Operator überladen für `CObject`. `WriteObject`, wiederum ruft die `Serialize` Funktion der archivierten-Klasse.

Sie müssen das IMPLEMENT_SERIAL-Makro verwenden, um Archivierung zu aktivieren. `WriteObject` Schreibt den Namen der ASCII-Klasse in das Archiv. Dieser Klassenname wird später während des Ladevorgangs überprüft. Ein spezieller Codierungsschema verhindert, dass unnötige Verdoppelung des Klassennamens für mehrere Objekte der Klasse. Dieses Schema wird auch verhindert, dass redundanten Speicher von Objekten, die Ziele der mehrere Zeiger sind.

Die genaue Objekt encoding-Methode (einschließlich das Vorhandensein von Namen der ASCII-Klasse) ist ein Implementierungsdetail und kann in zukünftigen Versionen der Bibliothek ändern.

> [!NOTE]
>  Beenden Sie erstellen, löschen und aktualisieren alle Ihre Objekte aus, bevor Sie beginnen, sie zu archivieren. Ihr Archiv ist beschädigt werden, wenn Sie die Archivierung mit einer objektänderung kombinieren.

### <a name="example"></a>Beispiel

Eine Definition der Klasse `CAge`, siehe das Beispiel für [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>  CArchive::WriteString

Verwenden Sie diese Memberfunktion zum Schreiben von Daten aus einem Puffer an die zugeordnete Datei die `CArchive` Objekt.

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Gibt einen Zeiger auf einen Puffer, die eine Null-terminierte Zeichenfolge enthält.

### <a name="remarks"></a>Hinweise

Das abschließende Nullzeichen ('\0') wird nicht in die Datei geschrieben; auch wird eine neue Zeile automatisch geschrieben.

`WriteString` löst eine Ausnahme als Reaktion auf verschiedene Bedingungen, einschließlich der Datenträger voll.

`Write` ist ebenfalls verfügbar, aber statt auf ein Null-Zeichen beendet, die angeforderte Anzahl von Bytes in die Datei geschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[CSocket-Klasse](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
