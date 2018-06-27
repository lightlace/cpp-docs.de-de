---
title: WinInet-Grundlagen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7061c3203436197eb1bd03ae56058e0bd0f26f9d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955582"
---
# <a name="wininet-basics"></a>WinInet-Grundlagen
WinInet können Sie FTP-Unterstützung zum Herunterladen und Hochladen von Dateien von innerhalb der Anwendung hinzufügen. Sie können außer Kraft setzen [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) und Verwenden der *DwContext* Parameter zum Bereitstellen von Statusinformationen für Benutzer, wie Sie suchen und Herunterladen von Dateien.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Erstellen Sie einen sehr einfachen Browser](#_core_create_a_very_simple_browser)  
  
-   [Herunterladen einer Webseite](#_core_download_a_web_page)  
  
-   [Eine Datei mit FTP](#_core_ftp_a_file)  
  
-   [Gopher-Verzeichnis abrufen](#_core_retrieve_a_gopher_directory)  
  
-   [Anzeigen von Statusinformationen bei der Übertragung von Dateien](#_core_display_progress_information_while_transferring_files)  
  
 Die nachstehenden Codebeispiele veranschaulichen, wie Sie erstellen einen einfache Browser eine Webseite, eine Datei mit FTP herunter, und suchen Sie nach einem Gopherdatei. Sie sollen nicht als vollständige Beispiele, und nicht alle Ausnahmebehandlung enthalten.  
  
 Weitere Informationen über WinInet, finden Sie unter [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Erstellen Sie einen sehr einfachen Browser  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Herunterladen einer Webseite  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> Eine Datei mit FTP  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Gopher-Verzeichnis abrufen  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>OnStatusCallback verwenden  
 Wenn Sie die WinInet-Klassen verwenden, können Sie die [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) Mitglied Ihrer Anwendungsverzeichnis [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt zum Abrufen von Statusinformationen. Wenn Sie eine eigene ableiten `CInternetSession` Objekt außer Kraft, indem `OnStatusCallback`, und aktivieren Sie die Status-Rückrufe MFC aufgerufen wird Ihrer `OnStatusCallback` -Funktion mit Statusinformationen zu allen Aktivitäten in dieser Sitzung Internet.  
  
 Da es sich bei eine einzelne Sitzung möglicherweise mehrere Verbindungen (d. h. über ihre Lebensdauer viele verschiedene unterschiedliche Vorgänge ausführen können), unterstützt `OnStatusCallback` benötigt einen Mechanismus zum Identifizieren jeder statusänderung mit einer bestimmten Verbindung oder Transaktion. Dieser Mechanismus wird durch den Kontext-ID-Parameter übergeben, um viele der Memberfunktionen in der WinInet-Unterstützungsklassen bereitgestellt. Dieser Parameter ist immer vom Typ **DWORD** und immer mit dem Namen *DwContext*.  
  
 Der Kontext auf ein bestimmtes Internetobjekt zugewiesen dient nur zur Identifizierung der Aktivitäts, führt dazu, das Objekt in dass, der `OnStatusCallback` Mitglied der `CInternetSession` Objekt. Der Aufruf von `OnStatusCallback` empfängt mehrere Parameter; diese Parameter arbeiten zusammen, um Ihre Anwendung informieren, welche Bearbeitung für die Transaktion und die Verbindung hergestellt wurde.  
  
 Beim Erstellen einer `CInternetSession` -Objekt können Sie angeben einer *DwContext* Parameter an den Konstruktor übergibt. `CInternetSession` selbst verwenden nicht die Kontext-ID. Stattdessen wird die Kontext-ID an alle **InternetConnection**-abgeleitete Objekte, die nicht explizit eine Kontext-ID, Ihren eigenen erhalten. Im Gegenzug wird die `CInternetConnection` Objekte übergibt die Kontext-ID zusammen, `CInternetFile` Objekte, sofern Sie nicht explizit eine anderen Kontext-ID angeben Wenn andererseits, Sie angeben, dass eine bestimmte Kontext-ID Ihrer Wahl, das Objekt und jede Arbeit, die dies der Fall ist dieser Kontext-ID zugeordnet werden soll Können Sie identifizieren, welche Statusinformationen Ihnen in angegeben wird, wird den Kontext-IDs Ihrer `OnStatusCallback` Funktion.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Anzeigen von Statusinformationen bei der Übertragung von Dateien  
 Z. B. Wenn Sie eine Anwendung, die eine Verbindung mit einem FTP-Server zum Lesen einer Datei erstellt und auch eine Verbindung mit einem HTTP-Server Schreiben auf eine Webseite zu erhalten, stehen Ihnen eine `CInternetSession` -Objekt, das zwei `CInternetConnection` Objekte (eine wäre eine `CFtpSession` und die andere eine `CHttpSession`), und zwei `CInternetFile` Objekte (eine für jede Verbindung). Bei Verwendung der Standardwerte für die *DwContext* Parameter, Sie wären nicht zwischen unterscheiden, die `OnStatusCallback` Aufrufe, die Status für die FTP-Verbindung und die Aufrufe, die angeben, den Fortschritt der HTTP-Verbindung. Bei Angabe einer *DwContext* -ID, die Sie später in testen `OnStatusCallback`, wissen Sie, welcher Vorgang den Rückruf generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammiergrundlagen](../mfc/mfc-internet-programming-basics.md)   
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)

