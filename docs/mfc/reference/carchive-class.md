---
title: CArchive-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 3269aa447502b9581dd1238fbe972bef3a0ccde4
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="carchive-class"></a>CArchive-Klasse
Können Sie ein komplexes Netzwerk von Objekten in einer permanenten binären Form (normalerweise in Festplattenspeicher) zu speichern, die erhalten bleibt, nachdem diese Objekte gelöscht wurden.  
  
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
|[CArchive::GetObjectSchema](#getobjectschema)|Wird aufgerufen, aus der `Serialize` -Funktion können Sie die Version des Objekts zu ermitteln, die deserialisiert wird.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Bestimmt, ob der Puffer während einer Windows-Sockets geleert wurde Empfangsprozess.|  
|[CArchive::IsLoading](#isloading)|Bestimmt, ob das Archiv geladen wird.|  
|[CArchive::IsStoring](#isstoring)|Bestimmt, ob das Archiv gespeichert sind.|  
|[CArchive::MapObject](#mapobject)|Speichert Objekte in der Zuordnung, die nicht in die Datei serialisiert, aber für den untergeordneten Objekte zu verweisen.|  
|[CArchive:: Read](#read)|Liest die unformatierten Bytes.|  
|[CArchive::ReadClass](#readclass)|Liest ein Klassenverweis zuvor aufbewahrten `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Ruft ein Objekt `Serialize` Funktion für das Laden.|  
|[CArchive::ReadString](#readstring)|Liest eine einzelne Textzeile.|  
|[CArchive::SerializeClass](#serializeclass)|Liest oder schreibt die Klassenverweises an die `CArchive` Objekt abhängig von der Richtung des der `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|Legt fest, der das Array laden vergrößert wird. Muss aufgerufen werden, bevor ein Objekt geladen wird oder bevor `MapObject` oder `ReadObject` aufgerufen wird.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Legt fest, das Objektschema im Archivobjekt gespeichert wird.|  
|[CArchive::SetStoreParams](#setstoreparams)|Legt fest, die Hashtabellengröße und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.|  
|[CArchive::Write](#write)|Schreibt die unformatierten Bytes.|  
|[CArchive::WriteClass](#writeclass)|Schreibt einen Verweis auf die `CRuntimeClass` auf die `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Ruft ein Objekt `Serialize` Funktion zum Speichern von.|  
|[CArchive::WriteString](#writestring)|Schreibt eine einzelne Textzeile.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::operator&lt;&lt;](#operator_lt_lt)|Speichert Objekte und primitive Typen in das Archiv.|  
|[CArchive::operator&gt;&gt;](#operator_gt_gt)|Lädt Objekte und primitive Typen aus dem Archiv.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Hinweise  
 `CArchive`eine Basisklasse verfügt nicht über.  
  
 Später können Sie die Objekte aus dem permanenten Speicher laden rekonstruieren im Arbeitsspeicher. Dieser Vorgang Daten persistent, heißt "Serialisierung".  
  
 Sie können ein Archivobjekt als eine Art von binären Datenstrom vorstellen. Wie ein e/a-Stream ein Archiv bezieht sich auf eine Datei und ermöglicht die gepufferten schreiben und Lesen von Daten aus dem Speicher. Ein e/a-Datenstrom verarbeitet Sequenzen von ASCII-Zeichen, aber ein Archiv verarbeitet binary Object-Daten in einem Format effiziente, nicht redundante.  
  
 Müssen Sie erstellen eine [CFile](../../mfc/reference/cfile-class.md) Objekt vor der Erstellung einer `CArchive` Objekt. Darüber hinaus müssen Sie sicherstellen, dass das Archiv laden/Store Status mit den Öffnungsmodus der Datei kompatibel ist. Sie sind auf einem aktiven Archiv pro Datei beschränkt.  
  
 Bei der Erstellung einer `CArchive` -Objekts können Sie ein Objekt der Klasse anfügen `CFile` (oder einer abgeleiteten Klasse), die eine offene Datei darstellt. Sie geben außerdem, ob das Archiv zum Laden oder Speichern von verwendet wird. Ein `CArchive` Objekt verarbeiten kann, nicht nur primitive Typen, sondern auch Objekte von [CObject](../../mfc/reference/cobject-class.md)-abgeleitete Klassen, die für die Serialisierung vorgesehen. In der Regel eine serialisierbare Klasse verfügt über eine `Serialize` Memberfunktion und in der Regel verwendet die [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makros, wie beschrieben unter Klasse `CObject`.  
  
 Die überladenen Extrahierung ( **>>**) und dem Einfügen ( **<<**) Operatoren sind praktisch Archiv-Programmierungsschnittstellen, die sowohl primitiven Typen unterstützt und `CObject`-abgeleitete Klassen.  
  
 `CArchive`unterstützt auch die Programmierung mit der Windows Sockets in MFC-Klassen [CSocket](../../mfc/reference/csocket-class.md) und [CSocketFile](../../mfc/reference/csocketfile-class.md). Die [IsBufferEmpty](#isbufferempty) Memberfunktion unterstützt diese Verwendung.  
  
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
 Die **CArchive** Destruktor wird normalerweise rufen **schließen**, dem wegschreibt alle Daten, die nicht gespeichert wurde, an die zugeordnete `CFile` Objekt. Dies kann dazu führen, dass Ausnahmen.  
  
 Wenn diese Ausnahmen abfangen, ist es ratsam, verwenden Sie **Abort**, sodass destructing der `CArchive` Objekt keine weiteren Ausnahmen auslösen. Beim Verarbeiten von Ausnahmen, `CArchive::Abort` wird nicht auf Fehler eine Ausnahme ausgelöst, da im Gegensatz zu [CArchive::Close](#close), **Abort** Fehler ignoriert.  
  
 Bei Verwendung **neue** Zuweisen der `CArchive` Objekt auf dem Heap, und Sie sie löschen müssen, nach dem Schließen der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).  
  
##  <a name="carchive"></a>CArchive::CArchive  
 Erstellt ein `CArchive` -Objekt und gibt an, ob es zum Laden oder Speichern von Objekten verwendet werden soll.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf die `CFile` -Objekt, das die ultimate Quelle oder Ziel der persistenten Daten ist.  
  
 `nMode`  
 Ein Flag, das angibt, ob die Objekte aus geladen oder in das Archiv gespeichert werden. Die `nMode` Parameter muss einen der folgenden Werte aufweisen:  
  
- **CArchive::load** lädt Daten aus dem Archiv. Erfordert nur `CFile` read-Berechtigung.  
  
- **CArchive::store** speichert Daten in das Archiv. Erfordert `CFile` Schreibberechtigung.  
  
- **CArchive::bNoFlushOnDelete** verhindert, dass das Archiv automatisch aufrufen `Flush` bei der Archiv-Destruktor aufgerufen wird. Wenn Sie dieses Flag festlegen, sind Sie verantwortlich für explizit aufrufen **schließen** vor der Destruktor aufgerufen wird. Wenn Sie nicht der Fall ist, werden dadurch Daten beschädigt werden.  
  
 `nBufSize`  
 Eine ganze Zahl, die die Größe des internen Puffers in Bytes angibt. Beachten Sie, dass die Standardpuffergröße 4.096 Bytes ist. Wenn Sie große Objekte routinemäßig archivieren, werden Sie die Leistung verbessert, wenn Sie einen größeren Puffer verwenden, der ein Vielfaches der Größe der Puffer ist.  
  
 `lpBuf`  
 Ein optionaler Zeiger auf einen Benutzer bereitgestellte Puffer der Größe `nBufSize`. Wenn Sie diesen Parameter nicht angeben, wird das Archiv einen Puffer aus dem lokalen Heap reserviert und freigegeben, wenn das Objekt zerstört wird. Das Archiv gibt einen Benutzer bereitgestellte Puffer nicht frei.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Spezifikation nicht ändern, nachdem Sie das Archiv erstellt haben.  
  
 Sie können nicht `CFile` Vorgänge, den Status der Datei zu ändern, bis Sie das Archiv geschlossen haben. Solche Vorgänge, die Integrität des Archivs beschädigen. Sie können die Position des Dateizeigers zu einem beliebigen Zeitpunkt während der Serialisierung aufrufen, durch Abrufen von Objekt "Datei" aus dem Archiv der [GetFile](#getfile) Memberfunktion, und klicken Sie dann mit der [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) Funktion. Rufen Sie [CArchive::Flush](#flush) vor dem Abrufen der Position des Dateizeigers.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>CArchive::Close  
 Leert alle Daten in den Puffer verbleiben, schließt das Archiv und trennt das Archiv, aus der Datei.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Es sind keine weiteren Vorgänge für das Archiv zulässig. Nachdem Sie ein Archiv schließen, können Sie ein weiteres Archiv für dieselbe Datei erstellen, oder können Sie die Datei schließen.  
  
 Die Memberfunktion **schließen** wird sichergestellt, dass alle Daten aus dem Archiv in die Datei übertragen werden, und das Archiv nicht verfügbar vereinfacht. Um die Übertragung aus der Datei für das Speichermedium abzuschließen, müssen Sie zunächst mithilfe [CFile::Close](../../mfc/reference/cfile-class.md#close) und entfernen Sie dann die `CFile` Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteString](#writestring).  
  
##  <a name="flush"></a>CArchive::Flush  
 Erzwingt, dass alle verbleibenden im Archiv Puffer in die Datei geschrieben werden sollen.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `Flush` wird sichergestellt, dass alle Daten aus dem Archiv auf die Datei übertragen wird. Rufen Sie [CFile::Close](../../mfc/reference/cfile-class.md#close) um die Übertragung aus der Datei für das Speichermedium abzuschließen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>CArchive::GetFile  
 Ruft die `CFile` Objektzeiger für dieses Archiv.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein konstanter Zeiger auf die `CFile` Objekt verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen das Archiv, bevor Sie mit leeren `GetFile`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization Nr. 14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>CArchive::GetObjectSchema  
 Mit dieser Funktion wird von der `Serialize` -Funktion können Sie die Version des Objekts zu ermitteln, die aktuell deserialisiert wird.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Während der Deserialisierung wird die Version des Objekts, das gelesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Funktion ist nur gültig, wenn die `CArchive` Objekt geladen wird ( [CArchive::IsLoading](#isloading) ungleich NULL zurückgibt). Es muss der erste Aufruf in die `Serialize` -Funktion und die aufgerufene nur einmal. Der Rückgabewert ( **"uint"**)-1 gibt an, dass die Anzahl unbekannt ist.  
  
 Ein `CObject`-abgeleitete Klasse verwenden kann **VERSIONABLE_SCHEMA** kombiniert (bitweises mit `OR`) mit der Schemaversion selbst (in der `IMPLEMENT_SERIAL` Makro) zum Erstellen einer "einsetzbarer Object", also ein Objekt, dessen `Serialize` Memberfunktion kann mehrere Versionen lesen. Der Standard-Framework-Funktionen (ohne **VERSIONABLE_SCHEMA**) ist eine Ausnahme auslöst, wenn die Version nicht übereinstimmt, ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>CArchive::IsBufferEmpty  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das Archivobjekt internen Puffer leer ist.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv Puffer leer ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird bereitgestellt, um die Unterstützung der Programmierung mit der Windows Sockets in MFC-Klasse `CSocketFile`. Sie müssen nicht für ein Archiv zugeordneten verwendet eine `CFile` Objekt.  
  
 Der Grund für die Verwendung von `IsBufferEmpty` mit einem zugeordneten Archiv eine `CSocketFile` Objekt ist, dass das Archiv Puffer mehr als eine Nachricht oder Datensatz enthalten kann. Nachdem eine Nachricht empfangen wurde, verwenden Sie `IsBufferEmpty` eine Schleife zu steuern, die lange empfangen von Daten, bis der Puffer leer ist. Weitere Informationen finden Sie unter der [Receive](../../mfc/reference/casyncsocket-class.md#receive) Memberfunktion der Klasse `CAsyncSocket`, die zeigt, wie `IsBufferEmpty`.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isloading"></a>CArchive::IsLoading  
 Bestimmt, ob das Archiv Daten lädt.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv für das Laden von derzeit verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, indem die `Serialize` Funktionen der archivierten Klassen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization Nr. 16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>CArchive::IsStoring  
 Bestimmt, ob das Archiv Daten gespeichert werden.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Archiv für das Speichern zurzeit verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, indem die `Serialize` Funktionen der archivierten Klassen.  
  
 Wenn die `IsStoring` Status eines Archivs ist ungleich NULL ist, und klicken Sie dann die `IsLoading` Status gleich 0 ist, und umgekehrt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>CArchive::MapObject  
 Rufen Sie diese Memberfunktion zum Platzieren von Objekten in der Zuordnung, die in die Datei wirklich nicht serialisiert werden, aber für den untergeordneten Objekte zu verweisen.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein konstanter Zeiger auf das Objekt gespeichert wird.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise können Sie ein Dokument nicht serialisieren, aber würden Sie die Elemente, die Teil des Dokuments sind serialisieren. Durch Aufrufen von `MapObject`, Sie können diese Elemente oder untergeordneten Objekte, um auf das Dokument zu verweisen. Darüber hinaus serialisierten Unterelemente serialisieren können ihre `m_pDocument` rückzeiger.  
  
 Sie erreichen `MapObject` Wenn Sie zum Speichern und Laden Sie aus der `CArchive` Objekt. `MapObject`Fügt das angegebene Objekt auf die internen Datenstrukturen, die von verwaltet die `CArchive` Objekt während der Serialisierung und Deserialisierung, jedoch im Gegensatz zu [ReadObject](#readobject) und [WriteObject](#writeobject)**,** wird nicht aufgerufen für das Objekt zu serialisieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization Nr. 18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization Nr. 19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization Nr. 20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization #21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>CArchive::m_pDocument  
 Legen Sie auf **NULL** standardmäßig ist dieser Zeiger auf eine **CDocument** können Wert festgelegt werden den Benutzer die `CArchive` Instanz nutzen will.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine allgemeine Verwendung des this-Zeigers werden zusätzliche Informationen zu den Serialisierungsprozess für alle Objekte, die serialisierte zu vermitteln. Dies wird erreicht, indem Sie den Zeiger mit dem Dokument initialisieren (eine **CDocument**-abgeleitete Klasse), werden serialisiert, so, dass Objekte innerhalb des Dokuments, das Dokument ggf. zugreifen können. This-Zeiger wird auch verwendet, indem Sie `COleClientItem` Objekte während der Serialisierung.  
  
 Das Framework legt `m_pDocument` auf das Dokument serialisiert werden, wenn ein Benutzer eine Datei ausgibt öffnen oder speichern (Befehl). Wenn Sie eine Object Linking and Embedding (OLE) Containerdokument Gründen als Datei öffnen oder Speichern Serialisieren, müssen Sie explizit festlegen `m_pDocument`. Beispielsweise würden Sie dies tun, bei der Serialisierung ein Containerdokument in die Zwischenablage.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>CArchive::operator&lt;&lt;  
 Speichert die angegebene Objekt oder ein primitiver Typ, in das Archiv.  
  
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
 Die letzten beiden Versionen, die oben genannten sind speziell für das Speichern von 64-Bit-Ganzzahlen.  
  
 Bei Verwendung der `IMPLEMENT_SERIAL` Makro in Ihrer klassenimplementierung, und klicken Sie dann auf den Operator zum Einfügen für überladen `CObject` Ruft die geschützte **WriteObject**. Diese Funktion wiederum die `Serialize` -Funktion der Klasse.  
  
 Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) einfügen-Operator ()<) supports diagnostic dumping and storing to an archive. supports="" diagnostic="" dumping="" and="" storing="" to="" an=""></) supports diagnostic dumping and storing to an archive.>  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Operator zum Einfügen < with="" the=""> `int` und `long` Typen.  
  
 [!code-cpp[NVC_MFCSerialization #31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel 2 veranschaulicht die Verwendung von der `CArchive` Operator zum Einfügen < with="" the=""> `CStringT` Typ.  
  
 [!code-cpp[NVC_MFCSerialization #32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>CArchive::operator&gt;&gt;  
 Lädt die angegebenen primitiven Typs aus dem Archiv.  
  
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
 Die letzten beiden Versionen, die oben genannten sind speziell für das Laden von 64-Bit-Ganzzahlen.  
  
 Bei Verwendung der `IMPLEMENT_SERIAL` Makro in Ihrer klassenimplementierung, und klicken Sie dann auf die Extraktionsoperatoren für überladen `CObject` rufen Sie die geschützte **ReadObject** -Funktion (mit einem Zeiger ungleich Run-Time-Klasse). Diese Funktion wiederum die `Serialize` -Funktion der Klasse.  
  
 Die [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) Extraktionsoperator (>) unterstützt das Laden aus einem Archiv.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Extraktionsoperator >> mit der `int` Typ.  
  
 [!code-cpp[NVC_MFCSerialization #33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung von der `CArchive` Einfügung und Extraktion Operatoren \< und >> mit der `CStringT` Typ.  
  
 [!code-cpp[NVC_MFCSerialization #34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>CArchive:: Read  
 Liest eine angegebene Anzahl von Bytes aus dem Archiv.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf einen Benutzer bereitgestellte Puffer, der zum Empfangen der Daten aus dem Archiv gelesen wird.  
  
 `nMax`  
 Eine Ganzzahl ohne Vorzeichen, die die Anzahl von Bytes angibt, aus dem Archiv gelesen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl ohne Vorzeichen, die die Anzahl der tatsächlich gelesenen Bytes enthält. Wenn der Rückgabewert kleiner als die angeforderte Anzahl ist, wurde das Dateiende erreicht. Auf der End-of-File-Bedingung wird keine Ausnahme ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Das Archiv kann nicht mit der Bytes interpretieren.  
  
 Können Sie die **lesen** Memberfunktion innerhalb Ihrer `Serialize` Funktion zum Lesen von normaler Strukturen, die in den Objekten enthalten sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>CArchive::ReadClass  
 Rufen Sie diese Memberfunktion, um einen Verweis auf eine Klasse, die zuvor aufbewahrten lesen [WriteClass](#writeclass).  
  
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
 Ein Zeiger auf ein Schema der Klasse zur Laufzeit zuvor gespeichert.  
  
 `pObTag`  
 Eine Zahl, die auf eine eindeutige Objekttag verweist. Wird intern verwendet, durch die Implementierung von [ReadObject](#readobject). Für die Erweiterte Programmierung verfügbar gemacht; `pObTag` normalerweise muss **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pClassRefRequested` nicht **NULL**, `ReadClass` überprüft, ob die archivierten Informationen mit Ihrer Laufzeitklasse kompatibel ist. Wenn er nicht kompatibel ist, ist `ReadClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden, muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `ReadClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Wenn `pSchema` ist **NULL**, das Schema der gespeicherten Klasse abgerufen werden kann, durch Aufrufen [CArchive::GetObjectSchema](#getobjectschema)ist, andernfalls **\*** `pSchema` enthält das Schema der Klasse zur Laufzeit, die zuvor gespeichert wurde.  
  
 Sie können [SerializeClass](#serializeclass) anstelle von `ReadClass`, lesen und Schreiben des Klassenverweises behandelt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteClass](#writeclass).  
  
##  <a name="readobject"></a>CArchive::ReadObject  
 Liest Objektdaten aus dem Archiv und erstellt ein Objekt des entsprechenden Typs.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parameter  
 `pClass`  
 Ein konstanter Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die dem Objekt Sie davon ausgehen entspricht, lesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CObject](../../mfc/reference/cobject-class.md) Zeiger, der problemlos in den richtigen umgewandelt werden, muss abgeleitete Klasse mit [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, indem Sie die `CArchive` extrahieren ( **>>**) Operator überladen für eine [CObject](../../mfc/reference/cobject-class.md) Zeiger. **ReadObject**, wiederum die `Serialize` Funktion der archivierten-Klasse.  
  
 Wenn Sie einen Wert ungleich NULL angeben `pClass` Parameter, der vom abgerufen wird die [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) -Makro, und klicken Sie dann auf die Funktion überprüft die Laufzeitklasse des archivierten-Objekts. Dabei wird vorausgesetzt, Sie verwendet haben, die `IMPLEMENT_SERIAL` Makros in der Implementierung der Klasse.  
  
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
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die resultierende Zeichenfolge nach dem Einlesen aus der Datei, die dem CArchive-Objekt zugeordnet.  
  
 `lpsz`  
 Gibt einen Zeiger auf einen Benutzer bereitgestellte Puffer, der eine Null-terminierte Zeichenfolge empfangen.  
  
 `nMax`  
 Gibt die maximale Anzahl der zu lesenden Zeichen. Einmal kleiner als die Größe der *Lpsz* Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 In der Version, die zurückgibt **BOOL**, **"true"** bei Erfolg; **"False"** andernfalls.  
  
 In der Version, die gibt eine `LPTSTR`, ein Zeiger auf den Puffer, enthält die Textdaten; **NULL** Ende der Datei erreicht wurde.  
  
### <a name="remarks"></a>Hinweise  
 In der Version der Memberfunktion mit dem `nMax` Parameter, der Puffer von aufnehmen wird, auf ein Limit von `nMax` - 1 Zeichen. Lesen wird durch eine Carriage Return-Zeilenvorschub beendet. Nachfolgende neue Zeilenumbruchzeichen werden immer entfernt. In beiden Fällen wird ein Null-Zeichen ('\0') angefügt.  
  
 [CArchive:: Read](#read) ist auch verfügbar, für die Textmodus Eingabe, sondern es wird nicht auf eine Carriage Return-Zeilenvorschub beendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArchive::WriteString](#writestring).  
  
##  <a name="serializeclass"></a>CArchive::SerializeClass  
 Rufen Sie diese Memberfunktion auf, wenn Sie verwenden möchten, speichern und laden die Versionsinformationen für eine Basisklasse.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parameter  
 `pClassRef`  
 Ein Zeiger auf ein Objekt Run-Time-Klasse für die Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 `SerializeClass`liest oder schreibt Sie den Verweis auf eine Klasse, um die `CArchive` -Objekt, abhängig von der Richtung des der `CArchive`. Verwendung `SerializeClass` anstelle von [ReadClass](#readclass) und [WriteClass](#writeclass) als eine einfache Möglichkeit zum Serialisieren von Objekten der Basisklasse; `SerializeClass` erfordert weniger Code und die weniger Parameter.  
  
 Wie `ReadClass`, `SerializeClass` überprüft, ob die archivierten Informationen mit Ihrer Laufzeitklasse kompatibel ist. Wenn er nicht kompatibel ist, ist `SerializeClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden, muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `SerializeClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Verwenden der [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) Makro zum Abrufen des Werts für die `pRuntimeClass` Parameter. Die Basisklasse muss haben verwendet die [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makro.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>CArchive::SetLoadParams  
 Rufen Sie `SetLoadParams` Wenn Sie sind im Begriff, eine große Anzahl von lesen `CObject`-abgeleiteten Objekte aus einem Archiv.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Parameter  
 `nGrowBy`  
 Die minimale Anzahl der Element-Slots zugewiesen werden, wenn eine Größenzuwachs erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 `CArchive`verwendet ein Array laden Auflösung von Verweisen auf Objekte im Archiv gespeichert. `SetLoadParams`können Sie die Größe festlegen, die das Array laden vergrößert wird.  
  
 Sie müssen nicht aufrufen, `SetLoadParams` jedes Objekt geladen wird oder nach [MapObject](#mapobject) oder [ReadObject](#readobject) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>CArchive::SetObjectSchema  
 Rufen Sie diese Memberfunktion zum Festlegen des Objektschemas in das Archivobjekt, das gespeichert `nSchema`.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Parameter  
 `nSchema`  
 Gibt das Objekt Schema.  
  
### <a name="remarks"></a>Hinweise  
 Beim nächsten Aufruf von [GetObjectSchema](#getobjectschema) zurück in gespeicherten `nSchema`.  
  
 Verwendung `SetObjectSchema` für die erweiterten versionsverwaltung; z. B. Wenn Sie eine bestimmte Version einlesen werden erzwingen möchten eine `Serialize` Funktion einer abgeleiteten Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>CArchive::SetStoreParams  
 Verwendung `SetStoreParams` beim Speichern eine große Anzahl von `CObject`-abgeleiteten Objekte in ein Archiv.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Parameter  
 *nHashSize*  
 Die Größe der Hashtabelle für Schnittstellenzeiger zugeordnet ist. Eine Primzahl sollte sein.  
  
 `nBlockSize`  
 Gibt die Granularität der speicherbelegung zum Erweitern der Parameter an. Muss eine Potenz von 2 für optimale Leistung zu erzielen.  
  
### <a name="remarks"></a>Hinweise  
 `SetStoreParams`ermöglicht das Festlegen der Hashgröße für die Tabelle und die Blockgröße der Zuordnung verwendet, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.  
  
 Sie müssen nicht aufrufen, `SetStoreParams` Objekte gespeichert werden, oder nach [MapObject](#mapobject) oder [WriteObject](#writeobject) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>CArchive::Write  
 Schreibt eine angegebene Anzahl von Bytes in das Archiv.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Zeiger auf einen vom Benutzer bereitgestellte Puffer mit den Daten in das Archiv geschrieben werden sollen.  
  
 `nMax`  
 Eine ganze Zahl, die angibt, die Anzahl der Bytes in das Archiv geschrieben werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Archiv formatiert die Bytes nicht.  
  
 Können Sie die **schreiben** Memberfunktion innerhalb Ihrer `Serialize` -Funktion schreiben Sie die normalen Strukturen, die in den Objekten enthalten sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>CArchive::WriteClass  
 Verwendung `WriteClass` zum Speichern der Version und Klasse Informationen von einer Basisklasse während der Serialisierung der abgeleiteten Klasse.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parameter  
 `pClassRef`  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur, die die angeforderte Klassenreferenz entspricht.  
  
### <a name="remarks"></a>Hinweise  
 `WriteClass`Schreibt einen Verweis auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) für die Basisklasse, die `CArchive`. Verwendung [CArchive::ReadClass](#readclass) um den Verweis abzurufen.  
  
 `WriteClass`überprüft, ob die archivierten Klasseninformationen kompatibel mit der Common Language Runtime-Klasse. Wenn er nicht kompatibel ist, ist `WriteClass` löst eine [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Die Common Language Runtime-Klasse verwenden, muss [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)ist, andernfalls `WriteClass` löst eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Sie können [SerializeClass](#serializeclass) anstelle von `WriteClass`, lesen und Schreiben des Klassenverweises behandelt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>CArchive::WriteObject  
 Speichert die angegebenen `CObject` in das Archiv.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein konstanter Zeiger auf das Objekt gespeichert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird normalerweise aufgerufen, indem Sie die `CArchive` einfügen ( **<<**) Operator überladen für `CObject`. **WriteObject**, wiederum die `Serialize` Funktion der archivierten-Klasse.  
  
 Verwenden Sie die `IMPLEMENT_SERIAL` -Makro Archivierung zu aktivieren. **WriteObject** schreibt den ASCII-Klassennamen in das Archiv. Der Klassenname wird später während des Ladevorgangs überprüft. Eine spezielle Codierungsschema, das verhindert, dass unnötige Verdoppelungen des Klassennamens für mehrere Objekte der Klasse. Dieses Schema wird auch verhindert, dass redundanten Speicher von Objekten, die Ziel des mehr als einen Zeiger sind.  
  
 Die genaue Objekt encoding-Methode (dazu gehört das Vorhandensein des Klassennamens ASCII) ist ein Implementierungsdetail und kann in zukünftigen Versionen der Bibliothek ändern.  
  
> [!NOTE]
>  Beenden Sie erstellen, löschen und aktualisieren alle Objekte aus, bevor Sie diese archivieren. Ihr Archiv wird beschädigt werden, wenn Sie kombinieren Archivierung mit Objekt ändern.  
  
### <a name="example"></a>Beispiel  
 Eine Definition der Klasse `CAge`, finden Sie im Beispiel für [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization #29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>CArchive::WriteString  
 Verwenden Sie diese Memberfunktion zum Schreiben von Daten aus einem Puffer in der Datei zugeordneten der `CArchive` Objekt.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Gibt einen Zeiger auf einen Puffer mit Null endende Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Das abschließende Nullzeichen ('\0') wird nicht in die Datei geschrieben; noch wird eine neue Zeile automatisch geschrieben.  
  
 `WriteString`löst eine Ausnahme als Reaktion auf verschiedene Bedingungen, einschließlich der Datenträger voll.  
  
 **Schreiben von** ist auch verfügbar, aber statt auf ein Null-Zeichen beendet, schreibt er die angeforderte Anzahl von Bytes in der Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSerialization #30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)

