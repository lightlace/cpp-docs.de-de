---
title: 'Vorgehensweise: Senden einer Nachricht in regelmäßigen Intervallen'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: c51a5cab6fcae5eb45b9d9b54c0dad8e8ec393b2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142465"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Vorgehensweise: Senden einer Nachricht in regelmäßigen Intervallen

Dieses Beispiel zeigt, wie Sie die Klasse "parallelcurrency::[Timer](../../parallel/concrt/reference/timer-class.md) " verwenden, um eine Nachricht in regelmäßigen Abständen zu senden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird während eines längeren Vorgangs der Status mithilfe eines `timer`-Objekts angezeigt. In diesem Beispiel wird das `timer`-Objekt mit einem [parallelcurrency:: Callcenter](../../parallel/concrt/reference/call-class.md) -Objekt verknüpft. Das `call`-Objekt gibt in regelmäßigen Intervallen an der Konsole eine Statusanzeige aus. Die [parallelcurrency:: Timer:: Start](reference/timer-class.md#start) -Methode führt den Timer in einem separaten Kontext aus. Die `perform_lengthy_operation`-Funktion Ruft die Funktion " [parallelcurrency:: Wait](reference/concurrency-namespace-functions.md#wait) " im Haupt Kontext auf, um einen zeitaufwändigen Vorgang zu simulieren.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `report-progress.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc Report-Progress. cpp**

## <a name="see-also"></a>Weitere Informationen

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
