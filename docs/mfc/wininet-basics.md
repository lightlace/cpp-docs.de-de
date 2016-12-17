---
title: "WinInet-Grundlagen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnStatusCallback-Methode"
  - "WinInet-Klassen, Informationen über WinInet-Klassen"
  - "WinInet-Klassen, Anzeigen des Fortschritts"
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# WinInet-Grundlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können WinInet\-Klassen verwenden, um FTP\-Unterstützung hinzuzufügen, um Dateien aus der Anwendung herunterladen und hochladen.  Sie können die [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) überschreiben und den `dwContext`\-Parameter verwenden, um Statusinformationen für Benutzer bereitstellen, während Sie suchen und Dateien herunterladen.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Erstellen Sie einen sehr einfachen Browser](#_core_create_a_very_simple_browser)  
  
-   [Laden Sie eine Webseite herunter](#_core_download_a_web_page)  
  
-   [FTP eine Datei](#_core_ftp_a_file)  
  
-   [Rufen Sie ein Gopher\-Verzeichnis ab](#_core_retrieve_a_gopher_directory)  
  
-   [Anzeigen von Statusinformationen an, während das Übertragen Dateien](#_core_display_progress_information_while_transferring_files)  
  
 Die folgenden Codeauszüge zeigen, wie ein einfacher Browser, eine Webseite, ein FTP eine Datei und eine Suche nach einer Gopher\-Datei herunterzuladen erstellt.  Es ist nicht vorgesehen, wie vollständige Beispiele und nicht alle Ausnahmebehandlung enthalten.  
  
 Weitere Informationen über WinInet\-Klassen finden Sie unter [Win32\-Internet\-Erweiterungen \(WinInet\-Klassen\)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Erstellen Sie einen sehr einfachen Browser  
 [!CODE [NVC_MFCWinInet#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#1)]  
  
##  <a name="_core_download_a_web_page"></a> Laden Sie eine Webseite herunter  
 [!CODE [NVC_MFCWinInet#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#2)]  
  
##  <a name="_core_ftp_a_file"></a> FTP eine Datei  
 [!CODE [NVC_MFCWinInet#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#3)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Rufen Sie ein Gopher\-Verzeichnis ab  
 [!CODE [NVC_MFCWinInet#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#4)]  
  
## Verwenden Sie OnStatusCallback  
 Wenn die Anwendung WinInets klassifiziert, können Sie den [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md)\-Member einer [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt der Anwendung verwenden, um Statusinformationen abzurufen.  Wenn Sie Ihr eigenes `CInternetSession`\-Objekt ableiten, `OnStatusCallback` überschreiben und Statusrückrufe aktivieren, MFC ruft die Funktion `OnStatusCallback` mit Statusinformationen zur gesamten Aktivität in dieser Internet\-Sitzung auf.  
  
 Da eine einzelne Sitzung kann mehrere Verbindungen unterstützte \(die möglicherweise, über die Lebensdauer, viele unterschiedliche verschiedene Operationen ausgeführt haben\), `OnStatusCallback` einen Mechanismus, um jeder Statusänderung mit eine bestimmte Verbindung oder einer Transaktion zu identifizieren.  Dieser Mechanismus vom Kontext\-ID\-Parameter bereitgestellt wird, der für viele der Memberfunktionen in der WinInet\-Unterstützung gegeben wird, unterschieden.  Dieser Parameter ist immer vom Typ `DWORD` und wird immer `dwContext`.  
  
 Der Kontext, der einem bestimmten Internet\-Objekt zugewiesen wird, ist, um die Aktivität nur zu identifizieren die im `OnStatusCallback`\-Objektursachen Member des `CInternetSession`\-Objekts.  Der Aufruf von `OnStatusCallback` werden einige Parameter; diese Parameter arbeiten zusammen, um der Anwendung zu kommunizieren, welche Fortschritte erzielt wurde, für den Transaktionen und Verbindung.  
  
 Wenn Sie ein `CInternetSession`\-Objekt erstellen, können Sie einem `dwContext`\-Parameter dem Konstruktor angeben.  `CInternetSession` selbst wird nicht die Kontext\-ID; Stattdessen wird die Kontext\-ID an alle **InternetConnection** abgeleitete Objekte angezeigt, die nicht explizit eine Kontext\-ID von eigenen abrufen.  Im Gegenzug übergeben diese Objekte die `CInternetConnection` Kontext\-ID entlang zu `CInternetFile`\-Objekten, die diese erstellen, wenn Sie nicht explizit eine unterschiedliche Kontext ID angeben  Wenn Sie aber eine bestimmte Kontext\-ID von eigenen, das Objekt angeben und Arbeit, die sie gar, Kontext mit dieser ID zugeordnet ist  Sie können die Kontext\-IDs verwenden, um zu ermitteln, welche Statusinformationen Sie in Ihrer `OnStatusCallback`\-Funktion angegeben werden.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Anzeigen von Statusinformationen an, während das Übertragen Dateien  
 Wenn Sie eine Anwendung schreiben, die eine Verbindung mit einem FTP\-Server erstellt, um eine Datei zu lesen und auch mit einem HTTP\-Server herstellt, um eine Webseite abzurufen, haben Sie ein `CInternetSession`\-Objekt, zwei `CInternetConnection`\-Objekte \(Verwendung wäre **CFtpSession** sein und das andere wird **CHttpSession** sein\) und zwei `CInternetFile`\-Objekte \(eine für jede Kombination\).  Wenn Sie verwendete Standardwerte für die Parameter `dwContext`, wird nicht in der Lage, zwischen den Aufrufen `OnStatusCallback` zu unterscheiden, der Status für die FTP\-Verbindung und die Aufrufe angeben, die den Status für die HTTP\-Verbindung angeben.  Wenn Sie eine ID `dwContext` angeben, die für in `OnStatusCallback` im Folgenden testen können, wissen Sie, welcher Vorgang den Rückruf generiert.  
  
## Siehe auch  
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)   
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)