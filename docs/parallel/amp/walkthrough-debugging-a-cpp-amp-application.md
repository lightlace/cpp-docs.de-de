---
title: "Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung"
ms.custom: na
ms.date: "12/16/2016"
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
  - "Debuggen, C++ AMP (Accelerated Massive Parallelism)"
  - "C++ AMP, Debuggen"
  - "C++ AMP (Accelerated Massive Parallelism), Debuggen"
  - "Debuggen, C++ AMP"
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: 35
caps.handback.revision: "34"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema veranschaulicht, wie eine Anwendung debuggen, die C\+\+ Accelerated Massive Parallelism \(C\+\+ AMP\) verwendet die Grafikverarbeitungseinheit \(GPU\) nutzen.  Es verwendet ein Parallelreduzierungsprogramm, von dem ein großes Array von Ganzzahlen aufsummiert.  In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Starten des GPU\-Debuggers.  
  
-   Das Überprüfen von GPUs Tabellen im GPU\-Threadfenster.  
  
-   Verwenden des parallelen Stapelfensters, die auf mehrere Aufruflisten gleichzeitig GPU Tabellen berücksichtigt.  
  
-   Verwenden des parallelen Überwachungsfensters, um von Werten eines einzelnen Ausdrucks über mehrere Threads gleichzeitig zu überprüfen.  
  
-   GPU\-Threads kennzeichnen, Fixieren, Entsperren und Gruppierung.  
  
-   Ausführen aller Threads einer Kachel an einem bestimmten Speicherort im Code.  
  
## Vorbereitungsmaßnahmen  
 Bevor Sie diese exemplarische Vorgehensweise beginnen:  
  
-   Lesen von [Übersicht über C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md).  
  
-   Überprüfen Sie, ob Zeilennummern im Text\-Editor angezeigt werden.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von Zeilennummern im Editor](../Topic/How%20to:%20Display%20Line%20Numbers%20in%20the%20Editor.md).  
  
-   Stellen Sie sicher, dass Sie [!INCLUDE[win8](../../build/includes/win8_md.md)] oder [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] ausführen, um das Debuggen auf dem Software\-Emulator zu unterstützen.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### So erstellen Sie das Beispielprojekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
3.  unter **Installiert** im Vorlagenbereich, wählen Sie **Visual C\+\+** aus.  
  
4.  Wählen Sie **Win32\-Konsolenanwendung** aus, geben Sie `AMPMapReduce` im Feld **Name** ein, und wählen Sie dann die Schaltfläche **OK** aus.  
  
5.  Wählen Sie die Schaltfläche **Weiter** aus.  
  
6.  Deaktivieren Sie das Kontrollkästchen **Vorkompilierte Headerdatei**, und wählen Sie dann die Schaltfläche **Fertig stellen** aus.  
  
7.  In **Projektmappen\-Explorer**, Lösch\- stdafx.h, targetver.h und stdafx.cpp aus dem Projekt.  
  
8.  Öffnen Sie AMPMapReduce.cpp und ersetzen Sie den Inhalt mit dem folgenden Code.  
  
    ```cpp  
  
    // AMPMapReduce.cpp defines the entry point for the program.  
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.   
  
    #include <stdio.h>  
    #include <tchar.h>  
    #include <amp.h>  
  
    const int BLOCK_DIM = 32;  
  
    using namespace concurrency;  
  
    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)  
    {  
        tile_static int localA[BLOCK_DIM];  
  
        index<1> globalIdx = t_idx.global * stride_size;  
        index<1> localIdx = t_idx.local;  
  
        localA[localIdx[0]] =  A[globalIdx];  
  
        t_idx.barrier.wait();  
  
        // Aggregate all elements in one tile into the first element.  
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)   
        {  
            if (localIdx[0] < i)   
            {  
  
                localA[localIdx[0]] += localA[localIdx[0] + i];  
            }  
  
            t_idx.barrier.wait();  
        }  
  
        if (localIdx[0] == 0)  
        {  
            A[globalIdx] = localA[0];  
        }  
    }  
  
    int size_after_padding(int n)  
    {  
        // The extent might have to be slightly bigger than num_stride to   
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.  
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)  
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;  
    }  
  
    int reduction_sum_gpu_kernel(array<int, 1> input)   
    {  
        int len = input.extent[0];  
  
        //Tree-based reduction control that uses the CPU.  
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)   
        {  
            // Number of useful values in the array, given the current  
            // stride size.  
            int num_strides = len / stride_size;    
  
            extent<1> e(size_after_padding(num_strides));  
  
            // The sum kernel that uses the GPU.  
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)  
            {  
                sum_kernel_tiled(idx, input, stride_size);  
            });  
        }  
  
        array_view<int, 1> output = input.section(extent<1>(1));  
        return output[0];  
    }  
  
    int cpu_sum(const std::vector<int> &arr) {  
        int sum = 0;  
        for (size_t i = 0; i < arr.size(); i++) {  
            sum += arr[i];  
        }  
        return sum;  
    }  
  
    std::vector<int> rand_vector(unsigned int size) {  
        srand(2011);  
  
        std::vector<int> vec(size);  
        for (size_t i = 0; i < size; i++) {  
            vec[i] = rand();  
        }  
        return vec;  
    }  
  
    array<int, 1> vector_to_array(const std::vector<int> &vec) {  
        array<int, 1> arr(vec.size());  
        copy(vec.begin(), vec.end(), arr);  
        return arr;  
    }  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
        std::vector<int> vec = rand_vector(10000);  
        array<int, 1> arr = vector_to_array(vec);  
  
        int expected = cpu_sum(vec);  
        int actual = reduction_sum_gpu_kernel(arr);  
  
        bool passed = (expected == actual);  
        if (!passed) {  
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);  
        }  
        printf("sum: %s\n", passed ? "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
    ```  
  
9. Wählen Sie in der Menüleiste die Option **Datei**, **Alle speichern** aus.  
  
10. In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften** aus.  
  
11. Im Dialogfeld **Eigenschaftenseiten** unter **Konfigurationseigenschaften**, wählen Sie **Vorkompilierte Header**, **C\/C\+\+** aus.  
  
12. Für die Eigenschaft **Vorkompilierter Header** wählen Sie **Vorkompilierte Header nicht verwenden** und wählen Sie dann die Schaltfläche **OK** aus.  
  
13. Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
## Debuggen CPU des Codes  
 In diesem Verfahren verwenden Sie den lokalen Windows\-Debugger, um sicherzustellen, dass der CPU\-Code in dieser Anwendung richtig ist.  Das Segment des CPU\-Codes in dieser Anwendung, die besonders interessant ist, ist die `for` \- Schleife in der Funktion `reduction_sum_gpu_kernel`.  Es steuert die strukturbasierte parallele Reduzierung, die auf dem GPU\-Computer ausgeführt wird.  
  
### Um den CPU\-Code debuggen  
  
1.  In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften** aus.  
  
2.  Im Dialogfeld **Eigenschaftenseiten** unter **Konfigurationseigenschaften**, wählen Sie **Debugging** aus.  Überprüfen Sie, ob **Lokaler Windows\-Debugger** in der Liste **Zu startender Debugger** ausgewählt ist.  
  
3.  Kehren Sie zum Code\-Editor zurück.  
  
4.  Legen Sie Haltepunkte auf den Codezeilen, die in der folgenden Abbildung gezeigt wurden \(zeichnet 67 ungefähr Zeile 70\).  
  
     ![CPU&#45;Haltepunkte](../../parallel/amp/media/campcpubreakpoints.png "CampCpuBreakpoints")  
CPU\-Haltepunkte  
  
5.  Klicken Sie in der Menüleiste auf **Debuggen** und dann auf **Debuggen starten**.  
  
6.  Im Fenster **Lokal** beobachten Sie den Wert für `stride_size`, bis der Haltepunkt in Zeile 70 erreicht wird.  
  
7.  Wählen Sie auf der Menüleiste **Debuggen** und dann **Debuggen beenden** aus.  
  
## Debuggen des GPU\-Codes  
 Dieser Abschnitt zeigt, wie den GPU\-Code debuggen, der Code ist, der in der `sum_kernel_tiled`\-Funktion enthalten ist.  Der GPU\-Code berechnet die Summe aller ganzen Zahlen für jeden "Block" parallel.  
  
### So den GPU\-Code debuggen  
  
1.  In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften** aus.  
  
2.  Im Dialogfeld **Eigenschaftenseiten** unter **Konfigurationseigenschaften**, wählen Sie **Debugging** aus.  
  
3.  In der Liste **Zu startender Debugger** wählen Sie **Lokaler Windows\-Debugger** aus.  
  
4.  In der Liste **Debuggertyp** wählen Sie **Nur GPU** aus.  
  
5.  Klicken Sie auf die Schaltfläche **OK**.  
  
6.  Legen Sie einen Haltepunkt in Zeile 30, wie in der folgenden Abbildung dargestellt.  
  
     ![GPU&#45;Haltepunkte](../../parallel/amp/media/campgpubreakpoints.png "CampGpuBreakpoints")  
GPU\-Haltepunkt  
  
7.  Klicken Sie in der Menüleiste auf **Debuggen** und dann auf **Debuggen starten**.  Die Haltepunkte im CPU\-Code an Zeilen 67 und 70 werden nicht während GPU\-Debuggings ausgeführt, da diese Codezeilen auf der CPU ausgeführt werden.  
  
### Um das GPU\-Threadfenster verwenden  
  
1.  Um das GPU\-Threadfenster, in der Menüleiste zu öffnen, wählen Sie **Fenster**, **GPU\-Threads**, **Debuggen** aus.  
  
     Sie können den Zustand überprüfen, den das GPU im GPU\-Threadfenster Tabellen, die angezeigt wird.  
  
2.  Docken Sie das GPU\-Threadfenster am unteren Rand von Visual Studio an.  Wählen Sie die Schaltfläche **Threadumschaltung erweitern**, um die Threadtextfelder Kachel\- und anzuzeigen.  Das GPU Tabellen Fenstershows die Gesamtanzahl aktiver und blockierten GPU\-Threads, wie in der folgenden Abbildung gezeigt.  
  
     ![GPU&#45;Threadfenster mit vier aktiven Threads](../../parallel/amp/media/campc.png "CampC")  
GPU Akkumulatorargument Fenster  
  
     Es gibt 313 Kacheln, die für diese Berechnung zugeordnet werden.  Jede Kachel enthält 32 Threads.  Da lokales GPU\-Debugging auf einem Software\-Emulator auftritt, gibt es vier aktive GPU\-Threads.  Die vier Threads führen die Anweisungen gleichzeitig aus und stellen dann zusammen der folgenden Anweisung weiter.  
  
     Im GPU\-Threadfenster gibt es vier GPU\-Threads, die aktiv sind und 28 GPU\-Threads, die an der Anweisung [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) blockiert werden, die ca. in Zeile 21 \(`t_idx.barrier.wait();`\) definiert ist.  Alle 32 GPU\-Threads gehören der ersten Kachel, `tile[0]`.  Ein Pfeil zeigt auf der Zeile, die den aktuellen Thread enthält.  Um zu einem anderen Thread zu wechseln, eine der folgenden Methoden:  
  
    -   In der Zeile, damit der Thread wechselt zu GPU\-Threads in das Fenster, öffnen Sie das Kontextmenü und wählen Sie **Zu Thread wechseln** aus.  Wenn die Zeile mehr als einen Thread darstellt, wechseln Sie zum ersten Thread entsprechend den Threadkoordinaten um.  
  
    -   Geben Sie den Threadwerten Kachel\- und des Threads in die entsprechenden Textfelder ein und wählen Sie dann die Schaltfläche **Threadwechsel** aus.  
  
     Das Fenster Aufrufliste wird die Aufrufliste des Threads der aktuellen GPU an.  
  
### Um das Fenster Parallele Stapel verwenden  
  
1.  Um das Fenster Parallele Stapel, in der Menüleiste zu öffnen, wählen Sie **Fenster**, **Parallele Stapel**, **Debuggen** aus.  
  
     Sie können das Fenster "Parallele Stapel" verwenden, um die Stapelrahmen mehrerer GPU\-Threads gleichzeitig zu überprüfen.  
  
2.  Docken Sie das Fenster "Parallele Stapel" am unteren Rand von Visual Studio an.  
  
3.  Überprüfen Sie, ob **Threads** in der Liste in der linken oberen Ecke ausgewählt ist.  In der folgenden Abbildung die Vogelperspektive angezeigt Aufrufliste eine fokussierte Ansicht der GPU\-Threads, dass Sie im Fenster von GPUs kam.  
  
     ![Fenster für parallele Stapel mit vier aktiven Threads](../../parallel/amp/media/campd.png "CampD")  
Fenster Parallele Stapel  
  
     32 Threads gingen von `_kernel_stub` zur Lambda\-Anweisung im Funktionsaufruf `parallel_for_each` und dann zur `sum_kernel_tiled`\-Funktion, in der die parallele Reduzierung auftritt. 28 aus den 32 Threads heraus sind bis zu der Anweisung [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) vorangeschritten und verbleiben in Zeile 22 blockiert, während andere 4 Threads in der Funktion `sum_kernel_tiled` in Zeile 30 aktiv bleiben.  
  
     Sie können die Eigenschaften eines GPU\-Threads überprüfen, die im GPU\-Threadfenster umfangreichen im DataTip des parallelen Stapelfensters verfügbar sind.  Hierzu, kommunizieren Sie den Mauszeiger auf dem Stapelrahmen von **sum\_kernel\_tiled** per.  Die folgende Abbildung zeigt den DataTip anzeigen.  
  
     ![DataTip für Fenster für parallele Stapel](../../parallel/amp/media/campe.png "CampE")  
GPU\-Thread DataTip  
  
     Weitere Informationen über die parallele Stapel Fenster, finden Sie unter [Verwenden des Fensters "Parallele Stapel"](../Topic/Using%20the%20Parallel%20Stacks%20Window.md).  
  
### So paralleles Überwachungsfenster verwenden  
  
1.  Um das parallelen Überwachungsfenster, in der Menüleiste zu öffnen, wählen Sie **Fenster**, **Parallele Überwachung**, **Parallele Überwachung 1**, **Debuggen** aus.  
  
     Sie können parallelen das Überwachungsfenster verwenden, um die Werte eines Ausdrucks zu mehreren Threads zu überprüfen.  
  
2.  Docken Sie das parallele Fenster die Überwachung 1 zum Ende von Visual Studio an.  Es gibt 32 Zeilen in der Tabelle des parallelen Überwachungsfensters.  Jedes entspricht einem GPU\-Thread, der im GPU\-Threadfenster und im Fenster Parallele Stapel angezeigt.  Jetzt können Sie Ausdrücke eingeben, deren Werte Sie über alle 32 GPU\-Threads überprüfen möchten.  
  
3.  Wählen Sie den Spaltenkopf **Überwachung hinzufügen** aus, geben Sie `localIdx` ein und wählen Sie dann die EINGABETASTE aus.  
  
4.  Wählen Sie den Spaltenkopf **Überwachung hinzufügen** erneut aus, geben Sie `globalIdx` ein und wählen Sie dann die EINGABETASTE aus.  
  
5.  Wählen Sie den Spaltenkopf **Überwachung hinzufügen** erneut aus, geben Sie `localA[localIdx[0]]` ein und wählen Sie dann die EINGABETASTE aus.  
  
     Sie können über einen angegebenen Ausdruck sortieren, indem Sie den zugehörigen Spaltenheader auswählen.  
  
     Wählen Sie den Spaltenkopf **localA\[localIdx\[0\]\]** aus, um die Spalte zu sortieren.  Die folgende Abbildung zeigt die Ergebnisse der Sortierung von **localA\[localIdx\[0\]\]** an.  
  
     ![Fenster für parallele Stapel mit sortierten Ergebnissen](../../parallel/amp/media/campf.png "CampF")  
 Ergebnisse der Sortierung  
  
     Sie können den Inhalt im parallelen Überwachungsfenster in Excel exportieren, indem Sie die " auswählen und dann **In Excel öffnen** auswählen.  Wenn Sie Excel haben, die auf dem Entwicklungscomputer installiert werden, wird dieser ein Excel\-Arbeitsblatt, das den Inhalt enthält.  
  
6.  In der rechten oberen Ecke des parallelen Überwachungsfensters gibt es ein Filtersteuerelement, das Sie verwenden können, um den Inhalt zu filtern, indem Sie boolesche Ausdrücke verwenden.  Geben Sie `localA[localIdx[0]] > 20000` im Filtertextgrundlagefeld ein und wählen Sie dann die EINGABETASTE aus.  
  
     Das Fenster enthält jetzt nur Threads, in denen `localA[localIdx[0]]` der Wert 20000 überschreitet.  Der Inhalt wird weiterhin durch die `localA[localIdx[0]]` Spalte sortiert, die die Sortierungsaktion, ist, die Sie bereits ausgeführt haben.  
  
## Kennzeichnen von GPU\-Threads  
 Sie können bestimmte GPU\-Threads markieren, indem Sie sie im GPU\-Threadfenster, in dem parallele Überwachungsfenster kennzeichnen, oder sich der DataTip in der " Parallele Stapel Fenster.  Wenn eine Zeile im GPU\-Threadfenster mehr als einen Thread enthält und kennzeichnet, dass Zeile alle Threads kennzeichnet, die in der Zeile enthaltene werden.  
  
### So GPU\-Threads kennzeichnen  
  
1.  Wählen Sie den Spaltenkopf **\[Thread\]\]** im parallelen Fenster die Überwachung 1 das Sortieren nach Kachelindex aus und den gewünschten Thread Index.  
  
2.  Wählen Sie in der Menüleiste **Weiter**, **Debuggen** aus, die vier Threads verursacht, die aktiv waren, bis zu der folgenden Barriere angehalten \(definiert in Zeile 32 der AMPMapReduce.cpp\).  
  
3.  Wählen Sie das Kennzeichnungssymbol auf der linken Seite der Zeile aus, in denen die vier Threads enthält, die jetzt aktiv sind.  
  
     Die folgende Abbildung zeigt die vier aktiven gekennzeichneten Threads im GPU\-Threadfenster an.  
  
     ![GPU&#45;Threadfenster mit gekennzeichneten Threads](../../parallel/amp/media/campg.png "CampG")  
Aktive GPU in Threads im Fenster  
  
     Das parallelen Überwachungsfenster und der DataTip des Ähnlichkeitsstapelfensters beide geben den gekennzeichneten Threads an.  
  
4.  Wenn Sie auf die vier Threads konzentrieren möchten, die Sie auch, Sie wählen können, um, in den GPU\-Threads, in der Ähnlichkeits\-Überwachung und in den Ähnlichkeits\-Stapelfenstern zu veranschaulichen, nur die gekennzeichneten Threads.  
  
     Wählen Sie die Schaltfläche eingeblendet gekennzeichnete nur auf einem der Fenster oder auf der Symbolleiste **Debugspeicherort** aus.  Die folgende Abbildung zeigt die aus nur gekennzeichnete Schaltfläche auf der Symbolleiste **Debugspeicherort** an.  
  
     ![Symbolleiste „Debugspeicherort“ mit Symbol für „Nur gekennzeichnete anzeigen“](../../parallel/amp/media/camph.png "CampH")  
Ein\- nur gekennzeichnete Schaltfläche  
  
     Nun werden die GPU\-Threads, die parallele Überwachungs\- und parallelen die Stapelfenster nur die gekennzeichneten Threads an.  
  
## GPU\-Threads Sperren und Entsperren von  
 Sie können \(Zusammenfassung\) GPU\-Threads entweder vom GPU\-Threadfenster oder im parallelen Überwachungsfenster einfrieren \(enthalten\) und reaktivieren.  Sie können CPU\-Threads einfrieren und reaktivieren die gleiche Methode; zu Informationen finden Sie unter [Gewusst wie: Verwenden des Fensters Threads](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
### So fixieren GPU\-Threads und reaktivieren  
  
1.  Wählen Sie die Schaltfläche **Nur gekennzeichnete anzeigen**, um alle Threads anzuzeigen.  
  
2.  Wählen Sie in der Menüleiste **Weiter**, **Debuggen** aus.  
  
3.  Öffnen Sie das Kontextmenü für die aktive Zeile und dann **Einfrieren** aus.  
  
     In der folgenden Abbildung des GPU\-Threadfensters zeigt, dass alle vier Threads fixiert werden.  
  
     ![GPU&#45;Threadfenster mit fixierten Threads](../../parallel/amp/media/campk.png "CampK")  
Fixierte GPU in Threads im Fenster  
  
     Ebenso stellt die parallelen Überwachungsfenster dar, alle vier Threads fixiert werden.  
  
4.  Wählen Sie in der Menüleiste, **Weiter**, um die folgenden vier GPU\-Threads Zustand hinter der Barriere in Zeile 22 zu ermöglichen **Debuggen** aus und den Haltepunkt in Zeile 30 erreicht.  Das GPU\-Threadfenster zeigt, dass die zuvor vier eingefrorenen Threads und im Zustand Aktiv fixiert bleiben.  
  
5.  Wählen Sie in der Menüleiste **Weiter**, **Debuggen** aus.  
  
6.  im parallelen Überwachungsfenster können einzelne oder mehrere GPU\-Threads auch reaktivieren.  
  
### So gruppieren GPU\-Threads  
  
1.  Klicken Sie im Kontextmenü eines der Threads im Fenster **GPU\-Threads**, wählen Sie **Adresse**, **Gruppieren nach** aus.  
  
     Die Threads im GPU\-Threadfenster werden durch Adresse gruppiert.  Die Adresse entspricht zur Anweisung der Disassembly, in der jede Gruppe Threads befindet. 24 Threads sind in Zeile 22, in der [tile\_barrier::wait\-Methode](../Topic/tile_barrier::wait%20Method.md) ausgeführt wird. 12 Threads sind bei der Anweisung für die Barriere in Zeile 32.  Vier dieser Threads werden gekennzeichnet.  Es gibt acht Threads sind am Haltepunkt in Zeile 30.  Vier dieser Threads werden gesperrt.  Die folgende Abbildung zeigt die gruppierten Threads im GPU\-Threadfenster an.  
  
     ![GPU&#45;Threadfenster mit nach Adresse angeordneten Threads](../../parallel/amp/media/campl.png "CampL")  
Gruppierte GPU in Threads im Fenster  
  
2.  Sie können den **Gruppieren nach** Vorgang auch ausführen, indem Sie das Kontextmenü für das Datenraster des parallelen Überwachungsfensters öffnen und **Gruppieren nach** auswählen, und dann das Menüelement auswählen, das entspricht, wie Sie die Threads gruppieren möchten.  
  
## Ausführen aller Threads an einem bestimmten Speicherort im Code  
 Sie führen alle Threads in einer angegebenen Kachel zur Zeile, die den Cursor enthält, indem sie den **Aktuelle Kachel bis zum Cursor ausführen** verwenden.  
  
### Um alle Threads zum Speicherort ausführen markiert vom Cursor  
  
1.  Klicken Sie im Kontextmenü für die fixierten Threads, wählen Sie **Reaktivieren** aus.  
  
2.  Im Code\-Editor platzieren Sie den Cursor in Zeile 30 ein.  
  
3.  Klicken Sie im Kontextmenü für den Code\-Editor, wählen Sie **Aktuelle Kachel bis zum Cursor ausführen** aus.  
  
     Die 24 Threads, die zuvor an der Barriere in Zeile 21 blockiert wurden, vorangeschritten sind, dass 32 zu zeichnen.  Dies wird im Fenster **GPU\-Threads** gezeigt.  
  
## Siehe auch  
 [Übersicht über C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md)   
 [Debuggen von GPU\-Code](../Topic/Debugging%20GPU%20Code.md)   
 [Gewusst wie: Verwenden des Fensters "GPU\-Threads"](../Topic/How%20to:%20Use%20the%20GPU%20Threads%20Window.md)   
 [Gewusst wie: Verwenden des parallelen Überwachungsfensters](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)   
 [Analysieren von Code mit der Parallelitätsschnellansicht AMP](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)