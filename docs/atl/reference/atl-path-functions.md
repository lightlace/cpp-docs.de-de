---
title: ATL-Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
keywords:
- ATL, Pfad
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
caps.latest.revision: 3
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 97d585eb8bbe59a8ccd92b866819fb869d35f64c
ms.lasthandoff: 02/24/2017

---
# <a name="atl-path-functions"></a>ATL-Funktionen

ATL stellt die ATLPath-Klasse zum Bearbeiten von Pfaden in Form von [CPathT](cpatht-class.md). Dieser Code kann in atlpath.h gefunden werden.  
  
### <a name="related-classes"></a>Verwandte Klassen  
  
|||  
|-|-|  
|[CPathT-Klasse](cpatht-class.md)|Diese Klasse stellt einen Pfad.|  

### <a name="related-typedefs"></a>Verwandte Typdefinitionen  
  
|||  
|-|-|  
|`CPath`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CString`.|  
|`CPathA`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CStringA`.|  
|`CPathW`|Eine Spezialisierung der [CPathT](cpatht-class.md) mit `CStringW`.|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[ATLPath::AddBackslash](#addbackslash)|Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](#addextension)|Diese Funktion ist ein überladener Wrapper für [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](#append)|Diese Funktion ist ein überladener Wrapper für [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](#buildroot)|Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](#canonicalize)|Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](#combine)|Diese Funktion ist ein überladener Wrapper für [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](#commonprefix)|Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](#compactpath)|Diese Funktion ist ein überladener Wrapper für [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](#compactpathex)|Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](#fileexists)|Diese Funktion ist ein überladener Wrapper für [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](#findextension)|Diese Funktion ist ein überladener Wrapper für [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](#findfilename)|Diese Funktion ist ein überladener Wrapper für [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](#isdirectory)|Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](#isfilespec)|Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](#isprefix)|Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](#isrelative)|Diese Funktion ist ein überladener Wrapper für [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](#isroot)|Diese Funktion ist ein überladener Wrapper für [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](#issameroot)|Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](#isunc)|Diese Funktion ist ein überladener Wrapper für [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](#isuncserver)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](#makepretty)|Diese Funktion ist ein überladener Wrapper für [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](#matchspec)|Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](#quotespaces)|Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](#relativepathto)|Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](#removeargs)|Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](#removebackslash)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](#removeblanks)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](#removeextension)|Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](#removefilespec)|Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](#renameextension)|Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](#skiproot)|Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](#strippath)|Diese Funktion ist ein überladener Wrapper für [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](#striptoroot)|Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlpath.h  

## <a name="a-nameaddbackslasha-atlpathaddbackslash"></a><a name="addbackslash"></a>ATLPath::AddBackSlash

Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561) Details.  
  
 
  

## <a name="a-nameaddextensiona-atlpathaddextension"></a><a name="addextension"></a>ATLPath::AddExtension
 Diese Funktion ist ein überladener Wrapper für [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563) Details. 
  
## <a name="a-nameappenda-atlpathappend"></a><a name="append"></a>ATLPath::Append
 Diese Funktion ist ein überladener Wrapper für [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565) Details.  
  
 
  

## <a name="a-namebuildroota-atlpathbuildroot"></a><a name="buildroot"></a>ATLPath::BuildRoot
 Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567) Details.  
  
 
  

## <a name="a-namecanonicalizea-atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath::Canonicalize
 Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569) Details.  
  
 
  

## <a name="a-namecombinea-atlpathcombine"></a><a name="combine"></a>ATLPath::Combine 
Diese Funktion ist ein überladener Wrapper für [PathCombine](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773571).  

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
Einzelheiten finden Sie unter PathCombine.


## <a name="a-namecommonprefixa-atlpathcommonprefix"></a><a name="commonprefix"></a>ATLPath::CommonPrefix
 Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
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
 Finden Sie unter [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574) Details.  
  
 
  

## <a name="a-namecompactpatha-atlpathcompactpath"></a><a name="compactpath"></a>ATLPath::CompactPath
 Diese Funktion ist ein überladener Wrapper für [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
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
 Finden Sie unter [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575) Details.  
  
 
  

## <a name="a-namecompactpathexa-atlpathcompactpathex"></a><a name="compactpathex"></a>ATLPath::CompactPathEx
 Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
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
 Finden Sie unter [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578) Details.  
  
 
  

## <a name="a-namefileexistsa-atlpathfileexists"></a><a name="fileexists"></a>ATLPath::FileExists
 Diese Funktion ist ein überladener Wrapper für [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584) Details.  
  
 
  

## <a name="a-namefindextensiona-atlpathfindextension"></a><a name="findextension"></a>ATLPath::FindExtension
 Diese Funktion ist ein überladener Wrapper für [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587) Details.  
  
 
  

## <a name="a-namefindfilenamea-atlpathfindfilename"></a><a name="findfilename"></a>ATLPath::FindFileName
 Diese Funktion ist ein überladener Wrapper für [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) Details.  
  
 
  

## <a name="a-namegetdrivenumbera-atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>ATLPath::GetDriveNumber  
 Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612) Details.  
  
 


## <a name="a-nameisdirectorya--atlpathisdirectory"></a><a name="isdirectory"></a>ATLPath::IsDirectory 
Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773621).

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>Hinweise
Einzelheiten finden Sie unter PathIsDirectory.  

## <a name="a-nameisfilespeca-atlpathisfilespec"></a><a name="isfilespec"></a>ATLPath::IsFileSpec
 Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627) Details.  
  
 
  

## <a name="a-nameisprefixa-atlpathisprefix"></a><a name="isprefix"></a>ATLPath::IsPrefix
 Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650) Details.  
  
 
  

## <a name="a-nameisrelativea-atlpathisrelative"></a><a name="isrelative"></a>ATLPath::IsRelative
 Diese Funktion ist ein überladener Wrapper für [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660) Details.  
  
 
  

## <a name="a-nameisroota-atlpathisroot"></a><a name="isroot"></a>ATLPath::IsRoot
 Diese Funktion ist ein überladener Wrapper für [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674) Details.  
  
 
  

## <a name="a-nameissameroota-atlpathissameroot"></a><a name="issameroot"></a>ATLPath::IsSameRoot
 Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687) Details.  
  
 
  

## <a name="a-nameisunca-atlpathisunc"></a><a name="isunc"></a>ATLPath::IsUNC
 Diese Funktion ist ein überladener Wrapper für [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712) Details.  
  
 
  

## <a name="a-nameisuncservera-atlpathisuncserver"></a><a name="isuncserver"></a>ATLPath::IsUNCServer
 Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722) Details.  
  
 
  

## <a name="a-nameisuncserversharea-atlpathisuncservershare"></a><a name="isuncservershare"></a>ATLPath::IsUNCServerShare
 Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723) Details.  
  
 
  

## <a name="a-namemakeprettya-atlpathmakepretty"></a><a name="makepretty"></a>ATLPath::MakePretty
 Diese Funktion ist ein überladener Wrapper für [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725) Details.  
  
 
  

## <a name="a-namematchspeca-atlpathmatchspec"></a><a name="matchspec"></a>ATLPath::MatchSpec  
 Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727) Details.  
  
 
  

## <a name="a-namequotespacesa-atlpathquotespaces"></a><a name="quotespaces"></a>ATLPath::QuoteSpaces  
 Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739) Details.  
  
 
  

## <a name="a-namerelativepathtoa-atlpathrelativepathto"></a><a name="relativepathto"></a>ATLPath::RelativePathTo
 Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
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
 Finden Sie unter [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740) Details.  
  
 
  

## <a name="a-nameremoveargsa-atlpathremoveargs"></a><a name="removeargs"></a>ATLPath::RemoveArgs  
 Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742) Details.  
  
 
  

## <a name="a-nameremovebackslasha-atlpathremovebackslash"></a><a name="removebackslash"></a>ATLPath::RemoveBackslash
 Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743) Details.  
  
 
  

## <a name="a-nameremoveblanksa-atlpathremoveblanks"></a><a name="removeblanks"></a>ATLPath::RemoveBlanks
 Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745) Details.  
  
 
  

## <a name="a-nameremoveextensiona-atlpathremoveextension"></a><a name="removeextension"></a>ATLPath::RemoveExtension
 Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746) Details.  
  
 
  

## <a name="a-nameremovefilespeca-atlpathremovefilespec"></a><a name="removefilespec"></a>ATLPath::RemoveFileSpec
 Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748) Details.  
  
 
  

## <a name="a-namerenameextensiona-atlpathrenameextension"></a><a name="renameextension"></a>ATLPath::RenameExtension
 Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749) Details.  
  
 
  

## <a name="a-nameskiproota-atlpathskiproot"></a><a name="skiproot"></a>ATLPath::SkipRoot
 Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754) Details.  
  
 
  

## <a name="a-namestrippatha-atlpathstrippath"></a><a name="strippath"></a>ATLPath::StripPath
 Diese Funktion ist ein überladener Wrapper für [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756) Details.  
  
 
  


## <a name="a-namestriptoroota-atlpathstriptoroot"></a><a name="striptoroot"></a>ATLPath::StripToRoot
 Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757) Details.  
  
 
  

## <a name="a-nameunquotespacesa-atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath::UnquoteSpaces
 Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
### <a name="syntax"></a>Syntax  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763) Details.  
  
 
  
 

