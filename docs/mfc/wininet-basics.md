---
title: WinInet-Grundlagen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3c9502c720b0f443ace3cfe637fb4826281ecf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wininet-basics"></a>WinInet-Grundlagen
WinInet können Sie FTP-Unterstützung zum Herunterladen und Hochladen von Dateien von innerhalb der Anwendung hinzufügen. Sie können außer Kraft setzen [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) und Verwenden der `dwContext` Parameter zum Bereitstellen von Statusinformationen für Benutzer, wie Sie suchen und Herunterladen von Dateien.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Erstellen Sie einen sehr einfachen Browser](#_core_create_a_very_simple_browser)  
  
-   [Herunterladen einer Webseite](#_core_download_a_web_page)  
  
-   [Eine Datei mit FTP](#_core_ftp_a_file)  
  
-   [Gopher-Verzeichnis abrufen](#_core_retrieve_a_gopher_directory)  
  
-   [Anzeigen von Statusinformationen bei der Übertragung von Dateien](#_core_display_progress_information_while_transferring_files)  
  
 Die nachstehenden Codebeispiele veranschaulichen, wie Sie erstellen einen einfache Browser eine Webseite, eine Datei mit FTP herunter, und suchen Sie nach einem Gopherdatei. Sie sollen nicht als vollständige Beispiele, und nicht alle Ausnahmebehandlung enthalten.  
  
 Weitere Informationen über WinInet, finden Sie unter [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a>Erstellen Sie einen sehr einfachen Browser  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a>Herunterladen einer Webseite  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a>Eine Datei mit FTP  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a>Gopher-Verzeichnis abrufen  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>OnStatusCallback verwenden  
 Wenn Sie die WinInet-Klassen verwenden, können Sie die [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) Mitglied Ihrer Anwendungsverzeichnis [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt zum Abrufen von Statusinformationen. Wenn Sie eine eigene ableiten `CInternetSession` Objekt außer Kraft, indem `OnStatusCallback`, und aktivieren Sie die Status-Rückrufe MFC aufgerufen wird Ihrer `OnStatusCallback` -Funktion mit Statusinformationen zu allen Aktivitäten in dieser Sitzung Internet.  
  
 Da es sich bei eine einzelne Sitzung möglicherweise mehrere Verbindungen (d. h. über ihre Lebensdauer viele verschiedene unterschiedliche Vorgänge ausführen können), unterstützt `OnStatusCallback` benötigt einen Mechanismus zum Identifizieren jeder statusänderung mit einer bestimmten Verbindung oder Transaktion. Dieser Mechanismus wird durch den Kontext-ID-Parameter übergeben, um viele der Memberfunktionen in der WinInet-Unterstützungsklassen bereitgestellt. Dieser Parameter ist immer vom Typ `DWORD` und immer mit dem Namen `dwContext`.  
  
 Der Kontext auf ein bestimmtes Internetobjekt zugewiesen dient nur zur Identifizierung der Aktivitäts, führt dazu, das Objekt in dass, der `OnStatusCallback` Mitglied der `CInternetSession` Objekt. Der Aufruf von `OnStatusCallback` empfängt mehrere Parameter; diese Parameter arbeiten zusammen, um Ihre Anwendung informieren, welche Bearbeitung für die Transaktion und die Verbindung hergestellt wurde.  
  
 Beim Erstellen einer `CInternetSession` -Objekt können Sie angeben einer `dwContext` Parameter an den Konstruktor übergibt. `CInternetSession`selbst verwenden nicht die Kontext-ID. Stattdessen wird die Kontext-ID an alle **InternetConnection**-abgeleitete Objekte, die nicht explizit eine Kontext-ID, Ihren eigenen erhalten. Im Gegenzug wird die `CInternetConnection` Objekte übergibt die Kontext-ID zusammen, `CInternetFile` Objekte, sofern Sie nicht explizit eine anderen Kontext-ID angeben Wenn andererseits, Sie angeben, dass eine bestimmte Kontext-ID Ihrer Wahl, das Objekt und jede Arbeit, die dies der Fall ist dieser Kontext-ID zugeordnet werden soll Können Sie identifizieren, welche Statusinformationen Ihnen in angegeben wird, wird den Kontext-IDs Ihrer `OnStatusCallback` Funktion.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a>Anzeigen von Statusinformationen bei der Übertragung von Dateien  
 Beispielsweise, wenn Sie eine Anwendung, die eine Verbindung mit einem FTP-Server zum Lesen einer Datei erstellt und auch eine Verbindung mit einem HTTP-Server Schreiben auf eine Webseite zu erhalten, stehen Ihnen eine `CInternetSession` -Objekt, das zwei `CInternetConnection` Objekte (eine wäre eine **einerseits** und der andere würde eine **CHttpSession**), und zwei `CInternetFile` Objekte (eine für jede Verbindung). Bei Verwendung der Standardwerte für die `dwContext` Parameter, Sie wären nicht unterscheiden, zwischen den `OnStatusCallback` Aufrufe, die angeben, für die FTP-Verbindung und die Aufrufe, die angeben, den Fortschritt der HTTP-Verbindung ausgeführt. Bei Angabe einer `dwContext` -ID, die Sie später in testen `OnStatusCallback`, wissen Sie, welcher Vorgang den Rückruf generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammiergrundlagen](../mfc/mfc-internet-programming-basics.md)   
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)

