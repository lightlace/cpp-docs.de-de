---
title: Schwerwiegender Fehler C1083
ms.date: 09/01/2017
f1_keywords:
- C1083
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
ms.openlocfilehash: 522bc4a36be59d4e2c9425e50b1238eb9f4aba61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368057"
---
# <a name="fatal-error-c1083"></a>Schwerwiegender Fehler C1083

> Kann nicht geöffnet werden *Filetype* Datei: '*Datei*': *Nachricht*

Der Compiler generiert einen Fehler C1083, wenn er eine Datei dafür nicht finden kann. Es gibt viele mögliche Ursachen für diesen Fehler. Eine falsche Include-Suche Pfad oder die fehlende oder falsch geschriebenen Headerdateien sind die häufigsten Ursachen, aber andere Dateitypen und Probleme können auch dazu führen, dass C1083. Hier sind einige der häufigsten Gründe, warum der Compiler diesen Fehler generiert.

## <a name="the-specified-file-name-is-wrong"></a>Der angegebene Dateiname ist falsch

Der Name einer Datei wurde möglicherweise falsch geschrieben werden. Ein auf ein Objekt angewendeter

`#include <algorithm.h>`

Die von Ihnen gewünschte Datei wird möglicherweise nicht gefunden. Eine h-Dateinamenerweiterung keine für die meisten Headerdateien der C++-Standardbibliothek. Die \<Algorithmus > Header würde nicht gefunden werden. von diesem `#include` Richtlinie. Um dieses Problem zu beheben, stellen Sie sicher, dass die richtigen Dateinamen, wie im folgenden Beispiel eingegeben wird:

`#include <algorithm>`

Bestimmte Header der C-Laufzeitbibliothek befinden sich in einem Unterverzeichnis des Standardincludeverzeichnisses. Beispielsweise wenn sys/Types.h einschließen möchten, müssen, enthalten Sie den Namen des Sys-Unterverzeichnisses in die `#include` Richtlinie:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>Die Datei ist nicht in den Include-Suchpfad enthalten.

Der Compiler kann die Datei anhand der Suchregeln, die in einer `#include`- oder `#import`-Anweisung angegeben wurden, nicht finden. Z. B. bei der eine Header-Dateiname in Anführungszeichen eingeschlossen ist,

`#include "myincludefile.h"`

Dies weist den Compiler an, suchen Sie nach der Datei im gleichen Verzeichnis, das die Quelldatei, zuerst enthält, und suchen Sie in andere Speicherorte, die von der Buildumgebung angegeben. Wenn die Anführungszeichen einen absoluten Pfad enthalten, sucht der Compiler nur nach der Datei an diesem Speicherort. Wenn die Anführungszeichen einen relativen Pfad enthalten, sucht der Compiler nach der Datei im Verzeichnis relativ zum Quellverzeichnis.

Wenn der Name in spitze Klammern eingeschlossen ist,

`#include <stdio.h>`

der Compiler folgt einen Suchpfad angeben, die von der Buildumgebung definiert ist die **/i** -Compileroption verwenden, die **/x** -Compileroption verwenden, und die **INCLUDE** -Umgebungsvariablen angegeben. Weitere Informationen einschließlich genauerer Details über die Suchreihenfolge verwendet, um eine Datei zu suchen finden Sie unter [#include-Direktive (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) und [#import-Anweisung](../../preprocessor/hash-import-directive-cpp.md).

Wenn die Include-Dateien befinden sich in einem anderen Verzeichnis relativ zu Ihrem Quellverzeichnis, und Sie einen relativen Pfad in Ihrer #include-Direktiven, müssen Sie doppelte Anführungszeichen verwenden, anstatt die spitzen Klammern. Z. B. wenn MeinHeader.h Ihrer Header-Datei in einem Unterverzeichnis des Ihre Projektquellen Header namens ist, klicken Sie dann in diesem Beispiel nicht die Datei nicht finden und bewirkt, dass C1083:

`#include <headers\myheader.h>`

aber dieses Beispiel funktioniert:

`#include "headers\myheader.h"`

Relative Pfade können auch mit Verzeichnissen, auf dem Include-Suchpfad verwendet werden. Wenn Sie ein Verzeichnis zum Hinzufügen der **INCLUDE** Umgebungsvariable oder Ihre **Includeverzeichnisse** Pfad in Visual Studio nicht auch Teil des Pfads auf die Include-Anweisungen hinzufügen. Angenommen, Ihre Header befindet sich unter \path\example\headers\myheader.h, und Sie \path\example\headers\ zum Hinzufügen Ihrer **Includeverzeichnisse** Pfad in Visual Studio, aber das `#include` Richtlinie bezieht sich auf die Datei als

`#include <headers\myheader.h>`

Anschließend wird die Datei nicht gefunden. Verwenden Sie den richtigen Pfad relativ zu dem Verzeichnis, in den Include-Suchpfad angegeben. Sie können den Includesuchpfad in \path\example ändern, in diesem Beispiel\, oder entfernen Sie die OData-Pfadsegment Headers\ aus der `#include` Richtlinie.

## <a name="third-party-library-issues-and-vcpkg"></a>Bibliotheken von Drittanbietern Probleme und Vcpkg

Wenn dieser Fehler angezeigt wird, wenn Sie eine Drittanbieter-Bibliothek als Teil Ihres Builds konfigurieren möchten, sollten Sie [Vcpkg](../../vcpkg.md), im Visual C++ Paket-Manager zum Installieren und erstellen Sie die Bibliothek. Vcpkg unterstützt eine große und wachsende [Liste der Drittanbieter-Bibliotheken](https://github.com/Microsoft/vcpkg/tree/master/ports), und legt alle Eigenschaften und Abhängigkeiten, die als Teil des Projekts für erfolgreiche Builds erforderlich sind. Weitere Informationen finden Sie im zugehörigen [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) Posten.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>Die Datei befindet sich in Ihrem Projekt, aber nicht den Includesuchpfad

Auch wenn Headerdateien in aufgeführt sind **Projektmappen-Explorer** als Teil eines Projekts, die Dateien werden nur die vom Compiler gefundene, wenn sie vom auf die verwiesen werden ein `#include` oder `#import` -Direktive in einer Datenquelle Datei, und befinden sich in einer Suchpfad einschließen. Für unterschiedliche Buildtypen können unterschiedliche Suchpfade verwendet werden. Die **/x** Compiler-Option kann verwendet werden, um Verzeichnisse aus dem Include-Suchpfad auszuschließen. Dadurch können für verschiedene Builds unterschiedliche Includedateien verwendet werden, die denselben Namen besitzen, sich aber in unterschiedlichen Verzeichnissen befinden. Dies ist eine Alternative zur bedingten Kompilierung mithilfe von Präprozessorbefehlen. Weitere Informationen zu den **/x** -Compileroption verwenden, finden Sie unter [/x (ignorieren Sie Include-Standardpfad)](../../build/reference/x-ignore-standard-include-paths.md).

Korrigieren Sie zur Behebung dieses Problems den Pfad, den der Compiler für die Suche nach der eingeschlossenen oder importierten Datei verwendet. Ein neuen Projekt verwendet, Standardwert include-Suchpfade. Sie müssen möglicherweise den Includesuchpfad zum Hinzufügen eines Verzeichnisses für Ihr Projekt zu ändern. Wenn Sie in der Befehlszeile kompilieren, fügen Sie den Pfad zu der **EINSCHLIEßEN** Umgebungsvariable oder **/i** -Compileroption verwenden, um den Pfad zur Datei angeben.

Öffnen Sie zum Festlegen des includeverzeichnispfads in Visual Studio des Projekts das **Eigenschaftenseiten** Dialogfeld. Wählen Sie **VC++-Verzeichnisse** unter **Konfigurationseigenschaften** im linken Bereich, und bearbeiten Sie dann die **Includeverzeichnisse** Eigenschaft. Weitere Informationen zu den pro Benutzer und pro Projekt Verzeichnisse, die vom Compiler in Visual Studio durchsucht, finden Sie unter [VC++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md). Weitere Informationen zu den **/i** -Compileroption verwenden, finden Sie unter [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md).

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>Die Befehlszeile EINSCHLIEßEN oder LIB-Umgebung ist nicht festgelegt.

Beim Aufrufen des Compilers über die Befehlszeile werden Suchpfade oft mithilfe von Umgebungsvariablen angegeben. Wenn im Suchpfad von beschrieben die **INCLUDE** oder **LIB** Umgebungsvariablen nicht ordnungsgemäß festgelegt ist, kann ein Fehler C1083 generiert werden. Es wird dringend empfohlen, dass builds mit, dass eine Developer-eingabeaufforderungsverknüpfung die basic-Umgebung für die Befehlszeile festlegen. Weitere Informationen finden Sie unter [C-/C++ zu erstellen, in der Befehlszeile](../../build/building-on-the-command-line.md). Weitere Informationen zur Verwendung von Umgebungsvariablen finden Sie unter [Vorgehensweise: Verwenden von Umgebungsvariablen in einem Build](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).

## <a name="the-file-may-be-locked-or-in-use"></a>Die Datei kann gesperrt werden oder verwendet werden

Wenn Sie zum Bearbeiten oder Zugriff auf die Datei ein anderes Programm verwenden, kann er die Datei gesperrt haben. Versuchen Sie die Datei in das andere Programm zu schließen. Manchmal kann das andere Programm Visual Studio selbst sein, wenn Sie Optionen für die parallele Kompilierung verwenden. Wenn die Option für die parallele projekterstellung aktivieren ist den Fehler behoben, dann ist dies der Fall ist. Andere parallele projekterstellung Systeme können auch auf dieses Problem aufweisen. Achten Sie darauf, dass Datei- und Projektinformationen-Abhängigkeiten festlegen, damit die Buildreihenfolge richtig ist. In einigen Fällen empfiehlt sich, ein intermediate-Projekt zur Erzwingung der Reihenfolge der Build-Abhängigkeiten für eine gemeinsame-Datei, die von mehreren Projekten erstellt werden kann. Manchmal Antivirenprogramme Sperren vorübergehend zuletzt geänderte Dateien für die Überprüfung. Wenn möglich, Sie ggf. Ihre Project Build-Verzeichnisse aus der Virenscanner.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>Die falsche Version eines Dateinamens wird verwendet

Ein Fehler C1083 kann auch darauf hinweisen, dass die falsche Version einer Datei verwendet wird. Ein Build kann z. B. die falsche Version einer Datei enthalten, die eine nicht für diesen Build vorgesehene `#include`-Anweisung für eine Headerdatei aufweist. Z. B. bestimmte Dateien möglicherweise gelten nur für X86 erstellt wurde, oder klicken Sie auf der Debug-Builds. Wenn die Headerdatei nicht gefunden wird, generiert der Compiler einen Fehler C1083. Dieses Problem kann behoben werden, indem die richtige Datei verwendet wird. Durch Hinzufügen der Headerdatei oder des Verzeichnisses zum Build lässt sich das Problem nicht beheben.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>Die vorkompilierten Header sind noch nicht vorkompiliert

Wenn ein Projekt zur Verwendung vorkompilierter Header konfiguriert ist, müssen die entsprechenden PCH-Dateien erstellt werden, damit Dateien, die den Headerinhalt verwenden, kompiliert werden können. Die Datei "stdafx.cpp" wird beispielsweise automatisch im Projektverzeichnis für neue Projekte erstellt werden. Kompilieren Sie diese Datei zuerst, um die vorkompilierten Headerdateien zu erstellen. In der typischen buildprozessentwurf wird dieser automatisch durchgeführt. Weitere Informationen finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/creating-precompiled-header-files.md).

## <a name="additional-causes"></a>Weitere Ursachen

- Sie installiert haben, ein SDK oder eine Drittanbieter-Bibliothek, aber Sie haben ein neues Fenster der Developer-Eingabeaufforderung nicht geöffnet, nachdem das SDK oder Bibliothek wird installiert. Wenn das SDK oder die Bibliothek, Dateien in hinzufügt der **INCLUDE** Pfad müssen Sie möglicherweise ein neues Fenster der Developer-Eingabeaufforderung übernimmt diese Änderungen an dieser Umgebungsvariablen geöffnet.

- Die Datei verwendet verwalteten Code, aber die Compileroption **"/ CLR"** nicht angegeben ist. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

- Die Datei wird mit einer anderen kompiliert **/ analyze** Einstellung als zum Vorkompilieren der Header verwendet wird. Wenn der Header für ein Projekt vorkompiliert werden, sollten alle verwenden die gleiche **/ analyze** Einstellungen. Weitere Informationen finden Sie unter [/analyze (Codeanalyse)](../../build/reference/analyze-code-analysis.md).

- Die Datei oder Verzeichnis wurde vom Windows-Subsystem für Linux erstellt und im angegebene Fall eine Pfad- oder Dateiname entspricht nicht den Fall, der den Pfad oder die Datei auf dem Datenträger pro Verzeichnis Groß-/Kleinschreibung aktiviert ist.

- Die Datei, das Verzeichnis oder der Datenträger ist schreibgeschützt.

- Visual Studio oder die Befehlszeilentools haben keine ausreichende Berechtigungen zum Lesen der Datei oder das Verzeichnis. Dies kann beispielsweise auftreten, wenn die Projektdateien verschiedene Besitz als der Prozess, der mit Visual Studio oder die Befehlszeilentools zugewiesen werden. In einigen Fällen kann dieses Problem behoben werden, durch Ausführen von Visual Studio oder Developer-Eingabeaufforderung als Administrator.

- Es sind nicht genügend Dateihandles vorhanden. Schließen Sie einige Anwendungen, und kompilieren Sie dann erneut. Diese Bedingung ist unter normalen Umständen ungewöhnlich. Sie kann jedoch auftreten, wenn große Projekte auf einem Computer erstellt werden, dessen physischer Speicher beschränkt ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird ein Fehler C1083 generiert. wenn die Headerdatei `"test.h"` im Quellverzeichnis oder auf dem Include-Suchpfad nicht vorhanden.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

Weitere Informationen zum Erstellen von C/C++-Projekten in der IDE oder über die Befehlszeile und Informationen zum Festlegen von Umgebungsvariablen finden Sie unter [Projekte und Buildsysteme](../../build/projects-and-build-systems-cpp.md).

## <a name="see-also"></a>Siehe auch

- [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties)
