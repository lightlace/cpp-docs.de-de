---
title: ATL-Pfad-Funktionen
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: 86ddb3c6916675a92070684a04c7a6a6ecd8a134
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586068"
---
# <a name="atl-path-functions"></a>ATL-Pfad-Funktionen

ATL stellt die ATLPath-Klasse für die Bearbeitung von Pfaden in Form von [CPathT](cpatht-class.md). Dieser Code kann in "atlpath.h" gefunden werden.

### <a name="related-classes"></a>Verwandte Klassen

|||
|-|-|
|[CPathT-Klasse](cpatht-class.md)|Diese Klasse stellt einen Pfad an.|

### <a name="related-typedefs"></a>Verwandte Typedefs

|||
|-|-|
|`CPath`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CString`.|
|`CPathA`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CStringA`.|
|`CPathW`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CStringW`.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).|
|[ATLPath::AddExtension](#addextension)|Diese Funktion ist ein überladener Wrapper für [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).|
|[ATLPath::Append](#append)|Diese Funktion ist ein überladener Wrapper für [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).|
|[ATLPath::BuildRoot](#buildroot)|Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).|
|[ATLPath::Canonicalize](#canonicalize)|Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).|
|[ATLPath::Combine](#combine)|Diese Funktion ist ein überladener Wrapper für [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).|
|[ATLPath::CommonPrefix](#commonprefix)|Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).|
|[ATLPath::CompactPath](#compactpath)|Diese Funktion ist ein überladener Wrapper für [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).|
|[ATLPath::CompactPathEx](#compactpathex)|Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).|
|[ATLPath::FileExists](#fileexists)|Diese Funktion ist ein überladener Wrapper für [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).|
|[ATLPath::FindExtension](#findextension)|Diese Funktion ist ein überladener Wrapper für [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).|
|[ATLPath::FindFileName](#findfilename)|Diese Funktion ist ein überladener Wrapper für [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).|
|[ATLPath::GetDriveNumber](#getdrivenumber)|Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).|
|[ATLPath::IsDirectory](#isdirectory)|Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).|
|[ATLPath::IsFileSpec](#isfilespec)|Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).|
|[ATLPath::IsPrefix](#isprefix)|Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).|
|[ATLPath::IsRelative](#isrelative)|Diese Funktion ist ein überladener Wrapper für [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).|
|[ATLPath::IsRoot](#isroot)|Diese Funktion ist ein überladener Wrapper für [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).|
|[ATLPath::IsSameRoot](#issameroot)|Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).|
|[ATLPath::IsUNC](#isunc)|Diese Funktion ist ein überladener Wrapper für [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).|
|[ATLPath::IsUNCServer](#isuncserver)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).|
|[ATLPath::IsUNCServerShare](#isuncservershare)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).|
|[ATLPath::MakePretty](#makepretty)|Diese Funktion ist ein überladener Wrapper für [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).|
|[ATLPath::MatchSpec](#matchspec)|Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).|
|[ATLPath::QuoteSpaces](#quotespaces)|Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).|
|[ATLPath::RelativePathTo](#relativepathto)|Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).|
|[ATLPath::RemoveArgs](#removeargs)|Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).|
|[ATLPath::RemoveBackslash](#removebackslash)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).|
|[ATLPath::RemoveBlanks](#removeblanks)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).|
|[ATLPath::RemoveExtension](#removeextension)|Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).|
|[ATLPath::RemoveFileSpec](#removefilespec)|Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).|
|[ATLPath::RenameExtension](#renameextension)|Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).|
|[ATLPath::SkipRoot](#skiproot)|Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).|
|[ATLPath::StripPath](#strippath)|Diese Funktion ist ein überladener Wrapper für [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).|
|[ATLPath::StripToRoot](#striptoroot)|Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).|
|[ATLPath::UnquoteSpaces](#unquotespaces)|Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="requirements"></a>Anforderungen

**Header:** "atlpath.h"

## <a name="addbackslash"></a> ATLPath::AddBackSlash

Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha).

### <a name="syntax"></a>Syntax

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha) Details.

## <a name="addextension"></a> ATLPath::AddExtension

Diese Funktion ist ein überladener Wrapper für [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona).

### <a name="syntax"></a>Syntax

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona) Details.

## <a name="append"></a> ATLPath::Append

Diese Funktion ist ein überladener Wrapper für [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda).

### <a name="syntax"></a>Syntax

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda) Details.

## <a name="buildroot"></a> ATLPath::BuildRoot

Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota).

### <a name="syntax"></a>Syntax

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota) Details.

## <a name="canonicalize"></a> ATLPath::Canonicalize

Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea).

### <a name="syntax"></a>Syntax

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea) Details.

## <a name="combine"></a> ATLPath::Combine

Diese Funktion ist ein überladener Wrapper für [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea).

### <a name="syntax"></a>Syntax

```
inline char* Combine(
   char* pszDest,
   const char* pszDir,
   const char* pszFile
);

inline wchar_t* Combine(
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```

### <a name="remarks"></a>Hinweise

Einzelheiten finden Sie in der PathCombine.

## <a name="commonprefix"></a> ATLPath::CommonPrefix

Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa).

### <a name="syntax"></a>Syntax

```
inline int CommonPrefix(
   const char* pszFile1,
   const char* pszFile2,
   char* pszDest);

inline int CommonPrefix(
   const wchar_t* pszFile1,
   const wchar_t* pszFile2,
   wchar_t* pszDest);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa) Details.

## <a name="compactpath"></a> ATLPath::CompactPath

Diese Funktion ist ein überladener Wrapper für [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha).

### <a name="syntax"></a>Syntax

```
inline BOOL CompactPath(
   HDC hDC,
   char* pszPath,
   UINT dx);

inline BOOL CompactPath(
   HDC hDC,
   wchar_t* pszPath,
   UINT dx);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha) Details.

## <a name="compactpathex"></a> ATLPath::CompactPathEx

Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa).

### <a name="syntax"></a>Syntax

```
inline BOOL CompactPathEx(
   char* pszDest,
   const char* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);

inline BOOL CompactPathEx(
   wchar_t* pszDest,
   const wchar_t* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa) Details.

## <a name="fileexists"></a> ATLPath::FileExists

Diese Funktion ist ein überladener Wrapper für [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa).

### <a name="syntax"></a>Syntax

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa) Details.

## <a name="findextension"></a> ATLPath::FindExtension

Diese Funktion ist ein überladener Wrapper für [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona).

### <a name="syntax"></a>Syntax

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona) Details.

## <a name="findfilename"></a> ATLPath::FindFileName

Diese Funktion ist ein überladener Wrapper für [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea).

### <a name="syntax"></a>Syntax

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) Details.

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber

Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera).

### <a name="syntax"></a>Syntax

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera) Details.

## <a name="isdirectory"></a>  ATLPath::IsDirectory

Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya).

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Einzelheiten finden Sie in der PathIsDirectory.

## <a name="isfilespec"></a> ATLPath::IsFileSpec

Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca).

### <a name="syntax"></a>Syntax

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca) Details.

## <a name="isprefix"></a> ATLPath::IsPrefix

Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa).

### <a name="syntax"></a>Syntax

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa) Details.

## <a name="isrelative"></a> ATLPath::IsRelative

Diese Funktion ist ein überladener Wrapper für [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea).

### <a name="syntax"></a>Syntax

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea) Details.

## <a name="isroot"></a> ATLPath::IsRoot

Diese Funktion ist ein überladener Wrapper für [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota).

### <a name="syntax"></a>Syntax

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota) Details.

## <a name="issameroot"></a> ATLPath::IsSameRoot

Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota).

### <a name="syntax"></a>Syntax

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota) Details.

## <a name="isunc"></a> ATLPath::IsUNC

Diese Funktion ist ein überladener Wrapper für [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca).

### <a name="syntax"></a>Syntax

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca) Details.

## <a name="isuncserver"></a> ATLPath::IsUNCServer

Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera).

### <a name="syntax"></a>Syntax

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera) Details.

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare

Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).

### <a name="syntax"></a>Syntax

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea) Details.

## <a name="makepretty"></a> ATLPath::MakePretty

Diese Funktion ist ein überladener Wrapper für [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).

### <a name="syntax"></a>Syntax

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya) Details.

## <a name="matchspec"></a> ATLPath::MatchSpec

Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).

### <a name="syntax"></a>Syntax

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca) Details.

## <a name="quotespaces"></a> ATLPath::QuoteSpaces

Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).

### <a name="syntax"></a>Syntax

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa) Details.

## <a name="relativepathto"></a> ATLPath::RelativePathTo

Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).

### <a name="syntax"></a>Syntax

```
inline BOOL RelativePathTo(
   char* pszPath,
   const char* pszFrom,
   DWORD dwAttrFrom,
   const char* pszTo,
   DWORD dwAttrTo);

inline BOOL RelativePathTo(
   wchar_t* pszPath,
   const wchar_t* pszFrom,
   DWORD dwAttrFrom,
   const wchar_t* pszTo,
   DWORD dwAttrTo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa) Details.

## <a name="removeargs"></a> ATLPath::RemoveArgs

Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).

### <a name="syntax"></a>Syntax

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa) Details.

## <a name="removebackslash"></a> ATLPath::RemoveBackslash

Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).

### <a name="syntax"></a>Syntax

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha) Details.

## <a name="removeblanks"></a> ATLPath::RemoveBlanks

Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).

### <a name="syntax"></a>Syntax

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa) Details.

## <a name="removeextension"></a> ATLPath::RemoveExtension

Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).

### <a name="syntax"></a>Syntax

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona) Details.

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec

Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).

### <a name="syntax"></a>Syntax

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca) Details.

## <a name="renameextension"></a> ATLPath::RenameExtension

Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).

### <a name="syntax"></a>Syntax

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona) Details.

## <a name="skiproot"></a> ATLPath::SkipRoot

Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).

### <a name="syntax"></a>Syntax

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota) Details.

## <a name="strippath"></a> ATLPath::StripPath

Diese Funktion ist ein überladener Wrapper für [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).

### <a name="syntax"></a>Syntax

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha) Details.

## <a name="striptoroot"></a> ATLPath::StripToRoot

Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).

### <a name="syntax"></a>Syntax

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota) Details.

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces

Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).

### <a name="syntax"></a>Syntax

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa) Details.

