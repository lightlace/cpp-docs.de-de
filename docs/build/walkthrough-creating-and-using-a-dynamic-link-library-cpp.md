---
title: 'Exemplarische Vorgehensweise: Erstellen und verwenden Sie eine eigene Dynamic Link Library (C++) | Microsoft Docs'
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19c9c013d591f4c6de14ecd4a2c582d8f0f3e4d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>Exemplarische Vorgehensweise: Erstellen Sie und verwenden Sie eine eigene Dynamic Link Library (C++)

Dieser schrittweise erläuterten exemplarischen zeigt, wie der Visual Studio-IDE zum Erstellen eigener dynamic Link Library (DLL) in C++ geschrieben wurde, und verwenden es aus einer anderen C++-app. DLLs sind eines der nützlichsten Arten von Windows-Komponenten. Sie können diese als eine Möglichkeit, Code und Ressourcen freizugeben so verkleinern Sie Ihre apps und zum service, und erweitern Ihre apps zu erleichtern. In dieser exemplarischen Vorgehensweise erstellen eine DLL, die einige mathematische Funktionen implementiert, und erstellen Sie eine Konsolenanwendung, die aus der DLL-Funktionen verwendet. Nebenbei erhalten Sie eine Einführung zu einigen der Programmierung Techniken und Konventionen, die in Windows-DLLs verwendet.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- Erstellen Sie ein DLL-Projekt in Visual Studio.

- Hinzufügen der DLL exportierten Funktionen und Variablen zu.

- Erstellen eines Konsolen-app-Projekts in Visual Studio.

- Verwenden Sie die Funktionen und Variablen, die aus der DLL in die Konsolen-app importiert.

- Führen Sie die abgeschlossene app.

Wie eine statisch verknüpfte Bibliothek, einer DLL _exportiert_ Variablen, Funktionen und Ressourcen anhand des Namens und Ihrer app _importiert_ diesen Namen, die diese Variablen, Funktionen und Ressourcen verwendet. Im Gegensatz zu einer statisch verknüpften Bibliothek verbindet Windows die Importe in Ihrer app mit den Exporten in einer DLL zur Ladezeit oder zur Laufzeit statt verbindenden zum Zeitpunkt der Verknüpfung an. Windows erfordert zusätzlichen Informationen, der nicht Teil des standard C++-Kompilierung-Modells, diese Verbindungen herzustellen. Visual C++-Compiler implementiert einige Microsoft-spezifische Erweiterungen für C++, um diese zusätzlichen Informationen bereitzustellen. Diese Erweiterungen wird erläutert, wie wir gehen.

In dieser exemplarischen Vorgehensweise erstellt zwei Visual Studio-Projektmappen. eine, die die DLL erstellt, und eine, in dem die Client-app erstellt. Die DLL verwendet C-Aufrufkonvention an, damit diese von apps, die mit anderen Sprachen erstellt werden, solange die Plattform und das Aufrufen und Verknüpfen von Konventionen entsprechen aufgerufen werden können. Der Client-app verwendet _implizite Verknüpfung_, auf dem Windows die app auf die DLL Ladezeit verknüpft ist. Auf diese Weise können die app, die die bereitgestellte DLL-Funktionen wie die Funktionen in einer statisch verknüpften Bibliothek aufrufen.

In dieser exemplarischen Vorgehensweise nicht in der einige häufige Situationen enthalten. Die Verwendung von C++-DLLs von anderen Programmiersprachen nicht angezeigt. Vorgehensweise: erstellen eine reinen Ressourcen DLL nicht angezeigt. Die Verwendung der expliziten Verknüpfung zum Laden von DLLs zur Laufzeit und nicht erst zur Ladezeit nicht ebenfalls angezeigt. Unterliegen, Visual C++ können Sie alle diese Aktionen ausgeführt werden. Links zu weiteren Informationen über DLLs, finden Sie unter [-DLLs in Visual C++](../build/dlls-in-visual-cpp.md). Weitere Informationen zu impliziten verknüpfen und explizites verknüpfen, finden Sie unter [Bestimmen der geeigneten Verknüpfungsmethode](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). Informationen zum Erstellen von C++-DLLs für die Verwendung mit Programmiersprachen zu vergleichen, die Konventionen der Programmiersprache C-Bindung verwenden, finden Sie unter [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md). Informationen zum Erstellen von DLLs für die Verwendung mit .NET-Sprachen finden Sie unter [Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen](../build/calling-dll-functions-from-visual-basic-applications.md).

Diese exemplarische Vorgehensweise verwendet Visual Studio 2017, aber der Code und die meisten Anweisungen gelten für frühere Versionen. Die Schritte zum Erstellen von neuer Projekten geändert in Visual Studio 2017 Version 15.3 ab. In dieser exemplarischen Vorgehensweise wird beschrieben, wie zum Erstellen von Projekten für neuere und ältere Versionen. Suchen Sie nach den Schritten, die Ihrer Version von Visual Studio entsprechen.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Ein Computer, der Microsoft Windows 7 oder höher ausgeführt wird. Wir empfehlen Windows 10 Entwicklung optimale Ergebnisse zu erzielen.

- Eine Kopie des Visual Studio-2017. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [installieren Sie Visual Studio 2017](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen sicher, dass die **Desktopentwicklung mit C++** arbeitsauslastung aktiviert ist. Machen Sie sich keine Gedanken Sie, wenn Sie diese arbeitsauslastung nicht installiert haben, wenn Sie Visual Studio installiert. Sie können das Installationsprogramm erneut ausführen und installieren Sie es jetzt.

   ![Desktop-Entwicklung mit C++](media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Einen Überblick über die Grundlagen der Verwendung von Visual Studio-IDE. Wenn Sie Windows-desktop-apps vor verwendet haben, können Sie wahrscheinlich Schritt zu halten. Eine Einführung finden Sie unter [Visual Studio-IDE Featuretour](/visualstudio/ide/visual-studio-ide).

- Einen Überblick über genügend die Grundlagen der Programmiersprache C++ nachvollziehen. Keine Sorge, wir keine zu kompliziert gestalten.

## <a name="create-the-dll-project"></a>Erstellen Sie das DLL-Projekt

In diesem Satz von Aufgaben erstellen Sie ein Projekt für die DLL, fügen Sie Code hinzu und erstellen Sie sie. Um zu beginnen, starten Sie Visual Studio-IDE, und melden Sie sich bei Bedarf. Die Anweisungen für Visual Studio 2017 Version 15.3 zuerst. Anweisungen für frühere Versionen Elements nachgeordnet sein, also fahren Sie bei Bedarf.

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>Zum Erstellen eines DLL-Projekts in Visual Studio 2017 Version 15,3 oder höher

1. Wählen Sie in der Menüleiste **Datei**, **neu**, **Projekt** So öffnen die **neues Projekt** (Dialogfeld).

1. Im linken Bereich des der **neues Projekt** Dialogfeld erweitern Sie **installiert** und **Visual C++** Wenn erforderlich, und Sie dann wählen **Windows Desktop**. Wählen Sie im mittleren Bereich **im Assistenten für Windows Desktop**. Geben Sie `MathLibrary` in der **Namen** Feld einen Namen für das Projekt an.

   ![Nennen Sie das Projekt MathLibrary](media/mathlibrary-new-project-name-153.png "MathLibrary Projektnamen")

1. Wählen Sie die **OK** Schaltfläche beim Schließen der **neues Projekt** Dialogfeld und Starten der **Windows-Desktop-Projekt** Assistenten.

1. In der **Windows-Desktop-Projekt** Assistenten unter **Anwendungstyp**Option **Dynamic Link Library (DLL)**.

   ![DLL im Assistenten für Windows-Desktopprojekt erstellen](media/mathlibrary-desktop-project-wizard-dll.png "-DLL im Assistenten für Windows-Desktopprojekt erstellen")

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen.

> [!NOTE]
> Es sind zusätzliche Schritte erforderlich, um ein Problem in Visual Studio 2017 Version 15.3 zu beheben. Um festzustellen, ob Sie diese Änderung vornehmen müssen, gehen Sie wie folgt vor.
>
>1. In **Projektmappen-Explorer**, sofern er nicht bereits ausgewählt, wählen ist die **MathLibrary** -Projekt unter **Lösung "MathLibrary"**.
>
>1. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus.
>
>1. Im linken Bereich des der **Eigenschaftenseiten** wählen Sie im Dialogfeld **Präprozessor** unter **Konfigurationseigenschaften**, **C/C++-**. Überprüfen Sie den Inhalt von der **Präprozessordefinitionen** Eigenschaft.<br/><br/>![Überprüfen Sie die Eigenschaft Präprozessordefinitionen](media/mathlibrary-153bug-preprocessor-definitions-check.png "überprüfen Sie die Präprozessordefinitionen-Eigenschaft")<br/><br/>Wenn dort **MATHLIBRARY&#95;EXPORTE** in der **Präprozessordefinitionen** aufzulisten, müssen Sie nicht ändert nichts. Wenn dort **MathLibrary&#95;EXPORTE** stattdessen, fahren Sie die folgenden Schritte ausführen.
>
>1. Am oberen Rand der **Eigenschaftenseiten** ändern Sie im Dialogfeld die **Konfiguration** Dropdownelement **alle Konfigurationen**.
>
>1. Wählen Sie im Eigenschaftenbereich die Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Präprozessordefinitionen**, und wählen Sie dann **bearbeiten**.<br/><br/>![Bearbeiten Sie die Eigenschaft Präprozessordefinitionen](media/mathlibrary-153bug-preprocessor-definitions-property.png "Präprozessordefinitionen Eigenschaft bearbeiten")
>
>1. Im oberen Bereich der **Präprozessordefinitionen** Dialogfeld hinzufügen ein neues Symbol `MATHLIBRARY_EXPORTS`.<br/><br/>![Fügen Sie das Symbol MATHLIBRARY_EXPORTS](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "fügen Sie das MATHLIBRARY_EXPORTS-Symbol")
>
>1. Wählen Sie **OK** beim Schließen der **Präprozessordefinitionen** Dialogfeld, und wählen Sie dann **OK** zum Speichern der Änderungen in den Projekteigenschaften.

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>So erstellen ein DLL-Projekt in früheren Versionen von Visual Studio

1. Wählen Sie in der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Im linken Bereich des der **neues Projekt** Dialogfeld erweitern Sie **installiert**, **Vorlagen**, und wählen Sie **Visual C++**, und klicken Sie dann in der Mitte Klicken Sie im Bereich **Win32-Konsolenanwendung**. Geben Sie `MathLibrary` in der **Namen** Eingabefeld zur Angabe eines Benutzernamens für das Projekt.

   ![Nennen Sie das Projekt MathLibrary](media/mathlibrary-project-name.png "MathLibrary Projektnamen")

1. Wählen Sie die **OK** Schaltfläche beim Schließen der **neues Projekt** Dialogfeld und Starten der **Win32-Anwendung-Assistent**.

   ![Übersicht über die Win32-Anwendung-Assistenten](media/mathlibrary-project-wizard-1.png "Win32-Anwendung-Assistenten (Übersicht)")

1. Klicken Sie auf **Weiter**. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **DLL**.

   ![Erstellen Sie die DLL im Win32-Anwendungs-Assistenten](media/mathlibrary-project-wizard-2.png "-DLL im Win32-Anwendungs-Assistenten erstellen")

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Beim Abschluss des Assistenten auf der Projektmappe, sehen Sie die generierten Dateien Projekt- und Quelldateien in der **Projektmappen-Explorer** Fenster in Visual Studio.

![Projektmappen in Visual Studio generiert](media/mathlibrary-solution-explorer-153.png "Projektmappen in Visual Studio generiert")

Rechts jetzt diese DLL kaum erfolgt jedoch nicht. Als Nächstes erstellen Sie eine Headerdatei, um die Funktionen der DLL deklarieren exportiert und dann die Funktionsdefinitionen nützlicher erleichtern die DLL hinzufügen.

### <a name="to-add-a-header-file-to-the-dll"></a>So fügen Sie eine Headerdatei für die DLL hinzu

1. Wählen Sie zum Erstellen einer Headerdatei für die Funktionen in der Menüleiste **Projekt**, **neues Element hinzufügen**.

1. In der **neues Element hinzufügen** (Dialogfeld), in den linken Bereich die Option **Visual C++**. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)**. Geben Sie `MathLibrary.h` als Namen für die Headerdatei.

   ![Header hinzufügen im Dialogfeld "Neues Element hinzufügen"](media/mathlibrary-add-new-item-header-file.png "-Header-Datei im Dialogfeld "Neues Element hinzufügen" hinzufügen")

1. Wählen Sie die **hinzufügen** Schaltfläche, um eine leere Headerdatei zu generieren, die in ein neues Editor-Fenster angezeigt wird.

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

Diese Headerdatei deklariert einige Funktionen, um eine generalisierte Fibonacci-Sequenz angegebenen zwei Anfangswerte zu erzeugen. Ein Aufruf von `fibonacci_init(1, 1)` generiert die Sequenz vertraut Fibonacci-Zahl.

Beachten Sie das Präprozessor-Anweisungen am Anfang der Datei ein. Standardmäßig fügt die neue Projektvorlage für eine DLL ***Projektname *&#95;EXPORTE** auf der definierten Präprozessormakros für die DLL-Projekt. In diesem Beispiel Visual Studio definiert **MATHLIBRARY&#95;EXPORTE** Wenn Ihr MathLibrary DLL-Projekt erstellt wird. (Der Assistenten in Visual Studio 2017 Version 15.3 erzwingt keine Symboldefinition in Großbuchstaben. Wenn Sie Namen für das Projekt "MathLibrary", und klicken Sie dann das Symbol definiert, MathLibrary ist&#95;EXPORTE statt MATHLIBRARY&#95;EXPORTIERT. That's Warum gibt es zusätzliche Schritte aus, um dieses Symbol hinzuzufügen.)

Wenn die **MATHLIBRARY&#95;EXPORTE** -Makro wird definiert, die **MATHLIBRARY&#95;API** Makro legt die `__declspec(dllexport)` Modifizierer in der Funktionsdeklarationen. Dieser Modifizierer weist den Compiler und Linker an, eine Funktion oder Variable aus der DLL zu exportieren, sodass sie von einer anderen Anwendung verwendet werden kann. Wenn **MATHLIBRARY&#95;EXPORTE** ist nicht definiert ist, z. B. wenn die Header-Datei, von einer Clientanwendung enthalten ist **MATHLIBRARY&#95;API** gilt die `__declspec(dllimport)` Modifizierer, um die Deklarationen. Dieser Modifizierer optimiert den Import der Funktion oder Variable in einer Anwendung. Weitere Informationen finden Sie unter [Dllexport, Dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>Eine Implementierung für die DLL hinzufügen.

1. Wählen Sie im Editor-Fenster, die Registerkarte für **MathLibrary.cpp** , wenn er bereits geöffnet ist. Wenn dies nicht der Fall, in **Projektmappen-Explorer**öffnen **MathLibrary.cpp** in der **Quelldateien** Ordner, der die **MathLibrary** Projekt.

1. Ersetzen Sie den Inhalt der Datei MathLibrary.cpp im Editor durch folgenden Code:

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

Um sicherzustellen, dass alles, was bisher funktioniert, kompilieren Sie die dynamic Link Library. Wählen Sie zum Kompilieren **erstellen**, **Projektmappe** in der Menüleiste. Die Ausgabe sollte etwa wie folgt aussehen:

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

Herzlichen Glückwunsch, Sie haben eine DLL, die mit Visual C++ erstellt! Als Nächstes erstellen Sie eine Client-app, die von der DLL exportierten Funktionen verwendet.

## <a name="create-a-client-app-that-uses-the-dll"></a>Erstellen Sie eine Client-app, die die DLL verwendet

Wenn Sie eine DLL erstellen, müssen Sie überlegen Sie sich wie die DLL verwendet werden kann. Um Code zu kompilieren, die von einer DLL exportierten Funktionen aufruft, müssen die Deklarationen im Clientquellcode enthalten sein. Zum Zeitpunkt der Verknüpfung, wenn diese Aufrufe von DLL-Funktionen aufgelöst werden, der Linker benötigen eine *Importbibliothek*, eine spezielle Art von Bibliotheksdatei, die für Windows finden Sie Informationen zu Funktionen, anstatt den eigentlichen Code enthält. Und zur Laufzeit kann die DLL muss auf dem Client in einem Speicherort, den das Betriebssystem finden können verfügbar sein.

Einer DLL verwenden, ob der Besitzer oder eine Drittanbieter-DLL das Client-app-Projekt muss exportiert werden die Header, die die DLL zu deklarieren, die Importbibliotheken für den Linker und die DLL selbst finden können. Eine Möglichkeit hierfür besteht darin all diese Dateien in Ihrem Clientprojekt zu kopieren. Für Drittanbieter-DLLs, die i. d. ändern r., während der Client in der Entwicklung befindet, kann dies die beste Möglichkeit, ihre Verwendung sein. Wenn Sie auch die DLL erstellen, ist es jedoch besser, Duplikation zu vermeiden. Wenn Sie eine Kopie der DLL-Dateien, die in der Entwicklungsphase befinden vornehmen, können Sie versehentlich eine Headerdatei in eine einzige Kopie, aber nicht in der anderen ändern oder verwenden eine Bibliothek nicht mehr aktuell. Um dieses Problem zu vermeiden, wird empfohlen, dass Festlegen des Include-Pfads im Clientprojekt die DLL-Header-Dateien über das DLL-Projekt einfügen. Legen Sie außerdem Bibliothekspfad in Ihrem Clientprojekt, um die DLL-Import-Bibliotheken über das DLL-Projekt einzuschließen. Und schließlich Kopieren Sie die erstellte DLL aus dem DLL-Projekt in Ihrer Buildausgabeverzeichnis. Dadurch wird sichergestellt, dass Ihre Client-app den gleichen DLL-Code verwendet, den Sie erstellen.

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>Zum Erstellen einer Client-app in Visual Studio 2017 Version 15,3 oder höher

1. Wählen Sie um eine C++-app zu erstellen, die die DLL verwendet, die Sie gerade in der Menüleiste erstellte **Datei**, **neu**, **Projekt**.

1. Im linken Bereich des der **neues Projekt** wählen Sie im Dialogfeld **Windows Desktop** unter **installiert**, **Visual C++**. Wählen Sie im mittleren Bereich **im Assistenten für Windows Desktop**. Geben Sie den Namen für das Projekt `MathClient`in der **Namen** Eingabefeld.

   ![Nennen Sie das Clientprojekt](media/mathclient-new-project-name-153.png "nennen Sie das Clientprojekt")

1. Wählen Sie **OK** zum Starten der **Windows-Desktop-Projekt** Assistenten. Wählen Sie im Assistenten **OK** auf das Client-app-Projekt zu erstellen.

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>So erstellen eine Client-app in früheren Versionen von Visual Studio 2017

1. Wählen Sie um eine C++-app zu erstellen, die die DLL verwendet, die Sie gerade in der Menüleiste erstellte **Datei**, **neu**, **Projekt**.

1. Im linken Bereich des der **neues Projekt** wählen Sie im Dialogfeld **Win32** unter **installiert**, **Vorlagen**, **Visual C++**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus. Geben Sie den Namen für das Projekt `MathClient`in der **Namen** Eingabefeld.

   ![Nennen Sie das Clientprojekt](media/mathclient-project-name.png "nennen Sie das Clientprojekt")

1. Wählen Sie die **OK** Schaltfläche beim Schließen der **neues Projekt** Dialogfeld und Starten der **Win32-Anwendung-Assistent**. Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32-Anwendungs-Assistent** die Schaltfläche **Weiter** .

1. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **Konsolenanwendung** , wenn er nicht bereits ausgewählt ist.

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Nach Abschluss des Assistenten wird ein minimaler Konsolenanwendungsprojekt für Sie erstellt. Der Name für die main-Quelldatei ist identisch mit den Namen des Projekts, den Sie zuvor eingegeben haben. In diesem Beispiel lautet er **MathClient.cpp**. Erstellen Sie sie aus, aber nicht die DLL noch verwenden.

Zum Aufrufen der MathLibrary-Funktionen in Ihren Quellcode muss das Projekt als Nächstes die MathLibrary.h-Datei enthalten. Sie konnten diese Headerdatei in Ihrem Client-app-Projekt kopieren und anschließend das Projekt als ein vorhandenes Element hinzufügen. Dies kann eine gute Wahl für Drittanbieter-Bibliotheken sein. Wenn Sie auf den Code für die DLL gleichzeitig als Client arbeiten, können jedoch, die auf Änderungen in einer Headerdatei führen, die nicht in den anderen wiedergegeben werden. Um dieses Problem zu vermeiden, können Sie ändern die **Zusätzliche Includeverzeichnisse** Pfad in Ihrem Projekt, um den Pfad zu der ursprünglichen Überschrift einschließen.

### <a name="to-add-the-dll-header-to-your-include-path"></a>Hinzufügen von DLL-Headers, der Ihre Includepfad

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt.

1. In der **Konfiguration** wählen Sie im Dropdown- **alle Konfigurationen** , wenn er nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **allgemeine** unter **Konfigurationseigenschaften**, **C/C++-**.

1. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **Zusätzliche Includeverzeichnisse** Eingabefeld ein, und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Eigenschaft Zusätzliche Includeverzeichnisse](media/mathclient-additional-include-directories-property.png "bearbeiten Sie die Zusätzliche Includeverzeichnisse-Eigenschaft")

1. Doppelklicken Sie im oberen Bereich auf die **Zusätzliche Includeverzeichnisse** (Dialogfeld), um ein Bearbeitungssteuerelement zu aktivieren.

1. Geben Sie den Pfad zum Speicherort der in das Bearbeitungssteuerelement der **MathLibrary.h** Headerdatei. In diesem Fall können Sie einen relativen Pfad verwenden:

   `..\..\MathLibrary\MathLibrary`

   ![Fügen Sie den Header-Speicherort für die Eigenschaft Zusätzliche Includeverzeichnisse](media/mathclient-additional-include-directories.png "fügen Sie den Header-Speicherort für die Zusätzliche Includeverzeichnisse-Eigenschaft")

1. Nachdem Sie den Pfad in der Headerdatei in eingegeben haben die **Zusätzliche Includeverzeichnisse** Dialogfeld Wählen Sie die **OK** Schaltfläche, um wieder zu den **Eigenschaftenseiten** (Dialogfeld), und Wählen Sie dann die **OK** Schaltfläche, um die Änderungen zu speichern.

Sie können jetzt enthalten die **MathLibrary.h** Datei, und verwenden Sie die Funktionen, die sie in Ihrer Clientanwendung deklariert. Ersetzen Sie den Inhalt des **MathClient.cpp** mit dem folgenden Code:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "stdafx.h"
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

Dieser Code kann kompiliert, aber nicht verknüpft werden, da der Linker die Importbibliothek erforderlich, um die app zu erstellen, noch nicht finden kann. Der Linker muss zum Ermitteln der MathLibrary.lib Datei erfolgreich verknüpfen können. Sie müssen die MathLibrary.lib-Datei in das Buildausgabeverzeichnis hinzufügen, durch Festlegen der **zusätzliche Abhängigkeiten** Eigenschaft. Noch einmal: konnte, kopieren Sie die Bibliotheksdatei in Ihrem Client-app-Projekt, aber die Bibliothek und die Client-app in der Entwicklungsphase befinden, führen, die möglicherweise Änderungen in eine einzige Kopie, die nicht in den anderen wiedergegeben werden. Um dieses Problem zu vermeiden, können Sie ändern die **Zusätzliche Bibliotheksverzeichnisse** Pfad in Ihrem Projekt, um den Pfad der ursprünglichen Bibliothek enthalten, beim verknüpfen.

### <a name="to-add-the-dll-import-library-to-your-project"></a>So fügen Sie die DLL-Importbibliothek zu Ihrem Projekt hinzu

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt.

1. In der **Konfiguration** wählen Sie im Dropdown- **alle Konfigurationen** , wenn er nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **Eingabe** unter **Konfigurationseigenschaften**, **Linker**. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **zusätzliche Abhängigkeiten** Eingabefeld ein, und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Eigenschaft zusätzliche Abhängigkeiten](media/mathclient-additional-dependencies-property.png "bearbeiten Sie die zusätzliche Dependencies-Eigenschaft")

1. In der **zusätzliche Abhängigkeiten** Dialogfeld hinzufügen `MathLibrary.lib` der Liste oben edit-Steuerelement.

   ![Fügen Sie der Bibliothek Abhängigkeit](media/mathclient-additional-dependencies.png "fügen Sie der Bibliothek-Abhängigkeit")

1. Wählen Sie **OK** zurückdatieren, um die **Eigenschaftenseiten** (Dialogfeld).

1. Wählen Sie im linken Bereich **allgemeine** unter **Konfigurationseigenschaften**, **Linker**. Aktivieren Sie im Eigenschaftenbereich neben den Dropdown-Steuerelement die **Zusätzliche Bibliotheksverzeichnisse** Eingabefeld ein, und wählen Sie dann **bearbeiten**.

   ![Bearbeiten Sie die Eigenschaft Zusätzliche Bibliotheksverzeichnisse](media/mathclient-additional-library-directories-property.png "bearbeiten Sie die zusätzliche Bibliotheksverzeichnisse-Eigenschaft")

1. Doppelklicken Sie im oberen Bereich auf die **Zusätzliche Bibliotheksverzeichnisse** (Dialogfeld), um ein Bearbeitungssteuerelement zu aktivieren. Geben Sie den Pfad zum Speicherort der in das Bearbeitungssteuerelement der **MathLibrary.lib** Datei. Geben Sie diesen Wert, um ein Makro verwenden, die für die Debugversion und Releaseversion funktioniert erstellt:

   `..\..\MathLibrary\$(IntDir)`

   ![Fügen Sie das Bibliotheksverzeichnis](media/mathclient-additional-library-directories.png "fügen Sie das Bibliotheksverzeichnis hinzu.")

1. Nachdem Sie den Pfad in die Bibliotheksdatei in eingegeben haben die **Zusätzliche Bibliotheksverzeichnisse** Dialogfeld Wählen Sie die **OK** Schaltfläche, um wieder zu den **Eigenschaftenseiten** (Dialogfeld).

Ihre Client-app kann jetzt kompilieren und verknüpfen erfolgreich, aber noch keine alles zum Ausführen benötigt. Wenn das Betriebssystem Ihrer app geladen wird, sucht es MathLibrary DLL. Wenn er in bestimmte Verzeichnisse, die Umgebungspfad oder das Verzeichnis lokale app die DLL finden kann, schlägt das Laden fehl. Eine Möglichkeit, dieses Problem zu vermeiden, ist die DLL in das Verzeichnis kopieren, die als Teil des Buildprozesses der ausführbare Client enthält. Um die DLL zu kopieren, fügen Sie eine **Postbuildereignis** zum Projekt, um einen Befehl hinzuzufügen, die die DLL in kopiert Ihre Buildausgabeverzeichnis. Der hier angegebene Befehl kopiert die DLL nur, wenn es nicht vorhanden ist oder geändert wurde und Makros zum Kopieren in und der richtigen Debuggen "oder" Retail Speicherorte für die Konfiguration verwendet.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>So kopieren Sie die DLL in ein Postbuildereignis

1. Öffnen Sie die **Eigenschaftenseiten** im Dialogfeld für die **MathClient** Projekt, sofern er nicht bereits geöffnet ist.

1. Wählen Sie im Dropdown-Konfiguration **alle Konfigurationen** , wenn er nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **Postbuildereignis** unter **Konfigurationseigenschaften**, **Buildereignisse**.

1. Wählen Sie im Eigenschaftenbereich, das Bearbeitungssteuerelement in der **Befehlszeile** ein, und geben Sie dann mit diesem Befehl:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Fügen Sie den Befehl nach der Erstellung](media/mathclient-post-build-command-line.png "fügen Sie den Befehl nach der Erstellung")

1. Wählen Sie die **OK** Schaltfläche, um die Änderungen in den Projekteigenschaften zu speichern.

Jetzt hat Ihre Client-app alle zum Erstellen und Ausführen benötigten Informationen. Erstellen Sie die Anwendung, indem Sie auswählen **erstellen**, **Projektmappe** in der Menüleiste. Die **Ausgabe** Fenster in Visual Studio sollte etwa wie folgt enthalten:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch, Sie erstellt haben, eine Anwendung, die in der DLL-Funktion aufruft. Führen Sie nun Ihre Anwendung, um festzustellen, welche Aktion er ausführt. Wählen Sie in der Menüleiste **Debuggen**, **Starten ohne Debugging**. Visual Studio öffnet ein Befehlsfenster, das für das Programm ausgeführt wird. Der letzte Teil der Ausgabe sollte wie folgt aussehen:

![Starten Sie die Client-app ohne Debuggen](media/mathclient-run-without-debugging.png "starten Sie die Client-app ohne Debuggen")

Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.

Nun, dass Sie eine DLL-Datei und einer Clientanwendung erstellt haben, können Sie experimentieren. Wiederholen Sie den Festlegen von Haltepunkten im Code der Client-app, und führen Sie die app im Debugger. Finden Sie, was geschieht, wenn Sie einem Bibliotheksaufruf in Einzelschritten. Fügen Sie andere Funktionen der Bibliothek hinzu, oder Schreiben Sie eine andere Client-app, die die DLL verwendet.

Wenn Sie Ihre app bereitstellen, müssen Sie auch die DLLs bereitstellen, verwendet. Die einfachste Möglichkeit zum Bereitstellen von DLLs, die Sie erstellen oder, die Sie einschließen, von Drittanbietern für Ihre app wird im gleichen Verzeichnis wie die app, auch bekannt als Einsatzort *Bereitstellung der app-lokal*. Weitere Informationen zur Bereitstellung finden Sie unter [Bereitstellung in Visual C++](..\ide\deployment-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)  
[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)  
[Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
[Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](../build/calling-dll-functions-from-visual-basic-applications.md)