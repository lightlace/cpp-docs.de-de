---
title: CGopherLocator Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 377708108f96a42d23dcf3aa5e8214d7bf9ffe5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366921"
---
# <a name="cgopherlocator-class"></a>CGopherLocator-Klasse
Ruft einen Gopher-"Locator" von einem Gopherserver zu ab, bestimmt den Locatortyp und macht den Locator für verfügbar [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da sie nicht auf Windows XP-Plattform funktionieren, jedoch wird auf älteren Plattformen funktionieren weiterhin.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Erstellt ein `CGopherLocator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Analysiert einen Gopher-Locator, und ihre Attribute bestimmt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Greift direkt in gespeicherten Zeichen auf eine `CGopherLocator` Objekt als Zeichenfolge im C-Format.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung muss einem Gopherserver Locator abrufen, bevor Sie Daten von diesem Server abgerufen werden können. Nach Anwendung des Locators verfügt, müssen sie als nicht transparenter Token des Locators behandeln.  
  
 Jede Gopher-Locator verfügt über Attribute, die bestimmen, den Typ der Datei bzw. dem Server gefunden. Finden Sie unter [GetLocatorType](#getlocatortype) eine Liste der Typen von Gopher-Locators.  
  
 Eine Anwendung verwendet normalerweise den Locator für Aufrufe von [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) um eine bestimmte Information abzurufen.  
  
 Erfahren Sie mehr darüber, wie `CGopherLocator` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherLocator` Objekt.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>Parameter  
 `ref`  
 Ein Verweis auf eine Konstante `CGopherLocator` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGopherLocator` -Objekts direkt. Rufen Sie stattdessen [CGopherConnection:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) erstellen und Zurückgeben der einen Zeiger auf die `CGopherLocator` Objekt.  
  
##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType  
 Rufen Sie diese Memberfunktion zum Abrufen des Locator-Typs.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwRef*  
 Ein Verweis auf eine `DWORD` erhalten, die die URL-Typ. Finden Sie unter **"Hinweise"** für eine Tabelle der locatortypen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die möglichen Typen lauten folgendermaßen:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Eine ASCII-Textdatei.|  
|GOPHER_TYPE_DIRECTORY|Zusätzliche Gopher-Elemente in einem Verzeichnis.|  
|GOPHER_TYPE_CSO|Ein CSO Telefonbuch-Server.|  
|GOPHER_TYPE_ERROR|Gibt eine fehlerbedingung an.|  
|GOPHER_TYPE_MAC_BINHEX|Eine BinHex-DECODIERTEN Format Macintoshdatei.|  
|GOPHER_TYPE_DOS_ARCHIVE|Eine DOS-Archivdatei.|  
|GOPHER_TYPE_UNIX_UUENCODED|Eine UUENCODED-Datei.|  
|GOPHER_TYPE_INDEX_SERVER|Ein Indexserver.|  
|GOPHER_TYPE_TELNET|Ein Telnet-Server.|  
|GOPHER_TYPE_BINARY|Eine Binärdatei.|  
|GOPHER_TYPE_REDUNDANT|Ein doppelt vorhandenen Server. Die enthaltenen Informationen ist ein Duplikat des primären Servers. Der primäre Server ist der letzten Verzeichniseintrag, der nicht über einen Typ GOPHER_TYPE_REDUNDANT verfügte.|  
|GOPHER_TYPE_TN3270|Ein TN3270-Server.|  
|GOPHER_TYPE_GIF|Eine GIF-Datei.|  
|GOPHER_TYPE_IMAGE|Eine Bilddatei.|  
|GOPHER_TYPE_BITMAP|Eine Bitmapdatei.|  
|GOPHER_TYPE_MOVIE|Eine Filmdatei.|  
|GOPHER_TYPE_SOUND|Eine Audiodatei.|  
|GOPHER_TYPE_HTML|Ein HTML-Dokument.|  
|GOPHER_TYPE_PDF|Eine PDF-Datei.|  
|GOPHER_TYPE_CALENDAR|Eine Datei dar.|  
|GOPHER_TYPE_INLINE|Eine Inlinedatei.|  
|GOPHER_TYPE_UNKNOWN|Der Elementtyp ist unbekannt.|  
|GOPHER_TYPE_ASK|Bitten Sie + Zielgruppenadressierungselement.|  
|GOPHER_TYPE_GOPHER_PLUS|Ein Gopher-Element.|  
  
##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR  
 Diese nützliche Typumwandlungsoperator bietet eine effiziente Methode für den Zugriff auf die Null-terminierte C-Zeichenfolge enthalten, die einem `CGopherLocator` Objekt.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger auf den String-Daten.  
  
### <a name="remarks"></a>Hinweise  
 Keine Zeichen kopiert werden; nur ein Zeiger zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)
