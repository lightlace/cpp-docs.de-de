---
title: Die Schritte in einer Typischen Internetclientanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd3dde01d87fccd1d19d947a1069fa92675e6053
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390341"
---
# <a name="steps-in-a-typical-internet-client-application"></a>Schritte in einer typischen Internetclientanwendung

Die folgende Tabelle zeigt die Schritte, dass Sie in einer typischen Internetclientanwendung ausführen können.

|Ihr Ziel|Maßnahmen ergreifen|Effekte|
|---------------|----------------------|-------------|
|Beginnen Sie eine internetsitzung.|Erstellen Sie eine [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|
|Legen Sie eine Internet-Abfrageoption (Timeouts oder Anzahl von Wiederholungen, z. B.).|Verwendung [CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Gibt FALSE zurück, wenn der Vorgang nicht erfolgreich war.|
|Stellen Sie eine Callback-Funktion zum Überwachen des Status der Sitzung her.|Verwendung [CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Richtet einen Rückruf zum [CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Außer Kraft setzen `OnStatusCallback` eigene Rückrufroutine zu erstellen.|
|Verbinden Sie mit einer Internet-Server, Intranetservers oder lokale Datei.|Verwendung [OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Analysiert die URL ein, und öffnet eine Verbindung mit dem angegebenen Server. Gibt eine [CStdioFile](../mfc/reference/cstdiofile-class.md) (Wenn Sie übergeben `OpenURL` einen Namen für die lokale Datei). Dies ist das Objekt, das über dem Sie aus dem Server oder die Datei abgerufene Daten zugreifen.|
|Aus der Datei gelesen.|Verwendung [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers, die, das Sie angeben.|
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Alle allgemeine Arten von Internet-Ausnahme behandelt werden.|
|Beenden Sie die Internet-Sitzung.|Löschen der [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt offenen Dateihandles und Verbindungen.|

## <a name="see-also"></a>Siehe auch

[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
