---
title: 'Exemplarische Vorgehensweise: Erstellen Sie und verwenden Sie Ihren eigenen Dynamic Link Library (C++)'
ms.custom: conceptual
ms.date: 09/24/2018
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: fb77230d5cc27c1fba1f7df1404150fada36d43a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416448"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>Exemplarische Vorgehensweise: Erstellen Sie und verwenden Sie Ihren eigenen Dynamic Link Library (C++)

Diese exemplarische Vorgehensweise veranschaulicht, verwenden Visual Studio-IDE zum Erstellen eigener dynamic Link Library (DLL) in C++ geschrieben wurden, und klicken Sie dann in einer anderen C++-app verwenden. DLLs sind eines der nützlichsten der Windows-Komponenten. Sie können sie als eine Methode zur Freigabe von Code und Ressourcen verwenden, um verkleinern Sie Ihre apps und service, und erweitern Ihre apps zu erleichtern. In dieser exemplarischen Vorgehensweise erstellen Sie eine DLL, die einige mathematische Funktionen implementiert, und klicken Sie dann erstellen Sie eine Konsolen-app, die die Funktionen aus der DLL verwendet. Dabei erhalten Sie eine Einführung in einige der Techniken und Programmierung Konventionen in der Windows-DLLs.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- Erstellen Sie ein DLL-Projekt in Visual Studio.

- Fügen Sie mit der DLL exportierten Funktionen und Variablen hinzu.

- Erstellen Sie ein Konsolenanwendungsprojekt in Visual Studio.

- Verwenden Sie die Funktionen und Variablen, die aus der DLL in die Konsolen-app importiert.

- Führen Sie die fertige app.

Wie Sie eine statisch verknüpfte Bibliothek, eine DLL _exportiert_ Variablen, Funktionen und Ressourcen nach Namen und Ihre app _importiert_ diesen Namen verwenden Sie diese Variablen, Funktionen und Ressourcen. Im Gegensatz zu einer statisch verknüpften Bibliothek Windows die Importe in Ihrer app eine Verbindung mit her die Exporte in einer DLL zur Ladezeit oder zur Laufzeit statt zum Zeitpunkt der Verknüpfung verbinden. Windows ist zusätzlichen Informationen, der Teil des Modells, standard C++ Kompilierung dieser Verbindungen ist nicht erforderlich. Visual C++-Compiler implementiert einige Microsoft-spezifische Erweiterungen für C++, um diese zusätzlichen Informationen bereitzustellen. Diese Erweiterungen wird erläutert, wie wir wechseln.

In dieser exemplarischen Vorgehensweise erstellt zwei Visual Studio-Projektmappen. eine, die die DLL erstellt, und eine, die die Client-app erstellt. Die DLL verwendet der C-Aufrufkonvention, damit sie kann, von apps aufgerufen werden mithilfe von anderen Sprachen erstellt werden, solange der Plattform und das Aufrufen und Verknüpfen von Konventionen übereinstimmen. Der Client-app verwendet _implizite Verknüpfung_, wobei Windows die app auf die DLL zur Ladezeit verknüpft ist. Diese Verknüpfung können die app, die die bereitgestellte DLL-Funktionen wie die Funktionen in einer statisch verknüpften Bibliothek aufrufen.

In dieser exemplarischen Vorgehensweise behandelt nicht allgemeinen Situationen. Die Verwendung von C++-DLLs von anderen Programmiersprachen nicht angezeigt. Es erläutert nicht zum Erstellen einer reinen Ressourcen DLL. Es zeigt auch nicht die Verwendung der expliziten Verknüpfung zum Laden von DLLs zur Laufzeit anstatt zur Ladezeit an. Das beruhigende Gefühl, Visual C++ können Sie all diese Aufgaben können. Links zu weiteren Informationen über DLLs finden Sie [-DLLs in Visual C++](../build/dlls-in-visual-cpp.md). Weitere Informationen über implizite Verknüpfen und explizites verknüpfen, finden Sie unter [Bestimmen der geeigneten Verknüpfungsmethode](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). Weitere Informationen zum Erstellen von C++-DLLs für die Verwendung mit Programmiersprachen zu vergleichen, die Konventionen der Programmiersprache C-Verknüpfung verwenden, finden Sie unter [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md). Weitere Informationen zum Erstellen von DLLs für die Verwendung mit Sprachen für .NET finden Sie unter [Aufrufen von DLL-Funktionen von Visual Basic-Anwendungen](../build/calling-dll-functions-from-visual-basic-applications.md).

In dieser exemplarischen Vorgehensweise wird Visual Studio 2017 verwendet, aber der Code und die meisten Anweisungen gelten für frühere Versionen. Die Schritte zum Erstellen von neuer Projekten geändert in Visual Studio 2017 Version 15.3 ab. In dieser exemplarischen Vorgehensweise wird beschrieben, wie zum Erstellen von Projekten für neuere und ältere Versionen. Suchen Sie nach den Schritten, die der Visual Studio-Version entsprechen.

## <a name="prerequisites"></a>Vorraussetzungen

- Ein Computer, der Microsoft Windows 7 oder höher ausgeführt wird. Wir empfehlen die Windows 10, für die bestmögliche entwicklungserfahrung.

- Eine Kopie von Visual Studio 2017. Informationen zum Herunterladen und installieren Sie Visual Studio finden Sie unter [Installieren von Visual Studio 2017](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen sicher, dass die **Desktopentwicklung mit C++** arbeitsauslastung aktiviert ist. Machen Sie sich keine Gedanken Sie, wenn Sie diese Workload nicht installiert haben, bei der Installation von Visual Studio. Sie können führen das Installationsprogramm erneut aus, und installieren Sie es jetzt.

   ![Desktopentwicklung mit C++](media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Einen Überblick über die Grundlagen der Verwendung von Visual Studio-IDE. Wenn Sie Windows-desktopanwendungen, bevor Sie verwendet haben, können Sie möglicherweise Schritt zu halten. Eine Einführung finden Sie unter [Führung durch Features von Visual Studio-IDE](/visualstudio/ide/visual-studio-ide).

- Einen Überblick über genug für die grundlegenden Aspekte der Programmiersprache C++ nachvollziehen. Keine Sorge, wir nicht nichts zu kompliziert.

## <a name="create-the-dll-project"></a>Erstellen der DLL-Projekt

In diesem Satz von Aufgaben erstellen Sie ein Projekt für Ihre DLL-Datei, fügen Code hinzu, und erstellen Sie sie. Um zu beginnen, starten Sie Visual Studio-IDE, und melden Sie sich, wenn Sie möchten. Die Anweisungen für Visual Studio 2017 Version 15.3 stehen im Mittelpunkt. Anweisungen für frühere Versionen später, also fahren Sie bei Bedarf.

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>Zum Erstellen einer DLL-Projekt in Visual Studio 2017 Version 15.3 oder höher

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.

1. Im linken Bereich des der **neues Projekt** Dialogfeld erweitern Sie **installiert** und **Visual C++** bei Bedarf, und wählen Sie dann **Windows Desktop** . Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**. Geben Sie `MathLibrary` in die **Namen** Feld einen Namen für das Projekt angeben.

   ![Nennen Sie das Projekt MathLibrary](media/mathlibrary-new-project-name-153.png "MathLibrary Projektnamen")

1. Wählen Sie die **OK** Schaltfläche zum Schließen der **neues Projekt** Dialogfeld und Starten der **-Projekt für Windows Desktop** Assistenten.

1. In der **-Projekt für Windows Desktop** unter **Anwendungstyp**Option **Dynamic Link Library (DLL)**.

   ![Erstellen Sie im Assistenten für Windows-Desktopprojekt DLL](media/mathlibrary-desktop-project-wizard-dll.png "DLL im Assistenten für Windows-Desktopprojekt erstellen")

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen.

> [!NOTE]
> Es sind zusätzliche Schritte erforderlich, um ein Problem in Visual Studio 2017 Version 15.3 zu beheben. Um festzustellen, ob Sie diese Änderung vornehmen müssen, gehen Sie wie folgt vor.
>
>1. In **Projektmappen-Explorer**, wenn es nicht bereits ausgewählt, wählen ist die **MathLibrary** Projekt **Lösung "MathLibrary"**.
>
>1. Wählen Sie in der Menüleiste **Projekt** > **Eigenschaften** aus.
>
>1. Klicken Sie im linken Bereich des der **Eigenschaftenseiten** wählen Sie im Dialogfeld **Präprozessor** unter **Konfigurationseigenschaften** > **C-/C++-**. Überprüfen Sie den Inhalt der **Präprozessordefinitionen** Eigenschaft.<br/><br/>![Überprüfen Sie die Eigenschaft Präprozessordefinitionen](media/mathlibrary-153bug-preprocessor-definitions-check.png "überprüfen Sie die Präprozessordefinitionen-Eigenschaft")<br/><br/>Wenn dort **MATHLIBRARY&#95;EXPORTE** in die **Präprozessordefinitionen** aufzulisten, benötigen Sie keine Änderungen vornehmen. Wenn dort **MathLibrary&#95;EXPORTE** stattdessen, fahren Sie die folgenden Schritte ausführen.
>
>1. Am oberen Rand der **Eigenschaftenseiten** ändern Sie im Dialogfeld die **Konfiguration** Dropdown-Liste für **alle Konfigurationen**.
>
>1. Wählen Sie im Eigenschaftenbereich neben dem Bearbeitungsfeld für die Dropdown-Steuerelement **Präprozessordefinitionen**, und wählen Sie dann **bearbeiten**.<br/><br/>![Bearbeiten Sie die Eigenschaft Präprozessordefinitionen](media/mathlibrary-153bug-preprocessor-definitions-property.png "Präprozessordefinitionen-Eigenschaft bearbeiten")
>
>1. Im oberen Bereich der **Präprozessordefinitionen** Dialogfeld hinzufügen ein neues Symbols, `MATHLIBRARY_EXPORTS`.<br/><br/>![Fügen Sie das Symbol MATHLIBRARY_EXPORTS](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "fügen Sie das Symbol MATHLIBRARY_EXPORTS")
>
>1. Wählen Sie **OK** zu schließen, die **Präprozessordefinitionen** Dialogfeld, und wählen Sie dann **OK** zum Speichern der Änderungen in den Projekteigenschaften.

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>Erstellen Sie ein DLL-Projekt in früheren Versionen von Visual Studio

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

1. Im linken Bereich die **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Vorlagen**, und wählen Sie **Visual C++**, und Wählen Sie dann im mittleren Bereich **Win32-Konsolenanwendung**. Geben Sie `MathLibrary` in die **Namen** "Bearbeiten", um einen Namen für das Projekt angeben.

   ![Nennen Sie das Projekt MathLibrary](media/mathlibrary-project-name.png "MathLibrary Projektnamen")

1. Wählen Sie die **OK** Schaltfläche zum Schließen der **neues Projekt** Dialogfeld und Starten der **Win32-Anwendungsassistenten**.

   ![Übersicht über die Win32-Anwendung-Assistenten](media/mathlibrary-project-wizard-1.png "Übersicht über die Win32-Anwendung-Assistenten")

1. Klicken Sie auf **Weiter**. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **DLL**.

   ![Erstellen Sie die DLL in Win32-Anwendungsassistenten](media/mathlibrary-project-wizard-2.png "DLL im Win32-Anwendungs-Assistenten erstellen")

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Nach Abschluss des Assistenten auf die Projektmappe, können Sie sehen, dass die generierten Dateien im Projekt und die Quelldateien der **Projektmappen-Explorer** Fenster in Visual Studio.

![Projektmappen in Visual Studio generiert](media/mathlibrary-solution-explorer-153.png "Projektmappen in Visual Studio generiert")

Rechts nun diese DLL-Datei sehr viel nicht. Als Nächstes erstellen Sie eine Headerdatei zum Deklarieren von Funktionen der DLL exportiert werden soll, und klicken Sie dann die Funktionsdefinitionen hinzufügen, auf die DLL aus, um es noch nützlicher zu machen.

### <a name="to-add-a-header-file-to-the-dll"></a>Die DLL eine Headerdatei hinzu

1. Wählen Sie zum Erstellen einer Headerdatei für die Funktionen, auf der Menüleiste **Projekt** > **neues Element hinzufügen**.

1. In der **neues Element hinzufügen** im Dialogfeld im linken Bereich auf **Visual C++**. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)**. Geben Sie `MathLibrary.h` als Namen für die Header-Datei.

   ![Header hinzufügen, im Dialogfeld "Neues Element hinzufügen"](media/mathlibrary-add-new-item-header-file.png "-Header-Datei im Dialogfeld \"Neues Element hinzufügen\" hinzufügen")

1. Wählen Sie die **hinzufügen** Schaltfläche, um eine leere Headerdatei, generiert die in ein neues Editor-Fenster angezeigt wird.

   ![Leere MathLibrary.h-Datei im Editor](media/edit-empty-mathlibrary-header.png "leere MathLibrary.h-Datei im Editor")

1. Ersetzen Sie den Inhalt der Header-Datei mit dem folgenden Code ein:

   ```cpp
   // MathLibrary.h - Contains declarations of math functions
   #pragma once

   #ifdef MATHLIBRARY_EXPORTS
   #define MATHLIBRARY_API __declspec(dllexport)
   #else
   #define MATHLIBRARY_API __declspec(dllimport)
   #endif

   // The Fibonacci recurrence relation describes a sequence F
   // where F(n) is { n = 0, a
   //               { n = 1, b
   //               { n > 1, F(n-2) + F(n-1)
   // for some initial integral values a and b.
   // If the sequence is initialized F(0) = 1, F(1) = 1,
   // then this relation produces the well-known Fibonacci
   // sequence: 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   extern "C" MATHLIBRARY_API void fibonacci_init(
       const unsigned long long a, const unsigned long long b);

   // Produce the next value in the sequence.
   // Returns true on success and updates current value and index;
   // false on overflow, leaves current value and index unchanged.
   extern "C" MATHLIBRARY_API bool fibonacci_next();

   // Get the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned long long fibonacci_current();

   // Get the position of the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned fibonacci_index();
   ```

Diese Headerdatei deklariert, einige Funktionen eine generalisierte Fibonacci-Sequenz, angegebenen beiden ersten Werte erzeugt wird. Ein Aufruf von `fibonacci_init(1, 1)` vertraut Fibonacci-Zahlenfolge generiert.

Beachten Sie, dass der Präprozessor-Anweisungen am Anfang der Datei. Standardmäßig fügt die neuen Projektvorlage für eine DLL  **<em>PROJECTNAME</em>&#95;EXPORTE** auf der definierten Präprozessormakros für die DLL-Projekt. In diesem Beispiel ist Visual Studio definiert **MATHLIBRARY&#95;EXPORTE** Wenn Ihr MathLibrary DLL-Projekt erstellt wurde. (Der Assistent in Visual Studio 2017 Version 15.3 nicht Symboldefinition in Großbuchstaben zu erzwingen. Wenn Sie Namen für das Projekt "MathLibrary", und klicken Sie dann das Symbol definiert, MathLibrary ist&#95;EXPORTE statt MATHLIBRARY&#95;EXPORTIERT. That's Warum gibt es zusätzliche Schritte aus, um dieses Symbol hinzuzufügen.)

Wenn die **MATHLIBRARY&#95;EXPORTE** Makro definiert ist, die **MATHLIBRARY&#95;-API-** Makro legt die `__declspec(dllexport)` Modifizierer für die Funktionsdeklarationen. Dieser Modifizierer weist den Compiler und Linker an, eine Funktion oder Variable aus der DLL zu exportieren, sodass es von anderen Anwendungen verwendet werden kann. Wenn **MATHLIBRARY&#95;EXPORTE** ist nicht definiert ist, beispielsweise, wenn die Header-Datei, von einer Clientanwendung enthalten ist, **MATHLIBRARY&#95;API** gilt der `__declspec(dllimport)` Modifizierer, um die Deklarationen. Dieser Modifizierer optimiert den Import der Funktion oder Variable in einer Anwendung. Weitere Informationen finden Sie unter [Dllexport, Dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>Eine Implementierung auf die DLL hinzufügen.

1. Wählen Sie im Editor-Fenster, die Registerkarte für **MathLibrary.cpp** , wenn sie bereits geöffnet ist. Falls nicht, im **Projektmappen-Explorer**öffnen **MathLibrary.cpp** in die **Quelldateien** Ordner die **MathLibrary** Projekt.

1. Ersetzen Sie in den Editor den Inhalt der Datei MathLibrary.cpp durch den folgenden Code ein:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h"
   #include <utility>
   #include <limits.h>
   #include "MathLibrary.h"

   // DLL internal state variables:
   static unsigned long long previous_;  // Previous value, if any
   static unsigned long long current_;   // Current sequence value
   static unsigned index_;               // Current seq. position

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   void fibonacci_init(
       const unsigned long long a,
       const unsigned long long b)
   {
       index_ = 0;
       current_ = a;
       previous_ = b; // see special case when initialized
   }

   // Produce the next value in the sequence.
   // Returns true on success, false on overflow.
   bool fibonacci_next()
   {
       // check to see if we'd overflow result or position
       if ((ULLONG_MAX - previous_ < current_) ||
           (UINT_MAX == index_))
       {
           return false;
       }

       // Special case when index == 0, just return b value
       if (index_ > 0)
       {
           // otherwise, calculate next sequence value
           previous_ += current_;
       }
       std::swap(current_, previous_);
       ++index_;
       return true;
   }

   // Get the current value in the sequence.
   unsigned long long fibonacci_current()
   {
       return current_;
   }

   // Get the current index position in the sequence.
   unsigned fibonacci_index()
   {
       return index_;
   }
   ```

Um sicherzustellen, dass alles bisher funktioniert, kompilieren Sie die dynamic Link Library. Wählen Sie zum Kompilieren **erstellen** > **Projektmappe** in der Menüleiste. Die Ausgabe sollte etwa so aussehen:

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch! Sie haben eine DLL, die mit Visual C++ erstellt. Als Nächstes erstellen Sie eine Client-app, die von der DLL exportierten Funktionen verwendet.

## <a name="create-a-client-app-that-uses-the-dll"></a>Erstellen Sie eine Client-app, die die DLL verwendet.

Wenn Sie eine DLL-Datei erstellen, müssen Sie überlegen wie die DLL verwendet werden kann. Um Code zu kompilieren, die von einer DLL exportierten Funktionen aufruft, müssen die Deklarationen in den Quellcode für die Clients enthalten sein. Zum Zeitpunkt der Verknüpfung, wenn diese Aufrufe von DLL-Funktionen zu erhalten, müssen der Linker eine *Importbibliothek*, eine spezielle Bibliotheksdatei mit Informationen für Windows über das die Funktionen, anstatt den eigentlichen Code zu suchen. Und zur Laufzeit kann die DLL muss an den Client an einem Speicherort an, dem das Betriebssystem finden verfügbar sein.

Eine DLL zu verwenden, ob Ihre besitzen oder eine Drittanbieter-DLL, das Client-app-Projekt muss finden exportiert die Header, die die DLL zu deklarieren, die die Importbibliotheken für den Linker aus, und die DLL selbst. Eine Möglichkeit, werden alle diese Dateien in das Clientprojekt kopiert. Für Drittanbieter-DLLs, die wahrscheinlich nicht geändert werden, wenn der Client in der Entwicklung befindet, kann diese Methode die beste Möglichkeit, diese zu verwenden sein. Wenn Sie auch die DLL erstellen, ist es jedoch besser, Duplizierung zu vermeiden. Wenn Sie eine Kopie der DLL-Dateien, die in der Entwicklungsphase befinden vornehmen, können Sie versehentlich eine Headerdatei in eine Kopie, jedoch keine anderen ändern oder eine veraltete-Bibliothek verwenden. Um dieses Problem zu vermeiden, empfehlen wir, dass Sie die Include-Pfad im Clientprojekt sollen die DLL-Header-Dateien aus dem DLL-Projekt festlegen. Legen Sie darüber hinaus den Bibliothekspfad im Clientprojekt auf die DLL-Import-Bibliotheken über das DLL-Projekt enthält. Und schließlich Kopieren Sie die erstellte DLL aus dem DLL-Projekt in Ihrem Build-Ausgabeverzeichnis. In diesem Schritt können Ihre Client-app, die den gleichen Code für die DLL zu verwenden, die, den Sie erstellen.

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>Um eine Client-app in Visual Studio 2017 Version 15.3 oder höher erstellen

1. Wählen Sie zum Erstellen einer C++-app, die die DLL, die Sie erstellt haben verwendet, klicken Sie auf der Menüleiste **Datei** > **neu** > **Projekt**.

1. Klicken Sie im linken Bereich die **neues Projekt** wählen Sie im Dialogfeld **Windows Desktop** unter **installiert** > **Visual C++**. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**. Geben Sie den Namen für das Projekt `MathClient`in die **Namen** "Bearbeiten".

   ![Nennen Sie das Clientprojekt](media/mathclient-new-project-name-153.png "nennen Sie das Clientprojekt")

1. Wählen Sie **OK** zum Starten der **-Projekt für Windows Desktop** Assistenten. Wählen Sie im Assistenten **OK** das Client-app-Projekt zu erstellen.

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Erstellen Sie eine Client-app in älteren Versionen von Visual Studio 2017

1. Wählen Sie zum Erstellen einer C++-app, die die DLL, die Sie erstellt haben verwendet, klicken Sie auf der Menüleiste **Datei** > **neu** > **Projekt**.

1. Klicken Sie im linken Bereich die **neues Projekt** wählen Sie im Dialogfeld **Win32** unter **installiert** > **Vorlagen**  >  **Visual C++**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus. Geben Sie den Namen für das Projekt `MathClient`in die **Namen** "Bearbeiten".

   ![Nennen Sie das Clientprojekt](media/mathclient-project-name.png "nennen Sie das Clientprojekt")

1. Wählen Sie die **OK** Schaltfläche zum Schließen der **neues Projekt** Dialogfeld und Starten der **Win32-Anwendungsassistenten**. Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32-Anwendungs-Assistent** die Schaltfläche **Weiter** .

1. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **Konsolenanwendung** , wenn sie nicht bereits ausgewählt ist.

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Wenn der Assistent abgeschlossen ist, wird ein minimaler Konsolenanwendungsprojekt für Sie erstellt. Der Name der Hauptquelldatei ist identisch mit den Namen des Projekts, den Sie zuvor eingegeben haben. In diesem Beispiel heißt es **MathClient.cpp**. Sie können es erstellen, aber die DLL nicht noch verwenden.

Um die MathLibrary-Funktionen in Ihrem Quellcode aufzurufen, muss das Projekt als Nächstes die MathLibrary.h-Datei enthalten. Sie könnten kopieren Sie diese Header-Datei in Ihrem Client-app-Projekt und dann das Projekt als vorhandenes Element hinzufügen. Diese Methode kann es sich um eine gute Wahl für Drittanbieter-Bibliotheken sein. Wenn Sie auf den Code für die DLL zur gleichen Zeit wie der Client arbeiten, können jedoch, die auf Änderungen in einer Headerdatei führen, die in der anderen nicht angezeigt werden. Um dieses Problem zu vermeiden, können Sie ändern die **Additional Include Directories** Pfad in Ihrem Projekt den Pfad zu der ursprünglichen Überschrift enthält.

### <a name="to-add-the-dll-header-to-your-include-path"></a>Hinzufügen der DLL-Kopfzeile, um Ihre Includepfad

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt.

1. In der **Konfiguration** wählen Sie im Dropdown- **alle Konfigurationen** , wenn sie nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **allgemeine** unter **Konfigurationseigenschaften** > **C/C++-**.

1. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **Additional Include Directories** "Bearbeiten", und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Eigenschaft Additional Include Directories](media/mathclient-additional-include-directories-property.png "Additional Include Directories-Eigenschaft bearbeiten")

1. Doppelklicken Sie im oberen Bereich der **Additional Include Directories** im Dialogfeld, um ein Edit-Steuerelement zu aktivieren.

1. Geben Sie im Bearbeitungssteuerelement, den Pfad zum Speicherort der der **MathLibrary.h** Headerdatei. In diesem Fall können Sie einen relativen Pfad verwenden:

   `..\..\MathLibrary\MathLibrary`

   ![Fügen Sie den Speicherort für die Header, der Zusätzliche Includeverzeichnisse-Eigenschaft](media/mathclient-additional-include-directories.png "fügen Sie den Speicherort für die Header, der Zusätzliche Includeverzeichnisse-Eigenschaft")

1. Nachdem Sie den Pfad zur Headerdatei in eingegeben haben die **Zusätzliche Includeverzeichnisse** Dialogfeld Wählen der **OK** um zurückzugehen, der **Eigenschaftenseiten** im Dialogfeld und Wählen Sie dann die **OK** Schaltfläche, um die Änderungen zu speichern.

Sie können jetzt enthalten die **MathLibrary.h** Datei, und verwenden Sie die Funktionen, die sie in der Clientanwendung deklariert. Ersetzen Sie den Inhalt der **MathClient.cpp** mit dem folgenden Code:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "pch.h"
#include <iostream>
#include "MathLibrary.h"

int main()
{
    // Initialize a Fibonacci relation sequence.
    fibonacci_init(1, 1);
    // Write out the sequence values until overflow.
    do {
        std::cout << fibonacci_index() << ": "
            << fibonacci_current() << std::endl;
    } while (fibonacci_next());
    // Report count of values written before overflow.
    std::cout << fibonacci_index() + 1 <<
        " Fibonacci sequence values fit in an " <<
        "unsigned 64-bit integer." << std::endl;
}
```

Dieser Code kann kompiliert, aber nicht verknüpft werden, weil der Linker die Importbibliothek erforderlich, um die app zu erstellen, noch nicht gefunden werden. Der Linker muss die Datei MathLibrary.lib erfolgreich Verknüpfen finden. Die MathLibrary.lib-Datei mit dem Build hinzufügen, durch Festlegen der **zusätzliche Abhängigkeiten** Eigenschaft. Erneut, Sie können die Bibliotheksdatei in Ihrem Client-app-Projekt kopieren, aber der Bibliothek und die Client-app in der Entwicklungsphase befinden, führen, die möglicherweise auf Änderungen in eine Kopie, die in der anderen nicht angezeigt werden. Um dieses Problem zu vermeiden, können Sie ändern die **Zusätzliche Bibliotheksverzeichnisse** Pfad in Ihrem Projekt aus, um den Pfad zu der ursprünglichen Bibliothek einzuschließen, verknüpfen.

### <a name="to-add-the-dll-import-library-to-your-project"></a>Die DLL-Importbibliothek zu Ihrem Projekt hinzufügen

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt.

1. In der **Konfiguration** wählen Sie im Dropdown- **alle Konfigurationen** , wenn sie nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **Eingabe** unter **Konfigurationseigenschaften** > **Linker**. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **zusätzliche Abhängigkeiten** "Bearbeiten", und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Additional Dependencies-Eigenschaft](media/mathclient-additional-dependencies-property.png "Additional Dependencies-Eigenschaft bearbeiten")

1. In der **zusätzliche Abhängigkeiten** Dialogfeld hinzufügen `MathLibrary.lib` der Liste oben edit-Steuerelement.

   ![Fügen Sie die bibliotheksabhängigkeit](media/mathclient-additional-dependencies.png "fügen Sie die bibliotheksabhängigkeit")

1. Wählen Sie **OK** zum zurückkehren an die **Eigenschaftenseiten** im Dialogfeld.

1. Wählen Sie im linken Bereich **allgemeine** unter **Konfigurationseigenschaften** > **Linker**. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **Zusätzliche Bibliotheksverzeichnisse** "Bearbeiten", und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Eigenschaft Zusätzliche Bibliotheksverzeichnisse](media/mathclient-additional-library-directories-property.png "Zusätzliche Bibliotheksverzeichnisse-Eigenschaft bearbeiten")

1. Doppelklicken Sie im oberen Bereich der **Zusätzliche Bibliotheksverzeichnisse** im Dialogfeld, um ein Edit-Steuerelement zu aktivieren. Geben Sie im Bearbeitungssteuerelement, den Pfad zum Speicherort der der **MathLibrary.lib** Datei. Geben Sie diesen Wert, um ein Makro zu verwenden, das funktioniert für sowohl für Debug- und Releasebuilds:

   `..\..\MathLibrary\$(IntDir)`

   ![Fügen Sie das Bibliotheksverzeichnis](media/mathclient-additional-library-directories.png "fügen Sie das Bibliotheksverzeichnis hinzu.")

1. Nachdem Sie den Pfad, auf die Bibliotheksdatei in angegeben haben die **Zusätzliche Bibliotheksverzeichnisse** Dialogfeld wählen die **OK** um zurückzugehen, die **Eigenschaftenseiten** im Dialogfeld.

Ihre Client-app kann jetzt kompilieren und verknüpfen Sie erfolgreich, aber noch keinen alles, was sie zum Ausführen benötigt. Wenn das Betriebssystem der app geladen wird, sucht es die MathLibrary-DLL. Wenn die DLL in bestimmten Systemverzeichnisse, den Umgebungspfad oder lokalen app-Verzeichnis kann nicht gefunden, schlägt das Laden fehl. Eine Möglichkeit, dieses Problem zu vermeiden, ist die DLL in das Verzeichnis kopieren, die die Client-ausführbare Datei als Teil des Buildprozesses enthält. Sie können zum Kopieren von der DLL hinzufügen eine **Postbuildereignis** zu Ihrem Projekt einen Befehl hinzufügen, kopiert die DLL in Ihrem Build-Ausgabeverzeichnis. Der hier angegebene Befehl kopiert die DLL nur dann, wenn es nicht vorhanden ist oder geändert wurde und Makros verwendet, kopieren und der richtigen Debug- oder Retailmodus Speicherorte für die Konfiguration.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>Kopieren Sie die DLL in ein Postbuildereignis

1. Öffnen Sie die **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt, wenn es nicht bereits geöffnet ist.

1. Wählen Sie im Dropdown-Konfiguration der **alle Konfigurationen** , wenn sie nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **Postbuildereignis** unter **Konfigurationseigenschaften** > **Buildereignisse**.

1. Wählen Sie im Eigenschaftenbereich, Edit-Steuerelement die **Befehlszeile** ein, und geben Sie dann mit diesem Befehl:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Fügen Sie den Befehl nach der Erstellung](media/mathclient-post-build-command-line.png "fügen Sie den Befehl nach der Erstellung")

1. Wählen Sie die **OK** Schaltfläche zum Speichern der Änderungen in den Projekteigenschaften.

Ihre Client-app verfügt jetzt über alles, was er benötigt, erstellt und ausgeführt werden soll. Erstellen Sie die Anwendung durch Auswahl **erstellen** > **Projektmappe** in der Menüleiste. Die **Ausgabe** Fenster in Visual Studio sollte etwa Folgendes enthalten:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch, Sie erstellt haben, eine Anwendung, die in der DLL-Funktionen aufgerufen. Führen Sie nun Ihre Anwendung aus, um festzustellen, welche Aktion er ausführt. Wählen Sie auf der Menüleiste **Debuggen** > **Starten ohne Debugging**. Visual Studio öffnet ein Befehlsfenster für das Programm ausgeführt wird. Der letzte Teil der Ausgabe aussehen sollte:

![Starten Sie die Client-app ohne Debuggen](media/mathclient-run-without-debugging.png "starten Sie die Client-app ohne Debuggen")

Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.

Nun, dass Sie eine DLL-Datei und einer Clientanwendung erstellt haben, können Sie experimentieren. Legen Sie Haltepunkte im Code der Client-app, und führen Sie die app im Debugger. Finden Sie, was geschieht, wenn Sie eine Bibliotheksaufruf schrittweise ausführen. Fügen Sie andere Funktionen zur Bibliothek hinzu, oder Schreiben Sie einen anderen Client-app, die die DLL verwendet.

Wenn Sie Ihre app bereitstellen, müssen Sie auch die DLLs bereitstellen, verwendet. Die einfachste Möglichkeit, die DLLs, die Sie erstellen oder, die Sie einschließen, von Drittanbietern zur Verfügung stellen zu Ihrer app wird im gleichen Verzeichnis wie die app, auch bekannt als Einsatzort *lokalen app-Bereitstellung*. Weitere Informationen zur Bereitstellung finden Sie unter [Deployment in Visual C++](../ide/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)<br/>
[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)<br/>
[Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)](../ide/walkthrough-deploying-your-program-cpp.md)<br/>
[Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](../build/calling-dll-functions-from-visual-basic-applications.md)
