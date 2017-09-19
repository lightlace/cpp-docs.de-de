---
title: CGopherFile-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- gopher protocol files
- Internet, gopher
- CGopherFile class
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 40c1e385d0f58095c2aa79cc23168fc00f48ed9b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfile-class"></a>CGopherFile-Klasse
Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da nicht unter Windows XP funktionieren, aber sie werden weiterhin auf frühere Plattformen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Erstellt ein `CGopherFile`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Gopher-Dienst ermöglicht dem Benutzer Daten in eine Gopherdatei zu schreiben, da dieser Dienst hauptsächlich als ein Benutzermenü zum Suchen von Informationen Funktionen nicht. Die `CGopherFile` Memberfunktionen **schreiben**, `WriteString`, und `Flush` nicht implementiert sind `CGopherFile`. Diese Funktionen aufrufen, auf eine `CGopherFile` -Objekt gibt ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Weitere Informationen zur Verwendung `CGopherFile` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CGopherFile` Objekt.  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>Parameter  
 `hFile`  
 Ein Handle für eine `HINTERNET` Datei.  
  
 `refLocator`  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 `pConnection`  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.  
  
 `hSession`  
 Ein Handle für die aktuelle Internet-Sitzung.  
  
 `pstrLocator`  
 Ein Zeiger auf eine Zeichenfolge verwendet, um den Gopher-Server zu suchen. Finden Sie unter [Gopher-Sitzungen](https://msdn.microsoft.com/library/24wz8xze.aspx) Weitere Informationen zu Gopher-Locators.  
  
 *dwLocLen*  
 Einen DWORD-Wert mit der Anzahl der Bytes im `pstrLocator`.  
  
 `dwContext`  
 Ein Zeiger auf die Kontext-ID, der die zu öffnende Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen ein `CGopherFile` -Objekt, das während einer Gopher-Internet-Sitzung aus einer Datei gelesen.  
  
 Erstellen Sie nie eine `CGopherFile` direkt. Rufen Sie stattdessen [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) beim Öffnen einer Datei auf einem Gopherserver.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)

