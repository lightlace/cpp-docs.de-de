---
title: 'Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: fc16fa5cfeddf82b9fcb0164796fb7f4c90aef15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653075"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz

Bei Anwendungen mit Aufgaben, die eine hohe Latenz aufweisen, lässt sich die allgemeine Effizienz durch die Überzeichnung verbessern. In diesem Thema wird veranschaulicht, wie Überzeichnung zum Kompensieren der Latenz beim Lesen von Daten von einer Netzwerkverbindung verwendet wird.

## <a name="example"></a>Beispiel

Dieses Beispiel verwendet die [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zum Herunterladen von Dateien von HTTP-Servern. Die `http_reader` Klasse leitet sich von [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) und verwendet übergeben, um die Namen der URL zum Herunterladen asynchron zu lesen.

Die `http_reader` -Klasse verwendet die [Concurrency:: task_group](reference/task-group-class.md) -Klasse zum gleichzeitigen Lesen jeder Datei. Ruft jede Aufgabe die [Oversubscribe](reference/context-class.md#oversubscribe) -Methode mit dem `_BeginOversubscription` Parametersatz zu **"true"** zur Aktivierung der Überzeichnung im aktuellen Kontext. Dann verwendet jede Aufgabe die Microsoft Foundation Classes (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) und [CHttpFile](../../mfc/reference/chttpfile-class.md) Klassen, die Datei herunterzuladen. Zum Schluss ruft jede Aufgabe `Context::Oversubscribe` mit der `_BeginOversubscription` Parametersatz zu **"false"** Überzeichnung zu deaktivieren.

Bei aktivierter Überzeichnung erstellt die Laufzeit einen zusätzlichen Thread, in dem Aufgaben ausgeführt werden. Jeder dieser Threads kann wiederum den aktuellen Kontext überzeichnen und dadurch weitere Threads erstellen. Die `http_reader` -Klasse verwendet ein [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Objekt, das die Anzahl der Threads beschränkt, die die Anwendung verwendet. Der Agent initialisiert den Puffer mit einer festen Anzahl von Tokenwerten. Für jeden Downloadvorgang liest der Agent einen Tokenwert aus dem Puffer, bevor der Vorgang gestartet wird, und schreibt diesen Wert nach Beenden des Vorgangs zurück in den Puffer. Wenn der Puffer leer ist, wartet der Agent, bis einer der Downloadvorgänge einen Wert in den Puffer zurückschreibt.

Im folgenden Beispiel wird die Anzahl der gleichzeitigen Aufgaben auf die doppelte Anzahl der verfügbaren Hardwarethreads beschränkt. Dieser Wert ist ein geeigneter Einstiegspunkt, wenn Sie mit der Überzeichnung experimentieren. Sie können einen Wert verwenden, der zu einer bestimmten Verarbeitungsumgebung passt, oder den Wert dynamisch an die tatsächliche Arbeitsauslastung anpassen.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

Dieses Beispiel erzeugt auf einem Computer mit vier Prozessoren die folgende Ausgabe:

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

Das Beispiel kann schneller ausgeführt werden, wenn die Überzeichnung aktiviert ist, da zusätzliche Aufgaben ausgeführt werden können, während andere Aufgaben darauf warten, dass ein Vorgang mit Latenz beendet wird.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `download-oversubscription.cpp` und dann führen Sie einen der folgenden Befehle in einem **Visual Studio-Eingabeaufforderung** Fenster.

**CL.exe/EHsc/MD/d "_AFXDLL" Download-oversubscription.cpp**

**CL.exe/EHsc/MT-Download-oversubscription.cpp**

## <a name="robust-programming"></a>Stabile Programmierung

Die Überzeichnung muss stets deaktiviert werden, wenn sie nicht mehr benötigt wird. Nehmen Sie an, eine Funktion behandelt die von einer anderen Funktion ausgelöste Ausnahme nicht. Wenn Sie die Überzeichnung nicht deaktivieren, bevor die Funktion einen Wert zurückgibt, wird der aktuelle Kontext von jeder zusätzlichen parallelen Aufgabe ebenfalls überzeichnet.

Sie können die *Resource Acquisition Is Initialization* (RAII)-Muster können Sie die Überzeichnung auf einen bestimmten Gültigkeitsbereich beschränken. Unter dem RAII-Muster wird dem Stapel eine Datenstruktur zugeordnet. Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird. Das RAII-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird. Daher wird die Ressource ordnungsgemäß verwaltet, wenn eine Ausnahme ausgelöst wird, oder wenn eine Funktion mehrere `return`-Anweisungen enthält.

Im folgenden Beispiel wird eine Struktur mit dem Namen `scoped_blocking_signal` definiert. Die Überzeichnung wird mit dem Konstruktor der `scoped_blocking_signal`-Struktur aktiviert und mit dem Destruktor deaktiviert.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

Im folgenden Beispiel wird der Text der `download`-Methode geändert, sodass RAII verwendet wird. So können Sie sicherstellen, dass die Überzeichnung deaktiviert wird, bevor die Funktion einen Wert zurückgibt. Durch diese Verfahrensweise wird die Ausnahmesicherheit der `download`-Methode sichergestellt.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Kontext](../../parallel/concrt/contexts.md)<br/>
[Context:: Oversubscribe-Methode](reference/context-class.md#oversubscribe)

