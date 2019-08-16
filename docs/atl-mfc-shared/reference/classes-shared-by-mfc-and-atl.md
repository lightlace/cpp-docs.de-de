---
title: Von MFC und ATL freigegebenen Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: e3e4b35721e84e289aed586c4d010a6986dcc61c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491463"
---
# <a name="classes-shared-by-mfc-and-atl"></a>Von MFC und ATL freigegebenen Klassen

In der folgenden Tabelle sind die von MFC und ATL gemeinsam genutzten Klassen aufgeführt.

|Klasse|Beschreibung|Header Datei|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Stellt Methoden zum Verwalten der Datums-und Uhrzeitwerte bereit, die einer Datei zugeordnet sind.|atltime. h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Stellt Methoden für die Verwaltung relativer Datums-und Uhrzeitwerte bereit, die einer Datei zugeordnet sind.|atltime. h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Stellt ein Zeichen folgen Objekt mit einem Puffer fester Zeichen dar.|cstringt.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Bietet erweiterte Unterstützung für Bitmap, einschließlich der Möglichkeit, Bilder in JPEG-, GIF-, BMP-und Portable Network Graphics-Formaten (PNG) zu laden und zu speichern.|atlimage. h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Kapselt den in der OLE-Automatisierung verwendeten Datums Datentyp.|ATLComTime. h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Stellt eine relative Zeitspanne, eine Zeitspanne dar.|ATLComTime. h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Eine-Klasse, die der Windows- [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur ähnelt und auch Element Funktionen `CPoint` zum `POINT` Bearbeiten von-und-Strukturen einschließt.|atltypes. h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Eine-Klasse, die einer Windows- [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur ähnelt, die auch `CRect` Element Funktionen zum `RECT` Bearbeiten von Objekten und Windows-Strukturen enthält.|atltypes. h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Stellt ein `CSimpleStringT` -Objekt dar.|atlsimpstr. h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Eine-Klasse, die der Windows- [Größen](/windows/win32/api/windef/ns-windef-size) Struktur ähnelt, die eine relative Koordinate oder Position implementiert.|atltypes. h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Bietet eine automatische Ressourcen Bereinigung `GetBuffer` für `ReleaseBuffer` -und-Aufrufe `CStringT` für ein vorhandenes-Objekt.|atlsimpstr. h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Stellt die Daten eines Zeichen folgen Objekts dar.|atlsimpstr. h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Stellt ein `CStringT` -Objekt dar.|CStringT. h (MFC-abhängig) atlstr. h (MFC unabhängig)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Stellt eine absolute Uhrzeit und ein Datum dar.|atltime. h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Ein Zeitraum, der intern als die Anzahl der Sekunden in der Zeitspanne gespeichert wird.|atltime. h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Stellt die Schnittstelle zu `CStringT` einem Speicher-Manager dar.|atlsimpstr. h|

## <a name="see-also"></a>Siehe auch

[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
