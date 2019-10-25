---
title: 'Exemplarische Vorgehensweise: Erstellen und Verwenden Ihrer eigenen Dynamic Link Library (C++)'
description: Verwenden Sie C++, um in Visual Studio eine Dynamic Link Library (DLL) für Windows zu erstellen.
ms.custom: conceptual
ms.date: 08/22/2019
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 7bc0cb58cbbe995aa9d74e3ccb627ddc442bd4fb
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "70026032"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>Exemplarische Vorgehensweise: Erstellen und Verwenden Ihrer eigenen Dynamic Link Library (C++)

Diese schrittweise exemplarische Vorgehensweise veranschaulicht, wie Sie die Visual Studio-IDE verwenden, um eine eigene dll (Dynamic Link Library) zu erstellen C++ , die in Microsoft (MSVC) geschrieben wurde. Anschließend wird gezeigt, wie die dll aus einer anderen C++ App verwendet wird. DLLs (auch als frei *gegebene Bibliotheken* in UNIX-basierten Betriebssystemen bezeichnet) sind eine der nützlichsten Arten von Windows-Komponenten. Sie können Sie verwenden, um Code und Ressourcen freizugeben und die Größe Ihrer apps zu verkleinern. DLLs können sogar die Dienstleistung vereinfachen und ihre apps erweitern.

In dieser exemplarischen Vorgehensweise erstellen Sie eine DLL, die einige mathematische Funktionen implementiert. Anschließend erstellen Sie eine Konsolen-APP, die die Funktionen aus der dll verwendet. Außerdem erhalten Sie eine Einführung in einige der Programmiertechniken und Konventionen, die in Windows-DLLs verwendet werden.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben behandelt:

- Erstellen eines DLL-Projekts in Visual Studio

- Hinzufügen von exportierten Funktionen und Variablen zur DLL

- Erstellen eines Konsolen-App-Projekts in Visual Studio

- Verwenden der aus der DLL importierten Funktionen und Variablen in der Konsolen-App

- Ausführen der fertigen App

Wie eine statisch verknüpfte Bibliothek _exportiert_ eine DLL Variablen, Funktionen und Ressourcen nach dem Namen. Eine Client-App _importiert_ die Namen, um diese Variablen, Funktionen und Ressourcen zu verwenden. Im Gegensatz zu einer statisch verknüpften Bibliothek stellt Windows die Verbindung zwischen den Importen in Ihrer App und den Exporten in einer DLL zur Lade- oder Laufzeit her, nicht zum Zeitpunkt der Verknüpfung. Zum Herstellen dieser Verbindungen erfordert Windows zusätzliche Informationen, die nicht Bestandteil des standardmäßigen C++-Kompilierungsmodells sind. Der MSVC-Compiler implementiert einige Microsoft-spezifische Erweiterungen für C++, um diese zusätzlichen Informationen bereitzustellen. Wir werden diese Erweiterungen im weiteren Verlauf näher erläutern.

In dieser exemplarischen Vorgehensweise werden zwei Visual Studio-Projektmappen erstellt: eine, die die DLL kompiliert, und eine andere, die die Client-App kompiliert. Die dll verwendet die C-Aufruf Konvention. Sie kann von apps aufgerufen werden, die in anderen Programmiersprachen geschrieben wurden, solange die Plattform, die Aufruf Konventionen und die Verknüpfungs Konventionen übereinstimmen. Die Client-App verwendet _implizite Verknüpfungen_, bei denen Windows die App zur Ladezeit mit der DLL verknüpft. Dank dieser Art der Verknüpfung kann die App die von der DLL bereitgestellten Funktionen genauso nutzen wie die Funktionen in einer statisch verknüpften Bibliothek.

In dieser exemplarischen Vorgehensweise werden einige gängige Situationen nicht behandelt. Der Code zeigt nicht die Verwendung von C++ DLLs durch andere Programmiersprachen. Es zeigt nicht, wie [eine reine Ressourcen-DLL erstellt](creating-a-resource-only-dll.md)wird, oder wie die [explizite Verknüpfung](linking-an-executable-to-a-dll.md#linking-explicitly) zum Laden von DLLs zur Laufzeit anstatt zur Ladezeit verwendet wird. Wir sind sicher, dass Sie MSVC und Visual Studio verwenden können, um all diese Aufgaben auszuführen.

Links mit weiteren Informationen zu DLLs finden Sie im Artikel [Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md). Weitere Informationen über implizites verknüpfen und explizites Verknüpfen finden [Sie unter Bestimmen der zu verwendenden Verknüpfungs Methode](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). Weitere Informationen zum Erstellen C++ von DLLs für Programmiersprachen, in denen Verknüpfungs Konventionen in c-Sprache verwendet werden, finden Sie unter [exportieren C++ von Funktionen zur Verwendung in ausführbaren c-](exporting-cpp-functions-for-use-in-c-language-executables.md)Dateien. Informationen zum Erstellen von DLLs zur Verwendung mit .NET-Sprachen finden Sie unter [Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](calling-dll-functions-from-visual-basic-applications.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

- Ein Computer, auf dem Microsoft Windows 7 oder eine höhere Version ausgeführt wird. Für ein optimales Entwicklungserlebnis empfehlen wir Windows 10.

::: moniker range=">=vs-2017"

- Eine Kopie von Visual Studio. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen Sie sicher, dass die Workload **Desktopentwicklung mit C++** aktiviert ist. Machen Sie sich keine Sorgen, wenn Sie diese Workload beim Installieren von Visual Studio nicht installiert haben. Sie können das Installationsprogramm erneut ausführen und die Workload jetzt installieren.

   ![Desktopentwicklung mit C++](media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

::: moniker-end

::: moniker range="vs-2015"

- Eine Kopie von Visual Studio. Informationen zum herunterladen und Installieren von Visual Studio 2015 finden Sie unter [Installieren von Visual Studio 2015](/visualstudio/install/install-visual-studio-2015?view=vs-2015). Verwenden Sie eine **benutzerdefinierte** Installation, C++ um den Compiler und die Tools zu installieren, da Sie nicht standardmäßig installiert werden.

::: moniker-end

- Grundkenntnisse der Verwendung der Visual Studio-IDE. Wenn Sie bereits früher Windows-Desktop-Apps verwendet haben, dürften keine Verständnisprobleme auftreten. Eine Einführung finden Sie unter [Willkommen in der Visual Studio-IDE](/visualstudio/ide/visual-studio-ide).

- Grundlegende Kenntnisse der Programmiersprache C++. Keine Sorge: Wir verwenden keine allzu komplizierten Verfahren.

::: moniker range="vs-2017"

> [!NOTE]
> In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie Visual Studio 2017 Version 15,9 oder höher verwenden. In einigen früheren Versionen von Visual Studio 2017 waren Fehler in den Code Vorlagen aufgetreten, oder es wurden verschiedene Dialogfelder für die Benutzeroberfläche verwendet. Um Probleme zu vermeiden, verwenden Sie die Visual Studio-Installer, um Visual Studio 2017 auf Version 15,9 oder höher zu aktualisieren.

::: moniker-end

## <a name="create-the-dll-project"></a>Erstellen des DLL-Projekts

Mit den folgenden Aufgaben erstellen Sie ein Projekt für Ihre DLL, fügen Code hinzu, und kompilieren das Projekt. Als Erstes starten Sie die Visual Studio-IDE und melden sich ggf. an. Je nachdem, welche Version von Visual Studio Sie verwenden, sind die Anweisungen geringfügig unterschiedlich. Stellen Sie sicher, dass Sie in der Dropdownliste links oben auf dieser Seite die richtige Version ausgewählt haben.

::: moniker range=">=vs-2019"

### <a name="to-create-a-dll-project-in-visual-studio-2019"></a>So erstellen Sie ein DLL-Projekt in Visual Studio 2019

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

   ![Erstellen eines neuen DLL-Projekts](media/create-new-dll-project-2019.png "Erstellen des MathLibrary-Projekts")

1. Legen Sie oben im Dialogfeld die **Sprache** auf **C++** , die **Plattform** auf **Windows** und den **Projekttyp** auf **Bibliothek** fest.

1. Wählen Sie in der gefilterten Liste der Projekttypen die Option **Dynamic-Link Library (dll)** aus, und wählen Sie dann **weiter**aus.

1. Geben Sie auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen *MathLibrary* ein, um einen Namen für das Projekt anzugeben. Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Deaktivieren Sie **Projekt Mappe und Projekt im gleichen Verzeichnis** , wenn es aktiviert ist.

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Projekt zu erstellen.

Wenn die Projekt Mappe erstellt wird, können Sie die generierten Projekt-und Quelldateien im **Projektmappen-Explorer** Fenster in Visual Studio sehen.

![Generierte Projektmappe in Visual Studio](media/mathlibrary-solution-explorer-162.png "Generierte Projektmappe in Visual Studio")

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-dll-project-in-visual-studio-2017"></a>So erstellen Sie ein DLL-Projekt in Visual Studio 2017

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.

1. Wählen Sie im linken Bereich des Dialog Felds **Neues Projekt** die Option **installierter** >   > **Visual C++**  **Windows-Desktop**aus. Wählen Sie im mittleren Bereich die Option **Dynamic-Link Library (dll)** aus. Geben Sie im Feld **Name** den Namen *MathLibrary* ein, um einen Namen für das Projekt anzugeben. Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen** .

   ![Benennen des MathLibrary-Projekts](media/mathlibrary-new-project-name-159.png "Benennen des MathLibrary-Projekts")

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen.

Wenn die Projekt Mappe erstellt wird, können Sie die generierten Projekt-und Quelldateien im **Projektmappen-Explorer** Fenster in Visual Studio sehen.

![Generierte Projektmappe in Visual Studio](media/mathlibrary-solution-explorer-159.png "Generierte Projektmappe in Visual Studio")

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-dll-project-in-visual-studio-2015-and-older-versions"></a>So erstellen Sie ein DLL-Projekt in Visual Studio 2015 und älteren Versionen

1. Wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Erweitern Sie im linken Bereich des Dialogfelds **Neues Projekt** den Eintrag **Installiert** > **Vorlagen**, und wählen Sie **Visual C++** aus. Klicken Sie dann im mittleren Bereich auf **Win32-Konsolenanwendung**. Geben Sie im Bearbeitungsfeld **Name** den Namen *MathLibrary* ein, um einen Namen für das Projekt anzugeben. Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen** .

   ![Benennen des MathLibrary-Projekts](media/mathlibrary-project-name.png "Benennen des MathLibrary-Projekts")

1. Klicken Sie auf **OK**, um das Dialogfeld **Neues Projekt** zu schließen und den **Win32-Anwendungs-Assistenten** zu starten.

   ![Win32-Anwendungs-Assistent – Übersicht](media/mathlibrary-project-wizard-1.png "Win32-Anwendungs-Assistent – Übersicht")

1. Klicken Sie auf **Weiter**. Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **DLL** aus.

   ![Erstellen der DLL im Win32-Anwendungs-Assistenten](media/mathlibrary-project-wizard-2.png "Erstellen der DLL im Win32-Anwendungs-Assistenten")

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Wenn der Assistent die Projektmappe erstellt hat, sehen Sie das generierte Projekt und die Quelldateien in Visual Studio im Fenster **Projektmappen-Explorer**.

![Generierte Projektmappe in Visual Studio](media/mathlibrary-solution-explorer-153.png "Generierte Projektmappe in Visual Studio")

::: moniker-end

Im Moment ist diese DLL noch nicht besonders nützlich. Als Nächstes erstellen Sie eine Header Datei, um die von der dll exportierte Funktionen zu deklarieren, und fügen dann die Funktionsdefinitionen der dll hinzu, um Sie nützlicher zu gestalten.

### <a name="to-add-a-header-file-to-the-dll"></a>So fügen Sie der DLL eine Headerdatei hinzu

1. Um eine Headerdatei für Ihre Funktionen zu erstellen, wählen Sie auf der Menüleiste **Projekt** > **Neues Element hinzufügen** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** die Option **Visual C++** aus. Wählen Sie im mittleren Bereich die Option **Headerdatei (.h)** . Geben Sie *MathLibrary. h* als Namen für die Header Datei an.

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

Beachten Sie die Präprozessoranweisungen am Anfang der Datei. Die neue Projektvorlage für ein DLL-Projekt fügt den definierten Präprozessormakros  **_ProjectName_&#95;-Exporte** hinzu. In diesem Beispiel definiert Visual Studio **MATHLIBRARY&#95;EXPORTS**, wenn Ihr MathLibrary-DLL-Projekt erstellt wird.

Wenn das **MATHLIBRARY&#95;EXPORTS**-Makro definiert ist, legt das **MATHLIBRARY&#95;API**-Makro den Modifizierer `__declspec(dllexport)` in den Funktionsdeklarationen fest. Dieser Modifizierer weist den Compiler und den Linker an, eine Funktion oder Variable aus der dll zu exportieren, die von anderen Anwendungen verwendet werden soll. Wenn **MATHLIBRARY&#95;EXPORTS** nicht definiert ist, weil beispielsweise die Headerdatei in einer Clientanwendung enthalten ist, wendet **MATHLIBRARY&#95;API** den Modifizierer `__declspec(dllimport)` auf die Deklarationen an. Dieser Modifizierer optimiert den Import der Funktion oder Variablen in eine Anwendung. Weitere Informationen finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>So fügen Sie der DLL eine Implementierung hinzu

::: moniker range=">=vs-2019"

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Knoten **Quelldateien** , und wählen Sie**Neues Element** **Hinzufügen** > aus. Erstellen Sie eine neue cpp-Datei namens *MathLibrary. cpp*, auf dieselbe Weise, wie Sie eine neue Header Datei im vorherigen Schritt hinzugefügt haben.

1. Wählen Sie im Editor-Fenster die Registerkarte für **MathLibrary.cpp** aus, wenn diese bereits geöffnet ist. Wenn dies nicht der Fall ist, doppelklicken Sie in **Projektmappen-Explorer**im Ordner **Quelldateien** des Projekts **MathLibrary** auf **MathLibrary. cpp** , um es zu öffnen.

1. Ersetzen Sie im Editor den Inhalt der Datei „MathLibrary.cpp“ durch den folgenden Code:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "pch.h" // use stdafx.h in Visual Studio 2017 and earlier
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

::: moniker-end

::: moniker range="<=vs-2017"

1. Wählen Sie im Editor-Fenster die Registerkarte für **MathLibrary.cpp** aus, wenn diese bereits geöffnet ist. Wenn dies nicht der Fall ist, doppelklicken Sie in **Projektmappen-Explorer**im Ordner **Quelldateien** des Projekts **MathLibrary** auf **MathLibrary. cpp** , um es zu öffnen.

1. Ersetzen Sie im Editor den Inhalt der Datei „MathLibrary.cpp“ durch den folgenden Code:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h" // use pch.h in Visual Studio 2019 and later
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

::: moniker-end

Um zu überprüfen, ob alles funktioniert, kompilieren Sie die Dynamic Link Library. Wählen Sie hierzu auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Die dll und die zugehörige Compilerausgabe werden in einem Ordner namens *Debug* direkt unterhalb des Projektmappenordners abgelegt. Wenn Sie einen Releasebuild erstellen, wird die Ausgabe in einen Ordner namens *Release*eingefügt. Die Ausgabe sollte in etwa wie folgt aussehen:

::: moniker range=">=vs-2019"

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>pch.cpp
1>dllmain.cpp
1>MathLibrary.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

::: moniker-end

::: moniker range="vs-2017"

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>dllmain.cpp
1>MathLibrary.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

::: moniker-end

::: moniker range="vs-2015"

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

::: moniker-end

Herzlichen Glückwunsch, Sie haben mithilfe von Visual Studio eine DLL erstellt. Als Nächstes erstellen Sie eine Client-App, die die von der DLL exportierten Funktionen verwendet.

## <a name="create-a-client-app-that-uses-the-dll"></a>Erstellen einer Client-App, die die DLL verwendet

Wenn Sie eine DLL erstellen, stellen Sie sich vor, wie Sie von Client-Apps verwendet werden können. Um die Funktionen aufzurufen oder auf die von einer DLL exportierten Daten zuzugreifen, muss der Client Quellcode über die Deklarationen verfügen, die zur Kompilierzeit verfügbar sind. Zur Verknüpfungs Zeit benötigt der Linker Informationen zum Auflösen von Funktionsaufrufen oder Datenzugriffen. Eine dll stellt diese Informationen in einer *Import Bibliothek*bereit, einer Datei, die Informationen darüber enthält, wie Sie die Funktionen und Daten anstelle des eigentlichen Codes finden. Zur Laufzeit muss die DLL dem Client an einem Speicherort zur Verfügung stehen, den das Betriebssystem finden kann.

Unabhängig davon, ob es sich um Ihre eigenen oder von einem Drittanbieter handelt, benötigt Ihr Client-App-Projekt mehrere Informationen, um eine DLL zu verwenden. Es muss nach den Headern gesucht werden, die die DLL-Exporte, die Import Bibliotheken für den Linker und die DLL selbst deklarieren. Eine Lösung besteht darin, alle diese Dateien in das Client Projekt zu kopieren. Da Drittanbieter-DLLs sich während der Entwicklung Ihres Clients wahrscheinlich nicht ändern, ist diese Methode möglicherweise die beste. Wenn Sie jedoch auch die DLL erstellen, sollten Sie eine Duplizierung besser vermeiden. Wenn Sie eine lokale Kopie von DLL-Dateien erstellen, die sich in der Entwicklung befinden, können Sie eine Header Datei versehentlich in einer Kopie, aber nicht in der anderen ändern oder eine veraltete Bibliothek verwenden.

Um Code, der nicht synchron ist, zu vermeiden, empfiehlt es sich, den Includepfad in Ihrem Client Projekt so festzulegen, dass die DLL-Header Dateien direkt aus dem DLL-Projekt eingeschlossen werden. Legen Sie auch den Bibliothekspfad in Ihrem Clientprojekt so fest, dass die DLL-Importbibliotheken aus dem DLL-Projekt eingeschlossen sind. Kopieren Sie schließlich die erstellten DLL aus dem DLL-Projekt in das Ausgabeverzeichnis des Client Builds. Mit diesem Schritt ermöglichen Sie es der Client-App, denselben DLL-Code zu verwenden.

::: moniker range=">=vs-2019"

### <a name="to-create-a-client-app-in-visual-studio"></a>So erstellen Sie eine Client-app in Visual Studio

1. Wählen Sie in der Menüleiste **Datei** > **neu** > **Projekt** aus, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

1. Legen Sie oben im Dialogfeld die **Sprache** auf **C++** , die **Plattform** auf **Windows** und den **Projekttyp** auf **Konsole** fest.

1. Wählen Sie aus der gefilterten Projekttypliste **Konsolen-App** aus, und klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen *mathclient* ein, um einen Namen für das Projekt anzugeben. Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Deaktivieren Sie **Projekt Mappe und Projekt im gleichen Verzeichnis** , wenn es aktiviert ist.

   ![Benennen des Clientprojekts](media/mathclient-project-name-2019.png "Benennen des Clientprojekts")

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Clientprojekt zu erstellen.

Ein minimales Konsolen Anwendungsprojekt wird für Sie erstellt. Der Name der Hauptquelldatei ist derselbe wie der Projektname, den Sie zuvor eingegeben haben. In diesem Beispiel lautet der Name **MathClient.cpp**. Sie können die App kompilieren, aber verwenden Sie noch nicht Ihre DLL.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-client-app-in-visual-studio-2017"></a>So erstellen Sie eine Client-App in Visual Studio 2017

1. Um eine C++-App zu erstellen, die die erstellte DLL verwendet, wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Projekt** unter **Installiert** > **Visual C++** den Eintrag **Windows Desktop** aus. Wählen Sie im mittleren Bereich die Option **Windows-Konsolenanwendung**aus. Geben Sie im Bearbeitungsfeld **Name** den Namen für das Projekt *mathclient*an.  Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen** .

   ![Benennen des Clientprojekts](media/mathclient-new-project-name-159.png "Benennen des Clientprojekts")

1. Wählen Sie **OK** , um das Client-App-Projekt zu erstellen.

Ein minimales Konsolen Anwendungsprojekt wird für Sie erstellt. Der Name der Hauptquelldatei ist derselbe wie der Projektname, den Sie zuvor eingegeben haben. In diesem Beispiel lautet der Name **MathClient.cpp**. Sie können die App kompilieren, aber verwenden Sie noch nicht Ihre DLL.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-client-app-in-visual-studio-2015"></a>So erstellen Sie eine Client-app in Visual Studio 2015

1. Um eine C++-App zu erstellen, die die erstellte DLL verwendet, wählen Sie auf der Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Wählen Sie im linken Bereich des Dialogfelds **Neues Projekt** unter **Installiert** > **Vorlagen** > **Visual C++** den Eintrag **Win32** aus. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus. Geben Sie im Bearbeitungsfeld **Name** den Namen für das Projekt *mathclient*an. Belassen Sie die Standardwerte für **Speicherort** und Projektmappenname. Legen **Sie Projekt** Mappe zum **Erstellen einer neuen**Projekt Mappe fest. Aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen** .

   ![Benennen des Clientprojekts](media/mathclient-project-name.png "Benennen des Clientprojekts")

1. Klicken Sie auf **OK**, um das Dialogfeld **Neues Projekt** zu schließen und den **Win32-Anwendungs-Assistenten** zu starten. Wählen Sie auf der Seite **Übersicht** des Dialogfelds **Win32-Anwendungs-Assistent** die Schaltfläche **Weiter** .

1. Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp**die Option **Konsolenanwendung** aus, falls diese nicht bereits ausgewählt ist.

1. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.

Nach Abschluss des Assistenten wurde ein minimales Konsolenanwendungsprojekt für Sie erstellt. Der Name der Hauptquelldatei ist derselbe wie der Projektname, den Sie zuvor eingegeben haben. In diesem Beispiel lautet der Name **MathClient.cpp**. Sie können die App kompilieren, aber verwenden Sie noch nicht Ihre DLL.

::: moniker-end

Um die MathLibrary-Funktionen im Quellcode aufzurufen, muss das Projekt die Datei *MathLibrary. h* enthalten. Sie könnten diese Headerdatei in Ihr Client-App-Projekt kopieren und dann als vorhandenes Element zum Projekt hinzufügen. Diese Methode ist für Drittanbieterbibliotheken möglicherweise eine gute Wahl. Wenn Sie jedoch gleichzeitig mit dem Code für die dll und den Client arbeiten, sind die Header Dateien möglicherweise nicht mehr synchron. Um dieses Problem zu vermeiden, legen Sie den Pfad der **zusätzlichen Includeverzeichnisse** in Ihrem Projekt so fest, dass er den Pfad zum ursprünglichen Header einschließt.

### <a name="to-add-the-dll-header-to-your-include-path"></a>So fügen Sie den DLL-Header zum Includepfad hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **MathClient**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.

1. Wählen Sie im Dropdown Feld **Konfiguration** die Option **alle Konfigurationen** aus, sofern diese nicht bereits ausgewählt ist.

1. Klicken Sie im linken Bereich auf **Konfigurations Eigenschaften** > **C/C++**  > **Allgemein**.

1. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Includeverzeichnisse** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Includeverzeichnisse“](media/mathclient-additional-include-directories-property.png "Bearbeiten der Eigenschaft „Zusätzliche Includeverzeichnisse“")

1. Doppelklicken Sie im oberen Bereich des Dialogfelds **Zusätzliche Includeverzeichnisse**, um ein Bearbeitungssteuerelement zu aktivieren. Oder wählen Sie das Ordnersymbol aus, um einen neuen Eintrag zu erstellen.

1. Geben Sie im Bearbeitungssteuerelement den Pfad zum Speicherort der Headerdatei **MathLibrary.h** an. Sie können das Steuerelement mit den Auslassungs Punkten ( **...** ) auswählen, um zum richtigen Ordner zu navigieren.

   Sie können auch einen relativen Pfad von den Client Quelldateien in den Ordner eingeben, der die DLL-Header Dateien enthält. Wenn Sie die Anweisungen befolgt haben, um das Client Projekt in einer separaten Lösung von der dll abzulegen, sollte der relative Pfad wie folgt aussehen:

   `..\..\MathLibrary\MathLibrary`

   Wenn sich die dll-und Client Projekte in derselben Projekt Mappe befinden, könnte der relative Pfad wie folgt aussehen:

   `..\MathLibrary`

   Wenn sich die dll-und Client Projekte in anderen Ordnern befinden, passen Sie den relativen Pfad entsprechend an. Oder verwenden Sie das Ellipse-Steuerelement, um nach dem Ordner zu suchen.

   ![Hinzufügen des Headerspeicherorts zur Eigenschaft „Zusätzliche Includeverzeichnisse“](media/mathclient-additional-include-directories.png "Hinzufügen des Headerspeicherorts zur Eigenschaft „Zusätzliche Includeverzeichnisse“")

1. Nachdem Sie den Pfad zur Header Datei im Dialogfeld **Zusätzliche Includeverzeichnisse** eingegeben haben, klicken Sie auf die Schaltfläche **OK** . Wählen Sie im Dialogfeld **Eigenschaften Seiten** die Schaltfläche **OK** aus, um die Änderungen zu speichern.

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

Dieser Code kann kompiliert, jedoch nicht verknüpft werden. Wenn Sie die Client-App jetzt erstellen, werden in der Fehlerliste mehrere LNK2019-Fehler angezeigt. Das liegt daran, dass in Ihrem Projekt einige Informationen fehlen: Sie haben noch nicht angegeben, dass das Projekt noch eine Abhängigkeit von der *MathLibrary. lib* -Bibliothek aufweist. Und Sie haben den Linker nicht dazu aufgefordert, die Datei " *MathLibrary. lib* " zu finden.

Um dieses Problem zu beheben, können Sie die Bibliotheksdatei direkt in das Client-App-Projekt kopieren. Der Linker findet und verwendet ihn automatisch. Wenn sich jedoch sowohl die Bibliothek als auch die Client-app in der Entwicklungsphase befinden, kann dies zu Änderungen in einer Kopie führen, die nicht in der anderen angezeigt werden. Um dieses Problem zu vermeiden, können Sie die Eigenschaft **Zusätzliche Abhängigkeiten** festlegen, um dem Buildsystem mitzuteilen, dass das Projekt von *MathLibrary. lib*abhängig ist. Außerdem können Sie in Ihrem Projekt einen Pfad für **Weitere Bibliotheks Verzeichnisse** festlegen, um beim Verknüpfen den Pfad zur ursprünglichen Bibliothek einzuschließen.

### <a name="to-add-the-dll-import-library-to-your-project"></a>So fügen Sie die DLL-Importbibliothek zu Ihrem Projekt hinzu

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **mathclient** , und wählen Sie Eigenschaften, um das Dialogfeld **Eigenschaften** **Seiten** zu öffnen.

1. Wählen Sie im Dropdown Feld **Konfiguration** die Option **alle Konfigurationen** aus, sofern diese nicht bereits ausgewählt ist. Dadurch wird sichergestellt, dass alle Eigenschafts Änderungen für Debug-und Releasebuilds gelten.

1. Wählen Sie im linken Bereich die Option **Konfigurations Eigenschaften** > **Linker** > **Eingabe**aus. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Abhängigkeiten** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Abhängigkeiten“](media/mathclient-additional-dependencies-property.png "Bearbeiten der Eigenschaft „Zusätzliche Abhängigkeiten“")

1. Fügen Sie im Dialogfeld " **Zusätzliche Abhängigkeiten** " *MathLibrary. lib* der Liste im oberen Bearbeitungs Steuerelement hinzu.

   ![Hinzufügen der Bibliotheksabhängigkeit](media/mathclient-additional-dependencies.png "Hinzufügen der Bibliotheksabhängigkeit")

1. Klicken Sie auf **OK**, um zum Dialogfeld **Eigenschaftenseiten** zurückzukehren.

1. Klicken Sie im linken Bereich auf **Konfigurations Eigenschaften** > **Linker** > **Allgemein**. Wählen Sie im Eigenschaftenbereich das Dropdown-Steuerelement neben dem Bearbeitungsfeld für **Zusätzliche Bibliotheksverzeichnisse** aus, und klicken Sie auf **Bearbeiten**.

   ![Bearbeiten der Eigenschaft „Zusätzliche Bibliotheksverzeichnisse“](media/mathclient-additional-library-directories-property.png "Bearbeiten der Eigenschaft „Zusätzliche Bibliotheksverzeichnisse“")

1. Doppelklicken Sie im oberen Bereich des Dialogfelds **Zusätzliche Bibliotheksverzeichnisse**, um ein Bearbeitungssteuerelement zu aktivieren. Geben Sie im Bearbeitungssteuerelement den Pfad zum Speicherort der Datei **MathLibrary.lib** an. Standardmäßig befindet Sie sich in einem Ordner namens *Debuggen* direkt unter dem dll-Projektmappenordner. Wenn Sie einen Releasebuild erstellen, wird die Datei in einen Ordner namens *Release*eingefügt. Sie können das `$(IntDir)` -Makro verwenden, damit der Linker die dll finden kann, unabhängig davon, welche Art von Build Sie erstellen. Wenn Sie die Anweisungen befolgt haben, um das Client Projekt in eine separate Lösung aus dem DLL-Projekt einzufügen, sollte der relative Pfad wie folgt aussehen:

   `..\..\MathLibrary\$(IntDir)`

   Wenn sich die dll-und Client Projekte in derselben Projekt Mappe befinden, sollte der relative Pfad wie folgt aussehen:

   `..\MathLibrary\$(IntDir)`

   ![Hinzufügen des Bibliotheksverzeichnisses](media/mathclient-additional-library-directories.png "Hinzufügen des Bibliotheksverzeichnisses")

1. Wenn Sie den Pfad zur Bibliotheksdatei im Dialogfeld **Zusätzliche Bibliotheksverzeichnisse** eingegeben haben, klicken Sie auf die Schaltfläche **OK**, um zum Dialogfeld **Eigenschaftenseiten** zurückzukehren. Wählen Sie **OK** aus, um die Eigenschaften Änderungen zu speichern.

Ihre Client-App kann jetzt erfolgreich kompiliert und verknüpft werden, aber noch sind nicht alle erforderlichen Komponenten für die Ausführung vorhanden. Wenn das Betriebssystem Ihre App lädt, sucht es nach der MathLibrary-DLL. Wenn die DLL in bestimmten Systemverzeichnissen, dem Umgebungspfad oder dem lokalen App-Verzeichnis nicht gefunden wird, kann die App nicht geladen werden. Abhängig vom Betriebssystem wird eine Fehlermeldung wie die folgende angezeigt:

![Fehler bei der MathLibrary-dll nicht gefunden](media/mathclient-system-error-mathlibrary-dll-not-found.png "Fehler bei der MathLibrary-dll nicht gefunden") .

Eine Möglichkeit zum Vermeiden dieses Problems besteht darin, die DLL in das Verzeichnis zu kopieren, das Ihre ausführbare Clientdatei als Bestandteil des Buildprozesses enthält. Sie können Ihrem Projekt ein **Postbuildereignis** hinzufügen, um einen Befehl hinzuzufügen, mit dem die dll in das Buildausgabeverzeichnis kopiert wird. Der hier angegebene Befehl kopiert die dll nur, wenn Sie fehlt oder geändert wurde. Sie verwendet Makros, um basierend auf der Buildkonfiguration in die Debug-oder releasespeicherorte zu kopieren.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>So kopieren Sie die DLL in einem Postbuildereignis

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **mathclient** , und wählen Sie Eigenschaften, um das Dialogfeld **Eigenschaften** **Seiten** zu öffnen.

1. Wählen Sie im Dropdownfeld **Konfiguration** den Eintrag **Alle Konfigurationen** aus, falls dieser nicht bereits ausgewählt ist.

1. Wählen Sie im linken Bereich **Konfigurations Eigenschaften** > **Buildereignisse** > **Postbuildereignis**aus.

1. Wählen Sie im Eigenschaften Bereich im Feld **Befehlszeile** das Bearbeitungs Steuerelement aus. Wenn Sie die Anweisungen befolgt haben, um das Client Projekt in einer separaten Projekt Mappe aus dem DLL-Projekt zu platzieren, geben Sie den folgenden Befehl ein:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   Wenn sich die dll-und Client Projekte im selben Projektmappenverzeichnis befinden, geben Sie den folgenden Befehl ein:

   `xcopy /y /d "..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Hinzufügen des Postbuildbefehls](media/mathclient-post-build-command-line.png "Hinzufügen des Postbuildbefehls")

1. Klicken Sie auf die Schaltfläche **OK**, um die Änderungen an den Projekteigenschaften zu speichern.

Jetzt sind alle Elemente vorhanden, die benötigt werden, damit die Client-App kompiliert und ausgeführt werden kann. Kompilieren Sie die Anwendung, in dem Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** auswählen. Das **Ausgabe** Fenster in Visual Studio sollte in Abhängigkeit von Ihrer Version von Visual Studio etwa wie das folgende Beispiel aussehen:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Herzlichen Glückwunsch: Sie haben eine Anwendung erstellt, die Funktionen in Ihrer DLL aufruft! Führen Sie Ihre Anwendung jetzt aus, um zu sehen, was passiert. Klicken Sie in der Menüleiste auf **Debuggen** > **Ohne Debuggen**. Visual Studio öffnet ein Befehlsfenster, in dem das Programm ausgeführt wird. Der letzte Teil der Ausgabe sollte wie folgt aussehen:

![Starten der Client-App ohne Debuggen](media/mathclient-run-without-debugging.png "Starten der Client-App ohne Debuggen")

Drücken Sie eine beliebige Taste, um das Befehlsfenster zu schließen.

Sie haben eine DLL und eine Clientanwendung erstellt – nun können Sie damit experimentieren. Legen Sie beispielsweise Haltepunkte im Code der Client-App fest, und führen Sie die App im Debugger aus. Sehen Sie sich an, was passiert, wenn Sie einen Bibliotheksaufruf schrittweise ausführen. Fügen Sie der Bibliothek weitere Funktionen hinzu, oder schreiben Sie eine weitere Client-App, die Ihre DLL verwendet.

Wenn Sie Ihre App bereitstellen, müssen Sie auch die DLL bereitstellen, die von der App verwendet wird. Die einfachste Möglichkeit zum Erstellen von DLLs, die Sie erstellen, oder die Sie von Drittanbietern einschließen, besteht darin, Sie in demselben Verzeichnis wie Ihre APP zu platzieren. Es wird als *App-local-Bereitstellung*bezeichnet. Weitere Informationen zur Bereitstellung finden Sie unter [Deployment in Visual C++](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen heraus](calling-dll-functions-from-visual-basic-applications.md)
