---
title: Klasse CGopherLocator | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- gopher locator
- CGopherLocator class
- Internet, gopher searches
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: 22
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
ms.openlocfilehash: c5c9b862714d046bc81a49dda27fd5fc062b9ba8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherlocator-class"></a>CGopherLocator-Klasse
Ruft einen Gopher-"Locator" von einem Gopherserver zu ab und bestimmt den Locatortyp macht den Locator zur [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da nicht unter Windows XP funktionieren, aber sie werden weiterhin auf frühere Plattformen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Erstellt ein `CGopherLocator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Analysiert einen Gopher-Locator und seine Attribute bestimmt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Greift direkt in gespeicherten Zeichen auf ein `CGopherLocator` Objekt als Zeichenfolge im C-Format.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung muss einem Gopherserver Locator abrufen, bevor Informationen von diesem Server abgerufen werden können. Sobald den Locator vorliegt, müssen sie den Locator als nicht transparente Token behandeln.  
  
 Jede Gopher-Locator enthält Attribute, die bestimmen den Typ der Datei oder Server gefunden. Finden Sie unter [GetLocatorType](#getlocatortype) eine Liste der Gopher-Locator-Typen.  
  
 Normalerweise verwendet eine Anwendung den Locator für Aufrufe von [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) bestimmte Informationen abrufen.  
  
 Weitere Informationen zur Verwendung `CGopherLocator` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherlocator"></a>CGopherLocator::CGopherLocator  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CGopherLocator` Objekt.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>Parameter  
 `ref`  
 Ein Verweis auf eine Konstante `CGopherLocator` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGopherLocator` direkt. Rufen Sie stattdessen [CGopherConnection:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) erstellen und Zurückgeben der einen Zeiger auf die `CGopherLocator` Objekt.  
  
##  <a name="getlocatortype"></a>CGopherLocator::GetLocatorType  
 Rufen Sie diese Memberfunktion zum Abrufen des URL-Typs.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwRef*  
 Ein Verweis auf eine `DWORD` , erhalten den Locatortyp. Finden Sie unter **Hinweise** für eine Tabelle der locatortypen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die möglichen Typen lauten wie folgt:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Eine ASCII-Textdatei.|  
|GOPHER_TYPE_DIRECTORY|Ein Verzeichnis der zusätzlichen Gopher-Elemente.|  
|GOPHER_TYPE_CSO|Ein CSO Telefonbuch-Server.|  
|GOPHER_TYPE_ERROR|Gibt einen Fehler.|  
|GOPHER_TYPE_MAC_BINHEX|Eine Macintoshdatei im BINHEX-Format.|  
|GOPHER_TYPE_DOS_ARCHIVE|Eine DOS-Archivdatei.|  
|GOPHER_TYPE_UNIX_UUENCODED|Eine UUENCODED-Datei.|  
|GOPHER_TYPE_INDEX_SERVER|Ein Indexserver.|  
|GOPHER_TYPE_TELNET|Ein Telnet-Server.|  
|GOPHER_TYPE_BINARY|Eine Binärdatei.|  
|GOPHER_TYPE_REDUNDANT|Ein doppelter Server. Die enthaltenen Informationen ist ein Duplikat des primären Servers. Der primäre Server ist dem letzten Verzeichniseintrag, der nicht über ein GOPHER_TYPE_REDUNDANT verfügt.|  
|GOPHER_TYPE_TN3270|Ein TN3270-Server.|  
|GOPHER_TYPE_GIF|Eine GIF-Datei.|  
|GOPHER_TYPE_IMAGE|Eine Bilddatei.|  
|GOPHER_TYPE_BITMAP|Eine Bitmapdatei.|  
|GOPHER_TYPE_MOVIE|Eine Movie-Datei.|  
|GOPHER_TYPE_SOUND|Eine Audiodatei.|  
|GOPHER_TYPE_HTML|Ein HTML-Dokument.|  
|GOPHER_TYPE_PDF|Eine PDF-Datei.|  
|GOPHER_TYPE_CALENDAR|Ein Kalenderdatei.|  
|GOPHER_TYPE_INLINE|Eine Inlinedatei.|  
|GOPHER_TYPE_UNKNOWN|Der Elementtyp ist unbekannt.|  
|GOPHER_TYPE_ASK|Ein Ask-Element.|  
|GOPHER_TYPE_GOPHER_PLUS|Ein Gopher-Element.|  
  
##  <a name="operator_lpctstr"></a>CGopherLocator::operator LPCTSTR  
 Dieser nützliche Umwandlungsoperator bietet eine effiziente Methode für den Zugriff auf die Null-terminierte C-Zeichenfolge enthalten, die einem `CGopherLocator` Objekt.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger von der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Es werden keine Zeichen kopiert. nur ein Zeiger zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)

