---
title: CDumpContext-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: a5b53ced4e20c920aab8e7ebcda3e3f6f8798ba5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164097"
---
# <a name="cdumpcontext-class"></a>CDumpContext-Klasse

Unterstützt die Darstellung gestreamter Diagnoseausgaben als Klartext.

## <a name="syntax"></a>Syntax

```
class CDumpContext
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDumpContext::CDumpContext](#cdumpcontext)|Erstellt ein `CDumpContext`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDumpContext::DumpAsHex](#dumpashex)|Gibt das angegebene Element im Hexadezimalformat an.|
|[CDumpContext::Flush](#flush)|Leert alle Daten in Dumps Kontextpuffer.|
|[CDumpContext::GetDepth](#getdepth)|Ruft eine ganze Zahl, die die Tiefe des Dumps ab.|
|[CDumpContext::HexDump](#hexdump)|Gibt die Byte in ein Array im Hexadezimalformat.|
|[CDumpContext::SetDepth](#setdepth)|Legt fest, die Tiefe des Speicherabbilds.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|Fügt der Dumpkontext Variablen und Objekte zu.|

## <a name="remarks"></a>Hinweise

`CDumpContext` eine Basisklasse keinen.

Sie können [AfxDump](diagnostic-services.md#afxdump), eine vorab deklarierte `CDumpContext` -Objekt, für die meisten Ihrer Sicherungen. Die `afxDump` Objekt nur in der Debugversion der Microsoft Foundation Class-Bibliothek verfügbar ist.

Mehrere des Arbeitsspeichers [Diagnosedienste](../../mfc/reference/diagnostic-services.md) verwenden `afxDump` für ihre Ausgabe.

Unter der Windows-Umgebung, die aus der vordefinierten `afxDump` Objekt, das konzeptionell identisch mit der `cerr` streamen, wird an den Debugger über die Windows-Funktion weitergeleitet `OutputDebugString`.

Die `CDumpContext` -Klasse verfügt über eine überladene Einfügung ( **<<**)-Operator für `CObject` Zeiger, die die Daten des Objekts sichert. Wenn Sie eine benutzerdefinierte dumpformat für ein abgeleitetes Objekt benötigen, überschreiben [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Die meisten Microsoft Foundation Classes implementieren eine überschriebene `Dump` Member-Funktion.

Nicht von abgeleiteten Klassen `CObject`, z. B. `CString`, `CTime`, und `CTimeSpan`, haben Sie ihre eigenen überladene `CDumpContext` Insertion-Operatoren als führen, die häufig verwendeten Strukturen wie z. B. `CFileStatus`, `CPoint`, und `CRect`.

Bei Verwendung der [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) oder [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makro in der Implementierung der Klasse, klicken Sie dann `CObject::Dump` gibt den Namen Ihrer `CObject`-abgeleitete Klasse. Andernfalls wird es ausgegeben `CObject`.

Die `CDumpContext` -Klasse ist verfügbar, mit dem Debug und Release-Versionen der Bibliothek, aber die `Dump` Memberfunktion ist nur in der Debugversion definiert. Verwendung **#ifdef _DEBUG**  /  `#endif` Anweisungen, die Ihre Diagnosecode, einschließlich Ihrer benutzerdefinierten Klammer `Dump` Memberfunktionen.

Bevor Sie Ihre eigenen erstellen `CDumpContext` Objekt ist, müssen Sie erstellen eine `CFile` Objekt, das als Ziel Dump dient.

Weitere Informationen zu `CDumpContext`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDumpContext`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext

Erstellt ein Objekt der Klasse `CDumpContext`.

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Parameter

*pFile*<br/>
Ein Zeiger auf die `CFile` -Objekt, das das Ziel der Sicherung ist.

### <a name="remarks"></a>Hinweise

Die `afxDump` Objekt wird automatisch erstellt.

Schreiben Sie nicht in den zugrunde liegenden `CFile` während sicherungskontexts aktiv; andernfalls ist, werden Sie mit der Dump beeinträchtigen. Unter der Windows-Umgebung wird die Ausgabe an den Debugger über die Windows-Funktion weitergeleitet `OutputDebugString`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex

Gibt den angegebenen Typ, der als hexadezimale Zahlen formatiert.

```
CDumpContext& DumpAsHex(BYTE b);
CDumpContext& DumpAsHex(DWORD dw);
CDumpContext& DumpAsHex(int n);
CDumpContext& DumpAsHex(LONG l);
CDumpContext& DumpAsHex(LONGLONG n);
CDumpContext& DumpAsHex(UINT u);
CDumpContext& DumpAsHex(ULONGLONG n);
CDumpContext& DumpAsHex(WORD w);
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein `CDumpContext`-Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um das Element des angegebenen Typs als hexadezimale Zahl zu sichern. Um ein Array zu speichern, rufen Sie [CDumpContext::HexDump](#hexdump).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

##  <a name="flush"></a>  CDumpContext::Flush

Erzwingt, dass alle Daten, die verbleibenden in Puffern, die in die Datei geschrieben werden an sicherungskontexts angefügt ist.

```
void Flush();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

##  <a name="getdepth"></a>  CDumpContext::GetDepth

Bestimmt, ob eine Tiefe oder flache Sicherung ausgeführt wird.

```
int GetDepth() const;
```

### <a name="return-value"></a>Rückgabewert

Die Tiefe des Speicherabbilds mit `SetDepth`.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [SetDepth](#setdepth).

##  <a name="hexdump"></a>  CDumpContext::HexDump

Gibt ein Array von Bytes, die als Hexadezimalzahlen formatiert.

```
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Parameter

*lpszLine*<br/>
Eine Zeichenfolge am Anfang einer neuen Zeile ausgegeben.

*pby*<br/>
Ein Zeiger auf einen Puffer, der die zu sichernden Bytes enthält.

*nBytes*<br/>
Die Anzahl der Bytes, um zu speichern.

*nWidth*<br/>
Maximale Anzahl von Bytes pro Zeile (nicht der Breite der Ausgabezeile) ausgegeben.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Sichern eines einzelnen, bestimmten Elementtyp als hexadezimale Zahl [CDumpContext::DumpAsHex](#dumpashex).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;

Gibt die angegebenen Daten in der Dumpkontext an.

```
CDumpContext& operator<<(const CObject* pOb);
CDumpContext& operator<<(const CObject& ob);
CDumpContext& operator<<(LPCTSTR lpsz);
CDumpContext& operator<<(const void* lp);
CDumpContext& operator<<(BYTE by);
CDumpContext& operator<<(WORD w);
CDumpContext& operator<<(DWORD dw);
CDumpContext& operator<<(int n);
CDumpContext& operator<<(double d);
CDumpContext& operator<<(float f);
CDumpContext& operator<<(LONG l);
CDumpContext& operator<<(UINT u);
CDumpContext& operator<<(LPCWSTR lpsz);
CDumpContext& operator<<(LPCSTR lpsz);
CDumpContext& operator<<(LONGLONG n);
CDumpContext& operator<<(ULONGLONG n);
CDumpContext& operator<<(HWND h);
CDumpContext& operator<<(HDC h);
CDumpContext& operator<<(HMENU h);
CDumpContext& operator<<(HACCEL h);
CDumpContext& operator<<(HFONT h);
```

### <a name="return-value"></a>Rückgabewert

Ein `CDumpContext` Verweis. Verwenden den Wert zurückgibt, können Sie mehrere einfügungen in einer einzelnen Zeile des Quellcodes schreiben.

### <a name="remarks"></a>Hinweise

Operator zum Einfügen des ist überladen, für die `CObject` Zeigern, die auch für die meisten primitiven Typen. Ein Zeiger auf Zeichen führt ein Speicherabbild des Zeichenfolgeninhalten; Ein Zeiger auf **"void"** in ein hexadezimales Speicherabbild der Adresse nur führt. Eine LONGLONG führt ein Speicherabbild des eine 64-Bit-Ganzzahl mit Vorzeichen; Ein-Wert ULONGLONG führt ein Speicherabbild des eine 64-Bit-Ganzzahl ohne Vorzeichen.

Wenn Sie über das IMPLEMENT_DYNAMIC oder IMPLEMENT_SERIAL-Makro in der Implementierung von Ihrer Klasse, und klicken Sie dann auf den Operator zum Einfügen, verwenden `CObject::Dump`, gibt den Namen Ihrer `CObject`-abgeleitete Klasse. Andernfalls wird es ausgegeben `CObject`. Wenn Sie außer Kraft setzen der `Dump` Funktion von der Klasse, Sie können eine aussagekräftigere Ausgabe der der Inhalt des Objekts statt ein hexadezimales Speicherabbild bereitstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

##  <a name="setdepth"></a>  CDumpContext::SetDepth

Legt die Tiefe für die Sicherung fest.

```
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Parameter

*nNewDepth*<br/>
Der neue Tiefenwert.

### <a name="remarks"></a>Hinweise

Wenn Sie einen primitiven Typ "oder" einfach Dump-Sicherungen werden `CObject` , die keine Zeiger auf andere Objekte enthält, und klicken Sie dann der Wert 0 ist ausreichend. Ein Wert größer als 0 ein deep Dump gibt an, wo alle Objekte gesichert rekursiv. Beispielsweise wird eine umfassende Sicherung eine Auflistung aller Elemente der Auflistung sichern. Sie können andere Tiefenwerte für bestimmte in Ihren abgeleiteten Klassen verwenden.

> [!NOTE]
>  Zirkelverweise werden nicht in Dumps für Tiefe erkannt und können zu Endlosschleifen führen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)
