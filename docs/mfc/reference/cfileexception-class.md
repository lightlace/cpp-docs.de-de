---
title: CFileException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df79b186aa515bba8d54083ad8a379aad36d2576
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954532"
---
# <a name="cfileexception-class"></a>CFileException-Klasse
Stellt eine dateibezogene Ausnahmebedingung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|Erstellt ein `CFileException`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|Gibt, dass Code, die einen Laufzeitfehler entspricht.|  
|[CFileException::GetErrorMessage](#geterrormessage)|Ruft die Nachricht, die eine Ausnahme beschreibt.|  
|[CFileException::OsErrorToException](#oserrortoexception)|Einen Ursachencode für ein Betriebssystem-Fehlercode zurückgegeben.|  
|[CFileException::ThrowErrno](#throwerrno)|Gibt eine Datei-Ausnahme, die basierend auf einer Common Language Runtime-Fehlernummer.|  
|[CFileException::ThrowOsError](#throwoserror)|Gibt eine Datei-Ausnahme, die basierend auf einem Betriebssystem-Fehlernummer.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::m_cause](#m_cause)|Enthält die portablen Code, der die Ursache der Ausnahme entspricht.|  
|[CFileException::m_lOsError](#m_loserror)|Enthält die verwandten Betriebssystem-Fehlernummer.|  
|[CFileException::m_strFileName](#m_strfilename)|Enthält den Namen der Datei für diese Ausnahme ausgelöst.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CFileException` Klasse enthält öffentliche Datenmember, die der Ursachencode portabel und die System-betriebssystemspezifische Fehlernummer enthalten. Die Klasse bietet auch statische Memberfunktionen für das Auslösen von Ausnahmen Datei und zum Zurückgeben von Ursache Codes für Betriebssystem-Fehler und C-Laufzeitfehler.  
  
 `CFileException` Objekte werden erstellt und ausgelöst `CFile` Memberfunktionen und in Memberfunktionen von abgeleiteten Klassen. Sie können diese Objekte innerhalb des Bereichs der zugreifen eine **CATCH** Ausdruck. Verwenden Sie für Portabilität nur Ursachencode, um den Grund für eine Ausnahme zu erhalten. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cfileexception"></a>  CFileException::CFileException  
 Erstellt eine `CFileException` -Objekt, das die Ursache und die Betriebssystem-Code in das Objekt speichert.  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Ursache*  
 Ein Aufzählungstyp-Variable, die die Ursache der Ausnahme angibt. Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Werte.  
  
 *lOsError*  
 Ein System-betriebssystemspezifische Ursache der Ausnahme, falls verfügbar. Die *lOsError* Parameter bietet mehr Informationen als *dazu führen, dass* verfügt.  
  
 *lpszArchiveName*  
 Verweist auf eine Zeichenfolge mit dem Namen des dem `CFile` Objekt, der die Ausnahme verursacht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowFileException](exception-processing.md#afxthrowfileexception).  
  
> [!NOTE]
>  Die Variable *lOsError* gilt nur für `CFile` und `CStdioFile` Objekte. Die `CMemFile` -Klasse behandelt keine mit diesem Fehlercode.  
  
##  <a name="errnotoexception"></a>  CFileException::ErrnoToException  
 Konvertiert einen angegebenen Laufzeit-Bibliothekscode Fehlerwert in einer `CFileException` Fehlerwert aufgelistet.  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>Parameter  
 *nErrno*  
 Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Enumerationswert, der eine bestimmte Laufzeitbibliothek Fehlerwert entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Enumerationswerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage  
 Ruft Text zur Beschreibung der Ausnahme ab.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] *LpszError*  
 Ein Zeiger auf einen Puffer, der eine Fehlermeldung empfängt.  
  
 [in] *nMaxError*  
 Die maximale Anzahl von Zeichen, die der angegebene Puffer aufnehmen kann. Dies schließt das abschließende Nullzeichen.  
  
 [in, out] *PnHelpContext*  
 Zeiger auf eine Ganzzahl ohne Vorzeichen, die die Hilfe-Kontext-ID empfängt. Wenn `NULL`, keine ID zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der angegebene Puffer zu klein ist, wird die Fehlermeldung abgeschnitten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `CFileException::GetErrorMessage`.  
  
 [!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>  CFileException::m_cause  
 Enthält Werte, die von einem `CFileException`-Enumerationstyp definiert wurden.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Hinweise  
 Datenmember ist eine öffentliche Variable des Typs **Int**. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:  
  
- `CFileException::none` 0: kein Fehler aufgetreten ist.  
  
- `CFileException::genericException` 1: ein nicht angegebener Fehler ist aufgetreten.  
  
- `CFileException::fileNotFound` 2: die Datei konnte nicht gefunden werden.  
  
- `CFileException::badPath` 3: alle oder einen Teil des Pfads ist ungültig.  
  
- `CFileException::tooManyOpenFiles` 4: die erlaubte Anzahl geöffneter Dateien wurde überschritten.  
  
- `CFileException::accessDenied` 5: die Datei konnte nicht zugegriffen werden.  
  
- `CFileException::invalidFile` 6: Es wurde versucht, ein ungültiges Dateihandle verwenden.  
  
- `CFileException::removeCurrentDir` 7: das aktuelle Arbeitsverzeichnis kann nicht entfernt werden.  
  
- `CFileException::directoryFull` 8: keine weiteren Verzeichniseinträge vorhanden sind.  
  
- `CFileException::badSeek` 9: Fehler bei der Versuch, den Dateizeiger zu setzen.  
  
- `CFileException::hardIO` 10: Es wurde ein Hardware-Fehler.  
  
- `CFileException::sharingViolation` 11: FREIGABE. EXE-Datei wurde nicht geladen, oder ein freigegebener Bereich wurde gesperrt.  
  
- `CFileException::lockViolation` 12: Es wurde versucht, einen Bereich zu sperren, die bereits gesperrt wurde.  
  
- `CFileException::diskFull` 14: der Datenträger voll ist.  
  
- `CFileException::endOfFile` 15: das Dateiende wurde erreicht.  
  
    > [!NOTE]
    >  Diese `CFileException`-Ursachenenumeratoren unterscheiden sich von den `CArchiveException`-Ursachenenumeratoren.  
  
    > [!NOTE]
    > `CArchiveException::generic` ist veraltet. Verwenden Sie stattdessen `genericException`. Wenn `generic` in einer Anwendung verwendet und mit /clr erstellt wird, können die resultierenden Syntaxfehler nicht leicht entschlüsselt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>  CFileException::m_lOsError  
 Enthält die Betriebssystem-Fehlercode für diese Ausnahme ausgelöst.  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter Ihrem Betriebssystem-Technisches Handbuch für eine Liste der Fehlercodes. Datenmember ist eine öffentliche Variable des Typs **lang**.  
  
##  <a name="m_strfilename"></a>  CFileException::m_strFileName  
 Enthält den Namen der Datei für diese Ausnahmebedingung.  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException  
 Gibt einen Enumerator, der entspricht einem bestimmten *lOsError* Wert. Wenn der Fehlercode unbekannt ist, und klicken Sie dann die Funktion gibt **CFileException::generic**.  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>Parameter  
 *lOsError*  
 Ein System-betriebssystemspezifische Fehlercode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Enumerationswert, der einen bestimmten Betriebssystemfehlers Wert entspricht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>  CFileException::ThrowErrno  
 Erstellt eine `CFileException` , Objekt entspricht einer bestimmten *nErrno* -Wert, dann wird die Ausnahme ausgelöst.  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nErrno*  
 Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.  
  
 *lpszFileName*  
 Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Datei, die der Ausnahme verursacht hat, falls verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>  CFileException::ThrowOsError  
 Löst ein `CFileException` entspricht einem bestimmten *lOsError* Wert. Wenn der Fehlercode ist unbekannt, löst die Funktion eine Ausnahme, die als **CFileException::generic**.  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lOsError*  
 Ein System-betriebssystemspezifische Fehlercode.  
  
 *lpszFileName*  
 Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Datei, die der Ausnahme verursacht hat, falls verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)



