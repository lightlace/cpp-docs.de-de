---
title: 'Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
ms.openlocfilehash: 4f8cdc315b561b5cbb4538e8486208d6278af9df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579902"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung

Dieses Thema veranschaulicht, wie Sie eine Anwendung zu debuggen, die C++ Accelerated Massive Parallelism (C++-AMP) verwendet wird, auf der grafikverarbeitungseinheit (GPU) nutzen. Zur Reduzierung von parallelen Programm, die addiert, um ein großes Array von ganzen Zahlen verwendet. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

- Den GPU-Debugger wird gestartet.

- GPU-Threads im GPU-Threadfenster wird überprüft.

- Mithilfe der **parallele Stapel** Fenster, das die Aufruflisten von mehreren GPU-Threads gleichzeitig überwacht werden.

- Mithilfe der **parallele Überwachung** Fenster aus, um Werte aus einem einzelnen Ausdruck über mehrere Threads gleichzeitig zu überprüfen.

- Kennzeichnen, sperren, entsperren und Gruppieren von GPU-Threads.

- Alle Threads von einer Kachel zu einer bestimmten Stelle im Code wird ausgeführt.

## <a name="prerequisites"></a>Vorraussetzungen

Bevor Sie in dieser exemplarischen Vorgehensweise beginnen:

- Lesen [Übersicht über C++ AMP](../../parallel/amp/cpp-amp-overview.md).

- Stellen Sie sicher, dass diese Zeile Zahlen werden im Text-Editor angezeigt. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zeilennummern im Editor](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor).

- Stellen Sie sicher, dass Sie Windows 8 oder Windows Server 2012, um das Debuggen im Softwareemulator unterstützt ausgeführt werden.

[!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]

### <a name="to-create-the-sample-project"></a>So erstellen Sie das Beispielprojekt

1. Starten Sie Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

3. Klicken Sie unter **installiert** wählen Sie im Vorlagenbereich **Visual C++**.

4. Wählen Sie **Win32-Konsolenanwendung**, Typ `AMPMapReduce` in die **Namen** ein, und wählen Sie dann die **OK** Schaltfläche.

5. Klicken Sie auf **Weiter**.

6. Deaktivieren der **vorkompilierter Header** aus, und wählen Sie dann die **Fertig stellen** Schaltfläche.

7. In **Projektmappen-Explorer**, löschen Sie "stdafx.h", "targetver.h" und "stdafx.cpp" aus dem Projekt.

8. Öffnen Sie AMPMapReduce.cpp, und Ersetzen Sie deren Inhalt durch den folgenden Code.

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
        printf("sum: %s\n", passed  "Passed!" : "Failed!");

        getchar();

        return 0;
    }
```

9. Klicken Sie in der Menüleiste auf **Datei** > **Alle speichern**.

10. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.

11. In der **Eigenschaftenseiten** Dialogfeld **Konfigurationseigenschaften**, wählen Sie **C/C++-** > **vorkompilierte Header**.

12. Für die **vorkompilierter Header** -Eigenschaft die Option **vorkompilierte Header nicht verwenden**, und wählen Sie dann die **OK** Schaltfläche.

13. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.

## <a name="debugging-the-cpu-code"></a>Debuggen des CPU-Codes

In diesem Verfahren werden der lokale Windows-Debugger können Sie sicherstellen, dass der CPU-Code in dieser Anwendung korrekt ist. Das Segment des CPU-Codes in dieser Anwendung, die besonders interessant ist die `for` wurde eine Schleife in der `reduction_sum_gpu_kernel` Funktion. Es steuert die strukturbasierte parallele Reduzierung, die auf dem GPU ausgeführt wird.

### <a name="to-debug-the-cpu-code"></a>So debuggen Sie die CPU-code

1. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.

2. In der **Eigenschaftenseiten** Dialogfeld **Konfigurationseigenschaften**, wählen Sie **Debuggen**. Überprüfen Sie, ob **lokaler Windows-Debugger** ausgewählt ist, der **zu startender Debugger** Liste.

3. Wechseln Sie zurück zur der **Code-Editor**.

4. Festlegen von Breakpoints für die Codezeilen, die in der folgenden Abbildung (etwa Zeilen 67 Zeile 70) angezeigt.

     ![CPU-Haltepunkte](../../parallel/amp/media/campcpubreakpoints.png "Campcpubreakpoints") CPU-Haltepunkte

5. Klicken Sie in der Menüleiste auf **Debuggen** > **Debuggen starten**.

6. In der **"lokal"** Fenster, beachten Sie den Wert für `stride_size` bis der Haltepunkt in Zeile 70 erreicht wird.

7. Klicken Sie in der Menüleiste auf **Debuggen** > **Debuggen beenden** aus.

## <a name="debugging-the-gpu-code"></a>Debuggen von GPU-Code

In diesem Abschnitt wird gezeigt, wie zum Debuggen von GPU-Code, der enthaltene Code wird in der `sum_kernel_tiled` Funktion. GPU-Code berechnet die Summe aus ganzen Zahlen für jede "Block" Parallel.

### <a name="to-debug-the-gpu-code"></a>Debuggen von GPU-code

1. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.

2. In der **Eigenschaftenseiten** Dialogfeld **Konfigurationseigenschaften**, wählen Sie **Debuggen**.

3. In der **zu startender Debugger** Liste **lokaler Windows-Debugger**.

4. In der **Debuggertyp** , ob **automatisch** ausgewählt ist.

    **Automatische** ist der Standardwert. Vor Windows 10 **nur GPU** den erforderlichen Wert anstelle von **automatisch**.

5. Klicken Sie auf die Schaltfläche **OK** .

6. Legen Sie einen Haltepunkt in Zeile 30, wie in der folgenden Abbildung dargestellt.

     ![GPU-Haltepunkte](../../parallel/amp/media/campgpubreakpoints.png "Campgpubreakpoints") GPU-Haltepunkt

7. Klicken Sie in der Menüleiste auf **Debuggen** > **Debuggen starten**. Die Haltepunkte in der CPU-Code in den Zeilen 67 und 70 werden nicht ausgeführt, während der GPU-debugging, da diese Codezeilen auf der CPU ausgeführt werden.

### <a name="to-use-the-gpu-threads-window"></a>Verwenden von GPU-Threadfenster

1. Zum Öffnen der **GPU-Threads** wählen Sie in der Menüleiste **Debuggen** > **Windows** > **GPU-Threads**.

   Sie können überprüfen, dass den Status die GPU-in Threads der **GPU-Threads** Fenster, das angezeigt wird.

2. Andocken der **GPU-Threads** Fenster am unteren Rand der Visual Studio. Wählen Sie die **Threadwechsel erweitern** Schaltfläche, um den Inhalt der Textfelder Kachel- und threadwerte anzuzeigen. Die **GPU-Threads** Fenster zeigt die Gesamtzahl der aktiven und blockierten GPU-Threads, wie in der folgenden Abbildung dargestellt.

     ![GPU-Threadfenster mit 4 aktiven Threads](../../parallel/amp/media/campc.png "Campc") GPU-Threadfenster

   313 Kacheln, die für diese Berechnung zugeordnet sind. Jede Kachel enthält 32 Threads. Da lokale GPU-debugging auf einem Softwareemulator auftritt, gibt es vier aktive GPU-Threads. Die vier Threads Gleichzeitiges Ausführen von Anweisungen, und klicken Sie dann fahren Sie zusammen mit der nächsten Anweisung.

   In der **GPU-Threads** Fenster gibt es vier GPU-Threads aktiv sind und 28 GPU-Threads blockiert werden, auf die [tile_barrier:: wait](reference/tile-barrier-class.md#wait) -Anweisung zu Zeile 21 definiert (`t_idx.barrier.wait();`). Alle 32 GPU-Threads gehören, auf die erste Kachel `tile[0]`. Ein Pfeil zeigt auf die Zeile, die den aktuellen Thread enthält. Verwenden Sie eine der folgenden Methoden, um in einem anderen Thread zu wechseln:

    - In der Zeile für den Thread zu wechseln, in der **GPU-Threads** Fenster öffnen Sie das Kontextmenü, und wählen Sie **zu Thread wechseln**. Wenn die Zeile mehr als einem Thread darstellt, wechseln Sie auf den ersten Thread gemäß den threadkoordinaten.

    - Geben Sie die Kachel- und threadwerte Werte des Threads in die entsprechenden Textfelder ein, und wählen Sie dann die **Switch Thread** Schaltfläche.

   Die **Aufrufliste** Fenster zeigt die Aufrufliste des aktuellen GPU-Threads.

### <a name="to-use-the-parallel-stacks-window"></a>Verwenden Sie das Fenster "Parallele Stapel"

1. Zum Öffnen der **parallele Stapel** wählen Sie in der Menüleiste **Debuggen** > **Windows** > **parallele Stapel**.

   Sie können die **parallele Stapel** Fenster aus, um die Stapelrahmen von mehreren GPU-Threads gleichzeitig zu überprüfen.

2. Andocken der **parallele Stapel** Fenster am unteren Rand der Visual Studio.

3. Stellen Sie sicher, dass **Threads** ausgewählt ist, in der Liste in der oberen linken Ecke. In der folgenden Abbildung wird die **parallele Stapel** Fenster zeigt Aufrufliste konzentriert sich die GPU-Threads, die Sie haben, in gesehen der **GPU-Threads** Fenster.

     ![Fenster "Parallele Stapel" mit 4 aktiven Threads](../../parallel/amp/media/campd.png "Campd") Fenster "Parallele Stapel"

   32 Threads hat sich von `_kernel_stub` der Lambda-Anweisung in der `parallel_for_each` Funktionsaufruf und wählen Sie dann die `sum_kernel_tiled` -Funktion, in dem die parallele Reduzierung auftritt. 28 aus 32 Threads haben fortgeschritten, um die [tile_barrier:: wait](reference/tile-barrier-class.md#wait) Anweisung und bleiben in Zeile 22, blockiert, während die anderen 4 Threads in aktiv bleiben die `sum_kernel_tiled` Funktion in Zeile 30.

   Sie können die Eigenschaften eines GPU-Threads, die in verfügbaren Überprüfen der **GPU-Threads** Fenster in der umfassenden DataTip von der **parallele Stapel** Fenster. Zu diesem Zweck führen Sie den Mauszeiger auf den Stapelrahmen der **Sum_kernel_tiled**. Die folgende Abbildung zeigt den DataTip an.

     ![DataTip für Fenster "Parallele Stapel"](../../parallel/amp/media/campe.png "Campe") GPU-Thread DataTip

   Weitere Informationen zu den **parallele Stapel** Fenster finden Sie unter [verwenden das Fenster "Parallele Stapel"](/visualstudio/debugger/using-the-parallel-stacks-window).

### <a name="to-use-the-parallel-watch-window"></a>Verwenden des parallelen Überwachungsfensters

1. Zum Öffnen der **parallele Überwachung** wählen Sie in der Menüleiste **Debuggen** > **Windows** > **parallele Überwachung**  >  **Parallele Überwachung 1**.

   Sie können die **parallele Überwachung** Fenster aus, um die Werte eines Ausdrucks über mehrere Threads hinweg zu untersuchen.

2. Andocken der **parallele Überwachung 1** Fenster am unteren Rand der Visual Studio. Es gibt 32 Zeilen in der Tabelle die **parallele Überwachung** Fenster. Jeder entspricht ein GPU-Thread, der in beiden GPU-Threadfenster angezeigt wurde, und die **parallele Stapel** Fenster. Jetzt können Sie Ausdrücke eingeben, deren Werte, die Sie über alle 32 GPU-Threads überprüfen möchten.

3. Wählen Sie die **Überwachung hinzufügen** Spaltenüberschrift klicken, geben Sie `localIdx`, und wählen Sie dann die **EINGABETASTE** Schlüssel.

4. Wählen Sie die **Überwachung hinzufügen** erneut die Kopfzeile der Spalte, Typ `globalIdx`, und wählen Sie dann die **EINGABETASTE** Schlüssel.

5. Wählen Sie die **Überwachung hinzufügen** erneut die Kopfzeile der Spalte, Typ `localA[localIdx[0]]`, und wählen Sie dann die **EINGABETASTE** Schlüssel.

   Sie können durch einen angegebenen Ausdruck durch Auswählen der entsprechenden Spaltenüberschrift sortieren.

   Wählen Sie die **LocalA [LocalIdx [0]]** Spaltenheader, um die Spalte zu sortieren. Die folgende Abbildung zeigt die Ergebnisse der Sortierung nach **LocalA [LocalIdx [0]]**.

     ![Fenster für parallele Überwachung mit sortierten Ergebnissen](../../parallel/amp/media/campf.png "Campf") Sortierergebnisse

   Sie können den Inhalt exportieren der **parallele Überwachung** Fenster in Excel durch Auswahl der **Excel** Schaltfläche auswählen und dann **in Excel öffnen**. Wenn Sie Excel auf Ihrem Entwicklungscomputer installiert haben, wird ein Excel-Arbeitsblatt mit dem Inhalt geöffnet.

6. In der oberen rechten Ecke des der **parallele Überwachung** Fenster besteht ein Filtersteuerelement, das Sie verwenden können, um den Inhalt mithilfe von booleschen Ausdrücken zu filtern. Geben Sie `localA[localIdx[0]] > 20000` in das Filtertextfeld für das Steuerelement ein, und wählen Sie dann die **EINGABETASTE** Schlüssel.

   Das Fenster enthält jetzt nur die Threads auf dem die `localA[localIdx[0]]` Wert ist höher als 20.000. Der Inhalt ist weiterhin sortiert nach der `localA[localIdx[0]]` Spalte, die die Sortierung Aktion ist Sie bereits ausgeführt.

## <a name="flagging-gpu-threads"></a>GPU-Threads kennzeichnen

Sie können bestimmte GPU-Threads kennzeichnen, durch kennzeichnen sie in der **GPU-Threads** Fenster die **parallele Überwachung** Fenster oder der DataTip, in der **parallele Stapel** Fenster. Enthält eine Zeile in der GPU-Threadfenster auf mehr als einem Thread, kennzeichnet das kennzeichnen dieser Zeile alle Threads, die in der Zeile enthalten sind.

### <a name="to-flag-gpu-threads"></a>So kennzeichnen Sie GPU-threads

1. Wählen Sie die **[Thread]** Spaltenüberschrift in der **parallele Überwachung 1** Fenster aus, um nach der Kachel und Threadindex zu sortieren.

2. Wählen Sie auf der Menüleiste **Debuggen** > **Weiter**, dadurch wird die vier Threads, die aktiv ausgeführt, die der nächsten Grenze (definiert in Zeile 32 der AMPMapReduce.cpp) wurden.

3. Wählen Sie das Flaggensymbol auf der linken Seite der Zeile, die die vier Threads enthält, die jetzt aktiv sind.

   Die folgende Abbildung zeigt die vier aktive gekennzeichneten Threads in der **GPU-Threads** Fenster.

     ![GPU-Threadfenster mit gekennzeichneten Threads](../../parallel/amp/media/campg.png "Campg") aktive Threads im GPU-Threadfenster

   Die **parallele Überwachung** Fenster und der DataTip, der die **parallele Stapel** beide Fenster anzuzeigen, die gekennzeichneten Threads.

4. Wenn Sie auf die vier Threads zu konzentrieren, die Sie gekennzeichnet werden sollen, können Sie anzeigen, in der **GPU-Threads**, **parallele Überwachung**, und **parallele Stapel** Windows, nur die gekennzeichneten Threads.

   Wählen Sie die **nur gekennzeichnete Threads anzeigen** Schaltfläche auf einem Fenster oder auf die **Debugspeicherort** Symbolleiste. Die folgende Abbildung zeigt die **nur gekennzeichnete Threads anzeigen** Schaltfläche der **Debugspeicherort** Symbolleiste.

     ![Mit dem Symbol "nur gekennzeichnete Elemente anzeigen" Symbolleiste "Debugspeicherort"](../../parallel/amp/media/camph.png "Camph")
**nur gekennzeichnete Threads anzeigen** Schaltfläche

   Jetzt die **GPU-Threads**, **parallele Überwachung**, und **parallele Stapel** Fenstern werden nur die gekennzeichneten Threads angezeigt.

## <a name="freezing-and-thawing-gpu-threads"></a>Sperren und Entsperren der GPU-Threads

Können Sie Einfrieren (anhalten) und reaktivieren (Fortsetzen) GPU-Threads aus den **GPU-Threads** Fenster oder der **parallele Überwachung** Fenster. Sie können Einfrieren und reaktivieren CPU-Threads die gleiche Weise; Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Fensters Threads](/visualstudio/debugger/how-to-use-the-threads-window).

### <a name="to-freeze-and-thaw-gpu-threads"></a>So sperren und Entsperren der GPU-threads

1. Wählen Sie die **nur gekennzeichnete Threads anzeigen** Schaltfläche, um alle Threads anzuzeigen.

2. Wählen Sie auf der Menüleiste **Debuggen** > **Weiter**.

3. Öffnen Sie das Kontextmenü für die aktive Zeile, und wählen Sie dann **fixieren**.

   Die folgende Abbildung, der die **GPU-Threads** zeigt an, dass alle vier Threads eingefroren werden.

     ![GPU-Threadfenster mit fixierten Threads](../../parallel/amp/media/campk.png "Campk") Threads fixiert die **GPU-Threads** Fenster

   Auf ähnliche Weise die **parallele Überwachung** zeigt an, dass alle vier Threads eingefroren werden.

4. Wählen Sie auf der Menüleiste **Debuggen** > **Weiter** die nächsten vier GPU-Threads nach der Barriere in Zeile 22 fortgesetzt und der Breakpoint in Zeile 30 erreichen können. Die **GPU-Threads** zeigt an, dass die vier zuvor fixierte Threads bleiben fixierte und im aktiven Zustand.

5. Wählen Sie auf der Menüleiste **Debuggen**, **Weiter**.

6. Von der **parallele Überwachung** Fenster können Sie auch einzelne oder mehrere GPU-Threads reaktivieren.

### <a name="to-group-gpu-threads"></a>GPU-Threads gruppieren

1. Auf der rechten Maustaste auf einen der Threads in der **GPU-Threads** Fenster wählen **Group By**, **Adresse**.

   Die Threads in der **GPU-Threads** Fenster nach Adresse angeordneten sind. Die Adresse entspricht den Anweisungen im Disassemblyfenster, die auf dem sich jede Gruppe von Threads befindet. 24 Threads befinden sich in Zeile 22, in denen die [tile_barrier:: Wait-Methode](reference/tile-barrier-class.md#wait) ausgeführt wird. 12-Threads werden bei der Anweisung für die Grenze in der Zeile 32. Vier dieser Threads werden gekennzeichnet. Acht Threads sind am Haltepunkt in Zeile 30. Vier dieser Threads sind eingefroren. Die folgende Abbildung zeigt die gruppierten Threads in der **GPU-Threads** Fenster.

     ![GPU-Threadfenster mit Threads nach Adresse angeordneten](../../parallel/amp/media/campl.png "Campl") gruppiert Threads in der **GPU-Threads** Fenster

2. Sie können auch Ausführen der **Group By** Vorgang öffnen Sie das Kontextmenü für das Datenraster, der die **parallele Überwachung** Fenster auswählen **Group By**, auswählen und dann im Menü Element entspricht, wie Sie Threads gruppieren möchten.

## <a name="running-all-threads-to-a-specific-location-in-code"></a>Ausführung alle Threads zu einer bestimmten Stelle im Code

Ausführen alle Threads in einer bestimmten Kachel auf die Zeile mit den Cursor mithilfe **aktuelle Kachel bis zum Cursor ausführen**.

### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>Um alle Threads ausgeführt werden, zu dem Speicherort, der vom Cursor markiert

1. Wählen Sie im Kontextmenü für die fixierte Threads **reaktivieren**.

2. In der **Code-Editor**, platzieren Sie den Cursor in Zeile 30.

3. Klicken Sie auf der rechten Maustaste auf die **Code-Editor**, wählen Sie **aktuelle Kachel bis zum Cursor ausführen**.

   24 Threads, die zuvor die Barriere in Zeile 21 blockiert wurden, haben in Zeile 32 Replikaten. Dies wird gezeigt, der **GPU-Threads** Fenster.

## <a name="see-also"></a>Siehe auch

[Übersicht über C++ AMP](../../parallel/amp/cpp-amp-overview.md)<br/>
[Debuggen von GPU-Code](/visualstudio/debugger/debugging-gpu-code)<br/>
[Gewusst wie: Verwenden des Fensters „GPU-Threads“](/visualstudio/debugger/how-to-use-the-gpu-threads-window)<br/>
[Gewusst wie: Verwenden des parallelen Überwachungsfensters](/visualstudio/debugger/how-to-use-the-parallel-watch-window)<br/>
[Analysieren von C++ AMP-Code mit der Nebenläufigkeitsschnellansicht](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)