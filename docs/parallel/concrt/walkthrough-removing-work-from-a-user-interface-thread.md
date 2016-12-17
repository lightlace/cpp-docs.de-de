---
title: "Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberfl&#228;chenthread"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Entfernen von Arbeit aus Benutzeroberflächenthreads [Concurrency Runtime]"
  - "Benutzeroberflächenthreads, Entfernen von Arbeit aus [Concurrency Runtime]"
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 14
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberfl&#228;chenthread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument veranschaulicht, wie Sie Verarbeitungsschritte, die in einer MFC\-Anwendung \(Microsoft Foundation Classes\) im Benutzeroberflächenthread ausgeführt werden, mithilfe der Concurrency Runtime in einen Arbeitsthread verschieben können.  Außerdem werden in diesem Dokument Möglichkeiten der Leistungsverbesserung bei aufwändigen Zeichenvorgängen beschrieben.  
  
 Durch das Auslagern blockierender Verarbeitungsschritte, z. B. für das Zeichnen, aus dem UI\-Thread in Arbeitsthreads kann die Reaktionszeit der Anwendung verbessert werden.  Diese exemplarische Vorgehensweise verwendet eine Zeichnungsroutine, die das Mandelbrot\-Fraktal generiert, um einen aufwändigen blockierenden Vorgang zu veranschaulichen.  Die Generierung des Mandelbrot\-Fraktals ist außerdem gut für die Parallelisierung geeignet, da die Berechnung jedes Pixels von allen anderen Berechnungen unabhängig ist.  
  
## Vorbereitungsmaßnahmen  
 Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)  
  
-   [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)  
  
 Es wird empfohlen, dass Sie sich auch mit den Grundlagen der MFC\-Anwendungsentwicklung und mit [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] vertraut machen, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.  Weitere Informationen über MFC finden Sie unter [MFC\-Desktopanwendungen](../../mfc/mfc-desktop-applications.md).  Weitere Informationen zu [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] finden Sie unter [GDI\+](_gdiplus_GDI_start_cpp).  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
-   [Erstellen der MFC\-Anwendung](#application)  
  
-   [Implementieren der seriellen Version der Mandelbrot\-Anwendung](#serial)  
  
-   [Entfernen von Verarbeitungsschritten aus dem Benutzeroberflächenthread](#removing-work)  
  
-   [Verbessern der Zeichenleistung](#performance)  
  
-   [Hinzufügen von Unterstützung für Abbrüche](#cancellation)  
  
##  <a name="application"></a> Erstellen der MFC\-Anwendung  
 In diesem Abschnitt wird beschrieben, wie die grundlegende MFC\-Anwendung erstellt wird.  
  
### So erstellen Sie eine Visual C\+\+\-MFC\-Anwendung  
  
1.  Klicken Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt**.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Installierte Vorlagen** den Typ **Visual C\+\+** aus, und klicken Sie dann im Bereich **Vorlagen** auf **MFC\-Anwendung**.  Geben Sie einen Namen für das Projekt ein, z. B. `Mandelbrot`, und klicken Sie dann auf **OK**, um den **MFC\-Anwendungs\-Assistenten** anzuzeigen.  
  
3.  Wählen Sie im Bereich **Anwendungstyp** die Option **Einfaches Dokument** aus.  Stellen Sie sicher, dass das Kontrollkästchen **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert ist.  
  
4.  Klicken Sie auf **Fertig stellen**, um das Projekt zu erstellen und den **MFC\-Anwendungs\-Assistenten** zu schließen.  
  
     Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um die Anwendung zu erstellen.  Wenn die Anwendung erfolgreich erstellt wird, führen Sie die Anwendung aus, indem Sie im Menü **Debug** auf **Debugging starten** klicken.  
  
##  <a name="serial"></a> Implementieren der seriellen Version der Mandelbrot\-Anwendung  
 In diesem Abschnitt wird beschrieben, wie das Mandelbrot\-Fraktal gezeichnet wird.  Diese Version zeichnet das Mandelbrot\-Fraktal in ein [Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx)\-Objekt von [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] und kopiert anschließend den Inhalt dieser Bitmap in das Clientfenster.  
  
#### So implementieren Sie die serielle Version der Mandelbrot\-Anwendung  
  
1.  Fügen Sie in der Datei stdafx.h die folgende `#include`\-Direktive hinzu:  
  
     [!CODE [concrt-mandelbrot#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#1)]  
  
2.  Definieren Sie in ChildView.h nach der `pragma`\-Direktive den `BitmapPtr`\-Typ.  Der `BitmapPtr`\-Typ ermöglicht es, einen Zeiger auf ein `Bitmap`\-Objekt in mehreren Komponenten gemeinsam zu verwenden.  Das `Bitmap`\-Objekt wird gelöscht, wenn keine Komponente mehr auf das Objekt verweist.  
  
     [!CODE [concrt-mandelbrot#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#2)]  
  
3.  Fügen Sie in ChildView.h im `protected`\-Abschnitt der `CChildView`\-Klasse folgenden Code hinzu:  
  
     [!CODE [concrt-mandelbrot#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#3)]  
  
4.  Löschen oder kommentieren Sie in ChildView.cpp folgende Zeilen aus.  
  
     [!CODE [concrt-mandelbrot#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#4)]  
  
     In Debugbuilds verhindert dieser Schritt, dass die Anwendung die `DEBUG_NEW`\-Belegungsfunktion verwendet, die mit [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] nicht kompatibel ist.  
  
5.  Fügen Sie in ChildView.cpp dem `Gdiplus`\-Namespace eine `using`\-Direktive hinzu.  
  
     [!CODE [concrt-mandelbrot#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#5)]  
  
6.  Fügen Sie dem Konstruktor und dem Destruktor der `CChildView`\-Klasse den folgenden Code zum Initialisieren und Schließen von [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] hinzu.  
  
     [!CODE [concrt-mandelbrot#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#6)]  
  
7.  Implementieren Sie die `CChildView::DrawMandelbrot`\-Methode.  Diese Methode zeichnet das Mandelbrot\-Fraktal im angegebenen `Bitmap`\-Objekt.  
  
     [!CODE [concrt-mandelbrot#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#7)]  
  
8.  Implementieren Sie die `CChildView::OnPaint`\-Methode.  Diese Methode ruft `CChildView::DrawMandelbrot` auf und kopiert anschließend den Inhalt des `Bitmap`\-Objekts in das Fenster.  
  
     [!CODE [concrt-mandelbrot#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#8)]  
  
9. Überprüfen Sie, ob das Aktualisieren der Anwendung erfolgreich war, indem Sie sie erstellen und ausführen.  
  
 Die folgende Abbildung zeigt die Ausgabe der Mandelbrot\-Anwendung.  
  
 ![Mandelbrot&#45;Anwendung](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")  
  
 Da die Berechnung für jedes Pixel rechenintensiv ist, kann der UI\-Thread erst dann wieder andere Meldungen verarbeiten, wenn die gesamte Berechnung abgeschlossen ist.  Dies kann die Reaktionszeit der Anwendung herabsetzen.  Sie können dieses Problem jedoch vermeiden, indem Sie die Verarbeitung aus dem UI\-Thread auslagern.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="removing-work"></a> Auslagern der Verarbeitung aus dem UI\-Thread  
 Dieser Abschnitt beschreibt, wie die Zeichenarbeit der Mandelbrot\-Anwendung aus dem UI\-Thread ausgelagert wird.  Wenn die Zeichenarbeit aus dem UI\-Thread in einen Arbeitsthread verschoben wird, kann der UI\-Thread weiter Meldungen verarbeiten, während der Arbeitsthread im Hintergrund das Bild generiert.  
  
 Die Concurrency Runtime bietet drei Möglichkeiten, Aufgaben auszuführen: [Aufgabengruppen](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [asynchrone Agents](../../parallel/concrt/asynchronous-agents.md) und [einfache Aufgaben](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  Obwohl Sie jeden dieser Mechanismen verwenden können, um die Arbeit aus dem UI\-Thread auszulagern, wird in diesem Beispiel ein [concurrency::task\_group](../Topic/task_group%20Class.md)\-Objekt, da Aufgabengruppen Abbrüche unterstützen.  Im weiteren Verlauf dieser exemplarischen Vorgehensweise werden Abbrüche verwendet, um den Arbeitsaufwand bei Größenänderungen des Clientfensters zu verringern und um die Bereinigung durchzuführen, wenn das Fenster zerstört wird.  
  
 Das Beispiel verwendet außerdem ein [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)\-Objekt, über das der UI\-Thread und der Arbeitsthread zu aktivieren, dass sie miteinander kommunizieren.  Nachdem der Arbeitsthread das Bild erzeugt hat, sendet er einen Zeiger auf das `Bitmap`\-Objekt an das `unbounded_buffer`\-Objekt und gibt anschließend eine paint\-Meldung an den UI\-Thread aus.  Der UI\-Thread empfängt dann das `Bitmap`\-Objekt vom `unbounded_buffer`\-Objekt und zeichnet es im Clientfenster.  
  
#### So lagern Sie die Zeichenarbeit aus dem UI\-Thread aus  
  
1.  Fügen Sie in der Datei stdafx.h folgende `#include`\-Direktiven hinzu:  
  
     [!CODE [concrt-mandelbrot#101](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#101)]  
  
2.  Fügen Sie in ChildView.h `task_group`\- und `unbounded_buffer`\-Membervariablen im `protected`\-Abschnitt der `CChildView`\-Klasse hinzu.  Das `task_group`\-Objekt enthält die Aufgaben, die das Zeichnen ausführen und das `unbounded_buffer`\-Objekt enthält das abgeschlossene Mandelbrot\-Bild.  
  
     [!CODE [concrt-mandelbrot#102](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#102)]  
  
3.  Fügen Sie in ChildView.cpp dem `concurrency`\-Namespace eine `using`\-Direktive hinzu.  
  
     [!CODE [concrt-mandelbrot#103](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#103)]  
  
4.  In der `CChildView::DrawMandelbrot`\-Methode nach dem Aufruf von `Bitmap::UnlockBits`, rufen Sie die [concurrency::send](../Topic/send%20Function.md)\-Funktion auf, um das `Bitmap`\-Objekt an den UI\-Thread zu übergeben.  Geben Sie dann eine paint\-Meldung an den UI\-Thread aus, und legen Sie den Clientbereich als ungültig fest.  
  
     [!CODE [concrt-mandelbrot#104](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#104)]  
  
5.  Aktualisieren Sie die `CChildView::OnPaint`\-Methode, um das aktualisierte `Bitmap`\-Objekt zu empfangen und das Bild im Clientfenster zu zeichnen.  
  
     [!CODE [concrt-mandelbrot#105](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#105)]  
  
     Die `CChildView::OnPaint`\-Methode erstellt eine Aufgabe zum Generieren des Mandelbrot\-Bilds, wenn im Meldungspuffer noch kein Bild vorhanden ist.  Der Meldungspuffer enthält in verschiedenen Fällen kein `Bitmap`\-Objekt, z. B. während der ersten paint\-Meldung oder wenn ein anderes Fenster das Clientfenster verdeckt.  
  
6.  Überprüfen Sie, ob das Aktualisieren der Anwendung erfolgreich war, indem Sie sie erstellen und ausführen.  
  
 Die Benutzeroberfläche reagiert jetzt schneller, da die Zeichenarbeit im Hintergrund ausgeführt wird.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="performance"></a> Verbessern der Zeichenleistung  
 Die Generierung des Mandelbrot\-Fraktals ist außerdem gut für die Parallelisierung geeignet, da die Berechnung jedes Pixels von allen anderen Berechnungen unabhängig ist.  Um die Zeichnungsprozedur zu parallelisieren, konvertieren Sie die äußere `for` \- Schleife in der `CChildView::DrawMandelbrot`\-Methode in einen Aufruf des [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) \- Algorithmus, wie folgt.  
  
 [!CODE [concrt-mandelbrot#301](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#301)]  
  
 Da jedes Bitmapelement unabhängig berechnet wird, müssen Sie die Zeichenvorgänge, die auf den Bitmaparbeitsspeicher zugreifen, nicht synchronisieren.  Dadurch kann die Zeichenleistung in Abhängigkeit von der Anzahl der verfügbaren Prozessoren skalieren.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="cancellation"></a> Hinzufügen von Unterstützung für Abbrüche  
 In diesem Abschnitt wird beschrieben, wie Änderungen der Fenstergröße behandelt und wie aktive Zeichenaufgaben abgebrochen werden können, wenn das Fenster zerstört wird.  
  
 Das Dokument [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md) erläutert, wie Abbrüche in der Laufzeit funktionieren.  Abbrüche sind kooperativ und treten daher nicht sofort auf.  Um eine abgebrochene Aufgabe zu beenden, löst die Laufzeit eine interne Ausnahme während eines nachfolgenden Aufrufs der Laufzeit durch die Aufgabe aus.  Der vorherige Abschnitt zeigt, wie der `parallel_for`\-Algorithmus zum Verbessern der Leistung der Zeichenaufgabe verwendet werden kann.  Durch den Aufruf von `parallel_for` ist die Laufzeit in der Lage, die Aufgabe zu beenden und Abbrüche auszuführen.  
  
### Abbrechen von aktiven Aufgaben  
 Die Mandelbrot\-Anwendung erstellt `Bitmap`\-Objekte, deren Dimensionen der Größe des Clientfensters entsprechen.  Jedes Mal wenn die Größe des Clientfensters geändert wird, erstellt die Anwendung eine zusätzliche Hintergrundaufgabe, um ein Bild für die neue Fenstergröße zu generieren.  Die Anwendung benötigt diese Zwischenbilder nicht. Es wird nur das Bild für die abschließende Fenstergröße benötigt.  Um zu verhindern, dass die Anwendung diese zusätzliche Arbeit durchführt, können Sie alle aktiven Zeichenaufgaben in den Meldungshandlern für die `WM_SIZE`\- und die `WM_SIZING`\-Meldung abbrechen und die Zeichenarbeit neu planen, sobald die endgültige Größe des Fensters feststeht.  
  
 Um aktive Zeichenaufgaben abzubrechen wenn die Größe des Fensters geändert wird, ruft die Anwendung die [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md)\-Methode in den Handlern für die Meldungen `WM_SIZING` und `WM_SIZE` auf.  Der Handler für die `WM_SIZE` \- Meldung ruft außerdem die [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md)\-Methode auf, um für alle aktiven Aufgaben gewartet abzuschließen und plant dann die Zeichenaufgabe für die aktualisierte Fenstergröße neu.  
  
 Wenn das Clientfenster zerstört wird, empfiehlt es sich, alle aktiven Zeichenaufgaben abzubrechen.  Durch das Abbrechen aktiver Zeichenaufgaben wird sichergestellt, dass Arbeitsthreads keine Meldungen an den UI\-Thread ausgeben, nachdem das Clientfenster zerstört wurde.  Die Anwendung bricht alle aktiven Zeichenaufgaben im Handler für die `WM_DESTROY`\-Meldung ab.  
  
### Reagieren auf Abbrüche  
 Die `CChildView::DrawMandelbrot`\-Methode, die die Zeichenaufgabe ausführt, muss auf den Abbruch reagieren.  Da die Laufzeit Aufgaben durch eine Ausnahmebehandlung abbricht, muss die `CChildView::DrawMandelbrot`\-Methode einen ausnahmesicheren Mechanismus verwenden, um zu gewährleisten, dass alle Ressourcen ordnungsgemäß bereinigt werden.  In diesem Beispiel wird das RAII \(*Resource Acquisition Is Initialization*\)\-Muster verwendet, um zu gewährleisten, dass die Bitmapbits entsperrt werden, wenn die Aufgabe abgebrochen wird.  
  
##### So fügen Sie die Unterstützung für Abbrüche in der Mandelbrot\-Anwendung hinzu  
  
1.  Fügen Sie in ChildView.h im `protected`\-Abschnitt der `CChildView`\-Klasse Deklarationen für die Meldungszuordnungsfunktionen `OnSize`, `OnSizing` und `OnDestroy` hinzu.  
  
     [!CODE [concrt-mandelbrot#201](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#201)]  
  
2.  Ändern Sie in ChildView.cpp die Meldungszuordnung, sodass sie Handler für die Meldungen `WM_SIZE`, `WM_SIZING` und `WM_DESTROY` enthält.  
  
     [!CODE [concrt-mandelbrot#202](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#202)]  
  
3.  Implementieren Sie die `CChildView::OnSizing`\-Methode.  Diese Methode bricht alle vorhandenen Zeichenaufgaben ab.  
  
     [!CODE [concrt-mandelbrot#203](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#203)]  
  
4.  Implementieren Sie die `CChildView::OnSize`\-Methode.  Diese Methode bricht alle vorhandenen Zeichenaufgaben ab und erstellt eine neue Zeichenaufgabe für die aktualisierte Clientfenstergröße.  
  
     [!CODE [concrt-mandelbrot#204](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#204)]  
  
5.  Implementieren Sie die `CChildView::OnDestroy`\-Methode.  Diese Methode bricht alle vorhandenen Zeichenaufgaben ab.  
  
     [!CODE [concrt-mandelbrot#205](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#205)]  
  
6.  Definieren Sie in ChildView.cpp die `scope_guard`\-Klasse, die das RAII\-Muster implementiert.  
  
     [!CODE [concrt-mandelbrot#206](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#206)]  
  
7.  Fügen Sie folgenden Code in der `CChildView::DrawMandelbrot`\-Methode nach dem Aufruf von `Bitmap::LockBits` hinzu.  
  
     [!CODE [concrt-mandelbrot#207](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#207)]  
  
     In diesem Code werden Abbrüche durch Erstellen eines `scope_guard`\-Objekts behandelt.  Wenn das Objekt den Gültigkeitsbereich verlässt, werden die Bitmapbits entsperrt.  
  
8.  Ändern Sie das Ende der `CChildView::DrawMandelbrot`\-Methode, sodass das `scope_guard`\-Objekt verworfen wird, nachdem die Bitmapbits entsperrt wurden, aber bevor Meldungen an den UI\-Thread gesendet werden.  Hierdurch wird sichergestellt, dass der UI\-Thread nicht aktualisiert wird, bevor die Bitmapbits entsperrt werden.  
  
     [!CODE [concrt-mandelbrot#208](../CodeSnippet/VS_Snippets_ConcRT/concrt-mandelbrot#208)]  
  
9. Überprüfen Sie, ob das Aktualisieren der Anwendung erfolgreich war, indem Sie sie erstellen und ausführen.  
  
 Wenn Sie die Größe des Fensters ändern, wird die Zeichenarbeit nur für die abschließende Fenstergröße ausgeführt.  Außerdem werden alle aktiven Zeichenaufgaben abgebrochen, wenn das Fenster zerstört wird.  
  
 \[[Nach oben](#top)\]  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [MFC\-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)