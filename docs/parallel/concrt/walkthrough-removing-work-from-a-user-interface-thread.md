---
title: "Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c32613aa6938b873a820fbb491fa2c507605a6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread
Dieses Dokument veranschaulicht, wie die Concurrency Runtime zu verwenden, um die Arbeit zu verschieben, die von der Benutzeroberfläche (UI)-Thread in einer Anwendung Microsoft Foundation Classes (MFC) zu einem Arbeitsthread ausgeführt wird. Dieses Dokument wird gezeigt, wie die Leistung eines langwierigen Zeichenvorgangs zu verbessern.  
  
 Entfernen von Arbeit aus dem UI-Thread durch Auslagern der blockierenden Vorgänge, kann z. B. zeichnen, um die Anzahl der Arbeitsthreads die Reaktionsfähigkeit der Anwendung verbessern. Diese exemplarische Vorgehensweise verwendet eine zeichnen-Routine, die das Mandelbrot-Fraktal zur Veranschaulichung eines langwierigen Blockierungsvorgang generiert. Die Generierung von Mandelbrot-Fraktal ist auch ein guter Kandidat für die Parallelisierung, da die Berechnung jedes Pixels von allen anderen Berechnungen unabhängig ist.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)  
  
-   [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Abbruch in der PPL](cancellation-in-the-ppl.md)  
  
 Zudem wird empfohlen, dass Sie wissen, dass die Grundlagen der MFC-Anwendungsentwicklung und [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] , bevor Sie diese exemplarische Vorgehensweise starten. Weitere Informationen über MFC finden Sie unter [MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md). Weitere Informationen zu [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)], finden Sie unter [GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798).  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
-   [Erstellen der Mfc_anwendung](#application)  
  
-   [Implementieren die serielle Version des Mandelbrot-Anwendung](#serial)  
  
-   [Entfernen von Arbeit aus dem Benutzeroberflächenthread](#removing-work)  
  
-   [Zeichnen die Leistung verbessern](#performance)  
  
-   [Hinzufügen von Unterstützung für den Abbruch](#cancellation)  
  
##  <a name="application"></a>Erstellen der Mfc_anwendung  
 Dieser Abschnitt beschreibt, wie die grundlegende MFC-Anwendung zu erstellen.  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Erstellen eine Visual C++-MFC-Anwendung  
  
1.  Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld die **installierte Vorlagen** klicken Sie im Bereich **Visual C++**, und dann auf die **Vorlagen** klicken Sie im Bereich **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. `Mandelbrot`, und klicken Sie dann auf **OK** zum Anzeigen der **MFC-Anwendung-Assistent**.  
  
3.  In der **Anwendungstyp** klicken Sie im Bereich **einzelnes Dokument**. Sicherstellen, dass die **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Kontrollkästchen ist deaktiviert.  
  
4.  Klicken Sie auf **Fertig stellen** zum Erstellen des Projekts, und schließen Sie die **MFC-Anwendung-Assistent**.  
  
     Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Um die Anwendung zu erstellen. die **erstellen** Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung, indem Sie auf **Debuggen** auf die **Debuggen** Menü.  
  
##  <a name="serial"></a>Implementieren die serielle Version des Mandelbrot-Anwendung  
 Dieser Abschnitt beschreibt, wie das Mandelbrot-Fraktal gezeichnet werden soll. Diese Version zeichnet das Mandelbrot-Fraktal zu einem [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/library/ms534420.aspx) Objekt, und klicken Sie dann auf die Client-Fenster kopiert den Inhalt dieser Bitmap.  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Implementieren Sie die serielle Version des Mandelbrot-Anwendung  
  
1.  Fügen Sie in "stdafx.h" die folgenden `#include` Richtlinie:  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  In ChildView.h nach der `pragma` Richtlinie definieren die `BitmapPtr` Typ. Die `BitmapPtr` Typ ermöglicht es, einen Zeiger auf eine `Bitmap` Objekt von mehreren Komponenten gemeinsam genutzt werden. Die `Bitmap` Objekt wird gelöscht, wenn er von keiner Komponente nicht mehr verwiesen wird.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  Fügen Sie den folgenden Code hinzu, in ChildView.h der `protected` Teil der `CChildView` Klasse:  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  Kommentieren Sie in ChildView.cpp Sie aus, oder entfernen Sie die folgenden Zeilen.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     In Debugbuilds verhindert diesen Schritt die Anwendung am Verwenden der `DEBUG_NEW` Zuweisung, die nicht kompatibel mit ist [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
5.  Fügen Sie in ChildView.cpp eine `using` -Direktive die `Gdiplus` Namespace.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  Fügen Sie den folgenden Code zum Konstruktor und Destruktor, der die `CChildView` Klasse zu initialisieren und Herunterfahren [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  Implementieren Sie die `CChildView::DrawMandelbrot`-Methode. Diese Methode zeichnet das Mandelbrot-Fraktal in den angegebenen `Bitmap` Objekt.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  Implementieren Sie die `CChildView::OnPaint`-Methode. Diese Methode ruft `CChildView::DrawMandelbrot` und kopiert dann den Inhalt der `Bitmap` -Objekt, das Fenster.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.  
  
 Die folgende Abbildung zeigt die Ergebnisse der Mandelbrot-Anwendung.  
  
 ![Mandelbrot-Anwendung](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")  
  
 Da die Berechnung von jedem Pixel rechenintensiv ist, verarbeiten nicht im UI-Thread zusätzliche Nachrichten, bis die gesamte Berechnung abgeschlossen ist. Dies könnte die Reaktionszeit der Anwendung verringern. Allerdings können Sie dieses Problem durch Entfernen von Arbeit aus dem UI-Thread entlasten.  
  
 [[Nach oben](#top)]  
  
##  <a name="removing-work"></a>Entfernen von Arbeit aus dem UI-Thread  
 In diesem Abschnitt veranschaulicht, wie die Zeichnung Arbeit vom UI-Thread in der Mandelbrot-Anwendung zu entfernen. Zeichnen von UI-Thread in einen Arbeitsthread verschieben, kann die UI-Thread Nachrichten verarbeiten, wie der Arbeitsthread das Bild im Hintergrund generiert.  
  
 Die Concurrency Runtime bietet drei Möglichkeiten zum Ausführen von Aufgaben: [Aufgabengruppen](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [asynchrone Agents](../../parallel/concrt/asynchronous-agents.md), und [einfache Aufgaben](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Obwohl Sie eine der folgenden Mechanismen zum Entfernen von Arbeit von UI-Thread verwenden können, um dieses Beispiel verwendet eine [Concurrency:: task_group](reference/task-group-class.md) Objekt, da Aufgabengruppen Abbrüche unterstützen. Diese exemplarische Vorgehensweise verwendet später Abbruch der verbleibende Arbeitsaufwand zu reduzieren, die ausgeführt wird, wenn der Client Fenstergröße und Cleanup auszuführen, wenn das Fenster zerstört wird.  
  
 Dieses Beispiel verwendet außerdem eine [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Objekt, das im UI-Thread und der Arbeitsthread seine miteinander kommunizieren können. Nachdem der Arbeitsthread auf das Bild erzeugt, sendet er einen Zeiger auf die `Bitmap` -Objekt an die `unbounded_buffer` Objekt, und klicken Sie dann sendet eine Paint-Meldung an den UI-Thread. Die UI-Thread empfängt dann von der `unbounded_buffer` Objekt die `Bitmap` -Objekt und zeichnet es auf dem Client-Fenster.  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>So entfernen Sie die Zeichnung Arbeit vom UI-thread  
  
1.  Fügen Sie in "stdafx.h" die folgenden `#include` Direktiven:  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  Fügen Sie in ChildView.h `task_group` und `unbounded_buffer` Membervariablen der `protected` Teil der `CChildView` Klasse. Die `task_group` -Objekt enthält die Aufgaben, die Zeichnung; Ausführen der `unbounded_buffer` -Objekt enthält das abgeschlossene Mandelbrot-Bild.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  Fügen Sie in ChildView.cpp eine `using` -Direktive die `concurrency` Namespace.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  In der `CChildView::DrawMandelbrot` Methode nach dem Aufruf von `Bitmap::UnlockBits`, rufen Sie die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion übergeben der `Bitmap` Objekt an den UI-Thread. Anschließend senden Sie eine Paint-Meldung an den UI-Thread und den Clientbereich für ungültig erklärt.  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  Update der `CChildView::OnPaint` Methode, um die aktualisierte empfangen `Bitmap` Objekt, und ziehen Sie das Bild zu Client-Fenster.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     Die `CChildView::OnPaint` Methode erstellt eine Aufgabe, um das Mandelbrot-Bild zu generieren, wenn noch nicht in den Nachrichtenpuffer vorhanden ist. Der Meldungspuffer enthält kein `Bitmap` Objekt in Fällen, z. B. die anfängliche Paint-Meldung, und wenn ein anderes Fenster vor der Client-Fenster verschoben wird.  
  
6.  Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.  
  
 Die Benutzeroberfläche ist nun anpassbar, da die Zeichnung Arbeit im Hintergrund ausgeführt wird.  
  
 [[Nach oben](#top)]  
  
##  <a name="performance"></a>Zeichnen die Leistung verbessern  

 Die Generierung von Mandelbrot-Fraktal ist ein guter Kandidat für die Parallelisierung, da die Berechnung jedes Pixels unabhängig von allen anderen Berechnungen ist. Um das Zeichnen Verfahren zu parallelisieren, konvertieren Sie die äußere `for` wurde eine Schleife in der `CChildView::DrawMandelbrot` Methode zu einem Aufruf von der [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus wie folgt.  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 Da die Berechnung der einzelnen Elemente mithilfe einer Bitmap unabhängig sind, müssen Sie nicht die Zeichenoperationen zu synchronisieren, die den Bitmapspeicher zugreifen. Dadurch können die Leistung als die Anzahl der verfügbaren Prozessoren zu skalieren.  
  
 [[Nach oben](#top)]  
  
##  <a name="cancellation"></a>Hinzufügen von Unterstützung für den Abbruch  
 In diesem Abschnitt wird beschrieben, wie Fenstergröße behandelt und wie Sie alle aktiven zeichnen Aufgaben abbrechen, wenn das Fenster zerstört wird.  
  
 Das Dokument [Abbruch in der PPL](cancellation-in-the-ppl.md) wird erläutert, wie Abbrüche in der Laufzeit funktionieren. Abbruch ist kooperativ; aus diesem Grund es nicht unmittelbar. Um eine abgebrochene Aufgabe beenden, löst die Laufzeit eine interne Ausnahme bei einem nachfolgenden Aufruf von der Aufgabe in der Laufzeit. Im vorherigen Abschnitt zeigt, wie die `parallel_for` Algorithmus zum Verbessern der Leistung des Tasks "Zeichnen". Der Aufruf von `parallel_for` kann die Laufzeit den Vorgang zu beenden und Abbrüche zu arbeiten.  
  
### <a name="cancelling-active-tasks"></a>Abbrechen von aktiven Aufgaben  
 Mandelbrot-Anwendung erstellt `Bitmap` Objekte, deren Dimensionen, die Größe des Clientfensters entsprechen. Jedes Mal, wenn das Clientfenster angepasst wird, erstellt die Anwendung eine zusätzliche Hintergrundaufgabe, um ein Bild für die neue Fenstergröße zu generieren. Die Anwendung erfordert keine diese intermediate Images; nur das Bild erforderlich für die abschließende Fenstergröße. Um zu verhindern, dass die Anwendung aus dieser zusätzlichen Arbeiten ausführen, brechen Sie alle aktiven zeichnen Aufgaben in die Message-Handler für das `WM_SIZE` und `WM_SIZING` Nachrichten und dann neu planen Zeichnung funktionieren nach der Größe des Fensters geändert wird.  
  
 Um aktiven zeichnen Aufgaben abbrechen, wenn die Fenstergröße geändert wird, ruft die Anwendung die [task_group](reference/task-group-class.md#cancel) Methode in die Handler für das `WM_SIZING` und `WM_SIZE` Nachrichten. Der Handler für das `WM_SIZE` Nachricht auch Aufrufe der [Concurrency:: task_group::](reference/task-group-class.md#wait) Methode zu warten, bis alle aktiven Aufgaben durch, um Sie abzuschließen und anschließend plant die Zeichnung Aufgabe für die aktualisierte Fenstergröße.  
  
 Wenn das Clientfenster zerstört wird, ist es empfiehlt sich, alle aktiven zeichnen Aufgaben abzubrechen. Alle aktiven zeichnen Aufgaben abbrechen, wird sichergestellt, dass es sich bei Arbeitsthreads keine buchen Nachrichten an den UI-Thread, nachdem der Client-Fenster zerstört wird. Bricht alle aktiven zeichnen Aufgaben im Handler für die Anwendung die `WM_DESTROY` Nachricht.  
  
### <a name="responding-to-cancellation"></a>Auf den Abbruch reagieren  
 Die `CChildView::DrawMandelbrot` -Methode, die die Zeichnung Aufgabe ausführt, muss auf den Abbruch reagieren. Da die Common Language Runtime zum Abbrechen der Aufgaben, Ausnahmebehandlung verwendet die `CChildView::DrawMandelbrot` Methode muss einen ausnahmesicheren Mechanismus verwenden, um sicherzustellen, dass alle Ressourcen ordnungsgemäß bereinigt werden. Dieses Beispiel verwendet die *Resource Acquisition Is Initialization* (RAII)-Muster können Sie sicherstellen, dass die Bitmapbits entsperrt werden, wenn die Aufgabe abgebrochen wird.  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Zum Hinzufügen der Unterstützung für den Abbruch in der Mandelbrot-Anwendung  
  
1.  In ChildView.h in der `protected` Teil der `CChildView` -Klasse verwenden, fügen Sie die Deklarationen für die `OnSize`, `OnSizing`, und `OnDestroy` Nachrichtenfunktionen Zuordnung.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  Ändern Sie in ChildView.cpp die meldungszuordnung, um Handler für enthalten die `WM_SIZE`, `WM_SIZING`, und `WM_DESTROY` Nachrichten.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  Implementieren Sie die `CChildView::OnSizing`-Methode. Diese Methode bricht alle vorhandenen zeichnen Aufgaben ab.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  Implementieren Sie die `CChildView::OnSize`-Methode. Diese Methode bricht alle vorhandenen zeichnen Aufgaben ab und erstellt eine neue zeichnen Aufgabe für die Fenstergröße des aktualisierten Clients.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  Implementieren Sie die `CChildView::OnDestroy`-Methode. Diese Methode bricht alle vorhandenen zeichnen Aufgaben ab.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  Definieren Sie in ChildView.cpp die `scope_guard` -Klasse, die das RAII-Muster implementiert.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  Fügen Sie folgenden Code, der `CChildView::DrawMandelbrot` Methode nach dem Aufruf von `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     Dieser Code behandelt Abbruch durch das Erstellen einer `scope_guard` Objekt. Wenn das Objekt den Gültigkeitsbereich verlässt, entsperrt, die mithilfe einer Bitmapbits.  
  
8.  Ändern Sie das Ende der `CChildView::DrawMandelbrot` Methode beim Schließen der `scope_guard` Objekt, nachdem die Bitmapbits entsperrt werden, aber vor dem Senden von Nachrichten an den UI-Thread. Dadurch wird sichergestellt, dass der UI-Thread nicht aktualisiert wird, bevor die Bitmapbits Sperre aufgehoben werden.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.  
  
 Beim Ändern der Größe des Fensters erfolgt nur für die Größe des endgültigen Fensters zeichnen arbeiten. Wenn das Fenster zerstört wird, werden alle aktiven zeichnen Aufgaben auch abgebrochen.  
  
 [[Nach oben](#top)]  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime Exemplarische Vorgehensweisen](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)
