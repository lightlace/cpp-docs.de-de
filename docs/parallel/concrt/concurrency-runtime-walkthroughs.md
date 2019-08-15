---
title: Exemplarische Vorgehensweisen für die Concurrency Runtime
ms.date: 11/04/2016
helpviewer_keywords:
- walkthroughs [Concurrency Runtime]
- Concurrency Runtime, walkthroughs
ms.assetid: 7374c5e9-54eb-44bf-9ed9-5e190cfd290b
ms.openlocfilehash: 7c5973f8010d7c428406a8a3f69574eab20edf82
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512829"
---
# <a name="concurrency-runtime-walkthroughs"></a>Exemplarische Vorgehensweisen für die Concurrency Runtime

In den szenariobasierten Themen in diesem Abschnitt wird gezeigt, wie viele Funktionen der Concurrency Runtime verwendet werden.

## <a name="in-this-section"></a>In diesem Abschnitt

[Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
Zeigt, wie die [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) -und [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) -Schnittstellen in Verbindung mit Aufgaben verwendet werden, um HTTP Get-und Post-Anforderungen an einen Webdienst in einer universelle Windows-Plattform-app (UWP) zu senden.

[Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
Hier wird beschrieben, wie eine einfache agentbasierte Anwendung erstellt wird.

[Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
Veranschaulicht, wie auf der Grundlage des Datenflusses statt der Ablauf Steuerung auf Agent basierende Anwendungen erstellt werden.

[Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
Veranschaulicht, wie ein Netzwerk von asynchronen Nachrichten Blöcken erstellt wird, die eine Bildverarbeitung durchführen.

[Exemplarische Vorgehensweise: Implementieren von Futures](../../parallel/concrt/walkthrough-implementing-futures.md)<br/>
Zeigt, wie Werte für die spätere Verwendung asynchron berechnet werden.

[Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)<br/>
Veranschaulicht anhand des Problems mit den gastronomischen Beispielen, wie Sie die Klasse " [parallelcurrency:: Join](../../parallel/concrt/reference/join-class.md) " verwenden, um Deadlocks in der Anwendung zu verhindern.

[Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
Veranschaulicht das Verbessern der Leistung einer MFC-Anwendung, die das Mandelbrot-Dezimaltrennzeichen zeichnet.

[Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung](../../parallel/concrt/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)<br/>
Veranschaulicht, wie die Concurrency Runtime in einer Anwendung verwendet wird, die die Component Object Model (com) verwendet.

[Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Tasks](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)<br/>
Zeigt, wie vorhandener Code, der die Windows-API verwendet, zum Erstellen und Ausführen eines Threads für die Verwendung einer Lightweight-Aufgabe angepasst wird.

[Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)<br/>
Beschreibt, wie ein benutzerdefinierter Nachrichten Blocktyp erstellt wird, der eingehende Nachrichten nach Priorität anordnet.

## <a name="related-sections"></a>Verwandte Abschnitte

[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)<br/>
Führt das parallele Programmier Framework für Visual C++ein.
