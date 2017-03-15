---
title: "Erstellen von asynchronen Vorg&#228;ngen in C++ f&#252;r Windows Store-Apps"
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
  - "Windows Store-Apps, Erstellung asynchroner Vorgänge in C++"
  - "Erstellung asynchroner Vorgänge in C++"
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
caps.latest.revision: 31
caps.handback.revision: "30"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von asynchronen Vorg&#228;ngen in C++ f&#252;r Windows Store-Apps
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument werden einige der wichtigsten zu berücksichtigenden Punkte für das Verwenden der task\-Klasse für Windows\-ThreadPool\-basierte asynchrone Vorgänge in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App beschrieben.  
  
 Bei der asynchronen Programmierung handelt es sich um eine Schlüsselkomponente des [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App\-Modells, da Apps auf diese Weise stets auf Benutzereingaben reaktionsfähig bleiben. Sie können eine lang dauernde Aufgabe starten, ohne den Benutzeroberflächenthread zu blockieren, und die Ergebnisse der Aufgabe später empfangen. Sie können Aufgaben auch abbrechen und Statusbenachrichtigungen beim Ausführen von Aufgaben im Hintergrund erhalten. Im Dokument [Asynchrone Programmierung in C\+\+](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx) finden Sie eine Übersicht der asynchronen Muster, die in Visual C\+\+ zum Erstellen von [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps zur Verfügung stehen. In diesem Dokument wird sowohl das Nutzen als auch das Erstellen von Ketten asynchroner [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Vorgänge erläutert. In diesem Abschnitt wird beschrieben, wie mit den Typen in ppltasks.h von einer anderen [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Komponente nutzbare asynchrone Vorgänge erstellt und wie die Ausführung asynchroner Arbeit gesteuert werden kann. Außerdem können Sie sich unter [Muster und Tipps für die asynchrone Programmierung in Hilo \(Windows Store\-Apps mit C\+\+ und XAML\)](http://msdn.microsoft.com/library/windows/apps/jj160321.aspx) darüber informieren, wie mit der Task\-Klasse asynchrone Vorgänge in Hilo implementiert wurden, einer auf C\+\+ und XAML beruhenden [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App.  
  
> [!NOTE]
>  Sie können die [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) und [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App verwendet. Aufgabenplaner oder Ressourcen\-Manager können jedoch nicht verwendet werden. In diesem Dokument werden zusätzliche von der PPL bereitgestellte Funktionen beschrieben, die nur für die [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App und nicht für die Desktop\-App verfügbar sind.  
  
## Wesentliche Punkte  
  
-   Erstellen Sie mithilfe von [concurrency::create\_async](../Topic/create_async%20Function.md) asynchrone Vorgänge, die von anderen Komponenten genutzt werden können \(die möglicherweise in einer anderen Sprache als C\+\+ geschrieben sind\).  
  
-   Verwenden Sie [concurrency::progress\_reporter](../../parallel/concrt/reference/progress-reporter-class.md) zum Übermitteln von Statusbenachrichtigungen an Komponenten, von denen die asynchronen Vorgänge aufgerufen werden.  
  
-   Mithilfe von Abbruchtoken können interne asynchrone Vorgänge abgebrochen werden.  
  
-   Das Verhalten der `create_async`\-Funktion hängt vom Rückgabetyp der daran übergebenen Arbeitsfunktion ab. Eine Arbeitsfunktion, die eine Aufgabe zurückgibt \(entweder `task<T>` oder `task<void>`\) oder synchron in dem Kontext ausgeführt wird, in dem `create_async` aufgerufen wurde. Eine Arbeitsfunktion, die `T` oder `void` zurückgibt, wird in einem die oft ausgegebene Befehlszeilen  Kontext ausgeführt.  
  
-   Mithilfe der [concurrency::task::then](../Topic/task::then%20Method.md)\-Methode können Sie eine Kette von Aufgaben erstellen, die nacheinander ausgeführt werden. In einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App hängt der Standardkontext für die Fortsetzungen einer Aufgabe davon ab, wie diese Aufgabe erstellt wurde. Wenn die Aufgabe durch Übergabe einer asynchronen Aktion an den Aufgabenkonstruktor oder durch Übergabe eines Lambda\-Ausdrucks erstellt wurde, der eine asynchrone Aktion zurückgibt, handelt es sich beim Standardkontext für alle Fortsetzungen dieser Aufgabe um den aktuellen Kontext. Wenn die Aufgabe nicht durch eine asynchrone Aktion erstellt wird, wird für die Fortsetzungen der Aufgabe standardmäßig ein beliebiger Kontext verwendet. Sie können den Standardkontext mit der [concurrency::task\_continuation\_context](../../parallel/concrt/reference/task-continuation-context-class.md)\-Klasse überschreiben.  
  
## Inhalt dieses Dokuments  
  
-   [Erstellen von asynchronen Operationen](#create-async)  
  
-   [Beispiel: Erstellen einer C\+\+\-Komponente für Windows\-Runtime](#example-component)  
  
-   [Steuern des Ausführungs\-Threads](#exethread)  
  
-   [Beispiel: Steuern der Ausführung in einer Windows Store\-App mit C\+\+ und XAML](#example-app)  
  
##  <a name="create-async"></a> Erstellen von asynchronen Operationen  
 Sie können das Aufgaben\- und Fortsetzungsmodell in der Parallel Patterns Library \(PPL\) verwenden, um Hintergrundaufgaben sowie zusätzliche Aufgaben zu definieren, die nach Abschluss der vorherigen Aufgabe ausgeführt werden sollen. Diese Funktionalität wird von der [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md)\-Klasse bereitgestellt. Weitere Informationen zu diesem Modell und der `task`\-Klasse finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Mit der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Programmierschnittstelle können Sie [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps erstellen, die nur in einer bestimmten Betriebssystemumgebung ausgeführt werden. Solche Apps verwenden autorisierte Funktionen, Datentypen und Geräte und werden über den [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] vertrieben.[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] wird durch die *ABI \(Application Binary Interface\)* dargestellt. Die ABI ist ein zugrunde liegender binärer Vertrag, der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-APIs für Programmiersprachen wie Visual C\+\+ verfügbar macht.  
  
 Mithilfe von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] können Sie die besten Funktionen verschiedener Programmiersprachen verwenden und in einer App kombinieren. Beispielsweise können Sie die Benutzeroberfläche in JavaScript erstellen und die rechenintensive App\-Logik in einer C\+\+\-Komponente ausführen. Die Fähigkeit, diese rechenintensiven Vorgänge im Hintergrund auszuführen, ist ein Schlüsselfaktor dafür, die Benutzeroberfläche reaktionsfähig zu halten. Da die `task`\-Klasse C\+\+\-spezifisch ist, müssen Sie eine [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Schnittstelle verwenden, um asynchrone Vorgänge an andere Komponenten zu übergeben \(die möglicherweise in anderen Sprachen als C\+\+ geschrieben sind\).[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] stellt vier Schnittstellen zum Darstellen von asynchronen Vorgängen bereit:  
  
 [Windows::Foundation::IAsyncAction](http://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncaction.aspx)  
 Stellt eine asynchrone Aktion dar.  
  
 [Windows::Foundation::IAsyncActionWithProgress\<TProgress\>](http://msdn.microsoft.com/library/windows/apps/br206581.aspx)  
 Stellt eine asynchrone Aktion für Statusbenachrichtigungen dar.  
  
 [Windows::Foundation::IAsyncOperation\<TResult\>](http://msdn.microsoft.com/library/windows/apps/br206598.aspx)  
 Stellt einen asynchronen Vorgang dar, der ein Ergebnis zurückgibt.  
  
 [Windows::Foundation::IAsyncOperationWithProgress\<TResult, TProgress\>](http://msdn.microsoft.com/library/windows/apps/br206594.aspx)  
 Stellt einen asynchronen Vorgang dar, der ein Ergebnis zurückgibt und den Status meldet.  
  
 Der Begriff *Aktion* bedeutet, dass die asynchrone Aufgabe keinen Wert generiert \(denken Sie an eine Funktion, die `void` zurückgibt\). Der Begriff *Vorgang* bedeutet, dass die asynchrone Aufgabe einen Wert generiert. Der Begriff *Status* bedeutet, dass die Aufgabe Statusbenachrichtigungen an den Aufrufer übermitteln kann. JavaScript, .NET Framework und Visual C\+\+ bieten jeweils eine eigene Möglichkeit zum Erstellen von Instanzen dieser Schnittstellen zur ABI\-übergreifenden Verwendung. Für Visual C\+\+ stellt die PPL die [concurrency::create\_async](../Topic/create_async%20Function.md)\-Funktion bereit. Von dieser Funktion wird eine asynchrone [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Aktion oder ein entsprechender Vorgang zum Darstellen des Abschlusses einer Aufgabe erstellt. Die `create_async`\-Funktion akzeptiert eine Arbeitsfunktion \(in der Regel einen Lambda\-Ausdruck\), erstellt intern ein `task`\-Objekt und umschließt diese Aufgabe mit einer der vier asynchronen [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Schnittstellen.  
  
> [!NOTE]
>  Verwenden Sie `create_async` nur, wenn Sie Funktionalität erstellen müssen, auf die von einer anderen Sprache oder einer anderen [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Komponente zugegriffen werden kann. Verwenden Sie die `task`\-Klasse direkt, wenn Sie wissen, dass der Vorgang von C\+\+\-Code in der gleichen Komponente sowohl erstellt als auch genutzt wird.  
  
 Der Rückgabetyp von `create_async` wird durch den Typ der Argumente bestimmt. Wenn z. B. die Arbeitsfunktion weder einen Wert zurückgibt und noch den Status meldet, wird von `create_async` eine `IAsyncAction` zurückgegeben. Wenn die Arbeitsfunktion keinen Wert zurückgibt, jedoch den Status meldet, wird von `create_async` eine `IAsyncActionWithProgress` zurückgegeben. Stellen Sie für Statusmeldungen ein [concurrency::progress\_reporter](../../parallel/concrt/reference/progress-reporter-class.md)\-Objekt als Parameter der Arbeitsfunktion bereit. Durch Statusbenachrichtigungen kann gemeldet werden, wie viel Arbeit bereits erledigt wurde und wie viel noch verbleibt \(beispielsweise als Prozentsatz\). Zudem können Ergebnisse gemeldet werden, sobald sie verfügbar sind.  
  
 Die `IAsyncAction`\-, `IAsyncActionWithProgress<TProgress>`\-, `IAsyncOperation<TResult>`\- und `IAsyncActionOperationWithProgress<TProgress, TProgress>`\-Schnittstellen bieten jeweils eine `Cancel`\-Methode, die das Abbrechen des asynchronen Vorgangs ermöglicht. Die `task`\-Klasse verwendet Abbruchtoken. Wenn Sie Arbeit mithilfe eines Abbruchtokens abbrechen, wird von der Runtime keine neue Verarbeitung gestartet, die dieses Token abonniert. Für eine bereits aktive Verarbeitung kann das entsprechende Abbruchtoken überwacht und die Verarbeitung zum angegebenen Zeitpunkt beendet werden. Im Dokument [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md) wird dieser Mechanismus ausführlich beschrieben. Es gibt zwei Möglichkeiten, den Aufgabenabbruch mit den `Cancel`\-Methoden von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] zu verbinden. Die erste Möglichkeit besteht darin, die an `create_async` zu übergebende Arbeitsfunktion so zu definieren, dass diese ein [concurrency::cancellation\_token](cancellation_token)\-Objekt akzeptiert. Beim Aufrufen der `Cancel`\-Methode wird dieses Abbruchtoken abgebrochen, und für das zugrunde liegende `task`\-Objekt, das den `create_async`\-Aufruf unterstützt, gelten die normale Abbruchregeln. Wenn Sie kein `cancellation_token`\-Objekt bereitstellen, wird dieses vom zugrunde liegenden `task`\-Objekt implizit definiert. Definieren Sie ein `cancellation_token`\-Objekt, wenn auf Abbrüche in der Arbeitsfunktion kooperativ reagiert werden muss. Im Abschnitt [Beispiel: Steuern der Ausführung in einer Windows Store\-App mit C\+\+ und XAML](#example-app) finden Sie ein Beispiel für das Ausführen von Abbrüchen in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App mit C\# und XAML, in der eine benutzerdefinierte [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Komponente in C\+\+ verwendet wird.  
  
> [!WARNING]
>  In einer Kette von Aufgabenfortsetzungen sollte stets der Zustand bereinigt und anschließend [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md) aufgerufen werden, wenn das Abbruchtoken abgebrochen wird. Wenn Sie frühzeitig zurückkehren, anstatt `cancel_current_task` aufzurufen, geht der Vorgang in den Zustand "Abgeschlossen" anstelle von "Abgebrochen" über.  
  
 In der folgenden Tabelle werden die Kombinationen zusammengefasst, die Sie zum Definieren asynchroner Vorgänge in Ihrer App verwenden können.  
  
|Zu erstellende [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Schnittstelle|Rückgabe dieses `create_async`\-Typs|Übergabe dieser Parametertypen an die Arbeitsfunktion zur Verwendung als implizites Abbruchtoken|Übergabe dieser Parametertypen an die Arbeitsfunktion zur Verwendung als explizites Abbruchtoken|  
|---------------------------------------------------------------------------------------|------------------------------------------|------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|  
|`IAsyncAction`|`void` oder `task<void>`|\(keine\)|\(`cancellation_token`\)|  
|`IAsyncActionWithProgress<TProgress>`|`void` oder `task<void>`|\(`progress_reporter`\)|\(`progress_reporter`, `cancellation_token`\)|  
|`IAsyncOperation<TResult>`|`T` oder `task<T>`|\(keine\)|\(`cancellation_token`\)|  
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` oder `task<T>`|\(`progress_reporter`\)|\(`progress_reporter`, `cancellation_token`\)|  
  
 Bei der Rückgabe kann es sich um einen Wert oder ein `task`\-Objekt handeln, dass von der an die `create_async`\-Funktion übergebenen Arbeitsfunktion zurückgeben wird. Diese Unterschiede führen zu verschiedenen Verhalten. Bei Rückgabe eines Werts wird die Arbeitsfunktion zur Ausführung auf einem Hintergrundthread mit `task` umschlossen. Zudem wird von der zugrunde liegenden `task` ein implizites Abbruchtoken verwendet. Umgekehrt wird die Arbeitsfunktion bei Rückgabe eines `task`\-Objekts synchron ausgeführt. Stellen Sie daher beim Zurückgeben eines `task`\-Objekts sicher, dass alle längeren Vorgänge in der Arbeitsfunktion auch als Aufgaben ausgeführt werden, damit die App reaktionsfähig bleiben kann. Zudem wird von der zugrunde liegenden `task` kein implizites Abbruchtoken verwendet. Daher müssen Sie die Arbeitsfunktion so definieren, dass diese ein `cancellation_token`\-Objekt akzeptiert, falls bei der Rückgabe eines `task`\-Objekts durch `create_async` Abbruchunterstützung erforderlich ist.  
  
 Im folgenden Beispiel werden die verschiedenen Möglichkeiten zum Erstellen eines `IAsyncAction`\-Objekts dargestellt, das von einer anderen [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Komponente genutzt werden kann.  
  
 [!CODE [concrt-windowsstore-primes#100](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-primes#100)]  
  
##  <a name="example-component"></a> Beispiel: Erstellen einer C\+\+ Windows\-Runtime\-Komponente und ihre Verwendung von C\# aus  
 Betrachten Sie eine App, in der XAML und C\# zum Definieren der Benutzeroberfläche und eine C\+\+ [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Komponente zum Ausführen rechenintensiver Vorgänge verwendet werden. In diesem Beispiel wird von der C\+\+\-Komponente berechnet, bei welchen Zahlen in einem angegebenen Bereich es sich um Primzahlen handelt. Erstellen Sie zunächst in Visual Studio eine **Leere Projektmappe** mit dem Namen `Primes`, um die Unterschiede zwischen den vier asynchronen [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]\-Aufgabenschnittstellen zu veranschaulichen. Fügen Sie der Projektmappe dann ein Projekt für **Windows\-Runtime\-Komponente** hinzu, und nennen Sie es `PrimesLibrary`. Fügen Sie der generierten C\+\+\-Headerdatei folgenden Code hinzu \(in diesem Beispiel wird "Class1.h" in "Primes.h" umbenannt\). Jede `public`\-Methode definiert eine der vier asynchronen Schnittstellen. Die einen Wert zurückgebenden Methoden geben ein [Windows::Foundation::Collections::IVector\<int\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx)\-Objekt zurück. Die den Status meldenden Methoden generieren `double`\-Werte, die den Prozentsatz der abgeschlossenen Gesamtarbeit definieren.  
  
 [!CODE [concrt-windowsstore-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-primes#1)]  
  
> [!NOTE]
>  Konventionsgemäß enden die Namen asynchroner Methoden in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] in der Regel mit "Async".  
  
 Fügen Sie der generierten C\+\+\-Quelldatei folgenden Code hinzu \(in diesem Beispiel wird "Class1.cpp" in "Primes.cpp" umbenannt\). Mit der `is_prime`\-Funktion wird ermittelt, ob es sich bei der Eingabe um eine Primzahl handelt. Mit den verbleibenden Methoden wird die `Primes`\-Klasse implementiert. Für jeden Aufruf von `create_async` wird eine mit der aufrufenden Methode kompatible Signatur verwendet. Da von `Primes::ComputePrimesAsync` beispielsweise `IAsyncAction` zurückgegeben wird, gibt die für `create_async` bereitgestellte Arbeitsfunktion keinen Wert zurück und akzeptiert kein `progress_reporter`\-Objekt als Parameter.  
  
 [!CODE [concrt-windowsstore-primes#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-primes#2)]  
  
 Jede Methode führt zuerst eine Validierung aus, um sicherzustellen, dass die Eingabeparameter nicht negativ sind. Im Fall eines negativen Eingabewerts wird von der Methode [Platform::InvalidArgumentException](http://msdn.microsoft.com/library/windows/apps/hh755794\(v=vs.110\).aspx) ausgelöst. Die Fehlerbehandlung wird weiter unten in diesem Abschnitt erläutert.  
  
 Um diese Methoden in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App zu nutzen, fügen Sie der Visual Studio\-Projektmappe mithilfe der Visual C\#\-Vorlage **Leere App \(XAML\)** ein zweites Projekt hinzu. In diesem Beispiel wird das Projekt `Primes` genannt. Fügen Sie anschließend im Projekt `Primes` einen Verweis auf das Projekt `PrimesLibrary` hinzu.  
  
 Fügen Sie "MainPage.xaml" den folgenden Code hinzu. Durch diesen Code wird die Benutzeroberfläche definiert, damit Sie die C\+\+\-Komponente aufrufen und Ergebnisse anzeigen können.  
  
 [!CODE [concrt-windowsstore-primes#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-primes#3)]  
  
 Fügen Sie der `MainPage`\-Klasse in "MainPage.xaml" den folgenden Code hinzu. Durch diesen Code werden ein `Primes`\-Objekt und die Ereignishandler für Schaltflächen definiert.  
  
 [!CODE [concrt-windowsstore-primes#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-primes#4)]  
  
 Von diesen Methoden wird mithilfe des `async`\-Schlüsselworts und des `await`\-Schlüsselworts die Benutzeroberfläche aktualisiert, nachdem die asynchronen Vorgänge abgeschlossen wurden. Weitere Informationen zu den in C\# und Visual Basic verfügbaren asynchronen Mustern finden Sie unter [Asynchrone Programmierung \(Windows Store\-Apps\) mit C\#](http://msdn.microsoft.com/library/windows/apps/hh464924.aspx) und [Asynchrone Programmierung \(Windows Store\-Apps\) mit VB](http://msdn.microsoft.com/library/windows/apps/hh464924.aspx).  
  
 Die `getPrimesCancellation`\-Methode und die `cancelGetPrimes`\-Methode werden zusammen verwendet, damit der Benutzer den Vorgang abbrechen kann. Wenn der Benutzer die Schaltfläche **Abbrechen** auswählt, wird von der `cancelGetPrimes`\-Methode [IAsyncOperationWithProgress\<TResult, TProgress\>::Cancel](http://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncinfo.cancel.aspx) aufgerufen, um den Vorgang abzubrechen. Von der Concurrency Runtime, die den zugrunde liegenden asynchronen Vorgang verwaltet, wird ein interner Ausnahmetyp ausgelöst, der von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] abgefangen wird, um den Abschluss des Abbrechens zu melden. Weitere Informationen zum Abbruchmodell finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
> [!IMPORTANT]
>  Damit von der PPL das Abbrechen des Vorgangs ordnungsgemäß an [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] gemeldet werden kann, fangen Sie diesen internen Ausnahmetyp nicht ab. Dies bedeutet auch, dass nicht alle Ausnahmen abgefangen werden sollten\(`catch (...)`\). Wenn alle Ausnahmen abfangen werden müssen, lösen Sie die Ausnahme erneut aus, um sicherzustellen, dass der Abbruchvorgang von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] abgeschlossen werden kann.  
  
 In der folgenden Abbildung wird die `Primes`\-App nach Auswahl aller Optionen dargestellt.  
  
 ![Windows Store&#45;Primes&#45;App](../../parallel/concrt/media/concrt_windows_primes.png "ConcRT\_windows\_Primes")  
  
 Beispiele für das Verwenden von `create_async` zum Erstellen asynchroner Aufgaben, die von anderen Sprachen genutzt werden können, finden Sie unter [Verwenden von C\+\+ im Beispiel zum Reise\-Optimierer von Bing Maps](http://msdn.microsoft.com/library/windows/apps/hh699891\(v=vs.110\).aspx) und [Windows 8 Asynchronous Operations in C\+\+ with PPL](http://code.msdn.microsoft.com/windowsapps/Windows-8-Asynchronous-08009a0d) \(Asynchrone Vorgänge unter Windows 8 in C\+\+ mit PPL\).  
  
##  <a name="exethread"></a> Steuern des Ausführungs\-Threads  
 Von [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] wird das COM\-Threadmodell verwendet. In diesem Modell werden Objekte in unterschiedlichen Apartments gehostet, abhängig von der jeweiligen Synchronisierungsmethode. Threadsichere Objekte werden im Multithread\-Apartment \(MTA\) gehostet. Objekte, auf die von einem einzelnen Thread zugegriffen werden muss, werden in einem Singlethread\-Apartment \(STA\) gehostet.  
  
 In einer App mit Benutzeroberfläche ist der ASTA \(Application STA\)\-Thread für das Verschieben von Fenstermeldungen zuständig und ist der einzige Thread im Prozess, von dem die STA\-gehosteten UI\-Steuerelemente aktualisiert werden können. Dies hat zwei Auswirkungen. Erstens sollten alle CPU\-intensiven und E\/A\-Vorgänge nicht im ASTA\-Thread ausgeführt werden, damit die App reaktionsfähig bleibt. Zweitens müssen von Hintergrundthreads stammende Ergebnisse zurück in das ASTA gemarshallt werden, um die Benutzeroberfläche zu aktualisieren. In einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App mit C\+\+ werden `MainPage` und alle anderen XAML\-Seiten im ASTA ausgeführt. Daher werden im ASTA deklarierte Aufgabenfortsetzungen standardmäßig dort ausgeführt, sodass Steuerelemente direkt im Fortsetzungstext aktualisiert werden können. Wenn Sie jedoch eine Aufgabe in einer anderen Aufgabe schachteln, werden alle Fortsetzungen dieser geschachtelten Aufgabe im MTA ausgeführt. Daher sollten Sie berücksichtigen, ob der Ausführungskontext dieser Fortsetzungen explizit angegeben werden muss.  
  
 Dank einer besonderen Semantik können die Threaddetails bei durch einen asynchronen Vorgang wie `IAsyncOperation<TResult>` erstellten Aufgaben ignoriert werden. Obwohl ein Vorgang möglicherweise in einem Hintergrundthread ausgeführt wird \(oder überhaupt nicht von einem Thread unterstützt wird\), erfolgen dessen Fortsetzungen in jedem Fall standardmäßig in dem Apartment, von dem die Fortsetzungsvorgänge gestartet wurden \(d. h. im Apartment, von dem `task::then` aufgerufen wurde\). Mithilfe der [concurrency::task\_continuation\_context](../../parallel/concrt/reference/task-continuation-context-class.md)\-Klasse kann der Ausführungskontext einer Fortsetzung gesteuert werden. Verwenden Sie zum Erstellen von `task_continuation_context`\-Objekten die folgenden statischen Hilfsmethoden:  
  
-   Mithilfe von [concurrency::task\_continuation\_context::use\_arbitrary](../Topic/task_continuation_context::use_arbitrary%20Method.md) geben Sie an, dass die Fortsetzung in einem Hintergrundthread ausgeführt wird.  
  
-   Mithilfe von [concurrency::task\_continuation\_context::use\_current](../Topic/task_continuation_context::use_current%20Method.md) geben Sie an, dass die Fortsetzung in dem Thread ausgeführt wird, von dem `task::then` aufgerufen wurde.  
  
 Sie können der [task::then](../Topic/task::then%20Method.md)\-Methode ein `task_continuation_context`\-Objekt übergeben, um den Ausführungskontext der Fortsetzung explizit zu steuern. Alternativ können Sie die Aufgabe an ein anderes Apartment übergeben und dann die `task::then`\-Methode aufrufen, um den Ausführungskontext implizit zu steuern.  
  
> [!IMPORTANT]
>  Da der Haupt\-UI\-Thread von [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps im STA ausgeführt wird, werden in diesem STA erstellte Fortsetzungen standardmäßig ebenfalls im STA ausgeführt. Entsprechend werden im MTA erstellte Fortsetzungen auch im MTA ausgeführt.  
  
 Im folgenden Abschnitt wird eine App dargestellt, die eine Datei auf dem Datenträger liest, die häufigsten Wörter in dieser Datei sucht und die Ergebnisse anschließend auf der Benutzeroberfläche anzeigt. Der letzte Vorgang \(die Aktualisierung der Benutzeroberfläche\) erfolgt im UI\-Thread.  
  
> [!IMPORTANT]
>  Dieses Verhalten ist für [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps spezifisch. Bei Desktop\-Apps wird die Ausführung von Fortsetzungen nicht von Ihnen gesteuert. Stattdessen wird vom Planer ein Arbeitsthread zur Ausführung der einzelnen Fortsetzungen ausgewählt.  
  
> [!IMPORTANT]
>  Rufen Sie nicht [concurrency::task::wait](../Topic/task::wait%20Method.md) im Text einer Fortsetzung auf, die im STA ausgeführt wird. Andernfalls löst die Laufzeit [concurrency::invalid\_operation](../../parallel/concrt/reference/invalid-operation-class.md) aus, da diese Methode den aktuellen Thread blockiert und die App dadurch möglicherweise nicht mehr reagiert. Sie können jedoch die [concurrency::task::get](../Topic/task::get%20Method.md)\-Methode aufrufen, um das Ergebnis der Vorgängeraufgabe in einer aufgabenbasierten Fortsetzung zu erhalten.  
  
##  <a name="example-app"></a> Beispiel: Steuern der Ausführung in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App mit C\+\+ und XAML  
 Betrachten Sie eine App mit C\+\+ und XAML, die eine Datei auf dem Datenträger liest, die häufigsten Wörter in dieser Datei sucht und die Ergebnisse anschließend auf der Benutzeroberfläche anzeigt. Erstellen Sie in Visual Studio zunächst mithilfe der Vorlage [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]**Leere App \(XAML\)** ein Projekt, und nennen Sie dieses `CommonWords`, um die App zu erstellen. Geben Sie im App\-Manifest die **Dokumentbibliothek**\-Funktion an, damit die App auf den Ordner "Dokumente" zugreifen kann. Fügen Sie im Deklarationsabschnitt des App\-Manifests außerdem den Textdateityp \(.txt\) hinzu. Weitere Informationen zu App\-Funktionen und \-Deklarationen finden Sie unter [App\-Pakete und \-Bereitstellung](http://msdn.microsoft.com/library/windows/apps/hh464929.aspx).  
  
 Aktualisieren Sie in "MainPage.xaml" das `Grid`\-Element mit einem `ProgressRing`\-Element und einem `TextBlock`\-Element.`ProgressRing` gibt an, dass der Vorgang ausgeführt wird, und `TextBlock` zeigt die Ergebnisse der Berechnung an.  
  
 [!CODE [concrt-windowsstore-commonwords#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#1)]  
  
 Fügen Sie "pch.h" die folgenden `#include`\-Anweisungen hinzu.  
  
 [!CODE [concrt-windowsstore-commonwords#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#2)]  
  
 Fügen Sie der `MainPage`\-Klasse \("MainPage.h"\) die folgenden Methodendeklarationen hinzu.  
  
 [!CODE [concrt-windowsstore-commonwords#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#3)]  
  
 Fügen Sie "MainPage.cpp" die folgenden `using`\-Anweisungen hinzu.  
  
 [!CODE [concrt-windowsstore-commonwords#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#4)]  
  
 Implementieren Sie in "MainPage.cpp" die Methoden `MainPage::MakeWordList`, `MainPage::FindCommonWords` und `MainPage::ShowResults`. Von `MainPage::MakeWordList` und `MainPage::FindCommonWords` werden rechenintensive Vorgänge ausgeführt. Von der `MainPage::ShowResults`\-Methode wird das Ergebnis der Berechnung auf der Benutzeroberfläche angezeigt.  
  
 [!CODE [concrt-windowsstore-commonwords#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#5)]  
  
 Ändern Sie den `MainPage`\-Konstruktor, um eine Kette von Fortsetzungsaufgaben zu erstellen, von denen häufige Wörter im Buch *Die Ilias* von Homer auf der Benutzeroberfläche angezeigt werden. Die ersten beiden Fortsetzungsaufgaben, von denen der Text in einzelne Wörter unterteilt und nach häufigen Wörtern durchsucht wird, können zeitaufwändig sein. Daher wird für diese Aufgaben explizit die Ausführung im Hintergrund festgelegt. Für die letzte Fortsetzungsaufgabe zur Aktualisierung der Benutzeroberfläche wird kein Fortsetzungskontext angegeben, weshalb hierbei die Apartmentthreadregeln befolgt werden.  
  
 [!CODE [concrt-windowsstore-commonwords#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-windowsstore-commonwords#6)]  
  
> [!NOTE]
>  In diesem Beispiel wird das Angeben eines Ausführungskontexts und Zusammenstellen einer Kette von Fortsetzungen veranschaulicht. Denken Sie daran, dass die Fortsetzungen einer durch einen asynchronen Vorgang erstellten Aufgabe standardmäßig in dem Apartment ausgeführt werden, von dem `task::then` aufgerufen wurde. In diesem Beispiel wird daher durch `task_continuation_context::use_arbitrary` angegeben, dass Vorgänge, die nicht die Benutzeroberfläche betreffen, in einem Hintergrundthread ausgeführt werden.  
  
 In der folgenden Abbildung werden die Ergebnisse der `CommonWords`\-App dargestellt.  
  
 ![Windows Store&#45;CommonWords&#45;App](../../parallel/concrt/media/concrt_windows_common_words.png "ConcRT\_windows\_Common\_Words")  
  
 In diesem Beispiel werden Abbruchvorgänge unterstützt, da die `task`\-Objekte zur Unterstützung von `create_async` ein implizites Abbruchtoken verwenden. Wenn die Aufgaben kooperativ auf Abbruchvorgänge reagieren sollen, definieren Sie die Arbeitsfunktion so, dass diese ein `cancellation_token`\-Objekt akzeptiert. Weitere Informationen zum Abbrechen in der PPL finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
## Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)