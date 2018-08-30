---
title: Cloud-Apps und Web-Programmierung in Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-azure
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f946a0e24790fd894e4eb908e77163306130e46a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214635"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Cloud- und Webprogrammierung in Visual C++

In C++ haben Sie mehrere Optionen, um eine Verbindung mit dem Web und der Cloud herzustellen.

## <a name="cloud-programming-options"></a>Cloud-Programmierung Optionen

- [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)

   Stellt systemeigene APIs, die Sie in apps für universelle Windows-Plattform (UWP) oder Windows-desktop-apps verwenden können, für die Verbindung zu Windows Azure Mobile Services bereit. Obwohl die meisten Beispiele auf der Website in C# geschrieben sind, können Sie auch C++ verwenden. Weitere Informationen finden Sie unter [Schnellstart: Hinzufügen eines mobilen Diensts mit C++](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx).

- [Microsoft Azure Storage-Clientbibliothek für C++](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

   Die Azure-Speicherclientbibliothek für C++ bietet eine umfassende API für die Arbeit mit Azure Storage, einschließlich aber nicht beschränkt auf die folgenden Möglichkeiten:

  - Erstellen, lesen, löschen und Auflisten von Blob-Container, Tabellen und Warteschlangen.
  - Erstellen Sie, lesen Sie, zu löschen Sie, Liste und kopieren Sie Blobs sowie Lesen und Schreiben von Blob-Bereiche.
  - INSERT, Delete, Replace, Merge und Abfragen von Entitäten in einer Azure-Tabelle.
  - In die Warteschlange einreihen und Entfernen aus der Warteschlange Nachrichten in einer Azure-Warteschlange.
  - Verzögert Auflisten von Containern, Blobs, Tabellen und Warteschlangen und verzögert Abfragen von Entitäten

- [OneDrive-API](https://dev.onedrive.com/README.htm)

   Die OneDrive-API bietet eine Reihe von HTTP-Diensten verbinden Sie Ihre Anwendung mit Dateien und Ordner in Office 365 und SharePoint Server 2016.

- [C++ REST SDK (Codename „Casablanca“)](https://github.com/Microsoft/cpprestsdk)

   Stellt eine moderne, plattformübergreifende, asynchrone API für die Interaktion mit REST-Dienste bereit.

  - Führen Sie die REST-Aufrufe für alle HTTP-Server, mit integrierter Unterstützung für JSON-Dokument analysieren und Serialisierung
  - Unterstützt die OAuth-1 und 2, einschließlich eines lokalen Umleitung-Listeners
  - Knüpfen Sie Kontakte Websockets für Remotedienste
  - Ein vollständig asynchrones Aufgaben-API, die basierend auf der PPL, einschließlich einer integrierten threadpool

   Unterstützt die Windows-Desktop (7 +), Windows Server (2012 und höher), universelle Windows-Plattform, Linux, OSX, Android und iOS. 

- [Windows::Web::http::HttpClient](https://msdn.microsoft.com/library/windows/apps/windows.web.http.httpclient.aspx)

   Eine Windows-Runtime-HTTP-Clientklasse, die in der .NET Framework-Klasse des gleichen Namens im System.Web-Namespace modelliert ist. `HttpClient` unterstützt vollständig den asynchronen Upload und Download über HTTP und Pipelinefilter, die das Einfügen von benutzerdefinierten HTTP-Handlern in die Pipeline ermöglichen. Das Windows SDK umfasst Beispielfilter für gemessene Netzwerke, OAuth-Authentifizierung und mehr. Für apps, die nur die universelle Windows-Plattform abzielen, empfehlen wir die Verwendung der `Windows::Web:HttpClient` Klasse. 

- [IXMLHTTPRequest2-Schnittstelle](/previous-versions/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

   Bietet eine systemeigene COM-Schnittstelle, Sie in der Windows-Runtime-apps oder Windows-desktop-apps über HTTP eine Verbindung mit dem Internet können und das Problem zu lösen, PUT- und andere HTTP-Befehlen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinInet)](https://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)

   Eine Windows-API, die Sie in Windows-Desktop-Apps verwenden können, um eine Verbindung mit dem Internet herzustellen.

## <a name="see-also"></a>Siehe auch

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[Netzwerke und Webdienste](/windows/uwp/networking/)
