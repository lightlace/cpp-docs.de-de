---
title: CPathT Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 781f2f6a3fba0e7ca4698809f196e623cfbb6bb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cpatht-class"></a>CPathT-Klasse
Diese Klasse stellt einen Pfad an.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>Parameter  
 `StringType`  
 ATL/MFC-Zeichenfolgenklasse für den Pfad zu verwenden (siehe [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|Eine Konstante Zeichenfolge-Typ.|  
|[CPathT::PXSTR](#pxstr)|Ein String-Datentyp.|  
|[CPathT::XCHAR](#xchar)|Ein Zeichentyp.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|Der Konstruktor für den Pfad.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|Rufen Sie diese Methode zum Hinzufügen von eines umgekehrten Schrägstrich am Ende einer Zeichenfolge auf die richtige Syntax für einen Pfad zu erstellen.|  
|[CPathT::AddExtension](#addextension)|Rufen Sie diese Methode, um ein Pfad eine Dateierweiterung hinzugefügt werden.|  
|[CPathT::Append](#append)|Rufen Sie diese Methode, um eine Zeichenfolge an den aktuellen Pfad angefügt werden soll.|  
|[CPathT::BuildRoot](#buildroot)|Rufen Sie diese Methode, um einen Stammpfad einer bestimmten Laufwerknummer zu erstellen.|  
|[CPathT::Canonicalize](#canonicalize)|Rufen Sie diese Methode zum Konvertieren des Pfads in kanonische Form.|  
|[CPathT::Combine](#combine)|Rufen Sie diese Methode zum Verketten einer Zeichenfolge, die einen Verzeichnisnamen darstellt und eine Zeichenfolge, die einen Dateinamen für den Pfad zu einem Pfad darstellt.|  
|[CPathT::CommonPrefix](#commonprefix)|Rufen Sie diese Methode, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix und den aktuellen Pfad gemeinsam verwendet wird.|  
|[CPathT::CompactPath](#compactpath)|Rufen Sie diese Methode, um einen Dateipfad an einen bestimmten Pixelbreite angepasst durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abgeschnitten.|  
|[CPathT::CompactPathEx](#compactpathex)|Rufen Sie diese Methode, um einen Dateipfad an innerhalb einer bestimmten Anzahl von Zeichen ersetzen Pfadkomponenten mit Auslassungspunkten abgeschnitten.|  
|[CPathT::FileExists](#fileexists)|Rufen Sie diese Methode, um zu überprüfen, ob die Datei unter diesem Pfadnamen vorhanden ist.|  
|[CPathT::FindExtension](#findextension)|Rufen Sie diese Methode, um die Position von der Erweiterung in diesem Pfad suchen.|  
|[CPathT::FindFileName](#findfilename)|Rufen Sie diese Methode, um die Position des Dateinamens im Pfad gefunden.|  
|[CPathT::GetDriveNumber](#getdrivenumber)|Rufen Sie diese Methode, um die Suche des Pfads für einen Laufwerkbuchstaben innerhalb des Bereichs von "A" bis "Z", und geben Sie die entsprechenden Laufwerknummer zurück.|  
|[CPathT::GetExtension](#getextension)|Rufen Sie diese Methode, um die Erweiterung aus dem Pfad zu erhalten.|  
|[CPathT::IsDirectory](#isdirectory)|Rufen Sie diese Methode, um zu überprüfen, ob der Pfad ein gültiges Verzeichnis ist.|  
|[CPathT::IsFileSpec](#isfilespec)|Rufen Sie diese Methode, um einen Pfad für alle Zeichen zur Einschränkung der Pfad zu suchen (z. B. ":" oder "\\"). Wenn keine Zeichen begrenzen von Pfad vorhanden sind, gilt der Pfad einer Dateispezifikation-Pfad sein.|  
|[CPathT::IsPrefix](#isprefix)|Rufen Sie diese Methode, um zu bestimmen, ob ein Pfad ein gültiges Präfix des Typs übergebenes enthält `pszPrefix`.|  
|[CPathT::IsRelative](#isrelative)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad relativ ist.|  
|[CPathT::IsRoot](#isroot)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad ein Stammverzeichnis ist.|  
|[CPathT::IsSameRoot](#issameroot)|Rufen Sie diese Methode, um zu bestimmen, ob ein anderer Pfad eine allgemeine Stammkomponente mit den aktuellen Pfad hat.|  
|[CPathT::IsUNC](#isunc)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für einen Server und freigeben.|  
|[CPathT::IsUNCServer](#isuncserver)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad für einen Server nur einen gültigen UNC (universal naming Convention)-Pfad ist.|  
|[CPathT::IsUNCServerShare](#isuncservershare)|Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen Freigabepfad UNC (universal naming Convention) ist \\ \  *Server*\ *freigeben*.|  
|[CPathT::MakePretty](#makepretty)|Rufen Sie diese Methode, um einen Pfad, um dem Pfad ein einheitliches Erscheinungsbild verleihen alle Kleinbuchstaben konvertieren.|  
|[CPathT::MatchSpec](#matchspec)|Rufen Sie diese Methode, um den Pfad für eine Zeichenfolge mit einem Platzhalter-Übereinstimmungstyp zu suchen.|  
|[CPathT::QuoteSpaces](#quotespaces)|Rufen Sie diese Methode, um den Pfad in Anführungszeichen gesetzt werden, wenn er keine Leerzeichen enthält.|  
|[CPathT::RelativePathTo](#relativepathto)|Rufen Sie diese Methode, um einen relativen Pfad in eine andere aus einer Datei oder einen Ordner zu erstellen.|  
|[CPathT::RemoveArgs](#removeargs)|Rufen Sie diese Methode, um Befehlszeilenargumente aus dem Pfad zu entfernen.|  
|[CPathT::RemoveBackslash](#removebackslash)|Rufen Sie diese Methode, um den nachgestellten umgekehrten Schrägstrich aus dem Pfad zu entfernen.|  
|[CPathT::RemoveBlanks](#removeblanks)|Rufen Sie diese Methode, um alle führende und nachfolgende Leerzeichen aus dem Pfad zu entfernen.|  
|[CPathT::RemoveExtension](#removeextension)|Rufen Sie diese Methode, um die Dateierweiterung des Pfads zu entfernen, sofern vorhanden.|  
|[CPathT::RemoveFileSpec](#removefilespec)|Rufen Sie diese Methode, um den Pfad, den nachgestellten Dateinamen und einen umgekehrten Schrägstrich aufheben, wenn sie diese verfügt.|  
|[CPathT::RenameExtension](#renameextension)|Rufen Sie diese Methode, um die Erweiterung im Pfad durch eine neue Erweiterung zu ersetzen. Wenn Sie der Dateinamen keine Erweiterung enthält, wird die Erweiterung an das Ende der Zeichenfolge angefügt werden.|  
|[CPathT::SkipRoot](#skiproot)|Rufen Sie diese Methode, um einen Pfad, ignoriert der Laufwerkbuchstabe oder ein UNC-Dateifreigabe/Pfad Teilen zu analysieren.|  
|[CPathT::StripPath](#strippath)|Rufen Sie diese Methode zum Entfernen des Pfadteil des einen vollqualifizierten Pfad und Dateinamen ein.|  
|[CPathT::StripToRoot](#striptoroot)|Rufen Sie diese Methode, um alle Teile des Pfads außer Stammverzeichnisinformationen zu den entfernen.|  
|[CPathT::UnquoteSpaces](#unquotespaces)|Rufen Sie diese Methode, um das Anführungszeichen am Anfang und Ende eines Pfads zu entfernen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const StringType CPathT::operator &](#operator_const_stringtype_amp)|Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.|  
|[CPathT::operator StringType &](#operator_stringtype)|Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.|  
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
 **Header:** atlpath.h  
  
##  <a name="addbackslash"></a>CPathT::AddBackslash  
 Rufen Sie diese Methode zum Hinzufügen von eines umgekehrten Schrägstrich am Ende einer Zeichenfolge auf die richtige Syntax für einen Pfad zu erstellen. Wenn der Pfad bereits abschließenden umgekehrten Schrägstrich enthält, wird kein umgekehrter Schrägstrich hinzugefügt werden.  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561).  
  
##  <a name="addextension"></a>CPathT::AddExtension  
 Rufen Sie diese Methode, um ein Pfad eine Dateierweiterung hinzugefügt werden.  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Parameter  
 `pszExtension`  
 Die Dateierweiterung hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).  
  
##  <a name="append"></a>CPathT::Append  
 Rufen Sie diese Methode, um eine Zeichenfolge an den aktuellen Pfad angefügt werden soll.  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Parameter  
 `pszMore`  
 Die anzufügende Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).  
  
##  <a name="buildroot"></a>CPathT::BuildRoot  
 Rufen Sie diese Methode, um einen Stammpfad einer bestimmten Laufwerknummer zu erstellen.  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>Parameter  
 *iDrive*  
 Die Laufwerknummer (0 ist A:, 1 ist, B:, usw.).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).  
  
##  <a name="canonicalize"></a>CPathT::Canonicalize  
 Rufen Sie diese Methode zum Konvertieren des Pfads in kanonische Form.  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).  
  
##  <a name="combine"></a>CPathT::Combine  
 Rufen Sie diese Methode zum Verketten einer Zeichenfolge, die einen Verzeichnisnamen darstellt und eine Zeichenfolge, die einen Dateinamen für den Pfad zu einem Pfad darstellt.  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>Parameter  
 `pszDir`  
 Der Verzeichnispfad.  
  
 *pszFile*  
 Der Dateipfad.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).  
  
##  <a name="commonprefix"></a>CPathT::CommonPrefix  
 Rufen Sie diese Methode, um zu bestimmen, ob der angegebene Pfad ein gemeinsames Präfix und den aktuellen Pfad gemeinsam verwendet wird.  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>Parameter  
 `pszOther`  
 Der Pfad zu der mit dem aktuellen Objekt verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das gemeinsame Präfix zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ein Präfix ist einem der folgenden Typen: "" c: "\\\\",".","..",".. \\\\". Weitere Informationen finden Sie unter [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).  
  
##  <a name="compactpath"></a>CPathT::CompactPath  
 Rufen Sie diese Methode, um einen Dateipfad an einen bestimmten Pixelbreite angepasst durch Ersetzen von Pfadkomponenten mit Auslassungspunkten abgeschnitten.  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Der Gerätekontext für Schriftarteigenschaften verwendet.  
  
 `nWidth`  
 Die Breite in Pixel, die die Zeichenfolge ist zu groß für erzwungen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).  
  
##  <a name="compactpathex"></a>CPathT::CompactPathEx  
 Rufen Sie diese Methode, um einen Dateipfad an innerhalb einer bestimmten Anzahl von Zeichen ersetzen Pfadkomponenten mit Auslassungspunkten abgeschnitten.  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxChars`  
 Die maximale Anzahl von Zeichen, die in die neue Zeichenfolge, einschließlich des abschließenden NULL-Zeichens enthalten sein.  
  
 `dwFlags`  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).  
  
##  <a name="cpatht"></a>CPathT::CPathT  
 Der Konstruktor.  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pszPath*  
 Der Zeiger auf einer Pfadzeichenfolge.  
  
 *path*  
 Die Pfadzeichenfolge.  
  
##  <a name="fileexists"></a>CPathT::FileExists  
 Rufen Sie diese Methode, um zu überprüfen, ob die Datei unter diesem Pfadnamen vorhanden ist.  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Datei "false" vorhanden, andernfalls ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).  
  
##  <a name="findextension"></a>CPathT::FindExtension  
 Rufen Sie diese Methode, um die Position von der Erweiterung in diesem Pfad suchen.  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position der "." vor der Erweiterung. Wenn keine Erweiterung gefunden wird, gibt-1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).  
  
##  <a name="findfilename"></a>CPathT::FindFileName  
 Rufen Sie diese Methode, um die Position des Dateinamens im Pfad gefunden.  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Dateinamens. Wenn kein Dateiname gefunden wird, gibt-1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).  
  
##  <a name="getdrivenumber"></a>CPathT::GetDriveNumber  
 Rufen Sie diese Methode, um die Suche des Pfads für einen Laufwerkbuchstaben innerhalb des Bereichs von "A" bis "Z", und geben Sie die entsprechenden Laufwerknummer zurück.  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Laufwerknummer als ganze Zahl von 0 bis 25 (entspricht "A" bis "Z") ein, wenn der Pfad einen Laufwerkbuchstaben oder-1 enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).  
  
##  <a name="getextension"></a>CPathT::GetExtension  
 Rufen Sie diese Methode, um die Erweiterung aus dem Pfad zu erhalten.  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Dateierweiterung an.  
  
##  <a name="isdirectory"></a>CPathT::IsDirectory  
 Rufen Sie diese Methode, um zu überprüfen, ob der Pfad ein gültiges Verzeichnis ist.  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich Null (16) zurück, wenn der Pfad ein Verzeichnis ist `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).  
  
##  <a name="isfilespec"></a>CPathT::IsFileSpec  
 Rufen Sie diese Methode, um einen Pfad für alle Zeichen zur Einschränkung der Pfad zu suchen (z. B. ":" oder "\\"). Wenn keine Zeichen begrenzen von Pfad vorhanden sind, gilt der Pfad einer Dateispezifikation-Pfad sein.  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn keine Zeichen begrenzen von Pfad innerhalb des Pfads vorhanden sind, oder "false", wenn Zeichen begrenzen von Pfad vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).  
  
##  <a name="isprefix"></a>CPathT::IsPrefix  
 Rufen Sie diese Methode, um zu bestimmen, ob ein Pfad ein gültiges Präfix des Typs übergebenes enthält `pszPrefix`.  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrefix`  
 Das Präfix, nach dem gesucht werden soll. Ein Präfix ist einem der folgenden Typen: "" c: "\\\\",".","..",".. \\\\".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Pfad des Präfixes oder "false" enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).  
  
##  <a name="isrelative"></a>CPathT::IsRelative  
 Rufen Sie diese Methode, um zu bestimmen, ob der Pfad relativ ist.  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Pfad relativ oder "false" ist, wenn es absolut ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).  
  
##  <a name="isroot"></a>CPathT::IsRoot  
 Rufen Sie diese Methode, um zu bestimmen, ob der Pfad ein Stammverzeichnis ist.  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Pfad einer Stamm- oder "false" ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).  
  
##  <a name="issameroot"></a>CPathT::IsSameRoot  
 Rufen Sie diese Methode, um zu bestimmen, ob ein anderer Pfad eine allgemeine Stammkomponente mit den aktuellen Pfad hat.  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pszOther`  
 Der andere Pfad.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn beide Zeichenfolgen die gleichen Stammkomponente oder "false" haben.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).  
  
##  <a name="isunc"></a>CPathT::IsUNC  
 Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen UNC (universal naming Convention)-Pfad für einen Server und freigeben.  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Pfad einen gültigen UNC-Pfad oder "false" ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).  
  
##  <a name="isuncserver"></a>CPathT::IsUNCServer  
 Rufen Sie diese Methode, um zu bestimmen, ob der Pfad für einen Server nur einen gültigen UNC (universal naming Convention)-Pfad ist.  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Zeichenfolge eine gültige UNC-Pfad für nur einen Server (keine Freigabename) oder "false" ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).  
  
##  <a name="isuncservershare"></a>CPathT::IsUNCServerShare  
 Rufen Sie diese Methode, um zu bestimmen, ob der Pfad einen gültigen Freigabepfad UNC (universal naming Convention) ist \\ \  *Server*\ *freigeben*.  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Pfad im Format \\ \  *Server*\ *freigeben*, oder "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).  
  
##  <a name="m_strpath"></a>CPathT::m_strPath  
 Der Pfad.  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>Hinweise  
 `StringType`der Vorlagenparameter ist `CPathT`.  
  
##  <a name="makepretty"></a>CPathT::MakePretty  
 Rufen Sie diese Methode, um einen Pfad, um dem Pfad ein einheitliches Erscheinungsbild verleihen alle Kleinbuchstaben konvertieren.  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zurück, andernfalls "true", wenn der Pfad konvertiert wurde, oder "false".  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).  
  
##  <a name="matchspec"></a>CPathT::MatchSpec  
 Rufen Sie diese Methode, um den Pfad für eine Zeichenfolge mit einem Platzhalter-Übereinstimmungstyp zu suchen.  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pszSpec`  
 Zeiger auf eine Null-terminierte Zeichenfolge mit den Dateityp für die Suche. Beispielsweise, um zu testen, ob die Datei unter dem aktuellen Pfad einer DOC-Datei `pszSpec` sollte festgelegt werden, auf "* .doc".  
  
### <a name="return-value"></a>Rückgabewert  
 Zurück, andernfalls "true", falls die Zeichenfolge übereinstimmt, oder "false".  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).  
  
##  <a name="operator_add_eq"></a>CPathT::operator +=  
 Dieser Operator Fügt eine Zeichenfolge in den Pfad an.  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>Parameter  
 `pszMore`  
 Die anzufügende Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten Pfad zurück.  
  
##  <a name="operator_const_stringtype_amp"></a>Const StringType CPathT::operator&amp;  
 Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Zeichenfolge, die den aktuellen Pfad von diesem Objekt verwaltet darstellt.  
  
##  <a name="operator_cpatht__pcxstr"></a>CPathT::operator CPathT::PCXSTR  
 Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Zeichenfolge, die den aktuellen Pfad von diesem Objekt verwaltet darstellt.  
  
##  <a name="operator_stringtype__amp"></a>CPathT::operator StringType&amp;  
 Mithilfe dieses Operators können das Objekt, z. B. eine Zeichenfolge behandelt werden.  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Zeichenfolge, die den aktuellen Pfad von diesem Objekt verwaltet darstellt.  
  
##  <a name="pcxstr"></a>CPathT::PCXSTR  
 Eine Konstante Zeichenfolge-Typ.  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>Hinweise  
 `StringType`der Vorlagenparameter ist `CPathT`.  
  
##  <a name="pxstr"></a>CPathT::PXSTR  
 Ein String-Datentyp.  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>Hinweise  
 `StringType`der Vorlagenparameter ist `CPathT`.  
  
##  <a name="quotespaces"></a>CPathT::QuoteSpaces  
 Rufen Sie diese Methode, um den Pfad in Anführungszeichen gesetzt werden, wenn er keine Leerzeichen enthält.  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).  
  
##  <a name="relativepathto"></a>CPathT::RelativePathTo  
 Rufen Sie diese Methode, um einen relativen Pfad in eine andere aus einer Datei oder einen Ordner zu erstellen.  
  
```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFrom`  
 Der Anfang der relative Pfad.  
  
 *dwAttrFrom*  
 Die Dateiattribute der `pszFrom`. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY, enthält `pszFrom` angenommenen, um ein Verzeichnis handeln, andernfalls `pszFrom` wird davon ausgegangen, dass eine Datei sein.  
  
 `pszTo`  
 Der Endpunkt, der den relativen Pfad.  
  
 *dwAttrTo*  
 Die Dateiattribute der `pszTo`. Wenn dieser Wert FILE_ATTRIBUTE_DIRECTORY, enthält `pszTo` angenommenen, um ein Verzeichnis handeln, andernfalls `pszTo` wird davon ausgegangen, dass eine Datei sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).  
  
##  <a name="removeargs"></a>CPathT::RemoveArgs  
 Rufen Sie diese Methode, um Befehlszeilenargumente aus dem Pfad zu entfernen.  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).  
  
##  <a name="removebackslash"></a>CPathT::RemoveBackslash  
 Rufen Sie diese Methode, um den nachgestellten umgekehrten Schrägstrich aus dem Pfad zu entfernen.  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).  
  
##  <a name="removeblanks"></a>CPathT::RemoveBlanks  
 Rufen Sie diese Methode, um alle führende und nachfolgende Leerzeichen aus dem Pfad zu entfernen.  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).  
  
##  <a name="removeextension"></a>CPathT::RemoveExtension  
 Rufen Sie diese Methode, um die Dateierweiterung des Pfads zu entfernen, sofern vorhanden.  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).  
  
##  <a name="removefilespec"></a>CPathT::RemoveFileSpec  
 Rufen Sie diese Methode, um den Pfad, den nachgestellten Dateinamen und einen umgekehrten Schrägstrich aufheben, wenn sie diese verfügt.  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).  
  
##  <a name="renameextension"></a>CPathT::RenameExtension  
 Rufen Sie diese Methode, um die Erweiterung im Pfad durch eine neue Erweiterung zu ersetzen. Wenn Sie der Dateinamen keine Erweiterung enthält, wird die Erweiterung bis zum Ende des Pfads angefügt werden.  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>Parameter  
 `pszExtension`  
 Die neue Dateinamenerweiterung vorangestellt wird, wird ein "." Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).  
  
##  <a name="skiproot"></a>CPathT::SkipRoot  
 Rufen Sie diese Methode, um einen Pfad, ignoriert der Laufwerkbuchstabe oder UNC (universal naming Convention)-Server-Freigabe Pfad Teile zu analysieren.  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Anfangs des untergeordnete Pfads, der den Stamm (Laufwerkbuchstaben oder UNC-Serverfreigabe) folgt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).  
  
##  <a name="strippath"></a>CPathT::StripPath  
 Rufen Sie diese Methode zum Entfernen des Pfadteil des einen vollqualifizierten Pfad und Dateinamen ein.  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).  
  
##  <a name="striptoroot"></a>CPathT::StripToRoot  
 Rufen Sie diese Methode, um alle Teile des Pfads außer Stammverzeichnisinformationen zu den entfernen.  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true", wenn auf einen gültigen Laufwerkbuchstaben gefunden wurde im Pfad, oder "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).  
  
##  <a name="unquotespaces"></a>CPathT::UnquoteSpaces  
 Rufen Sie diese Methode, um das Anführungszeichen am Anfang und Ende eines Pfads zu entfernen.  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).  
  
##  <a name="xchar"></a>CPathT::XCHAR  
 Ein Zeichentyp.  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>Hinweise  
 `StringType`der Vorlagenparameter ist `CPathT`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)