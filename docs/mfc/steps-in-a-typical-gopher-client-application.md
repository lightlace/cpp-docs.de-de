---
title: Schritte in einer typischen Gopher-Clientanwendung
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 123b8abd2ca65356c584fa52f9415504bcb701c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486423"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Schritte in einer typischen Gopher-Clientanwendung

Die folgende Tabelle zeigt die Schritte, dass Sie in einer typischen Gopher-Clientanwendung durchführen können.

|Ihr Ziel|Maßnahmen ergreifen|Effekte|
|---------------|----------------------|-------------|
|Eine Gophersitzung zu beginnen.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|
|Verbinden Sie mit einem Gopher-Server.|Verwendung [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Gibt eine [CGopherConnection](../mfc/reference/cgopherconnection-class.md) Objekt.|
|Suchen Sie die erste Ressource im Gopher.|Verwendung [CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile).|Sucht nach der ersten Datei aus. Gibt FALSE zurück, wenn keine Dateien gefunden werden.|
|Suchen Sie im Gopher der nächsten Ressource.|Verwendung [CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Sucht nach der nächsten Datei. Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|
|Öffnen Sie die Datei gefundenen `FindFile` oder `FindNextFile` zum Lesen.|Abrufen ein Gopher-Locators mit [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Verwendung [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Öffnet die Datei, die durch den Locator angegeben. `OpenFile` Gibt eine [CGopherFile](../mfc/reference/cgopherfile-class.md) Objekt.|
|Öffnen Sie eine Datei mit einem Gopher-Locator, die, den Sie angeben.|Erstellen Sie mithilfe von [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator). Verwendung [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Öffnet die Datei, die durch den Locator angegeben. `OpenFile` Gibt eine [CGopherFile](../mfc/reference/cgopherfile-class.md) Objekt.|
|Aus der Datei gelesen.|Verwendung [CGopherFile](../mfc/reference/cgopherfile-class.md).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers, die, das Sie angeben.|
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Alle allgemeine Arten von Internet-Ausnahme behandelt werden.|
|Beenden Sie die Gophersitzung.|Löschen der [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt offenen Dateihandles und Verbindungen.|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
