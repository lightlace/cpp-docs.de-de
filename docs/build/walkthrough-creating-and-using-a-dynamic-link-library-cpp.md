---
title: 'Exemplarische Vorgehensweise: Erstellen und Verwenden Ihrer eigenen Dynamic Link Library (C++)'
description: Verwenden Sie C++, um in Visual Studio eine Dynamic Link Library (DLL) für Windows zu erstellen.
ms.custom: conceptual
ms.date: 07/17/2019
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 8ca89471177ba2d1fa98bfaf51b86ed15dcd6d2f
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299826"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>Exemplarische Vorgehensweise: Erstellen und Verwenden Ihrer eigenen Dynamic Link Library (C++)

Diese exemplarische Vorgehensweise zeigt Schritt für Schritt, wie Sie die Visual Studio-IDE verwenden, um selbst eine in C++ geschriebene Dynamic Link Library (DLL) zu erstellen und diese dann in einer anderen C++-App zu verwenden. DLLs (in UNIX-basierten Betriebssystemen auch als freigegebene Bibliotheken bezeichnet) gehören zu den nützlichsten Arten von Windows-Komponenten. Sie können sie als Möglichkeit nutzen, Code und Ressourcen freizugeben, Ihre Apps zu verkleinern und die Wartung und Erweiterung Ihrer Apps zu vereinfachen. In dieser exemplarischen Vorgehensweise erstellen Sie eine DLL, die einige mathematische Funktionen implementiert. Danach erstellen Sie eine Konsolen-App, die die Funktionen aus der DLL verwendet. Im Verlauf dieser Vorgehensweise erhalten Sie eine Einführung in einige der Programmierungstechniken und -konventionen, die in Windows-DLLs zum Einsatz kommen.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- Erstellen eines DLL-Projekts in Visual Studio

- Hinzufügen von exportierten Funktionen und Variablen zur DLL

- Erstellen eines Konsolen-App-Projekts in Visual Studio

- Verwenden der aus der DLL importierten Funktionen und Variablen in der Konsolen-App

- Ausführen der fertigen App

Wie eine statisch verknüpfte Bibliothek _exportiert_ eine DLL Variablen, Funktionen und Ressourcen anhand des Namens, und Ihre App _importiert_ diese Namen, um diese Variablen, Funktionen und Ressourcen zu verwenden. Im Gegensatz zu einer statisch verknüpften Bibliothek stellt Windows die Verbindung zwischen den Importen in Ihrer App und den Exporten in einer DLL zur Lade- oder Laufzeit her, nicht zum Zeitpunkt der Verknüpfung. Zum Herstellen dieser Verbindungen erfordert Windows zusätzliche Informationen, die nicht Bestandteil des standardmäßigen C++-Kompilierungsmodells sind. Der MSVC-Compiler implementiert einige Microsoft-spezifische Erweiterungen für C++, um diese zusätzlichen Informationen bereitzustellen. Wir werden diese Erweiterungen im weiteren Verlauf näher erläutern.

In dieser exemplarischen Vorgehensweise werden zwei Visual Studio-Projektmappen erstellt: eine, die die DLL kompiliert, und eine andere, die die Client-App kompiliert. Die DLL nutzt die Aufrufkonvention von C und kann daher von Apps aufgerufen werden, die in anderen Sprachen geschrieben wurden, vorausgesetzt, Plattform sowie Aufruf- und Verknüpfungskonventionen stimmen überein. Die Client-App verwendet _implizite Verknüpfungen_, bei denen Windows die App zur Ladezeit mit der DLL verknüpft. Dank dieser Art der Verknüpfung kann die App die von der DLL bereitgestellten Funktionen genauso nutzen wie die Funktionen in einer statisch verknüpften Bibliothek.

In dieser exemplarischen Vorgehensweise werden einige gängige Situationen nicht behandelt. Die Verwendung von C++-DLLs durch andere Programmiersprachen wird nicht gezeigt. Die Erstellung einer DLL nur für Ressourcen wird nicht erläutert. Auch die Verwendung von expliziten Verknüpfungen zum Laden von DLLs zur Laufzeit statt zur Ladezeit wird nicht behandelt. Wir sind sicher, dass Sie Visual Studio verwenden können, um all diese Aufgaben auszuführen. Links mit weiteren Informationen zu DLLs finden Sie im Artikel [Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md). Weitere Informationen zu impliziten und expliziten Verknüpfungen finden Sie unter [Bestimmen der geeigneten Verknüpfungsmethode](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). Informationen zum Erstellen von C++-DLLs zur Verwendung mit Programmiersprachen, die Verknüpfungskonventionen der Sprache C verwenden, finden Sie unter [Exportieren von C++-Funktionen zur Verwendung in ausführbaren C-Dateien](exporting-cpp-functions-for-use-in-c-language-executables.md). Informationen zum Erstellen von DLLs zur Verwendung mit .NET-Sprachen finden Sie unter [Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](calling-dll-functions-from-visual-basic-applications.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

- Ein Computer, auf dem Microsoft Windows 7 oder eine höhere Version ausgeführt wird. Für ein optimales Entwicklungserlebnis empfehlen wir Windows 10.

- Eine Kopie von Visual Studio. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen Sie sicher, dass die Workload **Desktopentwicklung mit C++** aktiviert ist. Machen Sie sich keine Sorgen, wenn Sie diese Workload beim Installieren von Visual Studio nicht installiert haben. Sie können das Installationsprogramm erneut ausführen und die Workload jetzt installieren.

   ![Desktopentwicklung mit C++](media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Grundkenntnisse der Verwendung der Visual Studio-IDE. Wenn Sie bereits früher Windows-Desktop-Apps verwendet haben, dürften keine Verständnisprobleme auftreten. Eine Einführung finden Sie unter [Willkommen in der Visual Studio-IDE](/visualstudio/ide/visual-studio-ide).

- Grundlegende Kenntnisse der Programmiersprache C++. Keine Sorge: Wir verwenden keine allzu komplizierten Verfahren.

## <a name="create-the-dll-project"></a>Erstellen des DLL-Projekts

Mit den folgenden Aufgaben erstellen Sie ein Projekt für Ihre DLL, fügen Code hinzu, und kompilieren das Projekt. Als Erstes starten Sie die Visual Studio-IDE und melden sich ggf. an. Die Anweisungen variieren leicht, je nachdem, welche Version von Visual Studio Sie verwenden. Stellen Sie sicher, dass Sie in der Dropdownliste links oben auf dieser Seite die richtige Version ausgewählt haben.

::: moniker range="=vs-2019"

### <a name="to-create-a-dll-project-in-visual-studio-2019"></a>So erstellen Sie ein DLL-Projekt in Visual Studio 2019

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

   ![Erstellen eines neuen DLL-Projekts](media/create-new-dll-project-2019.png "Erstellen des MathLibrary-Projekts")

1. Legen Sie oben im Dialogfeld die **Sprache** auf **C++** , die **Plattform** auf **Windows** und den **Projekttyp** auf **Bibliothek** fest. 

1. Wählen Sie aus der gefilterten Projekttypliste **Dynamic Link Library (DLL)** aus, und klicken Sie auf **Weiter**. Geben Sie auf der nächsten Seite `MathLibrary` als Projektnamen in das Feld **Name** ein, und geben Sie den Projektspeicherort an, falls gewünscht.

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-dll-project-in-visual-studio-2017"></a>So erstellen Sie ein DLL-Projekt in Visual Studio 2017

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.

1. Erweitern Sie im linken Bereich des Dialogfelds **Neues Projekt** den Eintrag **Installiert** und ggf. **Visual C++** , und wählen Sie dann **Windows Desktop** aus. Wählen Sie im mittleren Bereich **Windows-Desktop-Assistent** aus. Geben Sie `MathLibrary` als Projektnamen im Textfeld **Name** ein.

   ![Benennen des MathLibrary-Projekts](media/mathlibrary-new-project-name-153.png "Benennen des MathLibrary-Projekts")

1. Klicken Sie auf **OK**, um das Dialogfeld **Neues Projekt** zu schließen und den Assistenten **Windows-Desktopprojekt** zu starten.

1. Wählen Sie im Assistenten **Windows-Desktopprojekt** und **Anwendungstyp** den Eintrag **Dynamic Link Library (DLL)** aus.

   ![Erstellen der DLL im Windows-Desktopprojekt-Assistenten](media/mathlibrary-desktop-project-wizard-dll.png "Erstellen der DLL im Windows-Desktopprojekt-Assistenten")

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen.

> [!NOTE]
> Um ein Problem in Visual Studio 2017 Version 15.3 zu beheben, sind weitere Schritt erforderlich. Führen Sie die folgenden Anweisungen aus, um zu ermitteln, ob Sie diese Änderung vornehmen müssen.
>
>1. Wählen Sie im **Projektmappen-Explorer** unter **Projektmappe „MathLibrary“** das Projekt **MathLibrary** aus.
>
>1. Klicken Sie in der Menüleiste auf **Projekt** > **Eigenschaften**.
>
>1. Wählen Sie im linken Bereich des Dialogfelds **Eigenschaftenseiten** unter **Konfigurationseigenschaften** > **C++** den Eintrag **Präprozessor** aus. Überprüfen Sie den Inhalt der Eigenschaft **Präprozessordefinitionen**.<br/><br/>![Überprüfen der Eigenschaft „Präprozessordefinitionen“](media/mathlibrary-153bug-preprocessor-definitions-check.png "Überprüfen der Eigenschaft „Präprozessordefinitionen“")<br/><br/>Wenn in der Liste **Präprozessordefinitionen** der Eintrag **MATHLIBRARY&#95;EXPORTS** angezeigt wird, müssen Sie nichts ändern. Wenn stattdessen **MathLibrary&#95;EXPORTS** angezeigt wird, müssen Sie die folgenden Schritte ausführen.
>
>1. Ändern Sie oben im Dialogfeld **Eigenschaftenseiten** die Dropdownliste **Konfiguration** zu **Alle Konfigurationen**.
>
>1. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Präprozessordefinitionen** aus, und klicken Sie auf **Bearbeiten**.<br/><br/>![Bearbeiten der Eigenschaft „Präprozessordefinitionen“](media/mathlibrary-153bug-preprocessor-definitions-property.png "Bearbeiten der Eigenschaft „Präprozessordefinitionen“")
>
>1. Fügen Sie im oberen Bereich der **Präprozessordefinitionen** das neue Symbol `MATHLIBRARY_EXPORTS` hinzu.<br/><br/>![Hinzufügen des MATHLIBRARY_EXPORTS-Symbols](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "Hinzufügen des MATHLIBRARY_EXPORTS-Symbols")
>
>1. Klicken Sie auf **OK**, um das Dialogfeld **Präprozessordefinitionen** zu schließen, und klicken Sie dann erneut auf **OK**, um Ihre Änderungen an den Projekteigenschaften zu speichern.

::: moniker-end

::: moniker range="=vs-2015"

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>So erstellen Sie ein DLL-Projekt in älteren Versionen von Visual Studio

1. Wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Erweitern Sie im linken Bereich des Dialogfelds **Neues Projekt** den Eintrag **Installiert** > **Vorlagen**, und wählen Sie **Visual C++** aus. Klicken Sie dann im mittleren Bereich auf **Win32-Konsolenanwendung**. Geben Sie `MathLibrary` als Projektnamen im Bearbeitungsfeld **Name** ein.

   ![Benennen des MathLibrary-Projekts](media/mathlibrary-project-name.png "Benennen des MathLibrary-Projekts")

1. Klicken Sie auf **OK**, um das Dialogfeld **Neues Projekt** zu schließen und den **Win32-Anwendungs-Assistenten** zu starten.

   ![Win32-Anwendungs-Assistent – Übersicht](media/mathlibrary-project-wizard-1.png "Win32-Anwendungs-Assistent – Übersicht")

1. Klicken Sie auf **Weiter**. Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **DLL** aus.

   ![Erstellen der DLL im Win32-Anwendungs-Assistenten](media/mathlibrary-project-wizard-2.png "Erstellen der DLL im Win32-Anwendungs-Assistenten")

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Wenn der Assistent die Projektmappe erstellt hat, sehen Sie das generierte Projekt und die Quelldateien in Visual Studio im Fenster **Projektmappen-Explorer**.

![Generierte Projektmappe in Visual Studio](media/mathlibrary-solution-explorer-153.png "Generierte Projektmappe in Visual Studio")

Im Moment ist diese DLL noch nicht besonders nützlich. Als Nächstes erstellen Sie die Headerdatei, um die Funktionen zu deklarieren, die von der DLL exportiert werden. Danach fügen Sie die Funktionsdefinitionen zur DLL hinzu, um sie nützlicher zu machen.

::: moniker-end

### <a name="to-add-a-header-file-to-the-dll"></a>So fügen Sie der DLL eine Headerdatei hinzu

1. Um eine Headerdatei für Ihre Funktionen zu erstellen, wählen Sie auf der Menüleiste **Projekt** > **Neues Element hinzufügen** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** die Option **Visual C++** aus. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)** . Geben Sie `MathLibrary.h` als Namen für die Headerdatei an.

   ![Hinzufügen des Headers im Dialogfeld „Neues Element hinzufügen“](media/mathlibrary-add-new-item-header-file.png "Hinzufügen des Headers im Dialogfeld „Neues Element hinzufügen“")

1. Klicken Sie auf die Schaltfläche **Hinzufügen**, um eine leere Headerdatei zu generieren, die in einem neuen Editor-Fenster angezeigt wird.

   ![Leere MathLibrary.h-Datei im Editor](media/edit-empty-mathlibrary-header.png "Leere MathLibrary.h-Datei im Editor")

1. Ersetzen Sie den Inhalt der Headerdatei durch diesen Code:

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

Diese Headerdatei deklariert einige Funktionen, um mit zwei Anfangswerten eine generalisierte Fibonacci-Folge zu erstellen. Ein Aufruf von `fibonacci_init(1, 1)` generiert die bekannte Fibonacci-Zahlenfolge.

Beachten Sie die Präprozessoranweisungen am Anfang der Datei. Standardmäßig fügt die Vorlage „Neues Projekt“ für eine DLL **\<em>PROJEKTNAME\</em>&#95;EXPORTS** zu den definierten Präprozessormakros für das DLL-Projekt hinzu. In diesem Beispiel definiert Visual Studio **MATHLIBRARY&#95;EXPORTS**, wenn Ihr MathLibrary-DLL-Projekt erstellt wird. 

::: moniker range="=vs-2017"

(Der Assistent in Visual Studio 2017 Version 15.3 erzwingt keine Schreibung in Großbuchstaben für diese Symboldefinition. Wenn Sie Ihr Projekt „MathLibrary“ nennen, wird das Symbol als „MathLibrary&#95;EXPORTS“ definiert, nicht als „MATHLIBRARY&#95;EXPORTS“. Dies ist der Grund für die zusätzlichen Schritte zum Hinzuzufügen dieses Symbols.)

::: moniker-end

Wenn das **MATHLIBRARY&#95;EXPORTS**-Makro definiert ist, legt das **MATHLIBRARY&#95;API**-Makro den Modifizierer `__declspec(dllexport)` in den Funktionsdeklarationen fest. Dieser Modifizierer weist den Compiler und Linker an, eine Funktion oder Variable aus der DLL zu exportieren, sodass sie von anderen Anwendungen verwendet werden kann. Wenn **MATHLIBRARY&#95;EXPORTS** nicht definiert ist, weil beispielsweise die Headerdatei in einer Clientanwendung enthalten ist, wendet **MATHLIBRARY&#95;API** den Modifizierer `__declspec(dllimport)` auf die Deklarationen an. Dieser Modifizierer optimiert den Import der Funktion oder Variablen in eine Anwendung. Weitere Informationen finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>So fügen Sie der DLL eine Implementierung hinzu

::: moniker range="vs-2019"

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Quelldateien**, und fügen Sie eine neue .cpp-Datei namens `MathLibrary.cpp` auf die gleiche Weise hinzu wie die neue Headerdatei im vorherigen Schritt.

::: moniker-end

1. Wählen Sie im Editor-Fenster die Registerkarte für **MathLibrary.cpp** aus, wenn diese bereits geöffnet ist. Andernfalls öffnen Sie im **Projektmappen-Explorer** die Datei **MathLibrary.cpp** im Ordner **Quelldateien** des Projekts **MathLibrary**.

1. Ersetzen Sie im Editor den Inhalt der Datei „MathLibrary.cpp“ durch den folgenden Code:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h" // use pch.h in Visual Studio 2019
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

Um zu überprüfen, ob alles funktioniert, kompilieren Sie die Dynamic Link Library. Wählen Sie hierzu auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Die Ausgabe sollte in etwa wie folgt aussehen. Beachten Sie, dass die ausführbare DLL-Datei und die zugehörige Compilerausgabe in einem Ordner namens *Debug* direkt unterhalb des Projektmappenordners Wenn Sie einen Releasebuild erstellen, wird die Ausgabe in einem Ordner namens *Release*abgelegt:

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch, Sie haben mithilfe von Visual Studio eine DLL erstellt. Als Nächstes erstellen Sie eine Client-App, die die von der DLL exportierten Funktionen verwendet.

## <a name="create-a-client-app-that-uses-the-dll"></a>Erstellen einer Client-App, die die DLL verwendet

Wenn Sie eine DLL erstellen, müssen Sie überlegen, wie diese DLL verwendet werden kann. Um Code zu kompilieren, der die von einer DLL exportierten Funktionen aufruft, müssen die Deklarationen im Clientquellcode enthalten sein. Wenn diese Aufrufe von DLL-Funktionen zum Zeitpunkt der Verknüpfung aufgelöst werden, muss der Linker über eine *Importbibliothek* verfügen – eine besondere Bibliothek, die anstelle des tatsächlichen Codes Informationen für Windows zum Auffinden der Funktionen enthält. Zur Laufzeit muss die DLL dem Client an einem Speicherort zur Verfügung stehen, den das Betriebssystem finden kann.

Um eine DLL zu nutzen – unabhängig davon, ob es Ihre eigene oder eine Drittanbieter-DLL ist –, muss Ihr Client-App-Projekt die Header, die die DLL-Exporte deklarieren, die Importbibliotheken für den Linker und die DLL selbst finden. Eine Möglichkeit, um dies zu erreichen, besteht darin, all diese Dateien in Ihr Clientprojekt zu kopieren. Da Drittanbieter-DLLs sich während der Entwicklung Ihres Clients wahrscheinlich nicht ändern, ist diese Methode möglicherweise die beste. Wenn Sie jedoch auch die DLL erstellen, sollten Sie eine Duplizierung besser vermeiden. Wenn Sie eine Kopie der DLL-Dateien erstellen, die sich noch in der Entwicklungsphase befinden, könnte es passieren, dass Sie versehentlich eine Headerdatei nur in einer Kopie der DLL ändern oder eine veraltete Bibliothek verwenden. Um dieses Problem zu vermeiden, empfiehlt es sich, den Includepfad in Ihrem Clientprojekt festzulegen, um die DLL-Headerdateien aus dem DLL-Projekt einzuschließen. Legen Sie auch den Bibliothekspfad in Ihrem Clientprojekt so fest, dass die DLL-Importbibliotheken aus dem DLL-Projekt eingeschlossen sind. Zum Schluss kopieren Sie die kompilierte DLL aus dem DLL-Projekt in das Buildausgabeverzeichnis. Mit diesem Schritt ermöglichen Sie es der Client-App, denselben DLL-Code zu verwenden.

::: moniker range="vs-2019"

### <a name="to-create-a-client-app-in-visual-studio-2019"></a>So erstellen Sie eine Client-App in Visual Studio 2019

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

1. Legen Sie oben im Dialogfeld die **Sprache** auf **C++** , die **Plattform** auf **Windows** und den **Projekttyp** auf **Konsole** fest. 

1. Wählen Sie aus der gefilterten Projekttypliste **Konsolen-App** aus, und klicken Sie auf **Weiter**. Geben Sie auf der nächsten Seite `MathClient` als Projektnamen in das Feld **Name** ein, und geben Sie den Projektspeicherort an, falls gewünscht.

   ![Benennen des Clientprojekts](media/mathclient-project-name-2019.png "Benennen des Clientprojekts")

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Clientprojekt zu erstellen.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-client-app-in-visual-studio-2017"></a>So erstellen Sie eine Client-App in Visual Studio 2017

1. Um eine C++-App zu erstellen, die die erstellte DLL verwendet, wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Projekt** unter **Installiert** > **Visual C++** den Eintrag **Windows Desktop** aus. Wählen Sie im mittleren Bereich **Windows-Desktop-Assistent** aus. Geben Sie `MathClient` als Projektnamen im Bearbeitungsfeld **Name** ein.

   ![Benennen des Clientprojekts](media/mathclient-new-project-name-153.png "Benennen des Clientprojekts")

1. Klicken Sie auf **OK**, um den **Windows-Desktopprojekt-Assistenten** zu starten. Klicken Sie im Assistenten auf **OK**, um das Client-App-Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>So erstellen Sie eine Client-App in älteren Versionen von Visual Studio 2017

1. Um eine C++-App zu erstellen, die die erstellte DLL verwendet, wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Projekt** unter **Installiert** > **Vorlagen** > **Visual C++** den Eintrag **Win32** aus. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus. Geben Sie `MathClient` als Projektnamen im Bearbeitungsfeld **Name** ein.

   ![Benennen des Clientprojekts](media/mathclient-project-name.png "Benennen des Clientprojekts")

1. Klicken Sie auf **OK**, um das Dialogfeld **Neues Projekt** zu schließen und den **Win32-Anwendungs-Assistenten** zu starten. Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32-Anwendungs-Assistent** die Schaltfläche **Weiter** .

1. Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp**die Option **Konsolenanwendung** aus, falls diese nicht bereits ausgewählt ist.

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

::: moniker-end

Nach Abschluss des Assistenten wurde ein minimales Konsolenanwendungsprojekt für Sie erstellt. Der Name der Hauptquelldatei ist derselbe wie der Projektname, den Sie zuvor eingegeben haben. In diesem Beispiel lautet der Name **MathClient.cpp**. Sie können die App kompilieren, aber verwenden Sie noch nicht Ihre DLL.

Um die MathLibrary-Funktionen in Ihrem Quellcode aufrufen zu können, muss Ihr Projekt die Datei „MathLibrary.h“ enthalten. Sie könnten diese Headerdatei in Ihr Client-App-Projekt kopieren und dann als vorhandenes Element zum Projekt hinzufügen. Diese Methode ist für Drittanbieterbibliotheken möglicherweise eine gute Wahl. Wenn Sie jedoch gleichzeitig am Clientcode und am Code für Ihre DLL arbeiten, könnten sich Änderungen an einer Headerdatei ergeben, die in der anderen nicht widergespiegelt werden. Um dieses Problem zu vermeiden, können Sie den Pfad **Zusätzliche Includeverzeichnisse** im Projekt ändern, um den Pfad zum ursprünglichen Header einzuschließen.

### <a name="to-add-the-dll-header-to-your-include-path"></a>So fügen Sie den DLL-Header zum Includepfad hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **MathClient**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.

1. Wählen Sie im Dropdownfeld **Konfiguration** den Eintrag **Alle Konfigurationen** aus, falls dieser nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich unter **Konfigurationseigenschaften** > **C/C++** den Eintrag **Allgemein** aus.

1. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Includeverzeichnisse** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Includeverzeichnisse“](media/mathclient-additional-include-directories-property.png "Bearbeiten der Eigenschaft „Zusätzliche Includeverzeichnisse“")

1. Doppelklicken Sie im oberen Bereich des Dialogfelds **Zusätzliche Includeverzeichnisse**, um ein Bearbeitungssteuerelement zu aktivieren.

1. Geben Sie im Bearbeitungssteuerelement den Pfad zum Speicherort der Headerdatei **MathLibrary.h** an. Klicken Sie auf den Pfeil nach unten, und wählen Sie  **\<dann > Bearbeiten**aus. Sie können auf das Ordnersymbol und dann auf die Auslassungs Punkte ( **...** ) klicken, um zum richtigen Ordner zu navigieren.
 
   Auch in diesem Fall können Sie einen relativen Pfad aus dem Ordner eingeben, der die CPP-Dateien im Client Projekt enthält, in den Ordner, der die h-Datei im DLL-Projekt enthält. Wenn sich Ihr Clientprojekt im gleichen Ordner wie die DLL-Projektmappe, aber in einer anderen Projektmappe befindet, sollte der relative Pfad folgendermaßen aussehen:

   `..\MathLibrary\MathLibrary`

   Wenn sich die dll-und Client Projekte in derselben Projekt Mappe befinden oder sich die Projektmappen in unterschiedlichen Ordnern befinden, müssen Sie den relativen Pfad entsprechend anpassen oder den Ordner mithilfe der zuvor beschriebenen Methode suchen.

   ![Hinzufügen des Headerspeicherorts zur Eigenschaft „Zusätzliche Includeverzeichnisse“](media/mathclient-additional-include-directories.png "Hinzufügen des Headerspeicherorts zur Eigenschaft „Zusätzliche Includeverzeichnisse“")

1. Nachdem Sie den Pfad zur Header Datei im Dialogfeld **zusätzliche** Includeverzeichnisse eingegeben haben, klicken Sie auf die Schaltfläche **OK** , um zum Dialogfeld **Eigenschaften Seiten** zurückzukehren, und wählen Sie dann die Schaltfläche **OK** aus, um die Änderungen zu speichern.

Jetzt können Sie die Datei **MathLibrary.h** einschließen und die von dieser Datei deklarierten Funktionen in Ihrer Clientanwendung verwenden. Ersetzen Sie den Inhalt von **MathClient.cpp** durch diesen Code:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
// #include "pch.h" Uncomment for Visual Studio 2017 and earlier
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

Dieser Code kann kompiliert, aber nicht verknüpft werden, weil der Linker die Importbibliothek, die zum Kompilieren der App erforderlich ist, noch nicht findet. Der Linker muss die Datei „MathLibrary.lib“ finden, um erfolgreich eine Verknüpfung herstellen zu können. Fügen Sie die Datei „MathLibrary.lib“ zum Build hinzu, indem Sie die Eigenschaft **Zusätzliche Abhängigkeiten** festlegen. Auch hier gilt: Sie könnten die Bibliotheksdatei in Ihr Client-App-Projekt kopieren. Wenn sich aber sowohl Bibliothek als auch Client-App noch in der Entwicklungsphase befinden, könnte dies zu Änderungen in einer Kopie führen, die in der anderen nicht widergespiegelt werden. Um dieses Problem zu vermeiden, können Sie den Pfad **Zusätzliche Bibliotheksverzeichnisse** im Projekt ändern, um beim Verknüpfen den Pfad zur ursprünglichen Bibliothek einzuschließen.

### <a name="to-add-the-dll-import-library-to-your-project"></a>So fügen Sie die DLL-Importbibliothek zu Ihrem Projekt hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **MathClient**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.

1. Wählen Sie im Dropdownfeld **Konfiguration** den Eintrag **Alle Konfigurationen** aus, falls dieser nicht bereits ausgewählt ist. Diese Einstellung stellt sicher, dass der Pfad sowohl für den Debug- als auch den Releasebuild festgelegt ist.

1. Wählen Sie im linken Bereich unter **Konfigurationseigenschaften** > **Linker** den Eintrag **Eingabe** aus. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Abhängigkeiten** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Abhängigkeiten“](media/mathclient-additional-dependencies-property.png "Bearbeiten der Eigenschaft „Zusätzliche Abhängigkeiten“")

1. Fügen Sie im Dialogfeld **Zusätzliche Abhängigkeiten** die Datei `MathLibrary.lib` zur Liste im oberen Bearbeitungssteuerelement hinzu.

   ![Hinzufügen der Bibliotheksabhängigkeit](media/mathclient-additional-dependencies.png "Hinzufügen der Bibliotheksabhängigkeit")

1. Klicken Sie auf **OK**, um zum Dialogfeld **Eigenschaftenseiten** zurückzukehren.

1. Wählen Sie im linken Bereich unter **Konfigurationseigenschaften** > **Linker** den Eintrag **Allgemein** aus. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Bibliotheksverzeichnisse** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Bibliotheksverzeichnisse“](media/mathclient-additional-library-directories-property.png "Bearbeiten der Eigenschaft „Zusätzliche Bibliotheksverzeichnisse“")

1. Doppelklicken Sie im oberen Bereich des Dialogfelds **Zusätzliche Bibliotheksverzeichnisse**, um ein Bearbeitungssteuerelement zu aktivieren. Geben Sie im Bearbeitungssteuerelement den Pfad zum Speicherort der Datei **MathLibrary.lib** an. Sie befindet sich in einem Ordner `Debug` , der direkt unter Ihrem Projektmappenordner aufgerufen wird. Wenn Sie einen Releasebuild erstellen, wird die Ausgabe in einen Ordner mit dem `Release`Namen eingefügt. Sie können das folgende Makro verwenden, damit der Linker die dll finden kann, unabhängig davon, welche Art von Build Sie erstellen:

   **Visual Studio 2019:**

   `..\MathLibrary\$(IntDir)`

   **Visual Studio 2017 und früher:**

   `..\..\MathLibrary\$(IntDir)`

   ![Hinzufügen des Bibliotheksverzeichnisses](media/mathclient-additional-library-directories.png "Hinzufügen des Bibliotheksverzeichnisses")

1. Wenn Sie den Pfad zur Bibliotheksdatei im Dialogfeld **Zusätzliche Bibliotheksverzeichnisse** eingegeben haben, klicken Sie auf die Schaltfläche **OK**, um zum Dialogfeld **Eigenschaftenseiten** zurückzukehren.

Ihre Client-App kann jetzt erfolgreich kompiliert und verknüpft werden, aber noch sind nicht alle erforderlichen Komponenten für die Ausführung vorhanden. Wenn das Betriebssystem Ihre App lädt, sucht es nach der MathLibrary-DLL. Wenn die DLL in bestimmten Systemverzeichnissen, dem Umgebungspfad oder dem lokalen App-Verzeichnis nicht gefunden wird, kann die App nicht geladen werden. Eine Möglichkeit zum Vermeiden dieses Problems besteht darin, die DLL in das Verzeichnis zu kopieren, das Ihre ausführbare Clientdatei als Bestandteil des Buildprozesses enthält. Um die DLL zu kopieren, können Sie Ihrem Projekt ein **Postbuildereignis** mit einem Befehl hinzufügen, der die DLL in Ihr Buildausgabeverzeichnis kopiert. Der hier angegebene Befehl kopiert die DLL nur, wenn sie fehlt oder geändert wurde, und verwendet Makros, um Kopiervorgänge in die und aus den richtigen Debug- oder Releasespeicherorten für Ihre Konfiguration auszuführen.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>So kopieren Sie die DLL in einem Postbuildereignis

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **MathClient**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.

1. Wählen Sie im Dropdownfeld „Konfiguration“ den Eintrag **Alle Konfigurationen** aus, falls dieser nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich unter **Konfigurationseigenschaften** > **Buildereignisse** den Eintrag **Postbuildereignis** aus.

1. Wählen Sie im Eigenschaftenbereich das Bearbeitungssteuerelement im Feld **Befehlszeile** aus, und geben Sie folgenden Befehl ein:

   **Visual Studio 2019:**

   `xcopy /y /d "..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

    **Visual Studio 2017 und früher:**

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Hinzufügen des Postbuildbefehls](media/mathclient-post-build-command-line.png "Hinzufügen des Postbuildbefehls")

1. Klicken Sie auf die Schaltfläche **OK**, um die Änderungen an den Projekteigenschaften zu speichern.

Jetzt sind alle Elemente vorhanden, die benötigt werden, damit die Client-App kompiliert und ausgeführt werden kann. Kompilieren Sie die Anwendung, in dem Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** auswählen. Das **Ausgabe** Fenster in Visual Studio sollte in Abhängigkeit von Ihrer Version von Visual Studio etwa wie das folgende Beispiel aussehen:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch: Sie haben eine Anwendung erstellt, die Funktionen in Ihrer DLL aufruft! Führen Sie Ihre Anwendung jetzt aus, um zu sehen, was passiert. Klicken Sie in der Menüleiste auf **Debuggen** > **Ohne Debuggen**. Visual Studio öffnet ein Befehlsfenster, in dem das Programm ausgeführt wird. Der letzte Teil der Ausgabe sollte wie folgt aussehen:

![Starten der Client-App ohne Debuggen](media/mathclient-run-without-debugging.png "Starten der Client-App ohne Debuggen")

Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.

Sie haben eine DLL und eine Clientanwendung erstellt – nun können Sie damit experimentieren. Legen Sie beispielsweise Haltepunkte im Code der Client-App fest, und führen Sie die App im Debugger aus. Sehen Sie sich an, was passiert, wenn Sie einen Bibliotheksaufruf schrittweise ausführen. Fügen Sie der Bibliothek weitere Funktionen hinzu, oder schreiben Sie eine weitere Client-App, die Ihre DLL verwendet.

Wenn Sie Ihre App bereitstellen, müssen Sie auch die DLL bereitstellen, die von der App verwendet wird. Die einfachste Möglichkeit, die DLLs, die Sie erstellen oder von Drittanbietern einschließen, Ihrer App zur Verfügung zu stellen, besteht darin, diese DLLs im gleichen Verzeichnis bereitzustellen, in dem sich Ihre App befindet. Dies wird als *App-lokale Bereitstellung* bezeichnet. Weitere Informationen zur Bereitstellung finden Sie unter [Deployment in Visual C++](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](calling-dll-functions-from-visual-basic-applications.md)
