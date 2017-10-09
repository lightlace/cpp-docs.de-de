---
title: Von MFC und ATL freigegebenen Klassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 5e74a0fb32a9f0dc95837b9c8d633001ac79da8a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="classes-shared-by-mfc-and-atl"></a>Von MFC und ATL freigegebenen Klassen
Die folgende Tabelle enthält die Klassen, die gemeinsam von MFC und ATL  
  
|Klasse|Beschreibung|Headerdatei|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Stellt Methoden zur Verwaltung der Datum und Uhrzeit-Werte, die mit einer Datei verknüpften bereit.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Stellt Methoden zum Verwalten von relativen Datums- und Uhrzeitwerten, die mit einer Datei verknüpften bereit.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Stellt ein Zeichenfolgenobjekt mit einer festen Zeichenpuffer dar.|CStringT.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Bietet erweiterte Bitmapunterstützung, einschließlich der Möglichkeit zum Laden und speichern Sie die Bilder in JPEG, GIF, BMP und Portable Network Graphics (PNG).|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Kapselt die **Datum** -Datentyp in OLE-Automatisierung verwendet.|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Stellt eine relative Zeit, eine Zeitspanne dar.|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Eine Klasse ähnelt der Windows [Punkt](../../mfc/reference/point-structure1.md) -Struktur, die Memberfunktionen zum Bearbeiten von der ereignissteuerung `CPoint` und **Punkt** Strukturen.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Eine Klasse ähnelt der Windows [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die Memberfunktionen zum Bearbeiten von der ereignissteuerung `CRect` Objekte und Windows `RECT` Strukturen.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Stellt eine `CSimpleStringT` Objekt.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Eine Klasse, die ähnlich der Größe der Windows-Struktur, die eine relative Koordinate oder Position implementiert.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Stellt die automatische ressourcenbereinigung für `GetBuffer` und `ReleaseBuffer` aufruft, die auf einer vorhandenen `CStringT` Objekt.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Stellt die Daten von einem String-Objekt.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Stellt eine `CStringT` Objekt.|CStringT.h (MFC-abhängig) atlstr.h (MFC-unabhängig)|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Stellt eine absolute Uhrzeit und Datum.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Eine Zeitspanne, die als die Anzahl der Sekunden, in dem Zeitraum intern gespeichert werden.|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Stellt die Schnittstelle, um eine `CStringT` Speicher-Manager.|atlsimpstr.h|  
  
## <a name="see-also"></a>Siehe auch  
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



