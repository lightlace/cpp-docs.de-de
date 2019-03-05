---
title: Win32- Internetklassen
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: c067d0c0067ee13b0e6ce6d84fd97135274c88b5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260555"
---
# <a name="win32-internet-classes"></a>Win32- Internetklassen

MFC dient als Wrapper für die Win32-Internet (WinInet) und ActiveX-Technologie, um Internet-Programmierung zu erleichtern.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
Erstellt und initialisiert eine Internet-Sitzung oder mehrere gleichzeitige internetsitzungen und beschreibt ggf. die Verbindung mit einem Proxyserver.

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
Verwaltet die Verbindung mit einem Internetserver.

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
Diese Klasse und ihrer abgeleiteten Klassen können den Zugriff auf Dateien auf Remotesystemen, die Internetprotokolle verwenden.

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
Verwaltet die Verbindung mit einem HTTP-Server.

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
Bietet Funktionen zum Suchen und Lesen von Dateien auf einem HTTP-Server.

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
Verwaltet die Verbindung mit einem FTP-Server an.

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
Verwaltet die Verbindung zu einem Gopherserver.

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
Führt die lokale und internetdateisuchen.

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
Unterstützt die Internetsuche nach Dateien auf FTP-Servern.

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
Unterstützt die Internetsuche nach Dateien auf Gopherservern.

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
Ruft einen Gopher-"Locator" von einem Gopherserver ab, bestimmt den Locatortyp, und macht den Locator für `CGopherFileFind` verfügbar.

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
Stellt eine Ausnahmebedingung dar, die sich auf einen Internetvorgang bezieht.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
