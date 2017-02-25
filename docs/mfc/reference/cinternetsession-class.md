---
title: "CInternetSession Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetSession class"
  - "Internet sessions"
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CInternetSession Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt und initialisiert einzelne oder mehrere gleichzeitigen Internet\-Sitzungen und beschreibt ggf. die Verbindung zu einem Proxyserver.  
  
## Syntax  
  
```  
class CInternetSession : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetSession::CInternetSession](../Topic/CInternetSession::CInternetSession.md)|Erstellt ein `CInternetSession`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetSession::Close](../Topic/CInternetSession::Close.md)|Schließt die Internetverbindung, wenn die Internet\-Sitzung beendet wird.|  
|[CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md)|Richtet eine Statusrückrufroutine ein.|  
|[CInternetSession::GetContext](../Topic/CInternetSession::GetContext.md)|Schließt die Internetverbindung, wenn die Internet\-Sitzung beendet wird.|  
|[CInternetSession::GetCookie](../Topic/CInternetSession::GetCookie.md)|EINGABETASTEcookien für die angegebene URL und der gesamten übergeordnete Element URL.|  
|[CInternetSession::GetCookieLength](../Topic/CInternetSession::GetCookieLength.md)|Ruft die Variable ab, die die Länge des Cookies angeben, das im Puffer gespeichert wird.|  
|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)|Öffnet eine FTP\-Sitzung mit einem Server.  Benachrichtigt den Benutzer an.|  
|[CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)|Öffnet einen Gopherserver für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md)|Öffnet einen HTTP\-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md)|Aktualisiert den Status eines Vorgangs, wenn Statusrückruf aktiviert ist.|  
|[CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md)|Analysiert und öffnet eine URL.|  
|[CInternetSession::SetCookie](../Topic/CInternetSession::SetCookie.md)|Legt ein Cookie für das angegebene URL fest.|  
|[CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md)|Legt Optionen für die Internet\-Sitzung fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](../Topic/CInternetSession::operator%20HINTERNET.md)|Ein Handle zur aktuellen Internet\-Sitzung.|  
  
## Hinweise  
 Wenn die Internetverbindung während der Dauer einer Anwendung beibehalten werden müssen, können Sie einen `CInternetSession`\-Member der Klasse [CWinApp](../../mfc/reference/cwinapp-class.md) erstellen.  
  
 Nachdem Sie eine Internet\-Sitzung hergestellt haben, können Sie [OpenURL](../Topic/CInternetSession::OpenURL.md) aufrufen.  `CInternetSession` analysiert dann die URL für Sie, indem es die globale Funktion [AfxParseURL](../Topic/AfxParseURL.md) aufruft.  Unabhängig von den Protokolltyp interpretiert `CInternetSession` die URL und verwaltet es für Sie.  Es kann Anforderungen für die lokalen Dateien bearbeiten, die der URL\-Ressource "file:\/\/" identifiziert werden.  `OpenURL` gibt einen Zeiger auf einen [CStdioFile](../../mfc/reference/cstdiofile-class.md)\-Objekt zurück, wenn der Name, den Sie ihn übergeben, eine lokale Datei ist.  
  
 Wenn Sie eine URL auf einem Internetserver mithilfe `OpenURL` öffnen, können Sie Informationen aus der Site lesen.  Wenn Sie dienstspezifische \(beispielsweise, HTTP, FTP, oder Gopher\) Aktionen für die Dateien auf einem Server ausführen möchten, müssen Sie die entsprechende Verbindung mit diesem Server herstellen.  Um eine bestimmte Art von Verbindung direkt an einen bestimmten Dienst zu öffnen, verwenden Sie eine der folgenden Memberfunktionen:  
  
-   [GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md), um eine Verbindung zu einem Gopher\-Dienst zu öffnen.  
  
-   [GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), um eine Verbindung zu einem HTTP\-Dienst zu öffnen.  
  
-   [GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), um eine Verbindung zu einem FTP\-Dienst zu öffnen.  
  
 [SetOption](../Topic/CInternetSession::SetOption.md) ermöglicht es Ihnen, die Abfrageoptionen der Sitzung, wie Timeoutwerte festzulegen, Zahl wiederholt, u. a.  
  
 `CInternetSession`\-Memberfunktionen [SetCookie](../Topic/CInternetSession::SetCookie.md), [GetCookie](../Topic/CInternetSession::GetCookie.md) und [GetCookieLength](../Topic/CInternetSession::GetCookieLength.md) bieten die Möglichkeit, um eine Win32\-Cookiedatenbank verwalten, durch die Server und Skripts Zustandsinformationen über die Clientarbeitsstation beibehalten.  
  
 Weitere Informationen zu den Aufgaben des grundlegenden Internet, finden Sie im Artikel [Internet\-erste Schritte: WinInet\-Klassen](../../mfc/wininet-basics.md).  Allgemeine Informationen über die Verwendung der Klassen MFC\-WinInet\-Unterstützung, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
>  `CInternetSession` löst [AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md) für nicht unterstützte Diensttypen aus.  Nur die folgenden Diensttypen werden derzeit unterstützt: FTP, HTTP, Gopher und Datei.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)