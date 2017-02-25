---
title: "Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verbinden mit Webdiensten, Windows Store-Apps [C++]"
  - "IXMLHTTPRequest2 und Aufgaben, Beispiel"
  - "IXHR2 und Aufgaben, Beispiel"
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie die [IXMLHTTPRequest2](assetId:///bbc11c4a-aecf-4d6d-8275-3e852e309908)\- und [IXMLHTTPRequest2Callback](assetId:///aa4b3f4c-6e28-458b-be25-6cce8865fc71)\-Schnittstellen zusammen mit Aufgaben für HTTP\-GET\- und POST\-Anforderungen an einen Webdienst in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App verwendet werden.  Beim Kombinieren von `IXMLHTTPRequest2` mit Aufgaben können Sie Code schreiben, der mit anderen Aufgaben zusammen erstellt wird.  Beispielsweise können Sie die Downloadaufgabe als Teil einer Kette von Aufgaben verwenden.  Wenn Arbeit abgebrochen wird, kann die Downloadaufgabe auch weiterhin antworten.  
  
> [!TIP]
>  Darüber hinaus können Sie das C\+\+\-REST\-SDK verwenden, um HTTP\-Anforderungen aus einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App mit einer C\+\+\-Desktopanwendung auszuführen.  Weitere Informationen hierzu finden Sie unter [C\+\+\-REST\-SDK \(Codename "Casablanca"\)](../../top/cpp-rest-sdk-codename-casablanca.md).  
  
 Weitere Informationen zu Aufgaben finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Weitere Informationen zur Verwendung von Aufgaben in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App finden Sie unter [Asynchronous programming in C\+\+](assetId:///512700b7-7863-44cc-93a2-366938052f31) und [Erstellen von asynchronen Vorgängen in C\+\+ für Windows Store\-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
 Dieses Dokument erläutert zunächst, wie die `HttpRequest`\-Klasse und unterstützende Klassen erstellt werden.  Anschließend wird dargestellt, wie diese Klasse in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App verwendet werden kann, die C\+\+ und XAML verwendet.  
  
 Ein vollständigeres Beispiel für die Verwendung der in diesem Dokument beschriebenen `HttpReader`\-Klasse finden Sie unter [Entwickeln des Reise\-Optimierers von Bing Maps, einer Windows Store\-App in JavaScript und C\+\+](../Topic/Developing%20Bing%20Maps%20Trip%20Optimizer,%20a%20Windows%20Store%20app%20in%20JavaScript%20and%20C++.md).  Ein weiteres Beispiel zum Verwenden von `IXMLHTTPRequest2`, jedoch ohne Aufgaben, finden Sie unter [Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](assetId:///cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35).  
  
> [!TIP]
>  `IXMLHTTPRequest2` und `IXMLHTTPRequest2Callback` sind die Schnittstellen, die wir für eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App empfehlen.  Darüber hinaus können Sie dieses Beispiel auch für die Verwendung in einer Desktop\-App anpassen.  
  
## Vorbereitungsmaßnahmen  
  
## Definieren der HttpRequest\-, HttpRequestBuffersCallback\- und HttpRequestStringCallback\-Klassen  
 Wenn Sie die `IXMLHTTPRequest2`\-Schnittstelle verwenden, um Webanforderungen über HTTP zu erstellen, implementieren Sie die `IXMLHTTPRequest2Callback`\-Schnittstelle, um die Serverantwort zu empfangen und auf andere Ereignisse zu reagieren.  In diesem Beispiel werden die `HttpRequest`\-Klasse zum Erstellen von Webanforderungen und die Klassen `HttpRequestBuffersCallback` und `HttpRequestStringCallback` zum Verarbeiten der Antworten definiert.  Die `HttpRequestBuffersCallback`\-Klasse und die `HttpRequestStringCallback`\-Klasse unterstützen die `HttpRequest`\-Klasse; Sie arbeiten im Anwendungscode nur mit der `HttpRequest`\-Klasse.  
  
 Die `GetAsync`\-Methode und die `PostAsync`\-Methode der `HttpRequest`\-Klasse ermöglichen Ihnen das Durchführen von HTTP\-Anforderungen \(GET, POST\).  Diese Methoden verwenden die `HttpRequestStringCallback`\-Klasse, um die Serverantwort als Zeichenfolge zu lesen.  Die `SendAsync`\-Methode und die `ReadAsync`\-Methode ermöglichen das Übertragen von umfangreichen Inhalten in Blöcken.  Diese Methoden geben jeweils [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) zurück, um den Vorgang darzustellen.  Die `GetAsync`\-Methode und die `PostAsync`\-Methode generieren `task<std::wstring>`\-Wert, wobei der `wstring`\-Teil die Antwort des Servers darstellt.  Die `SendAsync`\-Methode und die `ReadAsync`\-Methode generieren `task<void>`\-Werte. Diese Aufgaben werden abgeschlossen, wenn die "Send"\- und "Read"\-Vorgänge abgeschlossen werden.  
  
 Da die `IXMLHTTPRequest2`\-Schnittstellen sich asynchron verhalten, wird in diesem Beispiel [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md) verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, nachdem das Rückrufobjekt den Downloadvorgang abgeschlossen oder abgebrochen hat.  Die `HttpRequest`\-Klasse erstellt eine aufgabenbasierte Fortsetzung aus dieser Aufgabe, um das Endergebnis festzulegen.  Die `HttpRequest`\-Klasse verwendet eine aufgabenbasierte Fortsetzung, um sicherzustellen, dass die Fortsetzungsaufgabe ausgeführt wird, auch wenn die vorherige Aufgabe einen Fehler erzeugt oder abgebrochen wird.  Weitere Informationen zu aufgabenbasierten Fortsetzungen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Um ein Abbrechen zu unterstützen, verwenden die Klassen `HttpRequest`, `HttpRequestBuffersCallback` und `HttpRequestStringCallback` Abbruchtoken.  Die `HttpRequestBuffersCallback`\-Klasse und die `HttpRequestStringCallback`\-Klasse verwenden die [concurrency::cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md)\-Methode, um das Aufgabenabschlussereignis zu aktivieren und auf den Abbruch zu reagieren.  Dieser Abbruchsrückruf bricht den Download ab.  Weitere Informationen über Abbrüche finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
#### So definieren Sie die HttpRequest\-Klasse  
  
1.  Verwenden Sie die Visual C\+\+\-Vorlage **Leere App \(XAML\)**, um ein leeres XAML\-App\-Projekt zu erstellen.  In diesem Beispiel heißt das Projekt `UsingIXMLHTTPRequest2`.  
  
2.  Fügen Sie dem Projekt eine Headerdatei mit dem Namen "HttpRequest.h" und eine Quelldatei mit dem Namen "HttpRequest.cpp" hinzu.  
  
3.  Fügen Sie "pch.h" diesen Code hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#1](concrt-using-IXMLHTTPRequest2#1)]  
  
4.  Fügen Sie "HttpRequest.h" diesen Code hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#2](concrt-using-IXMLHTTPRequest2#2)]  
  
5.  Fügen Sie "HttpRequest.cpp" diesen Code hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#3](concrt-using-IXMLHTTPRequest2#3)]  
  
## Verwenden der HttpRequest\-Klasse in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App  
 In diesem Abschnitt wird veranschaulicht, wie die `HttpRequest`\-Klasse in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App verwendet wird.  Die App enthält ein Eingabefeld, das eine URL\-Ressource definiert, und Schaltflächen zum Durchführen von GET\- und POST\-Anforderungen und zum Abbrechen des aktuellen Vorgangs.  
  
#### So verwenden Sie die HttpRequest\-Klasse  
  
1.  In "MainPage.xaml" definieren Sie das [StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx)\-Element wie folgt.  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A1](concrt-using-IXMLHTTPRequest2#A1)]  
  
2.  In "MainPage.xaml.h" fügen Sie diese `#include`\-Direktive hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A2](concrt-using-IXMLHTTPRequest2#A2)]  
  
3.  Fügen Sie diese `private`\-Membervariablen der `MainPage`\-Klasse in "MainPage.xaml.h" hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A3](concrt-using-IXMLHTTPRequest2#A3)]  
  
4.  Deklarieren Sie in "MainPage.xaml.h" die `private`\-Methode `ProcessHttpRequest`:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A4](concrt-using-IXMLHTTPRequest2#A4)]  
  
5.  Fügen Sie "MainPage.xaml.cpp" diese `using`\-Anweisungen hinzu:  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A5](concrt-using-IXMLHTTPRequest2#A5)]  
  
6.  Implementieren Sie in "MainPage.xaml.cpp" die Methoden `GetButton_Click`, `PostButton_Click` und `CancelButton_Click` aus der `MainPage`\-Klasse.  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A6](concrt-using-IXMLHTTPRequest2#A6)]  
  
    > [!TIP]
    >  Wenn Ihre App keine Abbruchunterstützung benötigt, übergeben Sie [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md) an die `HttpRequest::GetAsync`\-Methode und die `HttpRequest::PostAsync`\-Methode.  
  
7.  Implementieren Sie die `MainPage::ProcessHttpRequest`\-Methode in "MainPage.xaml.cpp".  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A7](concrt-using-IXMLHTTPRequest2#A7)]  
  
8.  In den Projekteigenschaften unter **Linker** und **Eingabe** geben Sie `shcore.lib` und `msxml6.lib` an.  
  
 Hier ist die ausgeführte App:  
  
 ![Die Windows Store&#45;App, die ausgeführt wird](../../parallel/concrt/media/concrt_usingixhr2.png "ConcRT\_UsingIXHR2")  
  
## Nächste Schritte  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)  
  
## Siehe auch  
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Asynchronous programming in C\+\+](assetId:///512700b7-7863-44cc-93a2-366938052f31)   
 [Erstellen von asynchronen Vorgängen in C\+\+ für Windows Store\-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](assetId:///cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [task\-Klasse \(Concurrency Runtime\)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)   
 [task\_completion\_event\-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)   
 [IXMLHTTPRequest2](assetId:///bbc11c4a-aecf-4d6d-8275-3e852e309908)   
 [IXMLHTTPRequest2Callback](assetId:///aa4b3f4c-6e28-458b-be25-6cce8865fc71)