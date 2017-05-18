---
title: CFileException Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CFile class, exceptions of
- exceptions, file type
- CFileException class
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9064ae66f0dcd0e9f0dce0eedd8e38353f9da06
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cfileexception-class"></a>CFileException-Klasse
Stellt eine dateibezogene Ausnahmebedingung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|Erstellt ein `CFileException`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|Gibt dazu führen, dass Code, der eine Laufzeit-Fehlernummer entspricht.|  
|[CFileException::GetErrorMessage](#geterrormessage)|Ruft die Meldung mit einer Beschreibung der Ausnahme ab.|  
|[CFileException::OsErrorToException](#oserrortoexception)|Gibt einen Ursachencode, der ein Betriebssystem-Fehlercode entspricht.|  
|[CFileException::ThrowErrno](#throwerrno)|Löst die Ausnahme eine Datei basierend auf einer Common Language Runtime-Fehlernummer.|  
|[CFileException::ThrowOsError](#throwoserror)|Wird eine Datei ausgelöst, die basierend auf einem Betriebssystem-Fehlernummer.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileException::m_cause](#m_cause)|Enthält die portablen Code, der die Ursache der Ausnahme entspricht.|  
|[CFileException::m_lOsError](#m_loserror)|Enthält die zugehörigen Betriebssystem-Fehlernummer.|  
|[CFileException::m_strFileName](#m_strfilename)|Enthält den Namen der Datei für diese Ausnahme.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CFileException` Klasse enthält öffentliche Datenmember, die der portable Ursache und den Betriebssystem-System-spezifischen Fehler enthalten. Die Klasse bietet auch statische Memberfunktionen zum Auslösen von Ausnahmen der Datei und zum Zurückgeben des Codes der Ursache für Betriebssystem-Fehler und C-Laufzeitfehler.  
  
 `CFileException`Objekte werden erstellt und im ausgelöst `CFile` Memberfunktionen und Memberfunktionen von abgeleiteten Klassen. Sie können diese Objekte innerhalb des Bereichs zugreifen ein **CATCH** Ausdruck. Verwenden Sie für Portabilität nur Ursachencode, um den Grund für eine Ausnahme zu erhalten. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cfileexception"></a>CFileException::CFileException  
 Erstellt ein `CFileException` -Objekt, das die Ursache und die Betriebssystem-Code in das Objekt speichert.  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Ein enumerierter Typ-Variable, die den Grund für die Ausnahme angibt. Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Werte.  
  
 `lOsError`  
 Ein System-betriebssystemspezifische Ursache der Ausnahme, falls verfügbar. Die `lOsError` Parameter bietet mehr Informationen als `cause` ist.  
  
 `lpszArchiveName`  
 Verweist auf eine Zeichenfolge mit dem Namen der `CFile` Objekt, der die Ausnahme verursacht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Konstruktor nicht direkt, aber stattdessen rufen Sie die globale Funktion [AfxThrowFileException](exception-processing.md#afxthrowfileexception).  
  
> [!NOTE]
>  Die Variable `lOsError` gilt nur für `CFile` und `CStdioFile` Objekte. Die `CMemFile` -Klasse behandelt keine dieser Fehlercode.  
  
##  <a name="errnotoexception"></a>CFileException::ErrnoToException  
 Konvertiert einen angegebenen Laufzeitbibliothek Fehlerwert in einem `CFileException` Fehler-Enumerationswert.  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrno`  
 Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Enumerationswert, der eine bestimmte Laufzeitbibliothek Fehlerwert entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CFileException::m_cause](#m_cause) eine Liste der möglichen Enumerationswerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#26;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="geterrormessage"></a>CFileException::GetErrorMessage  
 Ruft Text zur Beschreibung der Ausnahme ab.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `lpszError`  
 Ein Zeiger auf einen Puffer, der eine Fehlermeldung erhalten.  
  
 [in] `nMaxError`  
 Die maximale Anzahl von Zeichen, die der angegebene Puffer aufnehmen kann. Dies schließt das abschließende Nullzeichen.  
  
 [in, out] `pnHelpContext`  
 Zeiger auf eine Ganzzahl ohne Vorzeichen, die die Hilfe-Kontext-ID empfängt. Wenn `NULL`, wird keine ID zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der angegebene Puffer zu klein ist, wird die Fehlermeldung abgeschnitten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `CFileException::GetErrorMessage`.  
  
 [!code-cpp[NVC_MFCExceptions&#22;](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>CFileException::m_cause  
 Enthält Werte, die von einem `CFileException`-Enumerationstyp definiert wurden.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Datenmember ist eine öffentliche Variable des Typs `int`. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:  
  
- `CFileException::none`0: kein Fehler aufgetreten ist.  
  
- `CFileException::genericException`1: ein nicht spezifizierter Fehler aufgetreten ist.  
  
- `CFileException::fileNotFound`2: die Datei konnte nicht gefunden werden.  
  
- `CFileException::badPath`3: alle oder einen Teil des Pfads ist ungültig.  
  
- `CFileException::tooManyOpenFiles`4: die zulässige Anzahl von geöffneten Dateien wurde überschritten.  
  
- `CFileException::accessDenied`5: die Datei konnte nicht zugegriffen werden.  
  
- `CFileException::invalidFile`6: Es wurde versucht, ein ungültiges Dateihandle verwenden.  
  
- `CFileException::removeCurrentDir`7: das aktuelle Arbeitsverzeichnis kann nicht entfernt werden.  
  
- `CFileException::directoryFull`8: Es sind keine weiteren Verzeichniseinträge.  
  
- `CFileException::badSeek`9: Fehler bei der Versuch, den Dateizeiger festzulegen.  
  
- `CFileException::hardIO`10: Es wurde ein Hardwarefehler.  
  
- `CFileException::sharingViolation`11: FREIGABE. EXE-Datei wurde nicht geladen, oder ein freigegebener Bereich wurde gesperrt.  
  
- `CFileException::lockViolation`12: Es wurde versucht, einen Bereich zu sperren, die bereits gesperrt wurde.  
  
- `CFileException::diskFull`14: der Datenträger ist voll.  
  
- `CFileException::endOfFile`15: das Ende der Datei erreicht wurde.  
  
    > [!NOTE]
    >  Diese `CFileException`-Ursachenenumeratoren unterscheiden sich von den `CArchiveException`-Ursachenenumeratoren.  
  
    > [!NOTE]
    > `CArchiveException::generic` ist veraltet. Verwenden Sie stattdessen `genericException`. Wenn `generic` in einer Anwendung verwendet und mit /clr erstellt wird, können die resultierenden Syntaxfehler nicht leicht entschlüsselt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#30;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>CFileException::m_lOsError  
 Enthält den Betriebssystem-Fehlercode für diese Ausnahme.  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter Ihrem Betriebssystem Technisches Handbuch eine Liste der Fehlercodes. Datenmember ist eine öffentliche Variable des Typs **lang**.  
  
##  <a name="m_strfilename"></a>CFileException::m_strFileName  
 Enthält den Namen der Datei für diese Ausnahmebedingung.  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>CFileException::OsErrorToException  
 Gibt einen Enumerator, der entspricht einem bestimmten `lOsError` Wert. Wenn der Fehlercode ist unbekannt, gibt die Funktion **CFileException::generic**.  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>Parameter  
 `lOsError`  
 Betriebssystem-System-spezifischen Fehlercode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Enumerationswert, der Wert eines bestimmten Betriebssystemfehler entspricht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#27;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>CFileException::ThrowErrno  
 Erstellt eine `CFileException` Objekt entspricht einer bestimmten `nErrno` und dann wird die Ausnahme ausgelöst.  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrno`  
 Ganzzahlige Fehlercode in der Laufzeit-Includedatei ERRNO definiert. H.  
  
 `lpszFileName`  
 Ein Zeiger auf die Zeichenfolge, die den Namen der Datei enthält, die die Ausnahme verursacht hat, sofern verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#28;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>CFileException::ThrowOsError  
 Löst ein `CFileException` entspricht einer bestimmten `lOsError` Wert. Wenn der Fehlercode ist unbekannt, löst die Funktion eine Ausnahme, die als **CFileException::generic**.  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lOsError`  
 Betriebssystem-System-spezifischen Fehlercode.  
  
 `lpszFileName`  
 Ein Zeiger auf die Zeichenfolge, die den Namen der Datei enthält, die die Ausnahme verursacht hat, sofern verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#29;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)




