---
title: Leerlaufschleifen-Verarbeitung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 0d0e3fcba9ce447ec359958fc5ed59c6d596dd7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219489"
---
# <a name="idle-loop-processing"></a>Leerlaufschleifen-Verarbeitung

Viele Anwendungen führt langwierige Verarbeitung "im Hintergrund." In einigen Fällen geben Überlegungen zur Leistung vor, die Verwendung von multithreading für diese Aufgaben. Threads verursachen zusätzlichen, damit sie für einfache Aufgaben wie die Arbeit der Leerlauf-Ablaufzeitpunkt nicht empfohlen, die MFC führt Sie werden in der [OnIdle](../mfc/reference/cwinthread-class.md#onidle) Funktion. Dieser Artikel konzentriert sich auf die leerlaufverarbeitung. Weitere Informationen zu multithreading, finden Sie unter [Themen zu Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Einige Arten von Verarbeitung im Hintergrund werden entsprechend während Intervallen ausgeführt werden, die der Benutzer andernfalls nicht mit der Anwendung interagiert wird. In einer Anwendung, die für das Betriebssystem Microsoft Windows entwickelt wurde kann eine Anwendung leerlaufzeitverarbeitung durchführen, einen lang andauernder Vorgang in vielen kleinen Fragmenten aufteilen. Nach der Verarbeitung jedes Fragment an, die Anwendung die Steuerung der Ausführung mit Windows ergibt eine [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) Schleife.

In diesem Artikel wird erläutert, zwei Möglichkeiten, um die Verarbeitung in Ihrer Anwendung im Leerlauf:

- Mithilfe von **PeekMessage** in MFC Hauptnachrichtenschleife.

- Einbetten von einem anderen **PeekMessage** an anderer Stelle in der Anwendung eine Schleife.

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> PeekMessage in der MFC-Nachrichtenschleife

In einer Anwendung, die mit MFC entwickelt wurde, wurde die Hauptnachricht eine Schleife in der `CWinThread` -Klasse enthält eine Meldungsschleife, die Aufrufe der [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) Win32-API. Diese Schleife auch Aufrufe der `OnIdle` Memberfunktion `CWinThread` zwischen Nachrichten. Eine Anwendung kann in diesem Zeitraum im Leerlauf Nachrichten verarbeiten, durch Überschreiben der `OnIdle` Funktion.

> [!NOTE]
>  `Run`, `OnIdle`, und bestimmte andere Memberfunktionen sind nun Elemente der Klasse `CWinThread` statt der Klasse `CWinApp`. `CWinApp` wird von `CWinThread` abgeleitet.

Weitere Informationen zum Ausführen von leerlaufverarbeitung finden Sie unter [OnIdle](../mfc/reference/cwinthread-class.md#onidle) in die *MFC-Referenz*.

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage an anderer Stelle in Ihrer Anwendung

Eine andere Methode zum Ausführen von im Leerlauf Verarbeitung in einer Anwendung umfasst eine Meldungsschleife in einer Ihrer Funktion eingebettet. Diese Meldungsschleife ist sehr ähnlich der MFC-Hauptnachrichtenschleife, finden Sie im [Hauptmeldungsschleife](../mfc/reference/cwinthread-class.md#run). Das bedeutet, solche Schleife in einer Anwendung, die mit MFC entwickelt wurden viele der gleichen Funktionen wie die primäre Meldungsschleife ausführen muss. Das folgende Codefragment zeigt, wie eine Meldungsschleife, die mit MFC kompatibel ist:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Dieser Code, eingebettet in einer Funktion die Schleife so lange, wie im Leerlauf verarbeiten müssen. Innerhalb dieser Schleife Ruft eine geschachtelte Schleife wiederholt `PeekMessage`. Solange dieser Aufruf einen Wert ungleich NULL zurückgibt, ruft die Schleife `CWinThread::PumpMessage` normale Meldung Übersetzung und Weiterleitung von ausführen. Obwohl `PumpMessage` ist nicht dokumentiert ist, können Sie Quellcode in der Datei ThrdCore.Cpp im \atlmfc\src\mfc Verzeichnis des Visual C++-Installation überprüfen.

Sobald die innere Schleife beendet, die äußere Schleife führt leerlaufverarbeitung durch eine oder mehrere Aufrufe `OnIdle`. Der erste Aufruf ist für MFC Zwecke. Sie können zusätzliche Aufrufe an `OnIdle` eigene Verarbeitung im Hintergrund zu tun.

Weitere Informationen zum Ausführen von leerlaufverarbeitung finden Sie unter [OnIdle](../mfc/reference/cwinthread-class.md#onidle) in der MFC-Bibliothek-Referenz.

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
