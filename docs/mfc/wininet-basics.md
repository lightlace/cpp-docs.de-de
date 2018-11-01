---
title: WinInet-Grundlagen
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: f56d2bb6e6a0b49b3d69dbcc0bf6346b72e9f7b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519183"
---
# <a name="wininet-basics"></a>WinInet-Grundlagen

Sie können WinInet verwenden, um FTP-Unterstützung zum Herunterladen und Hochladen von Dateien aus Ihrer Anwendung hinzuzufügen. Sie können außer Kraft setzen [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) und verwenden Sie die *DwContext* Parameter, um Statusinformationen für Benutzer bereitzustellen, wie Sie suchen und Herunterladen von Dateien.

Dieser Artikel enthält die folgenden Themen:

- [Erstellen Sie einen sehr einfachen Browser](#_core_create_a_very_simple_browser)

- [Herunterladen einer Webseite](#_core_download_a_web_page)

- [Eine Datei mit FTP](#_core_ftp_a_file)

- [Abrufen von einem Gopher-Verzeichnis](#_core_retrieve_a_gopher_directory)

- [Anzeigen von Statusinformationen bei der Übertragung von Dateien](#_core_display_progress_information_while_transferring_files)

Die nachstehenden Codebeispiele veranschaulichen, wie ein einfacher Browser erstellt, eine Webseite, eine Datei mit FTP Herunterladen und suchen Sie nach einem Gopherdatei. Sie dienen nicht als vollständige Beispiele, und nicht alle der Behandlung von Ausnahmen enthalten.

Weitere Informationen über WinInet, finden Sie unter [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md).

##  <a name="_core_create_a_very_simple_browser"></a> Erstellen Sie einen sehr einfachen Browser

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

##  <a name="_core_download_a_web_page"></a> Herunterladen einer Webseite

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

##  <a name="_core_ftp_a_file"></a> Eine Datei mit FTP

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

##  <a name="_core_retrieve_a_gopher_directory"></a> Abrufen von einem Gopher-Verzeichnis

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback verwenden

Wenn Sie die WinInet-Klassen verwenden zu können, können Sie die [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) Mitglied Ihrer Anwendungsverzeichnis [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt, das Statusinformationen abzurufen. Wenn Sie eigene ableiten `CInternetSession` Objekt außer Kraft, `OnStatusCallback`, und aktivieren Sie die Status-Rückrufen, MFC ruft Ihre `OnStatusCallback` -Funktion mit Statusinformationen über alle Aktivitäten in der Internet-Sitzung.

Da die eine einzelne Sitzung möglicherweise mehrere Verbindungen (die im Laufe ihrer Lebensdauer, die viele verschiedene unterschiedliche Vorgänge ausführen, die möglicherweise), unterstützt `OnStatusCallback` benötigt einen Mechanismus zum Identifizieren jeder statusänderung eine bestimmte Verbindung oder Transaktion. Dieser Mechanismus wird durch die Kontext-ID-Parameter übergeben, um viele der Memberfunktionen in der WinInet-Unterstützungsklassen bereitgestellt. Dieser Parameter ist immer vom Typ **DWORD** und wird stets der Name *DwContext*.

Der Kontext, der auf ein bestimmtes Internetobjekt zugewiesen wird verwendet, nur für die Aktivität zu identifizieren, führt dazu, das Objekt in dass, der `OnStatusCallback` Mitglied der `CInternetSession` Objekt. Der Aufruf von `OnStatusCallback` erhält mehrere Parameter; diese Parameter arbeiten zusammen, um Ihre Anwendung anweisen, welche Bearbeitung für die Transaktion und die Verbindung erfolgt ist.

Bei der Erstellung einer `CInternetSession` -Objekt können Sie angeben einer *DwContext* Parameter des Konstruktors. `CInternetSession` selbst verwenden nicht die Kontext-ID. Stattdessen wird die Kontext-ID mit einem **InternetConnection**-abgeleiteten Objekte aus, die nicht explizit über eine Kontext-ID, Ihre eigenen erhalten. Im Gegenzug erhält die `CInternetConnection` Objekte werden die Kontext-ID zusammen, um übergeben `CInternetFile` Objekte, sie erstellen, wenn Sie nicht explizit eine anderen Kontext-ID angeben Wenn Sie auf der anderen Seite Sie angeben, dass es sich bei einem bestimmten Kontext-ID Ihrer eigenen, das Objekt und jede Arbeit, die dies der Fall ist, Kontext-ID zugeordnet werden soll Können Sie die Kontext-IDs um zu ermitteln, welche Statusinformationen übergeben wird, die Sie in Ihrem `OnStatusCallback` Funktion.

##  <a name="_core_display_progress_information_while_transferring_files"></a> Anzeigen von Statusinformationen bei der Übertragung von Dateien

Z. B. Wenn Sie eine Anwendung, die eine Verbindung mit einem FTP-Server zum Lesen einer Datei erstellt und eine Verbindung mit einem HTTP-Server schreiben, um eine Webseite zu erhalten, müssen Sie eine `CInternetSession` -Objekt, das zwei `CInternetConnection` Objekte (eine ein `CFtpSession` und die andere wäre eine `CHttpSession`), und zwei `CInternetFile` Objekte (eine für jede Verbindung). Bei Verwendung der Standardwerte für die *DwContext* Parameter, Sie wären nicht unterscheiden zwischen der `OnStatusCallback` Aufrufe, die angeben, wird ausgeführt, für die FTP-Verbindung und die Aufrufe, die angeben, wird ausgeführt, für die HTTP-Verbindung. Bei Angabe einer *DwContext* -ID, die Sie in einem späteren Zeitpunkt für testen können `OnStatusCallback`, wissen Sie, welcher Vorgang den Rückruf generiert.

## <a name="see-also"></a>Siehe auch

[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)

