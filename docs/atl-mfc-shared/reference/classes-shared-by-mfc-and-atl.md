---
title: Von MFC und ATL freigegebenen Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 566164f40f8795c8402b04c9c25e13dda036961d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765436"
---
# <a name="classes-shared-by-mfc-and-atl"></a>Von MFC und ATL freigegebenen Klassen

Die folgende Tabelle enthält die von MFC und ATL freigegebenen Klassen

|Klasse|Beschreibung|Headerdatei|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Stellt Methoden für die Verwaltung von einer Datei zugeordneten Werte für Datum und Uhrzeit.|atltime.h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Stellt Methoden für die Verwaltung von relative Datum- und Zeitwerte, die einer Datei zugeordnet.|atltime.h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Stellt ein Zeichenfolgenobjekt mit einem festen Zeichenpuffer dar.|CStringT.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Bietet erweiterte Bitmapunterstützung, einschließlich der Möglichkeit zum Laden und Speichern von Bildern in JPEG, GIF, BMP und Portable Network Graphics (PNG).|atlimage.h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Kapselt die DATE-Datentyp in OLE-Automatisierung verwendet.|"atlcomtime.h"|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Stellt einen relativen Zeitpunkt, eine Zeitspanne dar.|"atlcomtime.h"|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Eine Klasse, die ähnlich wie die Windows [Punkt](../../mfc/reference/point-structure1.md) -Struktur, die Member-Funktionen zum Bearbeiten von der ereignissteuerung `CPoint` und `POINT` Strukturen.|atltypes.h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Eine Klasse, die ähnlich wie eine Windows [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die Member-Funktionen zum Bearbeiten von der ereignissteuerung `CRect` Objekte und Windows `RECT` Strukturen.|atltypes.h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Stellt eine `CSimpleStringT` Objekt.|atlsimpstr.h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Eine Klasse, die die Größe der Windows-Struktur, die eine relative Koordinate oder Position implementiert wird, ähnelt.|atltypes.h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Bietet automatische ressourcenbereinigung für `GetBuffer` und `ReleaseBuffer` Ruft für eine vorhandene `CStringT` Objekt.|atlsimpstr.h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Stellt die Daten von einem String-Objekt.|atlsimpstr.h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Stellt eine `CStringT` Objekt.|CStringT.h (MFC-abhängig) atlstr.h (MFC-unabhängig)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Stellt eine absolute Zeit und Datum dar.|atltime.h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Eine Zeitspanne, die intern als die Anzahl der Sekunden, in dem Zeitraum gespeichert ist.|atltime.h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Stellt die Schnittstelle zu einem `CStringT` Speicher-Manager.|atlsimpstr.h|

## <a name="see-also"></a>Siehe auch

[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

