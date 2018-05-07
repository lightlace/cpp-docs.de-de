---
title: CGopherFile-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98fa4b2a489b8abb3951719dc74e618a054a4025
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherfile-class"></a>CGopherFile-Klasse
Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da sie nicht auf Windows XP-Plattform funktionieren, jedoch wird auf älteren Plattformen funktionieren weiterhin.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Erstellt ein `CGopherFile`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Gopher-Dienst können Benutzer Daten in einem Gopherdatei zu schreiben, da dieser Dienst hauptsächlich als menügesteuerten-Schnittstelle für die Suche nach Informationen Funktionen nicht. Die `CGopherFile` Memberfunktionen **schreiben**, `WriteString`, und `Flush` nicht implementiert werden `CGopherFile`. Diese Funktionen aufrufen, auf eine `CGopherFile` -Objekt gibt ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Erfahren Sie mehr darüber, wie `CGopherFile` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherFile` Objekt.  
  
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
 Ein Handle für ein `HINTERNET` Datei.  
  
 `refLocator`  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 `pConnection`  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.  
  
 `hSession`  
 Ein Handle für die aktuelle Internet-Sitzung.  
  
 `pstrLocator`  
 Ein Zeiger auf eine Zeichenfolge, mit der Gopherserver zu suchen. Finden Sie unter [Gopher-Sitzungen](cgopherlocator-class.md) für Weitere Informationen zu Gopher-Locators.  
  
 *dwLocLen*  
 Einen DWORD-Wert mit der Anzahl der Bytes im `pstrLocator`.  
  
 `dwContext`  
 Ein Zeiger auf die Kontext-ID der Datei geöffnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen eine `CGopherFile` Objekt, das während einer Sitzung des Gopher Internet aus einer Datei gelesen.  
  
 Erstellen Sie nie eine `CGopherFile` -Objekts direkt. Rufen Sie stattdessen [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) , eine Datei auf einem Gopherserver zu öffnen.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)
