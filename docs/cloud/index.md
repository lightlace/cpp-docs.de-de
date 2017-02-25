---
title: "Cloud- und Webprogrammierung in Visual C++"
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
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "ghogen"
manager: "ghogen"
---
# Cloud- und Webprogrammierung in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In C\+\+ haben Sie mehrere Optionen, um eine Verbindung mit dem Web und der Cloud herzustellen.  
  
 [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)  
 Stellt systemeigene APIs bereit, die Sie in Windows Store\-Apps oder Windows\-Desktop\-Apps verwenden können, um eine Verbindung mit Windows Azure Mobile Services herzustellen. Obwohl die meisten Beispiele auf der Website in C\# geschrieben sind, können Sie auch C\+\+ verwenden. Weitere Informationen finden Sie im Schnellstart zum [Hinzufügen eines mobilen Diensts mit C\+\+](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).  
  
 [Live REST\-Schnittstelle](http://msdn.microsoft.com/library/live/hh243648.aspx)  
 Stellt REST\-Endpunkte \(Representational State Transfer\) bereit, die Sie in Windows Store\-Apps, Windows\-Desktop\-Apps oder C\+\+\-Linux\-Anwendungen verwenden können, um eine Verbindung mit [Live](http://msdn.microsoft.com/live/ff519582)\-Diensten wie SkyDrive, Outlook.com und Skype herzustellen. C\+\+\-Apps verwenden diese Endpunkte direkt anstatt über das Live SDK, das nur für .NET\-Apps vorgesehen ist.  
  
 [C\+\+\-REST\-SDK \(Codename "Casablanca"\)](../top/cpp-rest-sdk-codename-casablanca.md)  
 Stellt einfache asynchrone HTTP\-Wrappermethoden bereit, die für plattformübergreifende Kompatibilität und für Desktop\-Apps auf Betriebssystemen rückwärtskompatibel bis Windows 7 und Windows Server 2012 entwickelt sind. Sie können diese auch in UWP\-Apps \(universelle Windows\-Plattform\) verwenden. Für Apps, die nur auf die universelle Windows\-Plattform ausgerichtet sind, wird jedoch empfohlen, die `Windows::Web:HttpClient`\-Klasse zu verwenden. Das C\+\+\-REST\-SDK \(Codename "Casablanca"\) stellt auch Hilfsklassen bereit, die REST\-Aufrufe unterstützen und JSON\-Daten in C\+\+\-Typen konvertieren. Das SDK steht auf [CodePlex](http://casablanca.codeplex.com/) zur Verfügung, das Beispieldateien wie [live\_connect.h](http://casablanca.codeplex.com/SourceControl/latest#Release/collateral/Samples/WindowsLiveAuth/live_connect.h) umfasst, die Hilfsmethoden für die Verbindung mit [Live](http://msdn.microsoft.com/live/ff519582)\-Diensten bereitstellt.  
  
 [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 Eine Windows\-Runtime\-HTTP\-Clientklasse, die in der .NET Framework\-Klasse des gleichen Namens im System.Web\-Namespace modelliert ist.`HttpClient` unterstützt vollständig den asynchronen Upload und Download über HTTP und Pipelinefilter, die das Einfügen von benutzerdefinierten HTTP\-Handlern in die Pipeline ermöglichen. Das Windows SDK umfasst Beispielfilter für gemessene Netzwerke, OAuth\-Authentifizierung und mehr.  
  
 [IXMLHTTPRequest2\-Schnittstelle](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 Stellt eine systemeigene COM\-Schnittstelle bereit, die Sie in Windows Store\-Apps oder Windows\-Desktop\-Apps verwenden können, um über HTTP eine Verbindung mit dem Internet herzustellen und GET\-, PUT\- und andere HTTP\-Befehle auszugeben. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML\-HTTP\-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).  
  
 [Windows Internet \(WinInet\)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 Eine Windows\-API, die Sie in Windows\-Desktop\-Apps verwenden können, um eine Verbindung mit dem Internet herzustellen.  
  
## Siehe auch  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)   
 [Herstellen von Verbindungen mit Netzwerken und Webdiensten \(Windows Store\-Apps mit C\#\/VB\/C\+\+ und XAML\)](http://msdn.microsoft.com/library/windows/apps/br229573.aspx)