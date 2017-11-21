---
title: 'Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3dc050418d8053e04053d5eafbd328e49bd473b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung
In diesem Thema veranschaulicht, wie eine Anwendung zu debuggen, die C++ Accelerated Massive Parallelism (C++-AMP) verwendet wird, um die grafikverarbeitungseinheit (GPU) nutzen. Er verwendet ein paralleler Reduction-Programm, das sich ein großes Array von ganzen Zahlen addiert. In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Den GPU-Debugger wird gestartet.  
  
-   Überprüfen die GPU-Threads im GPU-Threadfenster.  
  
-   Verwenden das Fenster "Parallele Stapel", um die Aufruflisten von mehreren GPU-Threads gleichzeitig zu beobachten.  
  
-   Verwenden das parallele Überwachungsfenster, um Werte aus einem einzelnen Ausdruck über mehrere Threads gleichzeitig zu überprüfen.  
  
-   Kennzeichnen, fixieren, entsperren und GPU-Threads gruppieren.  
  
-   Alle Threads von einer Kachel an einem bestimmten Speicherort im Code wird ausgeführt.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Bevor Sie in dieser exemplarischen Vorgehensweise beginnen:  
  
-   Lesen [Übersicht über C++ AMP](../../parallel/amp/cpp-amp-overview.md).  
  
-   Stellen Sie sicher, dass dieser Zeile Zahlen werden im Text-Editor angezeigt. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zeilennummern im Editor](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor).  
  
-   Stellen Sie sicher, dass Sie ausgeführt werden [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] oder [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] Debuggen im Softwareemulator unterstützen.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-sample-project"></a>So erstellen Sie das Beispielprojekt  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
3.  Klicken Sie unter **installiert** wählen Sie im Vorlagenbereich **Visual C++**.  
  
4.  Wählen Sie **Win32-Konsolenanwendung**, Typ `AMPMapReduce` in der **Namen** ein, und wählen Sie dann die **OK** Schaltfläche.  
  
5.  Wählen Sie die **Weiter** Schaltfläche.  
  
6.  Deaktivieren der **vorkompilierter Header** Kontrollkästchen, und wählen Sie dann die **Fertig stellen** Schaltfläche.  
  
7.  In **Projektmappen-Explorer**, targetver.h, "stdafx.h" und "stdafx.cpp" aus dem Projekt löschen.  
  
8.  Öffnen Sie AMPMapReduce.cpp, und Ersetzen Sie den Inhalt durch folgenden Code.  
  
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
  
9. Wählen Sie in der Menüleiste die Option **Datei**, **Alle speichern** aus.  
  
10. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.  
  
11. In der **Eigenschaftenseiten** Dialogfeld unter **Konfigurationseigenschaften**, wählen Sie **C/C++-**, **vorkompilierte Header**.  
  
12. Für die **vorkompilierter Header** -Eigenschaft die Option **vorkompilierte Header nicht verwenden**, und wählen Sie dann die **OK** Schaltfläche.  
  
13. Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
## <a name="debugging-the-cpu-code"></a>Debuggen des CPU-Codes  
 In diesem Verfahren verwenden Sie die lokale Windows-Debugger, um sicherzustellen, dass der CPU-Code in dieser Anwendung korrekt ist. Das Segment des CPU-Codes in diese Anwendung besonders interessant ist, ist die `for` wurde eine Schleife in der `reduction_sum_gpu_kernel` Funktion. Es steuert die Struktur basierender parallele Reduzierung, die auf dem GPU ausgeführt wird.  
  
### <a name="to-debug-the-cpu-code"></a>So debuggen Sie die CPU-code  
  
1.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld unter **Konfigurationseigenschaften**, wählen Sie **Debuggen**. Überprüfen Sie, ob **lokaler Windows-Debugger** ausgewählt ist, der **zu startender Debugger** Liste.  
  
3.  Geben Sie im Code-Editor zurück.  
  
4.  Festlegen von Breakpoints für die Codezeilen, die in der folgenden Abbildung (ungefähr Zeilen 67 Line 70) angezeigt.  
  
     ![CPU-Haltepunkte](../../parallel/amp/media/campcpubreakpoints.png "Campcpubreakpoints")  
CPU-Haltepunkte  
  
5.  Wählen Sie in der Menüleiste **Debuggen**, **Debuggen**.  
  
6.  In der **"lokal"** Fenster, beachten Sie den Wert für `stride_size` fort, bis der Haltepunkt in Zeile 70 erreicht ist.  
  
7.  Wählen Sie in der Menüleiste **Debuggen**, **Beenden des Debuggens**.  
  
## <a name="debugging-the-gpu-code"></a>Debuggen von GPU-Code  
 In diesem Abschnitt wird gezeigt, wie die GPU-Code zu debuggen, dem Code enthalten in der `sum_kernel_tiled` Funktion. GPU-Code berechnet die Summe von ganzen Zahlen für jeden "Block" Parallel.  
  
### <a name="to-debug-the-gpu-code"></a>Debuggen von GPU-code  
  
1.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **AMPMapReduce**, und wählen Sie dann **Eigenschaften**.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld unter **Konfigurationseigenschaften**, wählen Sie **Debuggen**.  
  
3.  In der **zu startender Debugger** Liste **lokaler Windows-Debugger**.  
  
4.  In der **Debuggertyp** Liste **nur GPU**.  
  
5.  Klicken Sie auf die Schaltfläche **OK** .  
  
6.  Legen Sie einen Haltepunkt in Zeile 30, wie in der folgenden Abbildung dargestellt.  
  
     ![GPU-Haltepunkte](../../parallel/amp/media/campgpubreakpoints.png "Campgpubreakpoints")  
GPU-Haltepunkt  
  
7.  Wählen Sie in der Menüleiste **Debuggen**, **Debuggen**. Die Haltepunkte in der CPU-Code in den Zeilen 67 und 70 werden nicht ausgeführt, während der GPU-debugging, da diese Codezeilen auf der CPU ausgeführt werden.  
  
### <a name="to-use-the-gpu-threads-window"></a>Verwenden Sie das GPU-Threadfenster  
  
1.  Wählen Sie zum Öffnen von GPU-Threadfenster, klicken Sie auf der Menüleiste **Debuggen**, **Windows**, **GPU-Threads**.  
  
     Sie können dem Status der GPU-Threads im GPU-Threadfenster untersuchen, die angezeigt wird.  
  
2.  Docken Sie das GPU-Threadfenster am unteren Rand von Visual Studio. Wählen Sie die **erweitern Thread Switch** Schaltfläche, um die Kachel und bestimmten Thread Textfelder zeigen. GPU-Threadfenster zeigt die Gesamtanzahl der aktiven als auch blockierte GPU-Threads an, wie in der folgenden Abbildung dargestellt.  
  
     ![GPU-Threadfenster mit 4 aktiven Threads](../../parallel/amp/media/campc.png "Campc")  
GPU-Threadfenster  
  
     313 Kacheln, die für diese Berechnung zugeordnet sind. Jede Kachel enthält 32 Threads. Da lokale GPU-debugging auf eine Softwareemulator auftritt, stehen Ihnen vier aktive GPU-Threads. Die vier Threads Gleichzeitiges Ausführen von den Anweisungen und das Verschieben in die nächste Anweisung zusammen auf.  
  
     Im GPU-Threadfenster, gibt es vier GPU-Threads aktiv sind und 28 GPU-Threads blockiert die [tile_barrier:: wait](reference/tile-barrier-class.md#wait) am zu Zeile 21 definierte Anweisung (`t_idx.barrier.wait();`). Alle 32 GPU-Threads gehören, auf der ersten Kachel `tile[0]`. Ein Pfeil zeigt auf die Zeile, die den aktuellen Thread enthält. Um zu einem anderen Thread zu wechseln, verwenden Sie eine der folgenden Methoden:  

  
    -   In der Zeile des Threads im GPU-Threadfenster zu wechseln, öffnen Sie das Kontextmenü und wählen Sie **zu Thread wechseln**. Wenn die Zeile mehr als einem Thread darstellt, wechseln Sie für den ersten Ausführungsthread gemäß den Thread Koordinaten.  
  
    -   Geben Sie die Kachel- und threadwerte Werte des Threads in die entsprechenden Textfelder ein, und wählen Sie dann die **Switch Thread** Schaltfläche.  
  
     Das Fenster "Aufrufliste" zeigt die Aufrufliste des aktuellen GPU-Threads.  
  
### <a name="to-use-the-parallel-stacks-window"></a>Verwenden Sie das Fenster "Parallele Stapel"  
  
1.  Wählen Sie zum Öffnen des Fensters Parallele Stapel auf der Menüleiste **Debuggen**, **Windows**, **parallele Stapel**.  
  
     Das Fenster "Parallele Stapel" können Sie um gleichzeitig mehrere GPU-Threads Stapelrahmen zu überprüfen.  
  
2.  Docken Sie das Fenster "Parallele Stapel" am unteren Rand von Visual Studio.  
  
3.  Stellen Sie sicher, dass **Threads** in der oberen linken Ecke der Liste ausgewählt ist. In der folgenden Abbildung zeigt das Fenster "Parallele Stapel" eine Ansicht mit Fokus Aufrufliste die GPU-Threads, die Sie im GPU-Threadfenster gesehen haben.  
  
     ![Fenster "Parallele Stapel" mit 4 aktiven Threads](../../parallel/amp/media/campd.png "Campd")  
Fenster für parallele Stapel  
  
     32 Threads hat sich aus `_kernel_stub` für die Lambda-Anweisung in der `parallel_for_each` Funktionsaufruf, und klicken Sie dann auf die `sum_kernel_tiled` -Funktion, in dem die parallele Reduzierung tritt auf. 28 nicht mehr genügend 32 Threads haben fortgeschritten, um die [tile_barrier:: wait](reference/tile-barrier-class.md#wait) Anweisung und in Zeile 22, Sperrung bleibt, während die anderen 4 Threads in aktiv bleiben die `sum_kernel_tiled` Funktion in Zeile 30.  

  
     Sie können die Eigenschaften eines GPU-Threads untersuchen, die in der GPU-Threadfenster im rich DataTip des Fensters Parallele Stapel zur Verfügung stehen. Zu diesem Zweck führen Sie den Mauszeiger auf den Stapelrahmen des **Sum_kernel_tiled**. Die folgende Abbildung zeigt den DataTip.  
  
     ![DataTip für Fenster "Parallele Stapel"](../../parallel/amp/media/campe.png "Campe")  
GPU-Threads DataTip  
  
     Weitere Informationen über das Fenster "Parallele Stapel" finden Sie unter [verwenden das Fenster "Parallele Stapel"](/visualstudio/debugger/using-the-parallel-stacks-window).  
  
### <a name="to-use-the-parallel-watch-window"></a>Verwenden Sie das parallele Überwachungsfenster  
  
1.  Wählen Sie zum Öffnen des parallele Überwachungsfenster, in der Menüleiste **Debuggen**, **Windows**, **parallele Überwachung**, **parallele Überwachung 1**.  
  
     Das parallele Überwachungsfenster können Sie um die Werte eines Ausdrucks über mehrere Threads hinweg zu untersuchen.  
  
2.  Docken Sie das Fenster für parallele Überwachung 1 am unteren Rand von Visual Studio. Es gibt 32 Zeilen in der Tabelle für das parallele Überwachungsfenster. Jeder entspricht einem GPU-Thread, der im GPU-Threadfenster und das Fenster "Parallele Stapel" angezeigt wurden. Jetzt können Sie Ausdrücke eingeben, deren Werte, die Sie über alle 32 GPU-Threads überprüfen möchten.  
  
3.  Wählen Sie die **Überwachung hinzufügen** Spaltenheader, geben Sie `localIdx`, und wählen Sie dann die EINGABETASTE.  
  
4.  Wählen Sie die **Überwachung hinzufügen** Spaltenüberschrift erneut, den Typ `globalIdx`, und wählen Sie dann die EINGABETASTE.  
  
5.  Wählen Sie die **Überwachung hinzufügen** Spaltenüberschrift erneut, den Typ `localA[localIdx[0]]`, und wählen Sie dann die EINGABETASTE.  
  
     Sie können durch einen angegebenen Ausdruck durch Auswählen der entsprechenden Spaltenüberschrift sortieren.  
  
     Wählen Sie die **LocalA [LocalIdx [0]]** Spaltenheader, um die Spalte zu sortieren. Die folgende Abbildung zeigt die Ergebnisse sortieren nach **LocalA [LocalIdx [0]]**.  
  
     ![Fenster für parallele Überwachung mit sortierten Ergebnissen](../../parallel/amp/media/campf.png "Campf")  
 Sortierergebnisse  
  
     Sie können den Inhalt in das parallele Überwachungsfenster nach Excel exportieren, indem Sie die Schaltfläche "Excel" auswählen und dann **in Excel öffnen**. Wenn Sie Excel auf dem Entwicklungscomputer installiert haben, wird dies eine Excel-Arbeitsblatt mit dem Inhalt geöffnet.  
  
6.  In der oberen rechten Ecke des Fensters Parallele Überwachung ist es ein Filtersteuerelement, das Sie verwenden können, um den Inhalt mithilfe von booleschen Ausdrücken zu filtern. Geben Sie `localA[localIdx[0]] > 20000` in der Filtertext für das Steuerelement ein, und wählen Sie dann die EINGABETASTE.  
  
     Das Fenster enthält jetzt nur Threads auf dem die `localA[localIdx[0]]` Wert ist größer als 20000. Der Inhalt wird immer noch durch sortiert die `localA[localIdx[0]]` Spalte, die die Sortierung Aktion ist Sie zuvor ausgeführt haben.  
  
## <a name="flagging-gpu-threads"></a>Das Kennzeichnen von GPU-Threads  
 Sie können bestimmte GPU-Threads kennzeichnen, kennzeichnen sie in der GPU-Threadfenster, das parallele Überwachungsfenster oder der DataTip in das Fenster "Parallele Stapel". Enthält eine Zeile in der GPU-Threadfenster auf mehr als einem Thread, kennzeichnet das kennzeichnen diese Zeile alle Threads, die in der Zeile enthalten sind.  
  
### <a name="to-flag-gpu-threads"></a>So kennzeichnen Sie GPU-threads  
  
1.  Wählen Sie die **[Thread]** Spaltenüberschrift im Fenster parallele Überwachung 1 Sortierungskriterium Kachel und Threadindex.  
  
2.  Wählen Sie in der Menüleiste **Debuggen**, **Fortfahren**, die die vier Threads verursacht, des Status der nächsten Barriere (definiert in Zeile 32 der AMPMapReduce.cpp) aktiv waren.  
  
3.  Wählen Sie das Flaggensymbol auf der linken Seite der Zeile, die die vier Threads enthält, die jetzt aktiv sind.  
  
     Die folgende Abbildung zeigt die vier aktiven gekennzeichneten Threads im GPU-Threadfenster.  
  
     ![GPU-Threadfenster mit gekennzeichneten Threads](../../parallel/amp/media/campg.png "Campg")  
Aktive Threads im GPU-Threadfenster  
  
     Geben Sie das Fenster zur parallelen Überwachung und der DataTip des Fensters Parallele Stapel sowohl die gekennzeichneten Threads an.  
  
4.  Wenn auf die vier Threads zu konzentrieren, die Sie gekennzeichnet werden sollen, können Sie im GPU-Threads, parallele Überwachung und parallele Stapel Windows, nur gekennzeichnete Threads anzeigen.  
  
     Schaltfläche mit den nur gekennzeichnete Threads anzeigen auf jedem Windows oder in der **Debugspeicherort** Symbolleiste. Die folgende Abbildung zeigt die Schaltfläche "nur gekennzeichnete Threads anzeigen" auf die **Debugspeicherort** Symbolleiste.  
  
     ![Mit dem Symbol "nur gekennzeichnete anzeigen" Symbolleiste "Debugspeicherort"](../../parallel/amp/media/camph.png "Camph")  
Schaltfläche „Nur gekennzeichnete anzeigen“  
  
     Die GPU-Threads, parallele Überwachung und parallele Stapel Windows wird jetzt nur die gekennzeichneten Threads angezeigt.  
  
## <a name="freezing-and-thawing-gpu-threads"></a>Einfrieren und Reaktivieren von GPU-Threads  
 Sie können Einfrieren (anhalten) und reaktivieren (Fortsetzen) GPU-Threads von GPU-Threadfenster oder das parallele Überwachungsfenster. Sie können Einfrieren und reaktivieren CPU-Threads die gleiche Weise; Informationen finden Sie unter [wie: Verwenden des Fensters Threads](/visualstudio/debugger/how-to-use-the-threads-window).  
  
### <a name="to-freeze-and-thaw-gpu-threads"></a>So sperren und Entsperren von GPU-threads  
  
1.  Wählen Sie die **nur gekennzeichnete Threads anzeigen** Schaltfläche, um alle Threads angezeigt.  
  
2.  Wählen Sie in der Menüleiste **Debuggen**, **Fortfahren**.  
  
3.  Öffnen Sie das Kontextmenü für die aktive Zeile, und wählen Sie dann **fixieren**.  
  
     Der GPU-Threadfenster die folgende Abbildung zeigt, dass alle vier Threads eingefroren werden.  
  
     ![GPU-Threadfenster mit fixierten Threads](../../parallel/amp/media/campk.png "Campk")  
Fixierte Threads im GPU-Threadfenster  
  
     Auf ähnliche Weise zeigt das parallele Überwachungsfenster an, dass alle vier Threads eingefroren werden.  
  
4.  Wählen Sie in der Menüleiste **Debuggen**, **Fortfahren** ermöglichen die nächsten vier GPU-Threads nach der Barriere in Zeile 22 verstreichen und den Haltepunkt in Zeile 30 erreicht. GPU-Threadfenster zeigt, dass die vier zuvor fixierten Threads bleiben fixierte und im aktiven Zustand.  
  
5.  Wählen Sie in der Menüleiste **Debuggen**, **Fortfahren**.  
  
6.  Über das parallele Überwachungsfenster können Sie auch einzelne oder mehrere GPU-Threads reaktivieren.  
  
### <a name="to-group-gpu-threads"></a>GPU-Threads gruppieren  
  
1.  Klicken Sie im Kontextmenü für eines der Threads in der **GPU-Threads** Fenster, wählen Sie **Group By**, **Adresse**.  
  
     Die Threads im GPU-Threadfenster werden nach Adresse gruppiert. Die Adresse entspricht der Anweisung im Disassemblyfenster, in dem jede Gruppe von Threads befindet. 24 Threads werden in Zeile 22, in denen die [tile_barrier:: Wait-Methode](reference/tile-barrier-class.md#wait) ausgeführt wird. 12-Threads werden bei der Anweisung für die Grenze in Zeile 32. Vier dieser Threads werden gekennzeichnet. Acht Threads sind am Haltepunkt in Zeile 30. Vier diese Threads sind fixiert. Die folgende Abbildung zeigt die gruppierten Threads im GPU-Threadfenster.  

  
     ![GPU-Threadfenster mit Threads nach Adresse angeordneten](../../parallel/amp/media/campl.png "Campl")  
Gruppierte Threads im GPU-Threadfenster  
  
2.  Sie können auch Ausführen der **Group By** Vorgang durch, indem Sie das Kontextmenü für das Datenraster, der das parallele Überwachungsfenster öffnen auswählen **Group By**, und drücken Sie dann auf das Menüelement, die Vorstellung entspricht Threads gruppieren möchten.  
  
## <a name="running-all-threads-to-a-specific-location-in-code"></a>Ausführen von allen Threads an einem bestimmten Speicherort im Code  
 Sie können alle Threads in einer bestimmten Kachel ausführen, in der Zeile mit den Cursor mithilfe **ausführen aktuelle Kachel bis Cursor**.  
  
### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>Alle Threads ausgeführt werden, zu dem Speicherort, der vom Cursor markiert  
  
1.  Wählen Sie im Kontextmenü für die fixierten Threads **reaktivieren**.  
  
2.  Im Code-Editor, platzieren Sie den Cursor in Zeile 30.  
  
3.  Wählen Sie auf das Kontextmenü für den Code-Editor **aktuelle Kachel bis Cursor ausführen**.  
  
     24 Threads, die die Barriere in Zeile 21 zuvor bereits blockiert wurden, haben zur Zeile 32 fortgeschritten. Dies wird gezeigt, der **GPU-Threads** Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++ AMP](../../parallel/amp/cpp-amp-overview.md)   
 [Debuggen von GPU-Code](/visualstudio/debugger/debugging-gpu-code)   
 [Vorgehensweise: Verwenden Sie das GPU-Threadfenster](/visualstudio/debugger/how-to-use-the-gpu-threads-window)   
 [Vorgehensweise: Verwenden des parallelen Überwachungsfensters](/visualstudio/debugger/how-to-use-the-parallel-watch-window)   
 [Analysieren von C++ AMP-Code mit der Parallelitätsschnellansicht](http://go.microsoft.com/fwlink/linkid=253987&clcid=0x409)

