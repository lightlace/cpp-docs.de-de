---
title: "Aufgabenparallelität (Concurrency Runtime) | Microsoft Docs"
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
- structured task groups [Concurrency Runtime]
- structured tasks [Concurrency Runtime]
- task groups [Concurrency Runtime]
- task parallelism
- tasks [Concurrency Runtime]
ms.assetid: 42f05ac3-2098-494a-ba84-737fcdcad077
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e4b96228ac867781b00be7ca92a9debcad3f9eb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="task-parallelism-concurrency-runtime"></a>Aufgabenparallelität (Concurrency Runtime)
In der Concurrency Runtime wird eine *Aufgabe* ist eine Arbeitseinheit, die einen bestimmten Auftrag ausführt und normalerweise parallel zu anderen Aufgaben ausgeführt wird. Eine Aufgabe kann in weitere, differenziertere Aufgaben, die in organisiert sind zerlegt werden eine *Aufgabengruppe*.  
  
 Sie verwenden Aufgaben, wenn Sie asynchronen Code schreiben und ein Vorgang erst ausgeführt werden soll, nachdem der asynchrone Vorgang abgeschlossen ist. Sie können z. B. eine Aufgabe verwenden, um asynchron aus einer Datei lesen, und verwenden Sie eine andere Aufgabe – eine *Fortsetzungsaufgabe*, die weiter unten in diesem Dokument erläutert wird – zum Verarbeiten der Daten, nachdem sie verfügbar sind. Umgekehrt können Sie Aufgabengruppen verwenden, um parallele Arbeitsvorgänge in kleinere Teile zu zerlegen. Nehmen Sie zum Beispiel einmal an, dass Sie über einen rekursiven Algorithmus verfügen, der die verbleibende Arbeit in zwei Partitionen unterteilt. Sie können Aufgabengruppen verwenden, um diese Partitionen gleichzeitig auszuführen, und dann warten, bis die aufgeteilte Arbeit abgeschlossen ist.  
  
> [!TIP]

>  Wenn Sie die gleiche Routine auf jedes Element einer Auflistung gleichzeitig anwenden möchten, verwenden Sie parallele Algorithmen, wie z. B. [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for)statt einer Aufgabe oder Aufgabengruppe. Weitere Informationen zu parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  

  
## <a name="key-points"></a>Wesentliche Punkte  
  
-   Wenn Sie Variablen als Verweis an einen Lambdaausdruck übergeben, müssen Sie sicherstellen, dass die Lebensdauer dieser Variablen bis zum Beenden der Aufgabe erhalten bleibt.  
  
-   Verwenden Sie Aufgaben (die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) Klasse) Wenn Sie asynchronen Code schreiben. Die Aufgabenklasse verwendet den Windows-ThreadPool als zugehörigen Planer und nicht die Concurrency Runtime.  
  
-   Verwenden Sie Aufgabengruppen (die [Concurrency:: task_group](reference/task-group-class.md) Klasse oder die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus) Wenn Sie parallele Arbeitsvorgänge in kleinere Teile zerlegen und warten Sie dann diese kleinere möchten Schritte abgeschlossen.  
  
-   Verwenden der [Concurrency::task::then](reference/task-class.md#then) Methode, um Fortsetzungen zu erstellen. Ein *Fortsetzung* ist eine Aufgabe, die nach Abschluss einer anderen Aufgabe asynchron ausgeführt wird. Sie können eine beliebige Anzahl an Fortsetzungen verbinden, um eine Kette asynchroner Arbeitsvorgänge zu bilden.  
  
-   Die Ausführung einer aufgabenbasierten Fortsetzung wird immer für den Zeitpunkt geplant, zu dem die Vorgängeraufgabe abgeschlossen ist, auch wenn die Vorgängeraufgabe abgebrochen wird oder wenn diese eine Ausnahme auslöst.  
  
-   Verwendung [when_all](reference/concurrency-namespace-functions.md#when_all) zum Erstellen einer Aufgabe, die abgeschlossen wird, nachdem alle Mitglieder einer Gruppe von Aufgaben abgeschlossen. Verwendung [Concurrency:: when_any](reference/concurrency-namespace-functions.md#when_any) eine Aufgabe erstellt, die nach einem Mitglied einer Gruppe von Aufgaben abgeschlossen wird.  

  
-   Für Aufgaben und Aufgabengruppen kann der Abbruchmechanismus der Parallel Patterns Library (PPL) verwendet werden. Weitere Informationen finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
-   Um zu erfahren, wie die Runtime Ausnahmen behandelt, die von Aufgaben und Aufgabengruppen ausgelöst werden, finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="in-this-document"></a>In diesem Dokument  
  
- [Verwenden von Lambdaausdrücken](#lambdas)  
  
- [Die Task-Klasse](#task-class)  
  
- [Fortsetzungsaufgaben](#continuations)  
  
- [Wertbasierte und aufgabenbasierte Fortsetzungen](#value-versus-task)  
  
- [Verfassen von Aufgaben](#composing-tasks)  
  
    - [Die Funktion "when_all"](#when-all)  
  
    - [Die Funktion "when_any"](#when-any)  
  
- [Verzögerte Aufgabenausführung](#delayed-tasks)  
  
- [Aufgabengruppen](#task-groups)  
  
- [Task_group und structured_task_group im Vergleich](#comparing-groups)  
  
- [Beispiel](#example)  
  
- [Stabile Programmierung](#robust)  
  
##  <a name="lambdas">Verwenden von Lambdaausdrücken</a>  
 Aufgrund ihrer kompakten Syntax werden Lambda-Ausdrücke häufig zur Definition der Arbeit verwendet, die von Aufgaben und Aufgabengruppen ausgeführt wird. Im Folgenden finden Sie einige Verwendungstipps:  
  
-   Da Aufgaben in der Regel in Hintergrundthreads ausgeführt werden, beachten Sie die Objektlebensdauer, wenn Sie Variablen in Lambda-Ausdrücken erfassen. Wenn Sie eine Variable als Wert erfassen, wird eine Kopie dieser Variablen im Lambda-Text erstellt. Wenn Sie sie als Verweis erfassen, wird keine Kopie erstellt. Daher müssen Sie sicherstellen, dass die Lebensdauer jeder Variablen, die Sie als Verweis erfassen, länger ist als die Lebensdauer der Aufgabe, die diese verwendet.  
  
-   Wenn Sie einen Lambda-Ausdruck an eine Aufgabe übergeben, erfassen Sie keine Variablen, die auf dem Stapel als Verweis zugeordnet sind.  
  
-   Bezeichnen Sie die in Lambdaausdrücken erfassten Variablen eindeutig, damit Sie feststellen können, welche Variablen Sie als Wert und welche Sie als Verweis erfassen. Aus diesem Grund wird empfohlen, die Option `[=]` oder `[&]` für Lambda-Ausdrücke nicht zu verwenden.  
  
 Häufig wird in einer Aufgabe in einer Fortsetzungskette eine Zuweisung zu einer Variablen vorgenommen und in einer anderen Aufgabe diese Variable gelesen. Sie können die Variable nicht als Wert erfassen, da jede Fortsetzungsaufgabe über eine andere Kopie der Variablen verfügen würde. Bei auf dem Stapel zugeordneten Variablen können Sie diese auch nicht als Verweis erfassen, da die Variable möglicherweise nicht mehr gültig ist.  
  
 Verwenden Sie zum Lösen dieses Problems einen intelligenten Zeiger ein, z. B. [Std:: shared_ptr](../../standard-library/shared-ptr-class.md), um die Variable zu umschließen, und den intelligenten Zeiger als Wert übergeben. Auf diese Weise kann eine Zuweisung zum zugrunde liegenden Objekt erfolgen, und es kann aus diesem Objekt gelesen werden. Außerdem ist seine Lebensdauer länger als die der Aufgaben, die es verwenden. Verwenden Sie diese Methode auch, wenn die Variable ein Zeiger oder ein Handle mit Verweiszählung (`^`) für ein Windows-Runtime-Objekt ist. Es folgt ein einfaches Beispiel:  
  
 [!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]  
  
 Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../cpp/lambda-expressions-in-cpp.md).  
  
##  <a name="task-class">Die Task-Klasse</a>  
 Sie können die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) Klasse, um Aufgaben zu einem Satz abhängiger Vorgänge zu kombinieren. Dieses kompositionsmodell wird durch das Konzept der unterstützt *Fortsetzungen*. Eine Fortsetzung ermöglicht es Code ausgeführt wird, wenn die vorherige oder *Vorgänger*, Aufgabe abgeschlossen ist. Das Ergebnis der Vorgängeraufgabe wird als Eingabe an eine oder mehrere Fortsetzungsaufgaben übergeben. Wenn eine Vorgängeraufgabe abgeschlossen wird, werden alle Fortsetzungsaufgaben, die darauf warten, für die Ausführung geplant. Jede Fortsetzungsaufgabe erhält eine Kopie des Ergebnisses der Vorgängeraufgabe. Diese Fortsetzungsaufgaben wiederum können auch Vorgängeraufgaben für andere Fortsetzungen sein, sodass sie eine Kette von Aufgaben bilden. Mit Fortsetzungen können Sie Ketten von Aufgaben beliebiger Länge erstellen, die bestimmte Abhängigkeiten untereinander aufweisen. Außerdem kann für eine Aufgabe der Abbruchmechanismus verwendet werden – entweder vor dem Start einer Aufgabe oder in kooperativer Weise, während die Aufgabe ausgeführt wird. Weitere Informationen über dieses Abbruchmodell finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
 Bei `task` handelt es sich um eine Vorlagenklasse. Der Typparameter `T` gibt den Typ des Ergebnisses an, das von der Aufgabe erzeugt wird. Dieser Typ kann `void` sein, wenn die Aufgabe keinen Wert zurückgibt. Für `T` kann der `const`-Modifizierer nicht verwendet werden.  
  
 Wenn Sie eine Aufgabe erstellen, geben Sie einen *Arbeitsfunktion* , die den Aufgabentext ausführt. Bei dieser Arbeitsfunktion kann es sich um eine Lambda-Funktion, einen Funktionszeiger oder ein Funktionsobjekt handeln. Rufen Sie auf Fertig stellen, ohne das Ergebnis einer Aufgabe zu warten, die [Concurrency::task::wait](reference/task-class.md#wait) Methode. Die `task::wait` Methode gibt ein [Concurrency:: task_status](reference/concurrency-namespace-enums.md#task_group_status) Wert, der angibt, ob die Aufgabe abgeschlossen oder abgebrochen wurde. Um das Ergebnis des Vorgangs zu erhalten, rufen die [Concurrency](reference/task-class.md#get) Methode. Von dieser Methode wird `task::wait` aufgerufen, um darauf zu warten, dass die Aufgabe beendet wird. Daher wird die Ausführung des aktuellen Threads blockiert, bis das Ergebnis zur Verfügung steht.  
  
 Im folgenden Beispiel wird gezeigt, wie eine Aufgabe erstellt, auf das Ergebnis gewartet und dessen Wert angezeigt wird. In den Beispielen in dieser Dokumentation werden Lambda-Funktionen verwendet, da sie eine kompaktere Syntax aufweisen. Sie können bei der Verwendung von Aufgaben jedoch auch Funktionszeiger und Funktionsobjekte verwenden.  
  
 [!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]  
  

 Bei Verwendung der [Concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) -Funktion, die Sie verwenden die `auto` -Schlüsselwort anstelle der Deklaration des Typs. Betrachten Sie beispielsweise diesen Code, mit dem die Identitätsmatrix erstellt und ausgegeben wird:  

  
 [!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]  
  
 Sie können die `create_task`-Funktion verwenden, um den entsprechenden Vorgang zu erstellen.  
  
 [!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]  
  
 Wenn während der Ausführung einer Aufgabe eine Ausnahme ausgelöst wird, wird die Ausnahme von der Laufzeit im nachfolgenden Aufruf an `task::get`, `task::wait` oder eine aufgabenbasierte Fortsetzung gemarshallt. Weitere Informationen zu der Ausnahme Verarbeitungsmechanismus, finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Ein Beispiel, verwendet `task`, [Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), Abbruch, finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md). (Die `task_completion_event`-Klasse wird weiter unten in diesem Dokument beschrieben.)  
  
> [!TIP]
>  Um Details zu erfahren, die bestimmte Aufgaben in uwp-apps sind, finden Sie unter [asynchrone Programmierung in C++](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) und [Erstellen von asynchronen Vorgängen in C++ für uwp-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
##  <a name="continuations">Fortsetzungsaufgaben</a>  
 Bei der asynchronen Programmierung werden nach Abschluss eines asynchronen Vorgangs häufig ein zweiter Vorgang aufgerufen und Daten an diesen weitergegeben. Herkömmlicherweise werden hierfür Rückrufmethoden verwendet. In der Concurrency Runtime wird die gleiche Funktionalität vom bereitgestellt *Fortsetzungsaufgaben*. Eine Fortsetzungsaufgabe (auch kurz als Fortsetzung bezeichnet) ist eine asynchrone Aufgabe, die von einer anderen Aufgabe, die aufgerufen wird so genannte der *Vorgänger*, wenn der Vorgänger abgeschlossen wird. Mithilfe von Fortsetzungen können Sie folgende Aufgaben ausführen:  
  
-   Übergeben von Daten vom Vorgänger an die Fortsetzung  
  
-   Angeben der präzisen Bedingungen, unter denen die Fortsetzung aufgerufen bzw. nicht aufgerufen wird  
  
-   Abbrechen einer Fortsetzung, bevor diese gestartet wird oder kooperativ während sie ausgeführt wird  
  
-   Bereitstellen von Hinweisen zur Planung der Fortsetzung (Dies gilt für nur apps (Universelle Windows Plattform). Weitere Informationen finden Sie unter [Erstellen von asynchronen Vorgängen in C++ für uwp-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)  
  
-   Aufrufen mehrerer Fortsetzungen durch den gleichen Vorgänger  
  
-   Aufrufen einer Fortsetzung, wenn alle Vorgänger oder einer der Vorgänger abgeschlossen wird  
  
-   Verketten von Fortsetzungen auf eine beliebige Länge  
  
-   Behandeln von durch den Vorgänger ausgelösten Ausnahmen mithilfe einer Fortsetzung  
  
 Mithilfe dieser Funktionen können Sie eine oder mehrere Aufgaben ausführen, wenn die erste Aufgabe abgeschlossen wird. Sie können beispielsweise eine Fortsetzung erstellen, in der eine Datei komprimiert wird, nachdem sie von der ersten Aufgabe vom Datenträger gelesen wurde.  
  


 Im folgende Beispiel wird das vorherige so geändert verwenden die [Concurrency::task::then](reference/task-class.md#then) Methode zum Planen einer Fortsetzung, die den Wert der Vorgängeraufgabe ausgibt, wenn dieser verfügbar ist.  


  
 [!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]  
  
 Sie können Aufgaben auf eine beliebige Länge verketten und schachteln. Eine Aufgabe kann auch über mehrere Fortsetzungen verfügen. Im folgenden Beispiel wird eine einfache Fortsetzungskette dargestellt, in der der Wert der vorherigen Aufgabe dreimal erhöht wird.  
  
 [!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]  
  
 Eine Fortsetzung kann auch eine andere Aufgabe zurückgeben. Wenn kein Abbruch erfolgt, wird diese Aufgabe vor der nachfolgenden Fortsetzung ausgeführt. Diese Technik wird als bezeichnet *das asynchrone Entpacken*. Das asynchrone Entpacken ist nützlich, wenn Sie zusätzliche Arbeitsvorgänge im Hintergrund ausführen möchten, jedoch nicht möchten, dass der aktuelle Thread durch die aktuelle Aufgabe blockiert wird. (Dies ist häufig in UWP-apps, in denen können Fortsetzungen im UI-Thread ausgeführt). Im folgenden Beispiel werden drei Aufgaben gezeigt. Die erste Aufgabe gibt eine andere Aufgabe zurück, die vor einer Fortsetzungsaufgabe ausgeführt wird.  
  
 [!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]  
  
> [!IMPORTANT]
>  Wenn eine Fortsetzung einer Aufgabe eine geschachtelte Aufgabe vom Typ `N` zurückgibt, ist die resultierende Aufgabe vom Typ `N`, nicht vom Typ `task<N>`, und wird abgeschlossen, wenn die geschachtelte Aufgabe abgeschlossen wird. Das heißt, die Fortsetzung entpackt die geschachtelte Aufgabe.  
  
##  <a name="value-versus-task">Wertbasierte und aufgabenbasierte Fortsetzungen</a>  
 Bei einem `task`-Objekt, dessen Rückgabetyp `T` ist, können Sie einen Wert des Typs `T` oder `task<T>` für die zugehörigen Fortsetzungsaufgaben bereitstellen. Eine Fortsetzung, die Typ akzeptiert `T` wird als bezeichnet eine *wertbasierte Fortsetzung*. Eine wertbasierte Fortsetzung wird für die Ausführung geplant, wenn die Vorgängeraufgabe ohne Fehler abgeschlossen und nicht abgebrochen wird. Eine Fortsetzung, die Typ akzeptiert `task<T>` wie Parameter als bekannt ist ein *aufgabenbasierte Fortsetzung*. Die Ausführung einer aufgabenbasierten Fortsetzung wird immer für den Zeitpunkt geplant, zu dem die Vorgängeraufgabe abgeschlossen ist, auch wenn die Vorgängeraufgabe abgebrochen wird oder wenn diese eine Ausnahme auslöst. Sie können dann `task::get` aufrufen, um das Ergebnis der Vorgängeraufgabe abzurufen. Wenn die Vorgängeraufgabe abgebrochen wurde, `task::get` löst [Concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md). Wenn von der Vorgängeraufgabe eine Ausnahme ausgelöst wurde, wird von `task::get` diese Ausnahme erneut ausgelöst. Eine aufgabenbasierte Fortsetzung wird nicht als abgebrochen markiert, wenn die zugehörige Vorgängeraufgabe abgebrochen wird.  
  
##  <a name="composing-tasks">Verfassen von Aufgaben</a>  
 In diesem Abschnitt wird beschrieben, die [when_all](reference/concurrency-namespace-functions.md#when_all) und [Concurrency:: when_any](reference/concurrency-namespace-functions.md#when_all) -Funktionen, die Ihnen dabei helfen zu verfassen mehrere Aufgaben aus, um allgemeine Muster zu implementieren.  

  
###  <a name="when-all">Die Funktion "when_all"</a>  
 Von der `when_all`-Funktion wird eine Aufgabe erstellt, die abgeschlossen wird, nachdem ein Satz von Aufgaben abgeschlossen wurde. Diese Funktion gibt eine std::[Vektor](../../standard-library/vector-class.md) -Objekt, das das Ergebnis der einzelnen Aufgaben im Satz enthält. Im folgenden einfachen Beispiel wird mithilfe von `when_all` eine Aufgabe erstellt, die den Abschluss von drei anderen Aufgaben darstellt.  
  
 [!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]  
  
> [!NOTE]
>  Die Aufgaben, die Sie an `when_all` übergeben, müssen einheitlich sein. Das heißt, sie müssen alle den gleichen Typ zurückgeben.  
  
 Sie können auch die Syntax `&&` verwenden, um eine Aufgabe zu erstellen, die nach Abschluss eines Satzes von Aufgaben abgeschlossen wird, wie im folgenden Beispiel gezeigt.  
  
 `auto t = t1 && t2; // same as when_all`  
  
 Es ist üblich, eine Fortsetzung zusammen mit `when_all` zu verwenden, um eine Aktion auszuführen, nachdem ein Satz von Aufgaben abgeschlossen wurde. Im folgenden Beispiel wird das vorherige so geändert, dass die Summe von drei Aufgaben ausgegeben wird, die jeweils ein Ergebnis vom Typ `int` liefern.  
  
 [!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]  
  
 In diesem Beispiel können Sie auch `task<vector<int>>` angeben, um eine aufgabenbasierte Fortsetzung zu erstellen.  
  
 Wenn eine Aufgabe in einem Satz von Aufgaben abgebrochen wird oder eine Ausnahme auslöst, wird `when_all` sofort abgeschlossen und wartet nicht, bis die übrigen Aufgaben beendet sind. Wenn eine Ausnahme ausgelöst wird, löst die Laufzeit die Ausnahme erneut aus, wenn Sie `task::get` oder `task::wait` für das Task-Objekt aufrufen, das von `when_all` zurückgegeben wird. Wenn von mehr als einer Aufgabe eine Ausnahme ausgelöst wird, wird von der Laufzeit eine ausgewählt. Daher müssen Sie sicherstellen, dass Sie alle Ausnahmen nach Abschluss aller Aufgaben berücksichtigen. Eine nicht behandelte Ausnahme einer Aufgabe führt dazu, dass die App beendet wird.  
  
 Es steht eine Hilfsfunktion zur Verfügung, mit der Sie sicherstellen können, dass Ihr Programm alle Ausnahmen berücksichtigt. Die Funktion `observe_all_exceptions` löst für jede Aufgabe im bereitgestellten Bereich jede aufgetretene Ausnahme aus, damit diese erneut ausgelöst wird, und "schluckt" diese anschließend.  
  
 [!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]  
  
 Erwägen Sie eine UWP-app, die C++ und XAML verwendet und einen Satz von Dateien auf den Datenträger schreibt. Im folgenden Beispiel wird gezeigt, wie `when_all` und `observe_all_exceptions` verwendet werden, um sicherzustellen, dass das Programm alle Ausnahmen berücksichtigt.  
  
 [!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]  
  
##### <a name="to-run-this-example"></a>So führen Sie dieses Beispiel aus  
  
1.  Fügen Sie in "MainPage.xaml" ein `Button`-Steuerelement hinzu.  
  
 [!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]  
  
2.  Fügen Sie in "MainPage.xaml.h" diese Vorwärtsdeklarationen zum Abschnitt `private` der `MainPage`-Klassendeklaration hinzu.  
  
 [!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]  
  
3.  Implementieren Sie in "MainPage.xaml.cpp" den `Button_Click`-Ereignishandler.  
  
 [!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]  
  
4.  Implementieren Sie in "MainPage.xaml.cpp" `WriteFilesAsync` wie im Beispiel dargestellt.  
  
> [!TIP]

> `when_all` ist eine nicht blockierende Funktion, die `task` als Ergebnis erzeugt. Im Gegensatz zu [Task:: wait](reference/task-class.md#wait), es ist sicher, diese Funktion in einer uwp-app auf dem ASTA-(Application STA-) Thread aufzurufen.  

  
###  <a name="when-any">Die Funktion "when_any"</a>  
 Die `when_any`-Funktion erstellt eine Aufgabe, die abgeschlossen wird, wenn die erste Aufgabe in einem Satz von Aufgaben abgeschlossen wird. Diese Funktion gibt eine [Std:: Pair](../../standard-library/pair-structure.md) -Objekt, das das Ergebnis der abgeschlossenen Aufgabe und den Index dieser Aufgabe im Satz enthält.  
  
 Die `when_any`-Funktion ist insbesondere in folgenden Szenarien nützlich:  
  
-   Redundante Vorgänge. Betrachten Sie einen Algorithmus oder einen Vorgang, der auf verschiedene Weise ausgeführt werden kann. Sie können die `when_any`-Funktion verwenden, um den Vorgang auszuwählen, der zuerst beendet wird, und dann die verbleibenden Vorgänge abzubrechen.  
  
-   Überlappende Vorgänge. Sie können mehrere Vorgänge starten, die alle beendet werden müssen, und die `when_any`-Funktion verwenden, um Ergebnisse zu verarbeiten, wenn jeder Vorgang beendet wird. Nachdem ein Vorgang beendet wurde, können Sie eine oder mehrere weitere Aufgaben starten.  
  
-   Eingeschränkte Vorgänge. Sie können die `when_any`-Funktion verwenden, um das vorherige Szenario zu erweitern, indem Sie die Anzahl der gleichzeitigen Vorgänge einschränken.  
  
-   Abgelaufene Vorgänge. Sie können die `when_any`-Funktion verwenden, um zwischen einer oder mehreren Aufgaben und einer Aufgabe auszuwählen, die nach einer bestimmten Zeit beendet wird.  
  
 Wie bei `when_all` wird häufig eine Fortsetzung verwendet, in der mithilfe von `when_any` eine Aktion ausgeführt wird, wenn die erste Aufgabe in einem Satz von Aufgaben beendet wird. Im folgenden einfachen Beispiel wird mithilfe von `when_any` eine Aufgabe erstellt, die abgeschlossen wird, wenn die erste von drei anderen Aufgaben abgeschlossen wird.  
  
 [!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]  
  
 In diesem Beispiel können Sie auch `task<pair<int, size_t>>` angeben, um eine aufgabenbasierte Fortsetzung zu erstellen.  
  
> [!NOTE]
>  Wie bei `when_all` müssen alle an `when_any` übergebenen Aufgaben denselben Typ zurückgeben.  
  
 Sie können auch die Syntax `||` verwenden, um eine Aufgabe zu erstellen, die nach der ersten Aufgabe in einem Satz von Aufgaben abgeschlossen wird, wie im folgenden Beispiel gezeigt.  
  
 `auto t = t1 || t2; // same as when_any`  
  
> [!TIP]
>  Wie bei `when_all`, `when_any` nicht blockierend und sicher in einer uwp-app auf dem ASTA-Thread aufgerufen wird.  
  
##  <a name="delayed-tasks">Verzögerte Aufgabenausführung</a>  
 In einigen Fällen ist es notwendig, die Ausführung einer Aufgabe zu verzögern, bis eine Bedingung erfüllt ist, oder eine Aufgabe als Reaktion auf ein externes Ereignis zu starten. Bei der asynchronen Programmierung müssen Sie zum Beispiel möglicherweise eine Aufgabe als Reaktion auf ein E/A-Abschlussereignis starten.  
  
 Es gibt zwei Möglichkeiten, dies zu erreichen: Sie können eine Fortsetzung verwenden oder eine Aufgabe starten und auf ein Ereignis innerhalb der Arbeitsfunktion der Aufgabe warten. Allerdings gibt es Fälle, in denen es nicht möglich, eine dieser Techniken zu verwenden. Sie müssen beispielsweise über die Vorgängeraufgabe verfügen, um eine Fortsetzung zu erstellen. Jedoch, wenn Sie nicht über die Vorgängeraufgabe verfügen, können Sie erstellen eine *aufgabenabschlussereignis* und später dieses Ereignis mit der Vorgängeraufgabe verketten, sobald diese verfügbar sind. Da eine wartende Aufgabe auch einen Thread blockiert, können Sie Aufgabenabschlussereignisse außerdem dazu verwenden, Arbeitsvorgänge auszuführen, wenn ein asynchroner Vorgang abgeschlossen wird, und dadurch einen Thread freigeben.  
  
 Die [Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) -Klasse vereinfacht eine solche Komposition von Aufgaben. Wie die `task`-Klasse ist der Typparameter `T` der Typ des Ergebnisses, das von der Aufgabe erzeugt wird. Dieser Typ kann `void` sein, wenn die Aufgabe keinen Wert zurückgibt. Für `T` kann der `const`-Modifizierer nicht verwendet werden. In der Regel wird ein `task_completion_event`-Objekt für einen Thread oder eine Aufgabe bereitgestellt, der bzw. die signalisieren, wenn der Wert für das Objekt zur Verfügung steht. Gleichzeitig wird mindestens eine Aufgabe als Listener dieses Ereignisses festgelegt. Wenn das Ereignis festgelegt wird, werden die Listeneraufgaben abgeschlossen und ihre Fortsetzungen für die Ausführung geplant.  
  
 Ein Beispiel, verwendet `task_completion_event` für das Implementieren einer Aufgabe, die nach einer Verzögerung abgeschlossen wird, finden Sie unter [Vorgehensweise: Erstellen einer Aufgabe abgeschlossen wird nach einer Verzögerung](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md).  
  
##  <a name="task-groups">Aufgabengruppen</a>  
 Ein *Aufgabengruppe* verwaltet eine Auflistung von Aufgaben. Aufgabengruppen verschieben Aufgaben in eine Arbeitsübernahme-Warteschlange. Der Planer entfernt Aufgaben aus dieser Warteschlange und führt sie auf verfügbaren Computerressourcen aus. Nachdem Sie einer Aufgabengruppe Aufgaben hinzugefügt haben, können Sie warten, bis alle Aufgaben aufgeführt wurden, oder Sie können Aufgaben abbrechen, die noch nicht gestartet wurden.  
  
 In der PPL mithilfe der [Concurrency:: task_group](reference/task-group-class.md) und [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Klassen, Aufgabengruppen und [Concurrency:: task_handle](../../parallel/concrt/reference/task-handle-class.md) Klasse um die Aufgaben darstellen, die in diesen Gruppen ausgeführten. In der `task_handle`-Klasse wird der Code gekapselt, der die Arbeit ausführt. Wie die `task`-Klasse steht die Arbeitsfunktion in Form einer Lambda-Funktion, eines Funktionszeigers oder eines Funktionsobjekts zur Verfügung. In der Regel ist es nicht erforderlich, direkt mit `task_handle`-Objekten zu arbeiten. Stattdessen übergeben Sie Arbeitsfunktionen an eine Aufgabengruppe, die die `task_handle`-Objekte erstellt und verwaltet.  
  
 Die PPL unterscheidet zwischen Aufgabengruppen zwei Kategorien: *unstrukturierte Aufgabengruppen* und *strukturierte Aufgabengruppen*. In der PPL werden unstrukturierte Aufgabengruppen mithilfe der `task_group`-Klasse und strukturierte Aufgabengruppen mithilfe der `structured_task_group`-Klasse dargestellt.  
  
> [!IMPORTANT]

>  Die PPL definiert außerdem die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) -Algorithmus, der verwendet die `structured_task_group` Klasse, um eine Reihe von Aufgaben parallel ausgeführt werden. Da der `parallel_invoke`-Algorithmus eine kompaktere Syntax aufweist, wird empfohlen, diesen, sofern möglich, anstelle der `structured_task_group`-Klasse zu verwenden. Das Thema [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md) beschreibt `parallel_invoke` ausführlicher.  
  
 Verwenden Sie `parallel_invoke`, um mehrere unabhängige Aufgaben gleichzeitig auszuführen und sofort darauf zu warten, dass alle Aufgaben abgeschlossen sind. Diese Technik wird häufig als bezeichnet *Zweig- und Joinknoten* Parallelität. Verwenden Sie `task_group`, um mehrere unabhängige Aufgaben gleichzeitig auszuführen und später darauf zu warten, dass allle Aufgaben abgeschlossen sind. Beispielsweise können Sie einem `task_group`-Objekt Aufgaben hinzufügen und in einer anderen Funktion oder einem anderen Thread darauf warten, dass die Aufgaben beendet werden.  
  
 Aufgabengruppen unterstützen das Konzept eines Abbruchs. Mit einem Abbruch können Sie für alle aktiven Aufgaben angeben, dass der gesamte Vorgang abgebrochen werden soll. Durch den Abbruch wird außerdem verhindert, dass Aufgaben gestartet werden, die noch nicht gestartet wurden. Weitere Informationen über Abbrüche finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
 Die Laufzeit stellt außerdem ein Modell für die Ausnahmebehandlung bereit, mit dem Sie eine Ausnahme für eine Aufgabe auslösen und behandeln können, während Sie darauf warten, das die zugeordnete Aufgabengruppe fertig gestellt wird. Weitere Informationen zu diesem Modell für die Behandlung von Ausnahmen finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
##  <a name="comparing-groups">Task_group und structured_task_group im Vergleich</a>  
 Grundsätzlich wird die Verwendung von `task_group` oder `parallel_invoke` anstelle der `structured_task_group`-Klasse empfohlen. In Einzelfällen, beispielsweise beim Schreiben eines parallelen Algorithmus für eine variable Anzahl von Aufgaben oder mit der Möglichkeit eines Abbruchs, können Sie jedoch `structured_task_group` verwenden. In diesem Abschnitt werden die Unterschiede zwischen der `task_group`-Klasse und der `structured_task_group`-Klasse erläutert.  
  
 Die `task_group`-Klasse ist threadsicher. Sie können einem `task_group`-Objekt daher Aufgaben von mehreren Threads hinzufügen und in mehreren Threads auf ein `task_group`-Objekt warten oder dieses abbrechen. Das Erstellen und Zerstören eines `structured_task_group`-Objekts muss im gleichen lexikalischen Gültigkeitsbereich erfolgen. Darüber hinaus müssen alle Vorgänge für ein `structured_task_group`-Objekt im gleichen Thread ausgeführt werden. Die Ausnahme von dieser Regel wird die [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) und [is_canceling](reference/structured-task-group-class.md#is_canceling) Methoden. Eine untergeordnete Aufgabe kann diese Methoden aufrufen, um die übergeordnete Aufgabengruppe abzubrechen oder das Abbrechen jederzeit zu überprüfen.  
  
 Sie können zusätzliche Aufgaben ausführen, auf eine `task_group` Objekt nach dem Aufruf der [Concurrency:: task_group::](reference/task-group-class.md#wait) oder [run_and_wait](reference/task-group-class.md#run_and_wait) Methode. Umgekehrt, wenn Sie zusätzliche Aufgaben ausführen, auf eine `structured_task_group` Objekt nach dem Aufruf der [structured_task_group](reference/structured-task-group-class.md#wait) oder [Concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) Methoden , und klicken Sie dann das Verhalten nicht definiert ist.  
  
 Da die `structured_task_group`-Klasse nicht threadübergreifend synchronisiert, ist ihr Ausführungsaufwand im Vergleich zur `task_group`-Klasse geringer. Wenn die Planung von Arbeit für mehrere Threads nicht Teil eines Problems ist und der `parallel_invoke`-Algorithmus nicht verwendet werden kann, können Sie mit der `structured_task_group`-Klasse leistungsfähigeren Code schreiben.  
  
 Wenn Sie ein `structured_task_group`-Objekt in einem anderen `structured_task_group`-Objekt verwenden, muss das innere Objekt abgeschlossen und zerstört sein, bevor das äußere Objekt beendet wird. Bei der `task_group`-Klasse ist die Fertigstellung geschachtelter Aufgabengruppen vor der äußeren Gruppe nicht erforderlich.  
  
 Unstrukturierte Aufgabengruppen und strukturierte Aufgabengruppen verwenden Aufgabenhandles auf unterschiedliche Weise. Sie können Arbeitsfunktionen direkt an ein `task_group`-Objekt übergeben; das Aufgabenhandle wird unmittelbar vom `task_group`-Objekt für Sie erstellt und verwaltet. Die `structured_task_group`-Klasse erfordert die Verwaltung eines `task_handle`-Objekts für jede Aufgabe. Jedes `task_handle`-Objekt muss über die gesamte Lebensdauer des zugeordneten `structured_task_group`-Objekts hinweg gültig sein. Verwenden der [Concurrency:: make_task](reference/concurrency-namespace-functions.md#make_task) Funktion zum Erstellen einer `task_handle` -Objekts, wie im folgenden grundlegenden Beispiel gezeigt:  
  
 [!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]  
  
 Verwenden Sie zum Verwalten von Aufgabenhandles für Fälle, in denen eine Variable Anzahl von Aufgaben stehen Ihnen, eine stapelzuordnung Routine ein, z. B. [_malloca](../../c-runtime-library/reference/malloca.md) oder einer Containerklasse wie z. B. std::[Vektor](../../standard-library/vector-class.md).  
  
 `task_group` und `structured_task_group` unterstützen die Möglichkeit eines Abbruchs. Weitere Informationen über Abbrüche finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
##  <a name="example"></a> Beispiel  
 Im folgenden grundlegenden Beispiel wird die Verwendung von Aufgabengruppen veranschaulicht. In diesem Beispiel werden vom `parallel_invoke`-Algorithmus zwei Aufgaben gleichzeitig ausgeführt. In jeder Aufgabe werden einem `task_group`-Objekt untergeordnete Aufgaben hinzugefügt. Die `task_group`-Klasse ermöglicht das zeitgleiche Hinzufügen für mehrere Aufgaben.  
  
 [!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]  
  
 Nachfolgend wird eine Beispielausgabe für dieses Beispiel angezeigt:  
  
```Output  
Message from task: Hello  
Message from task: 3.14  
Message from task: 42  
```  
  
 Da die Aufgaben vom `parallel_invoke`-Algorithmus gleichzeitig ausgeführt werden, kann sich die Reihenfolge der Ausgabemeldungen unterscheiden.  
  
 Ausführliche Beispiele für die Funktionsweisen der `parallel_invoke` -Algorithmus finden Sie unter [Vorgehensweise: mithilfe von Parallel_invoke zum parallelen sortieren Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) und [Vorgehensweise: Parallel_invoke zum Ausführen von parallelen Vorgängen](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md). Für ein vollständiges Beispiel, verwendet der `task_group` Klasse zur Implementierung asynchroner Futures finden Sie unter [Exemplarische Vorgehensweise: Implementieren von Futures](../../parallel/concrt/walkthrough-implementing-futures.md).  
  
##  <a name="robust">Stabile Programmierung</a>  
 Es ist wichtig, dass Sie die Rolle des Abbruchs und der Ausnahmebehandlung verstehen, wenn Sie Aufgaben, Aufgabengruppen und parallele Algorithmen verwenden. Beispielweise kann eine abgebrochene Aufgabe in einer Struktur paralleler Arbeitsaufgaben dazu führen, dass untergeordnete Aufgaben nicht ausgeführt werden. Dies kann Probleme verursachen, wenn eine der untergeordneten Aufgaben einen Vorgang ausführen soll, der für die Anwendung von Bedeutung ist, beispielsweise das Freigeben einer Ressource. Wenn eine untergeordnete Aufgabe eine Ausnahme auslöst, kann diese Ausnahme außerdem über einen Objektdestruktor weitergeben werden und nicht definiertes Verhalten in der Anwendung auslösen. Ein Beispiel, in dem diese Punkte veranschaulicht, finden Sie die [verstehen wie Abbruch und Behandlung von Auswirkungen auf die Zerstörung](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) Abschnitt in der empfohlenen Vorgehensweisen im Dokument zur Parallel Patterns Library. Weitere Informationen über die Abbruchs- und ausnahmeverarbeitungsmodelle in der PPL finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md) und [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Vorgehensweise: Verwenden von parallel_invoke zum Schreiben einer Runtime für paralleles Sortieren](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Erläutert, wie die Leistung des bitonischen Sortieralgorithmus mit dem `parallel_invoke`-Algorithmus verbessert werden.|  
|[Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von parallel_invoke](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Erläutert, wie die Leistung eines Programms mit dem `parallel_invoke`-Algorithmus verbessert werden kann, das mehrere Vorgänge in einer freigegebenen Datenquelle ausführt.|  
|[Vorgehensweise: Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Zeigt, wie die `task`, `cancellation_token_source`, `cancellation_token`, und `task_completion_event` Klassen, die eine Aufgabe zu erstellen, die nach einer Verzögerung abgeschlossen wird.|  
|[Exemplarische Vorgehensweise: Implementieren von Futures](../../parallel/concrt/walkthrough-implementing-futures.md)|Zeigt, wie die vorhandene Funktionalität in der Concurrency Runtime kombiniert werden kann, um mehr Funktionalität zu erreichen.|  
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt die PPL, die ein obligatorisches Programmiermodell zum Entwickeln gleichzeitiger Anwendungen bereitstellt.|  
  
## <a name="reference"></a>Referenz  
 [task-Klasse (Concurrency Runtime)](../../parallel/concrt/reference/task-class.md)  
  
 [task_completion_event-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)  

 [Funktion "when_all"](reference/concurrency-namespace-functions.md#when_all)  
  
 [Funktion "when_any"](reference/concurrency-namespace-functions.md#when_any)  
  
 [Task_group-Klasse](reference/task-group-class.md)  
  
 [Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)  
  
 [structured_task_group-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)
