---
title: 'Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächen Thread'
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 2ee15d4660984c9afb77cb20f8ef0dab25a8b933
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631713"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächen Thread

In diesem Dokument wird veranschaulicht, wie die-Concurrency Runtime verwendet wird, um die vom Benutzeroberflächen Thread in einer Microsoft Foundation Classes (MFC)-Anwendung ausgeführten Aufgaben in einen Arbeits Thread zu verschieben. Außerdem wird in diesem Dokument veranschaulicht, wie Sie die Leistung eines langen Zeichnungs Vorgangs verbessern können.

Entfernen von Arbeit aus dem UI-Thread durch das Auslagern blockierender Vorgänge (z. b. zeichnen) in Arbeitsthreads kann die Reaktionsfähigkeit Ihrer Anwendung verbessern. In dieser exemplarischen Vorgehensweise wird eine Zeichnungs Routine verwendet, mit der das Mandelbrot-Dezimalstellen generiert wird, um eine lange blockierende Operation Die Generierung des Mandelbrot-Bruch Tales ist auch ein guter Kandidat für die Parallelisierung, da die Berechnung der einzelnen Pixel unabhängig von allen anderen Berechnungen ist.

## <a name="prerequisites"></a>Erforderliche Komponenten

Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:

- [Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)

- [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)

- [Abbruch in der PPL](cancellation-in-the-ppl.md)

Außerdem wird empfohlen, dass Sie die Grundlagen der MFC-Anwendungsentwicklung und GDI+ verstehen, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen. Weitere Informationen zu MFC finden Sie unter [MFC-Desktop Anwendungen](../../mfc/mfc-desktop-applications.md). Weitere Informationen zu GDI+ finden Sie unter [GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

##  <a name="top"></a> Abschnitte

Diese exemplarische Vorgehensweise enthält folgende Abschnitte:

- [Erstellen der MFC-Anwendung](#application)

- [Implementieren der seriellen Version der Mandelbrot-Anwendung](#serial)

- [Entfernen von Arbeit aus dem Benutzeroberflächen Thread](#removing-work)

- [Verbessern der Zeichnungs Leistung](#performance)

- [Hinzufügen von Unterstützung für Abbruch](#cancellation)

##  <a name="application"></a>Erstellen der MFC-Anwendung

In diesem Abschnitt wird beschrieben, wie die grundlegende MFC-Anwendung erstellt wird.

### <a name="to-create-a-visual-c-mfc-application"></a>So erstellen Sie eine C++ Visual MFC-Anwendung

1. Verwenden Sie den **MFC-Anwendungs-Assistenten** , um eine MFC-Anwendung mit allen Standardeinstellungen zu erstellen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Verwenden der neuen MFC-Shell](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md) -Steuerelemente, um Anweisungen zum Öffnen des Assistenten für Ihre Version von Visual Studio zu finden.

1. Geben Sie einen Namen für das Projekt ein, z `Mandelbrot`. b., und klicken Sie dann auf **OK** , um den **MFC-Anwendungs-Assistenten**anzuzeigen.

1. Wählen Sie im Bereich **Anwendungstyp** die Option **einzelnes Dokument**aus. Stellen Sie sicher, dass das Kontrollkästchen **Unterstützung für Dokumente/Ansichts Architektur** deaktiviert ist.

1. Klicken Sie auf **Fertig** stellen, um das Projekt zu erstellen und den **MFC-Anwendungs Assistenten**zu schließen

   Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Klicken Sie im Menü **Erstellen** auf Projekt Mappe **Erstellen**, um die Anwendung zu erstellen. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debuggen** auf **Debugging starten** klicken.

##  <a name="serial"></a>Implementieren der seriellen Version der Mandelbrot-Anwendung

In diesem Abschnitt wird beschrieben, wie das Mandelbrot-Bruchteil gezeichnet wird. Diese Version zeichnet das Mandelbrot-Bruch Tal mit einem GDI+- [Bitmap](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) -Objekt und kopiert dann den Inhalt dieser Bitmap in das Client Fenster.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>So implementieren Sie die serielle Version der Mandelbrot-Anwendung

1. Fügen Sie in " *PCH. h* " (*stdafx. h* in Visual Studio 2017 und früher) `#include` die folgende Direktive hinzu:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. Definieren Sie in childview. h nach `pragma` der-Direktive `BitmapPtr` den-Typ. Der `BitmapPtr` -Typ ermöglicht einen Zeiger auf `Bitmap` ein-Objekt, das von mehreren Komponenten gemeinsam genutzt werden kann. Das `Bitmap` -Objekt wird gelöscht, wenn von keiner Komponente mehr darauf verwiesen wird.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. Fügen Sie in childview. h dem- `protected` Abschnitt `CChildView` der-Klasse den folgenden Code hinzu:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. Kommentieren Sie in childview. cpp die folgenden Zeilen aus, oder entfernen Sie Sie.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   In Debugbuilds wird durch diesen Schritt verhindert, dass die `DEBUG_NEW` Anwendung die Zuweisung verwendet, die nicht mit GDI+ kompatibel ist.

1. Fügen Sie in childview. cpp eine `using` -Direktive `Gdiplus` zum-Namespace hinzu.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Fügen Sie dem Konstruktor und Dekonstruktor `CChildView` der-Klasse den folgenden Code hinzu, um GDI+ zu initialisieren und zu beenden.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Implementieren Sie die `CChildView::DrawMandelbrot`-Methode. Diese Methode zeichnet das Mandelbrot-Bruch Tal mit dem `Bitmap` angegebenen Objekt.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Implementieren Sie die `CChildView::OnPaint`-Methode. Diese Methode ruft `CChildView::DrawMandelbrot` auf und kopiert dann den Inhalt `Bitmap` des-Objekts in das-Fenster.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. Überprüfen Sie, ob die Anwendung erfolgreich aktualisiert wurde, indem Sie Sie entwickeln und ausführen.

Die folgende Abbildung zeigt die Ergebnisse der Mandelbrot-Anwendung.

![Die Mandelbrot-Anwendung](../../parallel/concrt/media/mandelbrot.png "Die Mandelbrot-Anwendung")

Da die Berechnung der einzelnen Pixel Rechen intensiv ist, kann der UI-Thread keine weiteren Nachrichten verarbeiten, bis die Gesamtberechnung abgeschlossen ist. Dies kann die Reaktionsfähigkeit in der Anwendung verringern. Sie können dieses Problem jedoch beheben, indem Sie die Arbeit aus dem UI-Thread entfernen.

[[Nach oben](#top)]

##  <a name="removing-work"></a>Entfernen von Arbeit aus dem UI-Thread

In diesem Abschnitt wird gezeigt, wie die Zeichnungs Arbeit aus dem UI-Thread in der Mandelbrot-Anwendung entfernt wird. Durch das Verschieben von Zeichnungs Arbeit aus dem UI-Thread in einen Arbeits Thread kann der UI-Thread Nachrichten verarbeiten, wenn der Arbeits Thread das Bild im Hintergrund generiert.

Der Concurrency Runtime bietet drei Möglichkeiten zum Ausführen von Tasks: Aufgaben [Gruppen](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)und [Lightweight-Tasks](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Obwohl Sie eine dieser Mechanismen verwenden können, um Arbeit aus dem UI-Thread zu entfernen, wird in diesem Beispiel ein [parallelcurrency:: task_group](reference/task-group-class.md) -Objekt verwendet, da Aufgaben Gruppen einen Abbruch unterstützen. In dieser exemplarischen Vorgehensweise wird später der Abbruch verwendet, um den Arbeitsaufwand zu reduzieren, der beim Ändern der Größe des Client Fensters ausgeführt wird, und um die Bereinigung auszuführen, wenn das Fenster zerstört wird.

In diesem Beispiel wird auch ein [parallelcurrency:: Unbounded_buffer](reference/unbounded-buffer-class.md) -Objekt verwendet, um den UI-Thread und den Arbeits Thread zu ermöglichen, miteinander zu kommunizieren. Nachdem der Arbeits Thread das Image erstellt hat, sendet er einen Zeiger auf `Bitmap` das-Objekt `unbounded_buffer` an das-Objekt und sendet dann eine Paint-Meldung an den UI-Thread. Der UI-Thread empfängt dann das `unbounded_buffer` `Bitmap` Objekt aus dem Objekt und zeichnet es in das Client Fenster.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>So entfernen Sie die Zeichnungs Arbeit aus dem UI-Thread

1. Fügen Sie in " *PCH. h* " (*stdafx. h* in Visual Studio 2017 und früher) `#include` die folgenden Anweisungen hinzu:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. Fügen Sie in childview. h `task_group` dem `unbounded_buffer` `protected` -Abschnitt der `CChildView` -Klasse die-und-Member-Variablen hinzu. Das `task_group` -Objekt enthält die Aufgaben, die das Zeichnen `unbounded_buffer` ausführen; das-Objekt enthält das abgeschlossene Mandelbrot-Bild.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. Fügen Sie in childview. cpp eine `using` -Direktive `concurrency` zum-Namespace hinzu.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. In der `CChildView::DrawMandelbrot` -Methode wird nach `Bitmap::UnlockBits`dem-Befehl die Funktion "parallelcurrency [:: Send](reference/concurrency-namespace-functions.md#send) " aufgerufen, `Bitmap` um das Objekt an den UI-Thread zu übergeben. Senden Sie dann eine Paint-Meldung an den UI-Thread, und machen Sie den Client Bereich für ungültig.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Aktualisieren Sie `CChildView::OnPaint` die-Methode, um `Bitmap` das aktualisierte Objekt zu erhalten, und zeichnen Sie das Bild in das Client Fenster.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   Die `CChildView::OnPaint` -Methode erstellt eine Aufgabe zum Generieren des Mandelbrot-Bilds, wenn keine im Nachrichten Puffer vorhanden ist. Der Nachrichten Puffer enthält `Bitmap` kein-Objekt in Fällen wie z. b. die anfängliche Zeichnungs Nachricht und, wenn ein anderes Fenster vor dem Client Fenster verschoben wird.

1. Überprüfen Sie, ob die Anwendung erfolgreich aktualisiert wurde, indem Sie Sie entwickeln und ausführen.

Die Benutzeroberfläche reagiert nun schneller, da die Zeichnungs Arbeit im Hintergrund ausgeführt wird.

[[Nach oben](#top)]

##  <a name="performance"></a>Verbessern der Zeichnungs Leistung

Die Generierung des Mandelbrot-Bruch Tales ist ein guter Kandidat für die Parallelisierung, da die Berechnung der einzelnen Pixel unabhängig von allen anderen Berechnungen ist. Um die Zeichnungs Prozedur zu parallelisieren, konvertieren Sie `for` die äußere Schleife `CChildView::DrawMandelbrot` in der-Methode wie folgt in einen aufzurufenden " [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) "-Algorithmus.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Da die Berechnung der einzelnen Bitmap-Elemente unabhängig ist, müssen Sie die Zeichnungsvorgänge, die auf den Bitmapspeicher zugreifen, nicht synchronisieren. Dies ermöglicht die Skalierung der Leistung, wenn sich die Anzahl der verfügbaren Prozessoren erhöht.

[[Nach oben](#top)]

##  <a name="cancellation"></a>Hinzufügen von Unterstützung für Abbruch

In diesem Abschnitt wird beschrieben, wie die Fenstergröße geändert wird und wie alle aktiven Zeichnungs Aufgaben abgebrochen werden, wenn das Fenster zerstört wird.

Der Dokument [Abbruch in der ppl](cancellation-in-the-ppl.md) erläutert, wie ein Abbruch in der Laufzeit funktioniert. Abbruch ist kooperativ; Daher wird Sie nicht sofort ausgeführt. Um eine abgebrochene Aufgabe zu beenden, löst die Laufzeit eine interne Ausnahme während eines nachfolgenden Aufrufes von der Aufgabe in der Laufzeit aus. Im vorherigen Abschnitt wird gezeigt, wie der `parallel_for` -Algorithmus verwendet wird, um die Leistung der Zeichnungs Aufgabe zu verbessern. Der-Befehl ermöglicht der Common Language Runtime, die Aufgabe zu unterbrechen, sodass der Abbruch funktioniert. `parallel_for`

### <a name="cancelling-active-tasks"></a>Aktive Tasks werden abgebrochen

Die Mandelbrot-Anwendung `Bitmap` erstellt-Objekte, deren Dimensionen der Größe des Client Fensters entsprechen. Jedes Mal, wenn die Größe des Client Fensters geändert wird, erstellt die Anwendung eine zusätzliche Hintergrundaufgabe zum Generieren eines Bilds für die neue Fenstergröße. Diese zwischen Abbilder sind für die Anwendung nicht erforderlich. Es ist nur das Bild für die endgültige Fenstergröße erforderlich. Um zu verhindern, dass die Anwendung diese zusätzliche Arbeit durchführt, können Sie alle aktiven Zeichnungs Aufgaben in den Meldungs Handlern `WM_SIZING` für die `WM_SIZE` Meldungen und Abbrechen und die Zeichnungs Arbeit nach der Größenänderung des Fensters erneut planen.

Um aktive Zeichnungs Aufgaben abzubrechen, wenn die Größe des Fensters geändert wird, ruft die Anwendung die Methode "parallelcurrency [:: task_group:: Cancel](reference/task-group-class.md#cancel) " in `WM_SIZING` den `WM_SIZE` Handlern für die Nachrichten und auf. Der Handler für die `WM_SIZE` Nachricht ruft auch die "parallelcurrency [:: task_group:: Wait](reference/task-group-class.md#wait) "-Methode auf, um zu warten, bis alle aktiven Aufgaben vollständig sind, und plant dann die Zeichnungs Aufgabe für die aktualisierte Fenstergröße neu.

Wenn das Client Fenster zerstört wird, empfiehlt es sich, alle aktiven Zeichnungs Aufgaben abzubrechen. Wenn Sie alle aktiven Zeichnungs Aufgaben abbrechen, wird sichergestellt, dass Arbeitsthreads keine Nachrichten an den UI-Thread senden, nachdem das Client Fenster zerstört wurde. Die Anwendung bricht alle aktiven Zeichnungs Aufgaben im Handler für die `WM_DESTROY` Nachricht ab.

### <a name="responding-to-cancellation"></a>Reagieren auf Abbruch

Die `CChildView::DrawMandelbrot` Methode, die die Zeichnungs Aufgabe ausführt, muss auf den Abbruch reagieren. Da die Common Language Runtime die Ausnahmebehandlung zum Abbrechen von `CChildView::DrawMandelbrot` Aufgaben verwendet, muss die-Methode einen Ausnahme sicheren Mechanismus verwenden, um sicherzustellen, dass alle Ressourcen ordnungsgemäß bereinigt werden. In diesem Beispiel wird das RAII ( *Resource Acquisition Is Initialization* )-Muster verwendet, um sicherzustellen, dass die Bitmapbits entsperrt werden, wenn die Aufgabe abgebrochen wird.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>So fügen Sie Unterstützung für den Abbruch in der Mandelbrot-Anwendung hinzu

1. Fügen Sie in childview. h im `protected` -Abschnitt `CChildView` der-Klasse Deklarationen für die `OnSize`- `OnSizing`,- `OnDestroy` und-Nachrichten Zuordnungs Funktionen hinzu.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. Ändern Sie in childview. cpp die Meldungs Zuordnung so, dass Sie Handler `WM_SIZE`für `WM_SIZING`die nach `WM_DESTROY` richten, und enthält.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Implementieren Sie die `CChildView::OnSizing`-Methode. Mit dieser Methode werden alle vorhandenen Zeichnungs Aufgaben abgebrochen.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Implementieren Sie die `CChildView::OnSize`-Methode. Diese Methode bricht alle vorhandenen Zeichnungs Aufgaben ab und erstellt eine neue Zeichnungs Aufgabe für die aktualisierte Client Fenstergröße.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Implementieren Sie die `CChildView::OnDestroy`-Methode. Mit dieser Methode werden alle vorhandenen Zeichnungs Aufgaben abgebrochen.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. Definieren Sie in childview. cpp die `scope_guard` -Klasse, die das RAII-Muster implementiert.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Fügen Sie den folgenden Code `CChildView::DrawMandelbrot` der-Methode nach dem `Bitmap::LockBits`-Befehl hinzu:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Dieser Code behandelt den Abbruch durch Erstellen `scope_guard` eines-Objekts. Wenn das Objekt den Gültigkeitsbereich verlässt, entsperrt es die Bitmapbits.

1. Ändern Sie das Ende der `CChildView::DrawMandelbrot` -Methode, um `scope_guard` das Objekt zu verwerfen, nachdem die Bitmapbits entsperrt wurden, aber bevor Nachrichten an den UI-Thread gesendet werden. Dadurch wird sichergestellt, dass der UI-Thread nicht aktualisiert wird, bevor die Bitmapbits entsperrt werden.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Überprüfen Sie, ob die Anwendung erfolgreich aktualisiert wurde, indem Sie Sie entwickeln und ausführen.

Wenn Sie die Größe des Fensters ändern, wird die Zeichnungs Arbeit nur für die endgültige Fenstergröße ausgeführt. Alle aktiven Zeichnungs Aufgaben werden auch abgebrochen, wenn das Fenster zerstört wird.

[[Nach oben](#top)]

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)
