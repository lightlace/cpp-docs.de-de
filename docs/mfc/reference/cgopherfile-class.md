---
title: CGopherFile-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: c6c4f87ffb1538e581320e9d6f36e8d4fbc6fc12
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335681"
---
# <a name="cgopherfile-class"></a>CGopherFile-Klasse
Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und deren Member sind veraltet, da, nicht auf der Windows XP-Plattform funktionieren, während sie weiterhin auf frühere Plattformen funktionieren.  
  
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
 Gopher-Dienst ist nicht zulässig, Daten in einer Gopherdatei zu schreiben, da für diesen Dienst hauptsächlich als menügesteuerten-Schnittstelle für die Suche nach Informationen Funktionen. Die `CGopherFile` Memberfunktionen `Write`, `WriteString`, und `Flush` sind nicht für implementiert `CGopherFile`. Diese Funktionen aufrufen, auf eine `CGopherFile` -Objekts gibt ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Weitere Informationen finden Sie `CGopherFile` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
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
 *hFile*  
 Ein Handle für eine HINTERNET-Datei.  
  
 *refLocator*  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 *pConnection*  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.  
  
 *hSession*  
 Ein Handle für die aktuelle Internet-Sitzung.  
  
 *pstrLocator*  
 Ein Zeiger auf eine Zeichenfolge, die zum Suchen des Gopher-Server verwendet. Finden Sie unter [Gopher-Sitzungen](cgopherlocator-class.md) für Weitere Informationen über das Gopher-Locators.  
  
 *dwLocLen*  
 Ein DWORD, das mit der Anzahl der Bytes im *PstrLocator*.  
  
 *dwContext*  
 Ein Zeiger auf den Kontextbezeichner, der die zu öffnende Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen eine `CGopherFile` Objekt, das während einer Sitzung des Gopher Internet aus einer Datei gelesen.  
  
 Erstellen Sie nie eine `CGopherFile` direkt. Rufen Sie stattdessen [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) zum Öffnen einer Datei auf einem Gopherserver.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)
