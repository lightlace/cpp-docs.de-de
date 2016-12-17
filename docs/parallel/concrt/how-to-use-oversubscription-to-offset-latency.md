---
title: "Gewusst wie: Verwenden der &#220;berzeichnung zum Kompensieren der Latenz"
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
  - "Überzeichnung, Verwenden [Concurrency Runtime]"
  - "Verwenden von Überzeichnung [Concurrency Runtime]"
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 17
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden der &#220;berzeichnung zum Kompensieren der Latenz
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei Anwendungen mit Aufgaben, die eine hohe Latenz aufweisen, lässt sich die allgemeine Effizienz durch die Überzeichnung verbessern.  In diesem Thema wird veranschaulicht, wie Überzeichnung zum Kompensieren der Latenz beim Lesen von Daten von einer Netzwerkverbindung verwendet wird.  
  
## Beispiel  
 In diesem Beispiel werden Dateien mithilfe der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) von HTTP\-Servern heruntergeladen.  Die `http_reader`\-Klasse wird von [concurrency::agent](../../parallel/concrt/reference/agent-class.md) abgeleitet und liest asynchron mittels Meldungsübergabe, welche URLs herunterzuladen sind.  
  
 Die `http_reader`\-Klasse verwendet die [concurrency::task\_group](../Topic/task_group%20Class.md)\-Klasse zum gleichzeitigen Lesen jeder Datei.  Zur Aktivierung der Überzeichnung im aktuellen Kontext ruft jede Aufgabe die [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md)\-Methode mit einem `_BeginOversubscription`\-Parameter auf, der auf `true` festgelegt ist.  Dann verwendet jede Aufgabe die Microsoft Foundation Classes \(MFC\) [CInternetSession](../../mfc/reference/cinternetsession-class.md) und [CHttpFile](../../mfc/reference/chttpfile-class.md) zum Herunterladen der Datei.  Zum Schluss ruft jede Aufgabe `Context::Oversubscribe` auf, wobei der `_BeginOversubscription`\-Parameter auf `false` festgelegt ist, um die Überzeichnung zu deaktivieren.  
  
 Bei aktivierter Überzeichnung erstellt die Laufzeit einen zusätzlichen Thread, in dem Aufgaben ausgeführt werden.  Jeder dieser Threads kann wiederum den aktuellen Kontext überzeichnen und dadurch weitere Threads erstellen.  Die `http_reader`\-Klasse beschränkt mithilfe eines [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)\-Objekts die Anzahl der von der Anwendung verwendeten Threads.  Der Agent initialisiert den Puffer mit einer festen Anzahl von Tokenwerten.  Für jeden Downloadvorgang liest der Agent einen Tokenwert aus dem Puffer, bevor der Vorgang gestartet wird, und schreibt diesen Wert nach Beenden des Vorgangs zurück in den Puffer.  Wenn der Puffer leer ist, wartet der Agent, bis einer der Downloadvorgänge einen Wert in den Puffer zurückschreibt.  
  
 Im folgenden Beispiel wird die Anzahl der gleichzeitigen Aufgaben auf die doppelte Anzahl der verfügbaren Hardwarethreads beschränkt.  Dieser Wert ist ein geeigneter Einstiegspunkt, wenn Sie mit der Überzeichnung experimentieren.  Sie können einen Wert verwenden, der zu einer bestimmten Verarbeitungsumgebung passt, oder den Wert dynamisch an die tatsächliche Arbeitsauslastung anpassen.  
  
 [!CODE [concrt-download-oversubscription#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#1)]  
  
 Dieses Beispiel erzeugt auf einem Computer mit vier Prozessoren die folgende Ausgabe:  
  
  **Downloading http:\/\/www.adatum.com\/...**  
**Downloading http:\/\/www.adventure\-works.com\/...**  
**Downloading http:\/\/www.alpineskihouse.com\/...**  
**Downloading http:\/\/www.cpandl.com\/...**  
**Downloading http:\/\/www.cohovineyard.com\/...**  
**Downloading http:\/\/www.cohowinery.com\/...**  
**Downloading http:\/\/www.cohovineyardandwinery.com\/...**  
**Downloading http:\/\/www.contoso.com\/...**  
**Downloading http:\/\/www.consolidatedmessenger.com\/...**  
**Downloading http:\/\/www.fabrikam.com\/...**  
**Downloading http:\/\/www.fourthcoffee.com\/...**  
**Downloading http:\/\/www.graphicdesigninstitute.com\/...**  
**Downloading http:\/\/www.humongousinsurance.com\/...**  
**Downloading http:\/\/www.litwareinc.com\/...**  
**Downloading http:\/\/www.lucernepublishing.com\/...**  
**Downloading http:\/\/www.margiestravel.com\/...**  
**Downloading http:\/\/www.northwindtraders.com\/...**  
**Downloading http:\/\/www.proseware.com\/...**  
**Downloading http:\/\/www.fineartschool.net...**  
**Downloading http:\/\/www.tailspintoys.com\/...**  
**Downloaded 1801040 bytes in 3276 ms.** Das Beispiel kann schneller ausgeführt werden, wenn die Überzeichnung aktiviert ist, da zusätzliche Aufgaben ausgeführt werden können, während andere Aufgaben darauf warten, dass ein Vorgang mit Latenz beendet wird.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `download-oversubscription.cpp` ein, und führen Sie dann in einem Visual Studio\-Eingabeaufforderungsfenster einen der folgenden Befehle aus.  
  
 **cl.exe \/EHsc \/MD \/D "\_AFXDLL" download\-oversubscription.cpp**  
  
 **cl.exe \/EHsc \/MT download\-oversubscription.cpp**  
  
## Robuste Programmierung  
 Die Überzeichnung muss stets deaktiviert werden, wenn sie nicht mehr benötigt wird.  Nehmen Sie an, eine Funktion behandelt die von einer anderen Funktion ausgelöste Ausnahme nicht.  Wenn Sie die Überzeichnung nicht deaktivieren, bevor die Funktion einen Wert zurückgibt, wird der aktuelle Kontext von jeder zusätzlichen parallelen Aufgabe ebenfalls überzeichnet.  
  
 Mit dem *Resource Acquisition Is Initialization* \(RAII\)\-Muster können Sie die Überzeichnung auf einen bestimmten Gültigkeitsbereich beschränken.  Unter dem RAII\-Muster wird dem Stapel eine Datenstruktur zugeordnet.  Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird.  Das RAII\-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird.  Daher wird die Ressource ordnungsgemäß verwaltet, wenn eine Ausnahme ausgelöst wird, oder wenn eine Funktion mehrere `return`\-Anweisungen enthält.  
  
 Im folgenden Beispiel wird eine Struktur mit dem Namen `scoped_blocking_signal` definiert.  Die Überzeichnung wird mit dem Konstruktor der `scoped_blocking_signal`\-Struktur aktiviert und mit dem Destruktor deaktiviert.  
  
 [!CODE [concrt-download-oversubscription#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#2)]  
  
 Im folgenden Beispiel wird der Text der `download`\-Methode geändert, sodass RAII verwendet wird. So können Sie sicherstellen, dass die Überzeichnung deaktiviert wird, bevor die Funktion einen Wert zurückgibt.  Durch diese Verfahrensweise wird die Ausnahmesicherheit der `download`\-Methode sichergestellt.  
  
 [!CODE [concrt-download-oversubscription#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#3)]  
  
## Siehe auch  
 [Kontexte](../../parallel/concrt/contexts.md)   
 [Context::Oversubscribe\-Methode](../Topic/Context::Oversubscribe%20Method.md)