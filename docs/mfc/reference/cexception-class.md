---
title: CException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: 5942e636809e3758f34d209a3da80f0d903ab708
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450362"
---
# <a name="cexception-class"></a>CException-Klasse

Die Basisklasse für alle Ausnahmen in der Microsoft Foundation Class-Bibliothek.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CException::CException](#cexception)|Erstellt ein `CException`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CException::Delete](#delete)|Löscht eine `CException` Objekt.|
|[CException::ReportError](#reporterror)|Gibt eine Fehlermeldung in einem Meldungsfeld an den Benutzer an.|

## <a name="remarks"></a>Hinweise

Da `CException` ist eine abstrakte Basisklasse kann nicht erstellt werden `CException` Objekte direkt, müssen Sie die Objekte der abgeleiteten Klassen erstellen. Wenn Sie Ihre eigenen erstellen `CException`-Klasse zu formatieren, verwenden Sie eine der abgeleiteten Klassen, die als Modell oben aufgeführten. Stellen Sie sicher, dass die abgeleitete Klasse auch verwendet `IMPLEMENT_DYNAMIC`.

Die abgeleiteten Klassen und deren Beschreibungen sind unten aufgeführt:

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Eine Basisklasse für kritische Ressourcen MFC-Ausnahmen|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Ungültiges Argument Ausnahmebedingung|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Out-of-Memory-Ausnahme|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Anforderung für einen nicht unterstützten Vorgang|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Archiv dienstspezifischem-Ausnahme|
|[CFileException](../../mfc/reference/cfileexception-class.md)|-Spezifischen-Ausnahme|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows-Ressource wurde nicht gefunden oder keine erstellbaren Objekts.|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE-Ausnahme|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Datenbankausnahme (d. h. Ausnahmebedingungen im Zusammenhang mit für MFC-Datenbankklassen in Bezug auf Open Database Connectivity)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE-Verteilung (Automatisierung)-Ausnahme|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Ausnahme, die angibt, dass eine Ressource nicht gefunden werden konnte|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Ausnahme beim (d. h. Ausnahmebedingungen im Zusammenhang mit für DAO-Klassen) eines Objekts für den Datenzugriff|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Internet-Ausnahme (d. h. Ausnahmebedingungen im Zusammenhang mit Internet-Klassen).|

Diese Ausnahmen mit verwendet werden sollen die [AUSLÖSEN](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [versuchen](exception-processing.md#try), [catch](exception-processing.md#catch), [And_catch](exception-processing.md#and_catch), und [End_catch](exception-processing.md#end_catch) Makros. Weitere Informationen zu Ausnahmen finden Sie unter [Ausnahme verarbeiten](exception-processing.md), oder finden Sie im Artikel [Ausnahmebehandlung (MFC)](../exception-handling-in-mfc.md).

Um eine bestimmte Ausnahme abzufangen, verwenden Sie die entsprechende abgeleitete Klasse. Verwenden Sie zum Abfangen aller Arten von Ausnahmen, `CException`, und verwenden Sie dann [CObject:: IsKindOf](cobject-class.md#iskindof) Unterscheidung zwischen `CException`-abgeleiteten Klassen. Beachten Sie, dass `CObject::IsKindOf` funktioniert nur für Klassen deklariert werden, mit der [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) Makro verwenden, um die dynamische typenüberprüfung nutzen. Alle `CException`-abgeleiteten Klasse, die Sie erstellen sollten verwenden die `IMPLEMENT_DYNAMIC` Makro zu.

Sie können Details zu Ausnahmen, die dem Benutzer melden, durch den Aufruf [GetErrorMessage](cfileexception-class.md#geterrormessage) oder [ReportError](#reporterror)zwei Memberfunktionen mit einer der `CException`abgeleiteten Klassen.

Wenn eine Ausnahme, von einem der Makros abgefangen wird, die `CException` Objekt automatisch gelöscht; Löschen Sie ihn nicht selbst. Wenn eine Ausnahme, mithilfe abgefangen wird einer **catch** -Schlüsselwort, sie wird nicht automatisch gelöscht. Finden Sie im Artikel [Ausnahmebehandlung (MFC)](../exception-handling-in-mfc.md) für Weitere Informationen dazu, wann ein Objekt der batchverarbeitungsorchestrierung zu löschen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cexception"></a>  CException::CException

Diese Memberfunktion erstellt eine `CException` Objekt.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parameter

*b_AutoDelete*<br/>
Geben Sie "true", wenn der Speicher für die `CException` Objekt auf dem Heap zugewiesen wurde. Dies bewirkt, dass die `CException` zu beim löschendes Objekt die `Delete` Member-Funktion wird aufgerufen, um die Ausnahme zu löschen. Geben Sie "false", wenn die `CException` Objekt ist auf dem Stapel oder ein globales Objekt. In diesem Fall die `CException` Objekt werden nicht gelöscht, wenn die `Delete` Memberfunktion aufgerufen wird.

### <a name="remarks"></a>Hinweise

Sie müssen normalerweise nicht direkt aufrufen dieses Konstruktors. Eine Funktion, die eine Ausnahme auslöst, sollte eine Instanz der Erstellen einer `CException`-abgeleitete Klasse und rufen Sie ihren Konstruktor, oder es sollte gehen wie die MFC-Bibliothek auslösen, Funktionen, z. B. [AfxThrowFileException](exception-processing.md#afxthrowfileexception), um einen vordefinierten Typ auslösen. In dieser Dokumentation wird nur aus Gründen der Vollständigkeit bereitgestellt.

##  <a name="delete"></a>  CException::Delete

Diese Funktion überprüft, ob die `CException` Objekt auf dem Heap erstellt wurde, und wenn dies der Fall ist, ruft es die **löschen** Operator für das Objekt.

```
void Delete();
```

### <a name="remarks"></a>Hinweise

Beim Löschen einer `CException` -Objekts die `Delete` Memberfunktion versucht, die die Ausnahme zu löschen. Verwenden Sie nicht die **löschen** -Operators direkt, da die `CException` Objekt möglicherweise ein globales Objekt, oder auf dem Stapel erstellt wurden.

Sie können angeben, ob das Objekt gelöscht werden soll, wenn das Objekt erstellt wird. Weitere Informationen finden Sie unter [CException::CException](#cexception).

Sie müssen nur aufrufen `Delete` bei Verwendung von C++ **versuchen**- **catch** Mechanismus. Bei Verwendung von MFC-Makros **versuchen** und **CATCH**, und klicken Sie dann diese Makros automatisch mit dieser Funktion aufgerufen werden.

### <a name="example"></a>Beispiel

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

##  <a name="reporterror"></a>  CException::ReportError

Rufen Sie diese Memberfunktion auf Fehlertext Bericht in einem Meldungsfeld an den Benutzer.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Parameter

*nType*<br/>
Gibt den Stil des Meldungsfelds. Wenden Sie eine beliebige Kombination der [meldungsfeldstile](styles-used-by-mfc.md#message-box-styles) in das Feld. Wenn Sie diesen Parameter nicht angeben, ist die Standardeinstellung MB_OK an.

*nMessageID*<br/>
Gibt die Ressourcen-ID (Zeichenfolgeneintrag) einer Nachricht, um anzuzeigen, wenn das Ausnahmeobjekt keine Fehlermeldung an. Wenn der Wert 0 gibt an, die Meldung "keine Fehlermeldung verfügbar ist" wird angezeigt.

### <a name="return-value"></a>Rückgabewert

Ein `AfxMessageBox` Wert ist; andernfalls 0, wenn nicht genügend Arbeitsspeicher, um das Meldungsfeld angezeigt. Finden Sie unter [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) für die möglichen Rückgabewerte.

### <a name="example"></a>Beispiel

Hier ist ein Beispiel zur Verwendung von `CException::ReportError`. Ein weiteres Beispiel finden Sie im Beispiel für [CATCH](exception-processing.md#catch).

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](cobject-class.md)<br/>
[Hierarchiediagramm](../hierarchy-chart.md)<br/>
[Ausnahmeverarbeitung](exception-processing.md)<br/>
[Gewusst wie: Erstellen Sie eigene benutzerdefinierte Ausnahmeklassen](https://go.microsoft.com/fwlink/p/?linkid=128045)
