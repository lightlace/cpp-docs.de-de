---
title: CPathT-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 36d8710bd7bb055d8629dec57ec4d8c3602c8f79
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273022"
---
# <a name="cpatht-class"></a>CPathT-Klasse

Diese Klasse stellt einen Pfad an.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>Parameter

*StringType*<br/>
Die ATL-/MFC-String-Klasse für den Pfad zu verwenden (siehe [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|Eine Konstante Zeichenfolge-Typ.|
|[CPathT::PXSTR](#pxstr)|Ein Zeichenfolgentyp.|
|[CPathT::XCHAR](#xchar)|Ein Zeichentyp.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|Der Konstruktor für den Pfad.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|Rufen Sie diese Methode zum Hinzufügen von eines umgekehrten Schrägstrichs am Ende einer Zeichenfolge in die richtige Syntax für einen Pfad zu erstellen.|
|[CPathT::AddExtension](#addextension)|Rufen Sie diese Methode, um einen Pfad eine Dateierweiterung hinzugefügt.|
|[CPathT::Append](#append)|Rufen Sie diese Methode, um eine Zeichenfolge an den aktuellen Pfad angefügt werden soll.|
|[CPathT::BuildRoot](#buildroot)|Rufen Sie diese Methode, um einen Stammpfad aus einer Reihe von bestimmten Laufwerks zu erstellen.|
|[CPathT::Canonicalize](#canonicalize)|Rufen Sie diese Methode, um den Pfad in kanonischer Form konvertieren.|
|[CPathT::Combine](#combine)|Rufen Sie diese Methode, um eine Zeichenfolge, die einen Verzeichnisnamen darstellt und eine Zeichenfolge mit Pfadnamen einer Datei in einen Pfad zu verketten.|
|[CPathT::CommonPrefix](#commonprefix)|Rufen Sie diese Methode, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix mit dem aktuellen Pfad aufweist.|
|[CPathT::CompactPath](#compactpath)|Rufen Sie diese Methode, um einen Dateipfad an ein angegebenes Pixelbreite angepasst durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abschneiden.|
|[CPathT::CompactPathEx](#compactpathex)|Rufen Sie diese Methode, um einen Dateipfad, passen Sie innerhalb einer bestimmten Anzahl von Zeichen durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abschneiden.|
|[CPathT::FileExists](#fileexists)|Rufen Sie diese Methode, um zu überprüfen, ob die Datei unter diesem Pfadnamen vorhanden ist.|
|[CPathT::FindExtension](#findextension)|Rufen Sie diese Methode, um die Position der Dateierweiterung im Pfad zu suchen.|
|[CPathT::FindFileName](#findfilename)|Rufen Sie diese Methode, um die Position in dem Pfad der Datei zu suchen.|
|[CPathT::GetDriveNumber](#getdrivenumber)|Rufen Sie diese Methode, um den Pfad für einen bestimmten Laufwerkbuchstaben innerhalb des Bereichs von "A" bis "Z" Suchen und die Laufwerknummer der entsprechenden zurück.|
|[CPathT::GetExtension](#getextension)|Rufen Sie diese Methode, um die Datei aus dem Pfad zu erhalten.|
|[CPathT::IsDirectory](#isdirectory)|Rufen Sie diese Methode, um zu überprüfen, ob der Pfad ein gültiges Verzeichnis ist.|
|[CPathT::IsFileSpec](#isfilespec)|Rufen Sie diese Methode, um einen Pfad für alle Zeichen als Trennzeichen bei Pfad zu suchen (z. B. ':' oder '\\"). Wenn keine Zeichen als Trennzeichen bei Pfad vorhanden sind, gilt der Pfad ein Dateispezifikation-Pfad sein.|
|[CPathT::IsPrefix](#isprefix)|Rufen Sie diese Methode, um zu bestimmen, ob ein Pfad ein gültiges Präfix des Typs übergebener enthält *PszPrefix*.|
|[CPathT::IsRelative](#isrelative)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad relativ ist.|
|[CPathT::IsRoot](#isroot)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einer Verzeichnisstamm ist.|
|[CPathT::IsSameRoot](#issameroot)|Rufen Sie diese Methode, um zu bestimmen, ob ein anderer Pfad eine gemeinsamen Root-Komponente mit dem aktuellen Pfad hat.|
|[CPathT::IsUNC](#isunc)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für einen Server aus, und teilen.|
|[CPathT::IsUNCServer](#isuncserver)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für nur einen Server ist.|
|[CPathT::IsUNCServerShare](#isuncservershare)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Freigabepfad ist \\ \  *Server*\ *freigeben*.|
|[CPathT::MakePretty](#makepretty)|Rufen Sie diese Methode zum Konvertieren eines Pfads in alle Kleinbuchstaben, die dem Pfad ein einheitliches Erscheinungsbild verleihen.|
|[CPathT::MatchSpec](#matchspec)|Rufen Sie diese Methode, um den Pfad für eine Zeichenfolge mit einem Platzhalter Abgleich von Typ zu durchsuchen.|
|[CPathT::QuoteSpaces](#quotespaces)|Rufen Sie diese Methode, um den Pfad in Anführungszeichen einschließen, wenn sie keine Leerzeichen enthält.|
|[CPathT::RelativePathTo](#relativepathto)|Rufen Sie diese Methode, um einen relativen Pfad zu einem anderen aus einer Datei oder Ordner zu erstellen.|
|[CPathT::RemoveArgs](#removeargs)|Rufen Sie diese Methode, um die Befehlszeilenargumente aus dem Pfad zu entfernen.|
|[CPathT::RemoveBackslash](#removebackslash)|Rufen Sie diese Methode, um den nachgestellten umgekehrten Schrägstrich aus dem Pfad zu entfernen.|
|[CPathT::RemoveBlanks](#removeblanks)|Rufen Sie diese Methode, um alle führenden und nachfolgenden Leerzeichen aus dem Pfad zu entfernen.|
|[CPathT::RemoveExtension](#removeextension)|Rufen Sie diese Methode, um die Erweiterung aus dem Pfad, zu entfernen, sofern vorhanden.|
|[CPathT::RemoveFileSpec](#removefilespec)|Rufen Sie diese Methode zum Entfernen von den nachfolgenden Dateinamen und einen umgekehrten Schrägstrich vom Pfad, wenn sie diese verfügt.|
|[CPathT::RenameExtension](#renameextension)|Rufen Sie diese Methode, um die Dateinamenerweiterung im Pfad durch eine neue Erweiterung zu ersetzen. Wenn Sie der Dateinamen keine Erweiterung enthält, wird die Erweiterung an das Ende der Zeichenfolge angefügt werden.|
|[CPathT::SkipRoot](#skiproot)|Rufen Sie diese Methode, um einen Pfad, ignorieren den Laufwerkbuchstaben oder einen UNC-Server bzw. eine Freigabe pfadanteile zu analysieren.|
|[CPathT::StripPath](#strippath)|Rufen Sie diese Methode, um den Pfadteil des einen vollqualifizierten Pfad und Dateinamen zu entfernen.|
|[CPathT::StripToRoot](#striptoroot)|Rufen Sie diese Methode, um alle Bestandteile des Pfads mit Ausnahme der Stammverzeichnisinformationen zu entfernen.|
|[CPathT::UnquoteSpaces](#unquotespaces)|Rufen Sie diese Methode, um Anführungszeichen am Anfang und Ende eines Pfads zu entfernen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Const StringType CPathT::operator &](#operator_const_stringtype_amp)|Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[CPathT::operator StringType &](#operator_stringtype)|Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.|
|[CPathT::operator +=](#operator_add_eq)|Dieser Operator Fügt eine Zeichenfolge in den Pfad an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|Der Pfad.|

## <a name="remarks"></a>Hinweise

`CPath`, `CPathA`, und `CPathW` sind Instanziierungen von `CPathT` wie folgt definiert:

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>Anforderungen

**Header:** "atlpath.h"

##  <a name="addbackslash"></a>  CPathT::AddBackslash

Rufen Sie diese Methode zum Hinzufügen von eines umgekehrten Schrägstrichs am Ende einer Zeichenfolge in die richtige Syntax für einen Pfad zu erstellen. Wenn der Pfad bereits einen nachgestellten umgekehrten Schrägstrich enthält, wird kein umgekehrter Schrägstrich hinzugefügt.

```
void AddBackslash();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathAddBackSlash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).

##  <a name="addextension"></a>  CPathT::AddExtension

Rufen Sie diese Methode, um einen Pfad eine Dateierweiterung hinzugefügt.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parameter

*pszExtension*<br/>
Die Dateierweiterung hinzufügen.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).

##  <a name="append"></a>  CPathT::Append

Rufen Sie diese Methode, um eine Zeichenfolge an den aktuellen Pfad angefügt werden soll.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>Parameter

*pszMore*<br/>
Die anzufügende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).

##  <a name="buildroot"></a>  CPathT::BuildRoot

Rufen Sie diese Methode, um einen Stammpfad aus einer Reihe von bestimmten Laufwerks zu erstellen.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>Parameter

*iDrive*<br/>
Die Laufwerks-ID (0 ist A:, ist 1, b usw.).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).

##  <a name="canonicalize"></a>  CPathT::Canonicalize

Rufen Sie diese Methode, um den Pfad in kanonischer Form konvertieren.

```
void Canonicalize();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).

##  <a name="combine"></a>  CPathT::Combine

Rufen Sie diese Methode, um eine Zeichenfolge, die einen Verzeichnisnamen darstellt und eine Zeichenfolge mit Pfadnamen einer Datei in einen Pfad zu verketten.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>Parameter

*pszDir*<br/>
Der Verzeichnispfad.

*pszFile*<br/>
Der Dateipfad.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).

##  <a name="commonprefix"></a>  CPathT::CommonPrefix

Rufen Sie diese Methode, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix mit dem aktuellen Pfad aufweist.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>Parameter

*pszOther*<br/>
Der Pfad, mit dem aktuellen Objekt verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das gemeinsame Präfix zurück.

### <a name="remarks"></a>Hinweise

Ein Präfix ist einem dieser Typen: "C:\\\\",".","..","... \\\\". Weitere Informationen finden Sie unter [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).

##  <a name="compactpath"></a>  CPathT::CompactPath

Rufen Sie diese Methode, um einen Dateipfad an ein angegebenes Pixelbreite angepasst durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abschneiden.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>Parameter

*hDC*<br/>
Der Gerätekontext, die für die Schriftarteigenschaften verwendet wird.

*nWidth*<br/>
Die Breite in Pixel, die die Zeichenfolge wird zum Einpassen in erzwungen werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).

##  <a name="compactpathex"></a>  CPathT::CompactPathEx

Rufen Sie diese Methode, um einen Dateipfad, passen Sie innerhalb einer bestimmten Anzahl von Zeichen durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abschneiden.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parameter

*nMaxChars*<br/>
Die maximale Anzahl von Zeichen in die neue Zeichenfolge, einschließlich des abschließenden NULL-Zeichens enthalten sein soll.

*dwFlags*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).

##  <a name="cpatht"></a>  CPathT::CPathT

Der Konstruktor.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
Der Zeiger auf eine Pfadzeichenfolge.

*path*<br/>
Die Pfadzeichenfolge.

##  <a name="fileexists"></a>  CPathT::FileExists

Rufen Sie diese Methode, um zu überprüfen, ob die Datei unter diesem Pfadnamen vorhanden ist.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Datei "false" vorhanden, andernfalls ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).

##  <a name="findextension"></a>  CPathT::FindExtension

Rufen Sie diese Methode, um die Position der Dateierweiterung im Pfad zu suchen.

```
int FindExtension() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position eines der "." vor der Erweiterung. Wenn keine Erweiterung gefunden wird, gibt-1 zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).

##  <a name="findfilename"></a>  CPathT::FindFileName

Rufen Sie diese Methode, um die Position in dem Pfad der Datei zu suchen.

```
int FindFileName() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position des Dateinamens. Wenn kein Dateiname gefunden wird, gibt-1 zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).

##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber

Rufen Sie diese Methode, um den Pfad für einen bestimmten Laufwerkbuchstaben innerhalb des Bereichs von "A" bis "Z" Suchen und die Laufwerknummer der entsprechenden zurück.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Laufwerknummer als ganze Zahl von 0 bis 25 (entspricht "A" bis "Z") ein, wenn der Pfad einen Laufwerkbuchstaben, oder-1 enthält.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).

##  <a name="getextension"></a>  CPathT::GetExtension

Rufen Sie diese Methode, um die Datei aus dem Pfad zu erhalten.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Dateierweiterung zurück.

##  <a name="isdirectory"></a>  CPathT::IsDirectory

Rufen Sie diese Methode, um zu überprüfen, ob der Pfad ein gültiges Verzeichnis ist.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich Null (16) zurück, wenn der Pfad ein Verzeichnis ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

##  <a name="isfilespec"></a>  CPathT::IsFileSpec

Rufen Sie diese Methode, um einen Pfad für alle Zeichen als Trennzeichen bei Pfad zu suchen (z. B. ':' oder '\\"). Wenn keine Zeichen als Trennzeichen bei Pfad vorhanden sind, gilt der Pfad ein Dateispezifikation-Pfad sein.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn keine Zeichen als Trennzeichen bei Pfad im Pfad vorhanden sind, oder FALSE, wenn das Zeichen als Trennzeichen bei Pfad vorhanden sind.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).

##  <a name="isprefix"></a>  CPathT::IsPrefix

Rufen Sie diese Methode, um zu bestimmen, ob ein Pfad ein gültiges Präfix des Typs übergebener enthält *PszPrefix*.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>Parameter

*pszPrefix*<br/>
Das Präfix, nach dem gesucht werden soll. Ein Präfix ist einem dieser Typen: "C:\\\\",".","..","... \\\\".

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Pfad das Präfix oder "false" enthält.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).

##  <a name="isrelative"></a>  CPathT::IsRelative

Rufen Sie diese Methode, um zu bestimmen, ob der Pfad relativ ist.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Pfad relativ oder "false" ist, wenn es absolut ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).

##  <a name="isroot"></a>  CPathT::IsRoot

Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einer Verzeichnisstamm ist.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Pfad einen Stamm oder "false" ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).

##  <a name="issameroot"></a>  CPathT::IsSameRoot

Rufen Sie diese Methode, um zu bestimmen, ob ein anderer Pfad eine gemeinsamen Root-Komponente mit dem aktuellen Pfad hat.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>Parameter

*pszOther*<br/>
Der andere Pfad.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn beide Zeichenfolgen die gleiche Stammkomponente oder "false" haben.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).

##  <a name="isunc"></a>  CPathT::IsUNC

Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für einen Server aus, und teilen.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Pfad einen gültigen UNC-Pfad, oder "false" ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).

##  <a name="isuncserver"></a>  CPathT::IsUNCServer

Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für nur einen Server ist.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Zeichenfolge eine gültige UNC-Pfad für nur einen Server (kein Name) oder "false" ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).

##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare

Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Freigabepfad ist \\ \  *Server*\ *freigeben*.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Pfad im Format \\ \  *Server*\ *freigeben*, oder "false" andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).

##  <a name="m_strpath"></a>  CPathT::m_strPath

Der Pfad.

```
StringType m_strPath;
```

### <a name="remarks"></a>Hinweise

`StringType` der Vorlagenparameter ist `CPathT`.

##  <a name="makepretty"></a>  CPathT::MakePretty

Rufen Sie diese Methode zum Konvertieren eines Pfads in alle Kleinbuchstaben, die dem Pfad ein einheitliches Erscheinungsbild verleihen.

```
BOOL MakePretty();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Pfad konvertiert wurde, oder "false" andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).

##  <a name="matchspec"></a>  CPathT::MatchSpec

Rufen Sie diese Methode, um den Pfad für eine Zeichenfolge mit einem Platzhalter Abgleich von Typ zu durchsuchen.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>Parameter

*pszSpec*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge mit dem Dateinamen für die Suche. Beispielsweise, um zu testen, ob die Datei unter dem aktuellen Pfad eine DOC-Datei, *PszSpec* sollte festgelegt werden, auf "* .doc".

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Zeichenfolge entspricht, oder "false" andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).

##  <a name="operator_add_eq"></a>  CPathT::operator +=

Dieser Operator Fügt eine Zeichenfolge in den Pfad an.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>Parameter

*pszMore*<br/>
Die anzufügende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt den aktuellen Pfad zurück.

##  <a name="operator_const_stringtype_amp"></a>  Const StringType CPathT::operator &amp;

Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operatorconst StringType&() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge, die den aktuellen Pfad verwaltet, die von diesem Objekt darstellt.

##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR

Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operatorPCXSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge, die den aktuellen Pfad verwaltet, die von diesem Objekt darstellt.

##  <a name="operator_stringtype__amp"></a>  CPathT::operator StringType &amp;

Dieser Operator kann das Objekt wie eine Zeichenfolge behandelt werden.

```
operatorStringType&() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge, die den aktuellen Pfad verwaltet, die von diesem Objekt darstellt.

##  <a name="pcxstr"></a>  CPathT::PCXSTR

Eine Konstante Zeichenfolge-Typ.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Hinweise

`StringType` der Vorlagenparameter ist `CPathT`.

##  <a name="pxstr"></a>  CPathT::PXSTR

Ein Zeichenfolgentyp.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Hinweise

`StringType` der Vorlagenparameter ist `CPathT`.

##  <a name="quotespaces"></a>  CPathT::QuoteSpaces

Rufen Sie diese Methode, um den Pfad in Anführungszeichen einschließen, wenn sie keine Leerzeichen enthält.

```
void QuoteSpaces();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).

##  <a name="relativepathto"></a>  CPathT::RelativePathTo

Rufen Sie diese Methode, um einen relativen Pfad zu einem anderen aus einer Datei oder Ordner zu erstellen.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>Parameter

*pszFrom*<br/>
Der Anfang der relative Pfad.

*dwAttrFrom*<br/>
Die Dateiattribute der *PszFrom*. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY, enthält *PszFrom* angenommenen ein Verzeichnis sein, andernfalls *PszFrom* wird davon ausgegangen, dass eine Datei sein.

*pszTo*<br/>
Der Endpunkt des relativen Pfads.

*dwAttrTo*<br/>
Die Dateiattribute der *PszTo*. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY, enthält *PszTo* angenommenen ein Verzeichnis sein, andernfalls *PszTo* wird davon ausgegangen, dass eine Datei sein.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).

##  <a name="removeargs"></a>  CPathT::RemoveArgs

Rufen Sie diese Methode, um die Befehlszeilenargumente aus dem Pfad zu entfernen.

```
void RemoveArgs();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).

##  <a name="removebackslash"></a>  CPathT::RemoveBackslash

Rufen Sie diese Methode, um den nachgestellten umgekehrten Schrägstrich aus dem Pfad zu entfernen.

```
void RemoveBackslash();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).

##  <a name="removeblanks"></a>  CPathT::RemoveBlanks

Rufen Sie diese Methode, um alle führenden und nachfolgenden Leerzeichen aus dem Pfad zu entfernen.

```
void RemoveBlanks();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).

##  <a name="removeextension"></a>  CPathT::RemoveExtension

Rufen Sie diese Methode, um die Erweiterung aus dem Pfad, zu entfernen, sofern vorhanden.

```
void RemoveExtension();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).

##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec

Rufen Sie diese Methode zum Entfernen von den nachfolgenden Dateinamen und einen umgekehrten Schrägstrich vom Pfad, wenn sie diese verfügt.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).

##  <a name="renameextension"></a>  CPathT::RenameExtension

Rufen Sie diese Methode, um die Dateinamenerweiterung im Pfad durch eine neue Erweiterung zu ersetzen. Wenn Sie der Dateinamen keine Erweiterung enthält, wird die Erweiterung an das Ende des Pfads angefügt werden.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>Parameter

*pszExtension*<br/>
Die neue Dateinamenerweiterung, vorangestellt wird, wird ein "." Zeichen.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).

##  <a name="skiproot"></a>  CPathT::SkipRoot

Rufen Sie diese Methode, um einen Pfad, ignoriert der Laufwerkbuchstabe oder pfadanteile für UNC (universal naming Convention)-Server bzw. eine Freigabe zu analysieren.

```
int SkipRoot() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Position des Anfangs des untergeordnete Pfads, der den Stamm (Laufwerkbuchstaben oder UNC-Server/Freigabe) folgt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).

##  <a name="strippath"></a>  CPathT::StripPath

Rufen Sie diese Methode, um den Pfadteil des einen vollqualifizierten Pfad und Dateinamen zu entfernen.

```
void StripPath();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).

##  <a name="striptoroot"></a>  CPathT::StripToRoot

Rufen Sie diese Methode, um alle Bestandteile des Pfads mit Ausnahme der Stammverzeichnisinformationen zu entfernen.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn auf einen gültigen Laufwerkbuchstaben gefunden wurde im Pfad, oder "false" andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).

##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces

Rufen Sie diese Methode, um Anführungszeichen am Anfang und Ende eines Pfads zu entfernen.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).

##  <a name="xchar"></a>  CPathT::XCHAR

Ein Zeichentyp.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Hinweise

`StringType` der Vorlagenparameter ist `CPathT`.

## <a name="see-also"></a>Siehe auch

[Klassen](../../atl/reference/atl-classes.md)<br/>
[CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)
