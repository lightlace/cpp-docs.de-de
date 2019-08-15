---
title: Cpatht-Klasse
ms.date: 03/27/2019
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: ba1c831d772deef34449d17adc2c8e7a6f90eaef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496617"
---
# <a name="cpatht-class"></a>Cpatht-Klasse

Diese Klasse stellt einen Pfad dar.

> [!IMPORTANT]
> Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Parameter

*StringType*<br/>
Die ATL/MFC-Zeichen folgen Klasse, die für den Pfad verwendet werden soll (siehe [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|Ein konstanter Zeichen folgertyp.|
|[CPathT::PXSTR](#pxstr)|Ein Zeichen Folgentyp.|
|[Cpatht:: xchar](#xchar)|Ein Zeichentyp.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|Der Konstruktor für den Pfad.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|Rufen Sie diese Methode auf, um einen umgekehrten Schrägstrich am Ende einer Zeichenfolge hinzuzufügen, um die korrekte Syntax für einen Pfad zu erstellen.|
|[CPathT::AddExtension](#addextension)|Mit dieser Methode können Sie einem Pfad eine Dateierweiterung hinzufügen.|
|[Cpatht:: Append](#append)|Rufen Sie diese Methode auf, um eine Zeichenfolge an den aktuellen Pfad anzufügen.|
|[CPathT::BuildRoot](#buildroot)|Rufen Sie diese Methode auf, um einen Stammpfad aus einer angegebenen Laufwerk Nummer zu erstellen.|
|[Cpatht:: Canonicalize](#canonicalize)|Mit dieser Methode wird der Pfad in eine kanonische Form konvertiert.|
|[CPathT::Combine](#combine)|Diese Methode wird aufgerufen, um eine Zeichenfolge zu verketten, die einen Verzeichnisnamen und eine Zeichenfolge darstellt, die einen Dateipfadnamen in einem Pfad darstellt.|
|[CPathT::CommonPrefix](#commonprefix)|Ruft diese Methode auf, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix mit dem aktuellen Pfad hat.|
|[CPathT::CompactPath](#compactpath)|Mit dieser Methode können Sie einen Dateipfad für eine bestimmte Pixel Breite abschneiden, indem Sie Pfad Komponenten durch Ellipsen ersetzen.|
|[CPathT::CompactPathEx](#compactpathex)|Ruft diese Methode auf, um einen Dateipfad für eine bestimmte Anzahl von Zeichen abzuschneiden, indem Pfad Komponenten durch Ellipsen ersetzt werden.|
|[Cpatht:: fileexistiert](#fileexists)|Mit dieser Methode können Sie überprüfen, ob die Datei mit diesem Pfadnamen vorhanden ist.|
|[CPathT::FindExtension](#findextension)|Ruft diese Methode auf, um die Position der Dateierweiterung innerhalb des Pfads zu ermitteln.|
|[CPathT::FindFileName](#findfilename)|Ruft diese Methode auf, um die Position des Datei namens innerhalb des Pfads zu ermitteln.|
|[CPathT::GetDriveNumber](#getdrivenumber)|Mit dieser Methode können Sie den Pfad nach einem Laufwerksbuchstaben innerhalb des Bereichs von "a" bis "Z" Durchsuchen und die entsprechende Laufwerksnummer zurückgeben.|
|[CPathT::GetExtension](#getextension)|Mit dieser Methode können Sie die Dateierweiterung aus dem Pfad abrufen.|
|[CPathT::IsDirectory](#isdirectory)|Mit dieser Methode können Sie überprüfen, ob der Pfad ein gültiges Verzeichnis ist.|
|[CPathT::IsFileSpec](#isfilespec)|Mit dieser Methode können Sie einen Pfad nach beliebigen Pfad Begrenzungs Zeichen (z. b. ': ' oder '\\') durchsuchen. Wenn keine Pfad Trennzeichen vorhanden sind, wird der Pfad als dateispezifikations Pfad betrachtet.|
|[CPathT::IsPrefix](#isprefix)|Ruft diese Methode auf, um zu bestimmen, ob ein Pfad ein gültiges Präfix des von *pszprefix*weiter gegebenen Typs enthält.|
|[CPathT::IsRelative](#isrelative)|Ruft diese Methode auf, um zu bestimmen, ob der Pfad relativ ist.|
|[CPathT::IsRoot](#isroot)|Ruft diese Methode auf, um zu bestimmen, ob der Pfad ein Verzeichnis Stamm ist.|
|[CPathT::IsSameRoot](#issameroot)|Ruft diese Methode auf, um zu bestimmen, ob ein anderer Pfad über eine gemeinsame Stamm Komponente mit dem aktuellen Pfad verfügt.|
|[Cpatht:: IsUnc](#isunc)|Verwenden Sie diese Methode, um zu bestimmen, ob der Pfad ein gültiger UNC-Pfad (Universal Naming Convention) für einen Server und eine Freigabe ist.|
|[CPathT::IsUNCServer](#isuncserver)|Mit dieser Methode können Sie feststellen, ob es sich bei dem Pfad um einen gültigen UNC-Pfad (Universal Naming Convention) für einen Server handelt.|
|[CPathT::IsUNCServerShare](#isuncservershare)|Verwenden Sie diese Methode, um \\zu bestimmen, \ ob der Pfad ein gültiger UNC-Freigabe Pfad (Universal Naming Convention) ist ( *Server*\ *Freigabe*).|
|[CPathT::MakePretty](#makepretty)|Mit dieser Methode wird ein Pfad in alle Kleinbuchstaben konvertiert, um dem Pfad eine konsistente Darstellung zu übergeben.|
|[CPathT::MatchSpec](#matchspec)|Mit dieser Methode können Sie den Pfad nach einer Zeichenfolge suchen, die einen Platzhalter Übereinstimmungs Typen enthält.|
|[CPathT::QuoteSpaces](#quotespaces)|Mit dieser Methode können Sie den Pfad in Anführungszeichen einschließen, wenn er Leerzeichen enthält.|
|[CPathT::RelativePathTo](#relativepathto)|Rufen Sie diese Methode auf, um einen relativen Pfad von einer Datei oder einem Ordner zu einem anderen zu erstellen.|
|[CPathT::RemoveArgs](#removeargs)|Diese Methode wird aufgerufen, um alle Befehlszeilenargumente aus dem Pfad zu entfernen.|
|[CPathT::RemoveBackslash](#removebackslash)|Mit dieser Methode wird der nachfolgende umgekehrte Schrägstrich aus dem Pfad entfernt.|
|[CPathT::RemoveBlanks](#removeblanks)|Diese Methode wird aufgerufen, um alle führenden und nachfolgenden Leerzeichen aus dem Pfad zu entfernen.|
|[CPathT::RemoveExtension](#removeextension)|Mit dieser Methode können Sie die Dateierweiterung aus dem Pfad entfernen, sofern vorhanden.|
|[CPathT::RemoveFileSpec](#removefilespec)|Mit dieser Methode können Sie den nachfolgenden Dateinamen und den umgekehrten Schrägstrich aus dem Pfad entfernen, wenn Sie diesen haben.|
|[Cpatht:: renameextension](#renameextension)|Mit dieser Methode können Sie die Dateinamenerweiterung im Pfad durch eine neue Erweiterung ersetzen. Wenn der Dateiname keine Erweiterung enthält, wird die Erweiterung an das Ende der Zeichenfolge angefügt.|
|[CPathT::SkipRoot](#skiproot)|Mit dieser Methode können Sie einen Pfad analysieren, wobei der Laufwerksbuchstabe oder der UNC-Server/die Freigabe Pfad Teile ignoriert werden.|
|[CPathT::StripPath](#strippath)|Diese Methode wird aufgerufen, um den Pfadteil eines voll qualifizierten Pfads und Datei namens zu entfernen.|
|[CPathT::StripToRoot](#striptoroot)|Mit dieser Methode können Sie alle Teile des Pfades außer den Stamm Informationen entfernen.|
|[Cpatht:: unquotespaces](#unquotespaces)|Mit dieser Methode können Sie Anführungszeichen am Anfang und am Ende eines Pfades entfernen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Cpatht:: Operator const StringType &](#operator_const_stringtype_amp)|Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[Cpatht:: Operator cpatht::P cxstr](#operator_cpatht__pcxstr)|Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[Cpatht:: Operator StringType-&](#operator_stringtype_amp)|Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[CPathT::operator +=](#operator_add_eq)|Dieser Operator Fügt eine Zeichenfolge an den Pfad an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|Der Pfad.|

## <a name="remarks"></a>Hinweise

`CPath`, `CPathA`und `CPathW` sind Instanziierungen von `CPathT` , die wie folgt definiert werden:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Anforderungen

**Header:** atlpath. h

##  <a name="addbackslash"></a>Cpatht:: addbackschräg Strich

Rufen Sie diese Methode auf, um einen umgekehrten Schrägstrich am Ende einer Zeichenfolge hinzuzufügen, um die korrekte Syntax für einen Pfad zu erstellen. Wenn der Pfad bereits einen nachfolgenden umgekehrten Schrägstrich enthält, wird kein umgekehrter Schrägstrich hinzugefügt.

```
void AddBackslash();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathaddbackschräg Strich](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw).

##  <a name="addextension"></a>Cpatht:: AddExtension

Mit dieser Methode können Sie einem Pfad eine Dateierweiterung hinzufügen.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parameter

*pszExtension*<br/>
Die hinzu zufügende Dateierweiterung.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathaddextension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw).

##  <a name="append"></a>Cpatht:: Append

Rufen Sie diese Methode auf, um eine Zeichenfolge an den aktuellen Pfad anzufügen.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Parameter

*pszMore*<br/>
Die anzufügende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw).

##  <a name="buildroot"></a>Cpatht:: Buildroot

Rufen Sie diese Methode auf, um einen Stammpfad aus einer angegebenen Laufwerk Nummer zu erstellen.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Parameter

*iDrive*<br/>
Die Laufwerksnummer (0 ist a:, 1 ist B: usw.).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathbuildroot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw).

##  <a name="canonicalize"></a>Cpatht:: Canonicalize

Mit dieser Methode wird der Pfad in eine kanonische Form konvertiert.

```
void Canonicalize();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathcanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew).

##  <a name="combine"></a>Cpatht:: Combine

Diese Methode wird aufgerufen, um eine Zeichenfolge zu verketten, die einen Verzeichnisnamen und eine Zeichenfolge darstellt, die einen Dateipfadnamen in einem Pfad darstellt.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Parameter

*pszDir*<br/>
Der Verzeichnispfad.

*pszFile*<br/>
Der Dateipfad.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathcombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew).

##  <a name="commonprefix"></a>Cpatht:: commonprefix

Ruft diese Methode auf, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix mit dem aktuellen Pfad hat.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Parameter

*pszOther*<br/>
Der Pfad, der mit dem aktuellen verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das gemeinsame Präfix zurück.

### <a name="remarks"></a>Hinweise

Ein Präfix ist einer der folgenden Typen: "C:\\\\", ".", "..", ".. \\\\". Weitere Informationen finden Sie unter [pathcommonprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw).

##  <a name="compactpath"></a>Cpatht:: compactpath

Mit dieser Methode können Sie einen Dateipfad für eine bestimmte Pixel Breite abschneiden, indem Sie Pfad Komponenten durch Ellipsen ersetzen.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Parameter

*hDC*<br/>
Der Gerätekontext, der für Schriftart Metriken verwendet wird.

*nWidth*<br/>
Die Breite in Pixel, in die die Zeichenfolge eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathcompactpath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw).

##  <a name="compactpathex"></a>Cpatht:: compactpathex

Ruft diese Methode auf, um einen Dateipfad für eine bestimmte Anzahl von Zeichen abzuschneiden, indem Pfad Komponenten durch Ellipsen ersetzt werden.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parameter

*nmaxchars*<br/>
Die maximale Anzahl von Zeichen, die in der neuen Zeichenfolge enthalten sein sollen, einschließlich des abschließenden NULL-Zeichens.

*dwFlags*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathcompactpathex](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw).

##  <a name="cpatht"></a>Cpatht:: cpatht

Der Konstruktor.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
Der Zeiger auf eine Pfad Zeichenfolge.

*path*<br/>
Die Pfad Zeichenfolge.

##  <a name="fileexists"></a>Cpatht:: fileexistiert

Mit dieser Methode können Sie überprüfen, ob die Datei mit diesem Pfadnamen vorhanden ist.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Datei vorhanden ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathfilevorhanden](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw).

##  <a name="findextension"></a>Cpatht:: findextension

Ruft diese Methode auf, um die Position der Dateierweiterung innerhalb des Pfads zu ermitteln.

```
int FindExtension() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position des "." vor der Erweiterung zurück. Wenn keine Erweiterung gefunden wird, wird-1 zurückgegeben.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathfindextension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw).

##  <a name="findfilename"></a>Cpatht:: findfilename

Ruft diese Methode auf, um die Position des Datei namens innerhalb des Pfads zu ermitteln.

```
int FindFileName() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position des Datei namens zurück. Wenn kein Dateiname gefunden wird, wird-1 zurückgegeben.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathfindfilename](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew).

##  <a name="getdrivenumber"></a>Cpatht:: getdrivenumschlag

Mit dieser Methode können Sie den Pfad nach einem Laufwerksbuchstaben innerhalb des Bereichs von "a" bis "Z" Durchsuchen und die entsprechende Laufwerksnummer zurückgeben.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Laufwerksnummer als Ganzzahl zwischen 0 und 25 zurück (entspricht "A" bis "Z"), wenn der Pfad einen Laufwerk Buchstaben aufweist, andernfalls "-1".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathgetdrivenumschlag](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw).

##  <a name="getextension"></a>Cpatht:: GetExtension

Mit dieser Methode können Sie die Dateierweiterung aus dem Pfad abrufen.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Dateierweiterung zurück.

##  <a name="isdirectory"></a>Cpatht:: IsDirectory

Mit dieser Methode können Sie überprüfen, ob der Pfad ein gültiges Verzeichnis ist.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich 0 (null) zurück, wenn der Pfad ein Verzeichnis ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw).

##  <a name="isfilespec"></a>Cpatht:: isfilespec

Mit dieser Methode können Sie einen Pfad nach beliebigen Pfad Begrenzungs Zeichen (z. b. ': ' oder '\\') durchsuchen. Wenn keine Pfad Trennzeichen vorhanden sind, wird der Pfad als dateispezifikations Pfad betrachtet.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn keine Pfad Trennzeichen innerhalb des Pfads vorhanden sind, oder false, wenn Pfad Trennzeichen vorhanden sind.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisfilespec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw).

##  <a name="isprefix"></a>Cpatht:: iationfix

Ruft diese Methode auf, um zu bestimmen, ob ein Pfad ein gültiges Präfix des von *pszprefix*weiter gegebenen Typs enthält.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Parameter

*pszPrefix*<br/>
Das Präfix, nach dem gesucht werden soll. Ein Präfix ist einer der folgenden Typen: "C:\\\\", ".", "..", ".. \\\\".

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Pfad das Präfix enthält, andernfalls "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthistreufix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)".

##  <a name="isrelative"></a>Cpatht:: IsRelative

Ruft diese Methode auf, um zu bestimmen, ob der Pfad relativ ist.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Pfad relativ ist, oder "false", wenn es absolut ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisrelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew).

##  <a name="isroot"></a>Cpatht:: IsRoot

Ruft diese Methode auf, um zu bestimmen, ob der Pfad ein Verzeichnis Stamm ist.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Pfad ein root ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisroot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw).

##  <a name="issameroot"></a>Cpatht:: issameroot

Ruft diese Methode auf, um zu bestimmen, ob ein anderer Pfad über eine gemeinsame Stamm Komponente mit dem aktuellen Pfad verfügt.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Parameter

*pszOther*<br/>
Der andere Pfad.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn beide Zeichen folgen die gleiche Stamm Komponente aufweisen, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)".

##  <a name="isunc"></a>Cpatht:: IsUnc

Verwenden Sie diese Methode, um zu bestimmen, ob der Pfad ein gültiger UNC-Pfad (Universal Naming Convention) für einen Server und eine Freigabe ist.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Pfad ein gültiger UNC-Pfad ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw).

##  <a name="isuncserver"></a>Cpatht:: isuncserver

Mit dieser Methode können Sie feststellen, ob es sich bei dem Pfad um einen gültigen UNC-Pfad (Universal Naming Convention) für einen Server handelt.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Zeichenfolge ein gültiger UNC-Pfad für einen Server ist (kein Freigabe Name), andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisuncserver](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw).

##  <a name="isuncservershare"></a>Cpatht:: isuncservershare

Verwenden Sie diese Methode, um \\zu bestimmen, \ ob der Pfad ein gültiger UNC-Freigabe Pfad (Universal Naming Convention) ist ( *Server*\ *Freigabe*).

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn sich der Pfad im \\ \ Formular *Server*\ *Freigabe*befindet, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathisuncservershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).

##  <a name="m_strpath"></a>Cpatht:: m_strPath

Der Pfad.

```
StringType m_strPath;
```

### <a name="remarks"></a>Hinweise

`StringType`der Vorlagen Parameter für `CPathT`.

##  <a name="makepretty"></a>Cpatht:: makepretty

Mit dieser Methode wird ein Pfad in alle Kleinbuchstaben konvertiert, um dem Pfad eine konsistente Darstellung zu übergeben.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Pfad konvertiert wurde, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathmakepretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).

##  <a name="matchspec"></a>Cpatht:: matchspec

Mit dieser Methode können Sie den Pfad nach einer Zeichenfolge suchen, die einen Platzhalter Übereinstimmungs Typen enthält.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Parameter

*pszSpec*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge mit dem Dateityp, der durchsucht werden soll. Um beispielsweise zu testen, ob es sich bei der Datei im aktuellen Pfad um eine doc-Datei handelt, sollte *pszspec* auf "*. doc" festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Zeichenfolge übereinstimmt, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).

##  <a name="operator_add_eq"></a>Cpatht:: Operator + =

Dieser Operator Fügt eine Zeichenfolge an den Pfad an.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Parameter

*pszMore*<br/>
Die anzufügende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt den aktualisierten Pfad zurück.

##  <a name="operator_const_stringtype_amp"></a>Cpatht:: Operator const StringType&amp;

Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge zurück, die den aktuellen, von diesem-Objekt verwalteten Pfad darstellt.

##  <a name="operator_cpatht__pcxstr"></a>Cpatht:: Operator cpatht::P cxstr

Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge zurück, die den aktuellen, von diesem-Objekt verwalteten Pfad darstellt.

##  <a name="operator_stringtype_amp"></a>Cpatht:: Operator StringType&amp;

Mit diesem Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operator StringType&() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge zurück, die den aktuellen, von diesem-Objekt verwalteten Pfad darstellt.

##  <a name="pcxstr"></a>Cpatht::P cxstr

Ein konstanter Zeichen folgertyp.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Hinweise

`StringType`der Vorlagen Parameter für `CPathT`.

##  <a name="pxstr"></a>Cpatht::P xstr

Ein Zeichen Folgentyp.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Hinweise

`StringType`der Vorlagen Parameter für `CPathT`.

##  <a name="quotespaces"></a>Cpatht:: quotespaces

Mit dieser Methode können Sie den Pfad in Anführungszeichen einschließen, wenn er Leerzeichen enthält.

```
void QuoteSpaces();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathquotespaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).

##  <a name="relativepathto"></a>Cpatht:: RelativePathTo

Rufen Sie diese Methode auf, um einen relativen Pfad von einer Datei oder einem Ordner zu einem anderen zu erstellen.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Parameter

*pszFrom*<br/>
Der Anfang des relativen Pfads.

*dwAttrFrom*<br/>
Die Dateiattribute von *pszfrom*. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY enthält, wird davon ausgegangen, dass *pszfrom* ein Verzeichnis ist. Andernfalls wird davon ausgegangen, dass *pszfrom* eine Datei ist.

*pszTo*<br/>
Der Endpunkt des relativen Pfads.

*dwAttrTo*<br/>
Die Dateiattribute von *pszto*. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY enthält, wird davon ausgegangen, dass *pszto* ein Verzeichnis ist. Andernfalls wird davon ausgegangen, dass es sich bei *pszto* um eine Datei handelt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathrelativepathto](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).

##  <a name="removeargs"></a>Cpatht:: removeargs

Diese Methode wird aufgerufen, um alle Befehlszeilenargumente aus dem Pfad zu entfernen.

```
void RemoveArgs();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthremuveargs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)".

##  <a name="removebackslash"></a>Cpatht:: removebackschräg Strich

Mit dieser Methode wird der nachfolgende umgekehrte Schrägstrich aus dem Pfad entfernt.

```
void RemoveBackslash();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthremuvebackschräg Strich](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)".

##  <a name="removeblanks"></a>Cpatht:: removeblank

Diese Methode wird aufgerufen, um alle führenden und nachfolgenden Leerzeichen aus dem Pfad zu entfernen.

```
void RemoveBlanks();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthremuveblank](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)".

##  <a name="removeextension"></a>Cpatht:: removeextension

Mit dieser Methode können Sie die Dateierweiterung aus dem Pfad entfernen, sofern vorhanden.

```
void RemoveExtension();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthremuveextension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)".

##  <a name="removefilespec"></a>Cpatht:: removefilespec

Mit dieser Methode können Sie den nachfolgenden Dateinamen und den umgekehrten Schrägstrich aus dem Pfad entfernen, wenn Sie diesen haben.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [pthremuvefilespec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)".

##  <a name="renameextension"></a>Cpatht:: renameextension

Mit dieser Methode können Sie die Dateinamenerweiterung im Pfad durch eine neue Erweiterung ersetzen. Wenn der Dateiname keine Erweiterung enthält, wird die Erweiterung am Ende des Pfads angefügt.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parameter

*pszExtension*<br/>
Die neue Dateinamenerweiterung, der ein "."-Zeichen vorangestellt ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathrenameextension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).

##  <a name="skiproot"></a>Cpatht:: skiproot

Mit dieser Methode können Sie einen Pfad analysieren, wobei der Laufwerk Buchstabe bzw. UNC-Server/Freigabe Pfad Teile ignoriert werden.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position des Anfangs des untergeordneten Pfads zurück, der auf den Stamm folgt (Laufwerk Buchstabe oder UNC-Server/-Freigabe).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathskiproot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).

##  <a name="strippath"></a>Cpatht:: strippath

Diese Methode wird aufgerufen, um den Pfadteil eines voll qualifizierten Pfads und Datei namens zu entfernen.

```
void StripPath();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathstrippath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).

##  <a name="striptoroot"></a>Cpatht:: striptor

Mit dieser Methode können Sie alle Teile des Pfades außer den Stamm Informationen entfernen.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn ein gültiger Laufwerk Buchstabe im Pfad gefunden wurde, andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathstriptorioot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).

##  <a name="unquotespaces"></a>Cpatht:: unquotespaces

Mit dieser Methode können Sie Anführungszeichen am Anfang und am Ende eines Pfades entfernen.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [pathunquotespaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).

##  <a name="xchar"></a>Cpatht:: xchar

Ein Zeichentyp.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Hinweise

`StringType`der Vorlagen Parameter für `CPathT`.

## <a name="see-also"></a>Siehe auch

[Klassen](../../atl/reference/atl-classes.md)<br/>
[CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)
