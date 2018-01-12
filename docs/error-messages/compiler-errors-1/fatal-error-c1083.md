---
title: Schwerwiegender Fehler C1083 | Microsoft Docs
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1083
dev_langs: C++
helpviewer_keywords: C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd929403afc86beabf185d099a79bfab5578482a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1083"></a>Schwerwiegender Fehler C1083

> Kann nicht geöffnet werden *Filetype* Datei: "*Datei*": *Nachricht*

Wenn er eine Datei finden kann, die erforderlich ist, generiert der Compiler einen Fehler C1083. Es gibt zahlreiche mögliche Ursachen für diesen Fehler. Eine falsche Include-Suche Pfad oder die fehlende oder falsch geschriebenen Headerdateien sind die häufigsten Ursachen, aber andere Dateitypen und Probleme können auch dazu führen, dass C1083. Hier sind einige der häufigsten Gründe, warum der Compiler diesen Fehler generiert.

## <a name="the-specified-file-name-is-wrong"></a>Der angegebene Dateiname ist falsch

Der Name einer Datei wurde möglicherweise falsch geschrieben werden. Ein auf ein Objekt angewendeter

`#include <algorithm.h>`

Die von Ihnen gewünschte Datei wird möglicherweise nicht gefunden. Die meisten Headerdateien der C++-Standardbibliothek keine Erweiterung .h-Datei. Die \<Algorithmus > Header würde nicht gefunden werden, von diesem `#include` Richtlinie. Um dieses Problem zu beheben, stellen Sie sicher, dass der richtige Dateiname, wie in diesem Beispiel eingegeben wird:

`#include <algorithm>`

Bestimmte Header der C-Laufzeitbibliothek befinden sich in einem Unterverzeichnis des Standardincludeverzeichnisses. Z. B. sys/Types.h einbeziehen möchten, müssen Sie den Namen des Sys-Unterverzeichnisses in einschließen der `#include` Richtlinie:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>Die Datei ist im Includepfad Suche nicht enthalten.

Der Compiler kann die Datei anhand der Suchregeln, die in einer `#include`- oder `#import`-Direktive angegeben wurden, nicht finden. Z. B. wenn der Name einer Headerdatei in Anführungszeichen eingeschlossen ist,

`#include "myincludefile.h"`

Das weist den Compiler an, suchen Sie nach der Datei im gleichen Verzeichnis, das zuerst die Quelldatei enthält, und suchen Sie in anderen Speicherorten, die durch die Buildumgebung angegeben. Wenn die Anführungszeichen einen absoluten Pfad enthalten, sucht der Compiler nur nach der Datei an diesem Speicherort. Wenn die Anführungszeichen einen relativen Pfad enthalten, sucht der Compiler nach der Datei im Verzeichnis relativ zum Quellverzeichnis.

Wenn der Name in spitze Klammern eingeschlossen ist,

`#include <stdio.h>`

der Compiler folgt einen Suchpfad, der durch die Buildumgebung definiert ist die **/i** -Compileroption verwenden, die **/x** (Compileroption), und die **INCLUDE** -Umgebungsvariablen angegeben. Weitere Informationen, einschließlich spezifische Details über die Suchreihenfolge verwendet, um eine Datei zu suchen, finden Sie unter [#include-Direktive (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) und [#import-Direktive](../../preprocessor/hash-import-directive-cpp.md).

Wenn die Include-Dateien befinden sich in einem anderen Verzeichnis relativ zum Quellverzeichnis, und Sie einen relativen Pfad in Ihrem #include-Direktiven hinzu, verwenden Sie doppelte Anführungszeichen, anstelle von spitzen Klammern. Angenommen, MeinHeader.h die Header-Datei in einem Unterverzeichnis des Projektquellen Header namens ist, klicken Sie dann in diesem Beispiel wird ein Fehler auftritt, um die Datei zu suchen und bewirkt, dass C1083:

`#include <headers\myheader.h>`

Dieses Beispiel funktioniert jedoch:

`#include "headers\myheader.h"`

Relative Pfade können auch mit Verzeichnisse auf Includepfad Suche verwendet werden. Wenn Sie ein Verzeichnis hinzufügen der **INCLUDE** -Umgebungsvariablen angegeben oder auf Ihre **Includeverzeichnisse** Pfad in Visual Studio nicht auch Teil des Pfads zu den Include-Direktiven hinzugefügt. Angenommen, Ihr Header befindet sich unter \path\example\headers\myheader.h und \path\example\headers\ zum Hinzufügen Ihrer **Includeverzeichnisse** Pfad in Visual Studio, aber das `#include` Richtlinie bezieht sich auf die Datei als

`#include <headers\myheader.h>`

Anschließend wird die Datei nicht gefunden. Verwenden Sie den richtigen Pfad relativ zum Verzeichnis angegeben, in der Include-Pfad durchsuchen. In diesem Beispiel können Sie Suche Includepfad in \path\example ändern\, oder entfernen Sie das Pfadsegment Headers\ aus der `#include` Richtlinie.

## <a name="third-party-library-issues-and-vcpkg"></a>Drittanbieter-Bibliothek Probleme und Vcpkg

Wenn dieser Fehler angezeigt, wenn Sie eine Bibliothek eines Drittanbieters als Teil Ihres Builds konfigurieren möchten, erwägen Sie [Vcpkg](../../vcpkg.md), die Visual C++ Paket-Manager, zum Installieren und die Bibliothek erstellen. Vcpkg unterstützt eine große und wachsende [Liste der Bibliotheken von Drittanbietern](https://github.com/Microsoft/vcpkg/tree/master/ports), und legt alle Konfigurationseigenschaften und Abhängigkeiten für erfolgreiche Builds, die als Teil Ihres Projekts erforderlich sind. Weitere Informationen finden Sie unter den zugehörigen [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) bereitstellen.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>Die Datei befindet sich in Ihrem Projekt, aber nicht den Include-Suchpfad

Auch wenn Headerdateien im aufgeführt sind **Projektmappen-Explorer** als Teil eines Projekts müssen die Dateien nur gefunden, durch den Compiler, wenn sie von bezeichnet werden ein `#include` oder `#import` -Direktive in einer Quelle Datei, und befinden sich in ein Suchpfad einschließen. Für unterschiedliche Buildtypen können unterschiedliche Suchpfade verwendet werden. Die **/x** -Compileroption kann verwendet werden, um Verzeichnisse aus dem Include-Pfad durchsuchen auszuschließen. Dadurch können für verschiedene Builds unterschiedliche Includedateien verwendet werden, die denselben Namen besitzen, sich aber in unterschiedlichen Verzeichnissen befinden. Dies ist eine Alternative zur bedingten Kompilierung mithilfe von Präprozessorbefehlen. Weitere Informationen zu den **/x** -Compileroption verwenden, finden Sie unter [/x (ignorieren Standard Standardincludepfad)](../../build/reference/x-ignore-standard-include-paths.md).

Korrigieren Sie zur Behebung dieses Problems den Pfad, den der Compiler für die Suche nach der eingeschlossenen oder importierten Datei verwendet. Verwendet standardmäßig eine neue Suche Includepfaden. Sie müssen möglicherweise so ändern Sie den Suchpfad einschließen, um ein Verzeichnis für das Projekt hinzuzufügen. Wenn Sie über die Befehlszeile kompilieren, fügen Sie den Pfad zu der **INCLUDE** -Umgebungsvariablen angegeben oder die **/i** Compileroption, um den Pfad zur Datei angeben.

Öffnen Sie zur Festlegung des includeverzeichnispfads in Visual Studio des Projekts **Eigenschaftenseiten** (Dialogfeld). Wählen Sie **VC++-Verzeichnisse** unter **Konfigurationseigenschaften** im linken Bereich, und bearbeiten Sie dann die **Includeverzeichnisse** Eigenschaft. Weitere Informationen zu den Erweiterungen pro Benutzer und pro Projekt Verzeichnisse, die vom Compiler in Visual Studio durchsucht, finden Sie unter [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md). Weitere Informationen zu den **/i** -Compileroption verwenden, finden Sie unter [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md).

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>Die Befehlszeile EINSCHLIEßEN oder LIB-Umgebung ist nicht festgelegt.

Beim Aufrufen des Compilers über die Befehlszeile werden Suchpfade oft mithilfe von Umgebungsvariablen angegeben. Wenn von der Suchpfad beschrieben die **INCLUDE** oder **LIB** -Umgebungsvariable nicht ordnungsgemäß festgelegt ist, kann ein Fehler C1083 generiert werden. Es wird dringend empfohlen, Builds mit einer Developer-eingabeaufforderungsverknüpfung die basic-Umgebung für die Befehlszeile festlegen. Weitere Informationen finden Sie unter finden Sie unter [C-/C++ erstellen, in der Befehlszeile](../../build/building-on-the-command-line.md). Weitere Informationen zur Verwendung von Umgebungsvariablen finden Sie unter [wie: Verwenden von Umgebungsvariablen in einem Build](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).

## <a name="the-file-may-be-locked-or-in-use"></a>Die Datei ist möglicherweise gesperrt, oder verwenden Sie in

Wenn Sie zum Bearbeiten oder Zugriff auf die Datei ein anderes Programm verwenden, kann es die Datei gesperrt haben. Schließen Sie die Datei in das andere Programm. In einigen Fällen kann das andere Programm Visual Studio selbst sein, bei Verwendung von parallelen Kompilierungsoptionen. Wenn die Option für die parallele Build aktivieren wird den Fehler behoben, ist dies das Problem. Andere parallele Builds Systeme können auch dieses Problem aufweisen. Achten Sie darauf, dass Datei- und Projektnamen-Abhängigkeiten festlegen, damit Buildreihenfolge für Ziele richtig ist. Sollten Sie in einigen Fällen in der Erstellung eines intermediate-Projekts zum Build Abhängigkeitsreihenfolge für eine Datei mit allgemeinen erzwingen, die mehrere Projekte erstellt werden kann. In einigen Fällen Antivirenprogramme Sperren vorübergehend zuletzt geänderte Dateien zum Scannen. Nach Möglichkeit erwägen, dass Sie Ihre Builds Projektverzeichnisse aus der Antivirenscanner auszuschließen.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>Die falsche Version eines Dateinamens wird verwendet

Ein Fehler C1083 kann auch darauf hinweisen, dass die falsche Version einer Datei verwendet wird. Ein Build kann z. B. die falsche Version einer Datei enthalten, die eine nicht für diesen Build vorgesehene `#include`-Direktive für eine Headerdatei aufweist. Z. B. bestimmte Dateien möglicherweise gelten nur für X86 erstellt wurde, oder um Debug-Builds. Wenn die Headerdatei nicht gefunden wird, generiert der Compiler einen Fehler C1083. Dieses Problem kann behoben werden, indem die richtige Datei verwendet wird. Durch Hinzufügen der Headerdatei oder des Verzeichnisses zum Build lässt sich das Problem nicht beheben.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>Die vorkompilierten Header sind noch nicht vorkompiliert

Wenn ein Projekt zur Verwendung vorkompilierter Header konfiguriert ist, müssen die entsprechenden PCH-Dateien erstellt werden, damit Dateien, die den Headerinhalt verwenden, kompiliert werden können. Beispielsweise wird die Datei "stdafx.cpp" im Projektverzeichnis für neue Projekte automatisch erstellt. Kompilieren Sie diese Datei zuerst, um die vorkompilierten Headerdateien zu erstellen. In den typischen buildprozessentwurf erfolgt dies automatisch. Weitere Informationen finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md).

## <a name="additional-causes"></a>Weitere Ursachen

- Ein SDK oder eine Bibliothek eines Drittanbieters installiert haben, aber Sie haben ein neues Developer-Eingabeaufforderungsfenster nicht geöffnet, nach dem das SDK oder Bibliothek installiert ist. Wenn das SDK oder Bibliothek fügt Dateien an die **INCLUDE** Pfad, müssen Sie möglicherweise ein neue Developer-Eingabeaufforderungsfenster zum Übernehmen von Änderungen an dieser Umgebungsvariablen zu öffnen.

- Die Datei verwendet verwalteten Code, aber die Compileroption " **" / CLR "** nicht angegeben wird. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

- Die Datei wird mit einer anderen kompiliert **/ analyze** Einstellung als zum Vorkompilieren der Header verwendet wird. Wenn der Header für ein Projekt vorkompiliert werden, sollten alle verwenden die gleiche **/ analyze** Einstellungen. Weitere Informationen finden Sie unter [/analyze (Codeanalyse)](../../build/reference/analyze-code-analysis.md).

- Die Datei, das Verzeichnis oder der Datenträger ist schreibgeschützt.

- Visual Studio oder die Befehlszeilentools verfügen nicht über ausreichende Berechtigungen zum Lesen der Datei oder das Verzeichnis über. Dies kann beispielsweise auftreten, wenn die Projektdateien anderen Besitzer als der Prozess, der mit Visual Studio oder die Befehlszeilentools zur Verfügung haben. In einigen Fällen kann dieses Problem korrigiert werden, indem Sie Visual Studio oder Developer-Eingabeaufforderung als Administrator ausführen.

- Es sind nicht genügend Dateihandles vorhanden. Schließen Sie einige Anwendungen, und kompilieren Sie dann erneut. Diese Bedingung ist unter normalen Umständen ungewöhnlich. Sie kann jedoch auftreten, wenn große Projekte auf einem Computer erstellt werden, dessen physischer Speicher beschränkt ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird ein Fehler C1083 generiert. wenn die Headerdatei `"test.h"` existiert nicht im Quellverzeichnis oder auf dem Include-Pfad durchsuchen.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

Informationen zum Erstellen von C/C++-Projekten in der IDE oder in der Befehlszeile und Informationen zum Festlegen von Umgebungsvariablen finden Sie [Erstellen eines C/C++-Programms](../../build/building-c-cpp-programs.md).

## <a name="see-also"></a>Siehe auch

[MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties)