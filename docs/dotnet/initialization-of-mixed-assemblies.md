---
title: Initialisierung gemischter Assemblys | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mixed assemblies [C++], loader lock
- loader lock [C++]
- initializing mixed assemblies
- deadlocks [C++]
- .cctor [C++]
- custom locales [C++]
- mixed assemblies [C++], initilizing
ms.assetid: bfab7d9e-f323-4404-bcb8-712b15f831eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 389246b6b002204260170fb44680c2756cd7aa6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="initialization-of-mixed-assemblies"></a>Initialisierung gemischter Assemblys

Windows-Entwickler müssen immer für die Loadersperre vorsichtig sein, beim Ausführen von Code während der `DllMain`. Es gibt jedoch einige zusätzliche Aspekte, die eine sprachbasierte, beim Umgang mit C möglich + c++ / im gemischten Modus von Clr-Assemblys.

Code in [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) darf nicht auf CLR zugreifen. Dies bedeutet, dass `DllMain` keine verwalteten Funktionen – weder direkt noch indirekt – aufrufen sollte; in `DllMain`sollte kein verwalteter Code deklariert oder implementiert werden; und in `DllMain`sollte weder eine Garbagecollection noch automatisches Laden der Bibliothek stattfinden.
  
## <a name="causes-of-loader-lock"></a>Ursachen für die Loadersperre

Mit der Einführung der .NET-Plattform stehen zwei verschiedene Mechanismen für das Laden eines Ausführungsmoduls (EXE oder DLL) zur Verfügung: einer für Windows, der für nicht verwaltete Module verwendet wird, und einer für die .NET-Common Language Runtime (CLR), der .NET-Assemblys lädt. Das Problem beim Laden gemischter DLLs konzentriert sich auf den Loader des Microsoft Windows-Betriebssystems.

Wenn eine Assembly, die nur .NET-Konstrukte enthält, in einen Prozess geladen wird, kann der CLR-Loader alle notwendigen Lade- und Initialisierungsaufgaben selbst ausführen. Jedoch muss bei gemischten Assemblys auch das Windows-Ladeprogramm verwendet werden, da sie nativen Code und native Daten enthalten können.

Das Windows-Ladeprogramm gewährleistet, dass kein Code auf Code oder Daten in dieser DLL zugreifen kann, bevor sie initialisiert ist, und dass kein Code die DLL redundant laden kann, während sie teilweise initialisiert ist. Zu diesem Zweck verwendet das Windows-Ladeprogramm einen (oft als „Ladeprogrammsperre“ bezeichneten) prozessglobalen kritischen Abschnitt , der unsicheren Zugriff während der Initialisierung des Moduls verhindert. Daher ist der Ladevorgang für viele klassische Deadlockszenarien anfällig. Bei gemischten Assemblys erhöhen die folgenden zwei Szenarien das Deadlockrisiko:

- Erstens kann ein Deadlock auftreten, wenn ein Benutzer versucht, in die Microsoft Intermediate Language (MSIL) kompilierte Funktionen auszuführen, wenn die Loadersperre aktiviert ist (z. B. aus `DllMain` oder in statischen Initialisierern). Nehmen wir den Fall an, dass die MSIL-Funktion auf einen Typ in einer Assembly verweist, die nicht geladen wurde. Die CLR versucht, diese Assembly automatisch zu laden, was erfordern kann, dass das Windows-Ladeprogramm von der Loadersperre blockiert wird. Da die Loadersperre bereits von Code aktiviert ist, der früher in der Aufrufsequenz vorkommt, tritt ein Deadlock auf. Die MSIL-Ausführung unter der Loadersperre garantiert jedoch nicht, dass ein Deadlock auftritt, sodass dieses Szenario schwierig zu diagnostizieren und reparieren ist. In einigen Fällen, wo z. B. die DLL des referenzierten Typs keine nativen Konstrukte enthält, und alle ihre Abhängigkeiten keine nativen Konstrukte enthalten, ist das Windows-Ladeprogramm nicht erforderlich, um die .NET-Assembly des referenzierten Typs zu laden. Darüber hinaus wurden die erforderliche Assembly oder ihre gemischten nativen/.NET-Abhängigkeiten möglicherweise bereits durch anderen Code geladen. Folglich kann die Vorhersage eines Deadlocks schwierig sein und abhängig von der Konfiguration des Zielcomputers variieren.

- Zweitens ging die CLR beim Laden von DLLs in den Versionen 1.0 und 1.1 von .NET Framework davon aus, dass die Loadersperre nicht aktiviert wurde, und führte verschiedene Aktionen aus, die unter der Loadersperre ungültig sind. Vorauszusetzen, dass die Loadersperre nicht aktiviert ist, gilt bei reinen .NET-DLLs, aber da gemischte DLLs native Initialisierungsroutinen ausführen, benötigen sie das native Windows-Ladeprogramm und somit die Loadersperre. Also bestand bei den Versionen 1.0 und 1.1 von .NET Framework auch dann die geringe Möglichkeit eines nichtdeterministischen Deadlocks, wenn der Entwickler nicht versuchte, MSIL-Funktionen während der DLL-Initialisierung auszuführen.

Der gesamte Nichtdeterminismus wurde aus dem Prozess des Ladens gemischter DLLs entfernt. Dies wurde mit diesen Änderungen erreicht:

- Die CLR geht beim Laden von gemischten DLLs nicht mehr von falschen Annahmen aus.

- Nicht verwaltete und verwaltete Initialisierung erfolgen in zwei separaten und unterschiedlichen Stufen. Nicht verwaltete Initialisierung wird zuerst ausgeführt (über DllMain), und die verwaltete Initialisierung wird danach durch ein. NET-unterstütztes Konstrukt mit einem *.cctor*-Namen ausgeführt. Letzteres ist für den Benutzer vollständig transparent, wenn **/Zl** oder **/NODEFAULTLIB** verwendet wird. Weitere Informationen finden Sie unter[/NODEFAULTLIB (Ignore Libraries)](../build/reference/nodefaultlib-ignore-libraries.md) und [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md) .

Die Loadersperre kann zwar immer noch auftreten, jetzt aber reproduzierbar, und wird erkannt. Wenn `DllMain` enthält MSIL-Anweisungen, generiert der Compiler die Warnung [Compilerwarnung (Stufe 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md). Darüber hinaus versucht die CRT oder die CLR, Versuche zu erkennen und zu melden, die MSIL unter der Loadersperre auszuführen. CRT-Erkennung führt zum Laufzeitdiagnose-C-Laufzeitfehler R6033.

Im weiteren Verlauf dieses Dokuments werden die verbleibenden Szenarien, für die MSIL unter der Loadersperre ausgeführt werden kann, Lösungen für das Problem unter jedem dieser Szenarien und Debugverfahren beschrieben.

## <a name="scenarios-and-workarounds"></a>Szenarien und Problemumgehungen

Es gibt mehrere Situationen, in denen Benutzercode MSIL unter der Loadersperre ausführen kann. Der Entwickler muss sicherstellen, dass die Benutzercodeimplementierung nicht versucht, in allen diesen Fällen MSIL-Anweisungen auszuführen. In den folgenden Unterabschnitten werden alle Möglichkeiten mit einer Erläuterung der Problemlösung in den häufigsten Fällen beschrieben.

### <a name="dllmain"></a>DllMain

Die `DllMain` -Funktion ist ein benutzerdefinierter Einstiegspunkt für eine DLL. Wenn vom Benutzer nicht anders angegeben, wird `DllMain` jedes Mal aufgerufen, wenn ein Prozess oder Thread der enthaltenden DLL angefügt oder davon getrennt wird. Da dieser Aufruf auftreten kann, während die Loadersperre aktiv ist, sollte keine benutzerdefinierte `DllMain` -Funktion in MSIL kompiliert werden. Darüber hinaus kann keine Funktion in der Aufrufstruktur, die in `DllMain` wurzelt, in MSIL kompiliert werden. Um hier Probleme zu lösen, sollte der Codeblock, der `DllMain` definiert, mit „#pragma“ `unmanaged`geändert werden. Das gleiche sollte für jede Funktion getan werden, die `DllMain` aufruft.

In Fällen, in denen diese Funktionen eine Funktion aufrufen müssen, die eine MSIL-Implementierung für andere aufrufende Kontexte erfordert, kann eine Duplizierungsstrategie verwendet werden, wo .NET und eine native Version der gleichen Funktion erstellt werden.

Alternativ kann, wenn `DllMain` nicht erforderlich ist bzw. nicht unter der Loadersperre ausgeführt werden muss, die vom Benutzer bereitgestellte `DllMain` Implementierung entfernt und damit das Problem gelöst werden.

Wenn DllMain versucht, MSIL direkt auszuführen, führt dies zu [Compiler Warning (level 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) . Der Compiler kann jedoch keine Fälle erkennen, in denen DllMain eine Funktion in einem anderen Modul aufruft, das wiederum versucht, MSIL auszuführen.

Weitere Informationen zu diesem Szenario finden Sie unter „Diagnosehindernisse“.

### <a name="initializing-static-objects"></a>Initialisieren von statischen Objekten

Initialisieren von statischen Objekten kann zu Deadlocks führen, wenn ein dynamischer Initialisierer erforderlich ist. In einfachen Fällen, wenn z. B. einer statischen Variablen einfach ein zum Zeitpunkt der Kompilierung bekannter Wert zugewiesen wird, ist keine dynamische Initialisierung erforderlich, sodass kein Deadlockrisiko besteht. Allerdings erfordern alle statischen Variablen, die durch Funktionsaufrufe, Konstruktoraufrufe oder Ausdrücke initialisiert werden, die zur Kompilierzeit nicht ausgewertet werden können, während der Initialisierung des Moduls auszuführenden Code.

Der folgende Code zeigt Beispiele für statische Initialisierer, die dynamische Initialisierung erfordern: ein Funktionsaufruf, eine Objektkonstruktion und eine Initialisierung eines Zeigers. (Diese Beispiele sind nicht statisch, aber wir gehen davon aus, dass sie im globalen Gültigkeitsbereich definiert werden, was die gleiche Auswirkung hat.)

```cpp
// dynamic initializer function generated
int a = init();
CObject o(arg1, arg2);
CObject* op = new CObject(arg1, arg2);
```

Das Deadlockrisiko hängt davon ab, ob das enthaltende Modul mit **/clr** kompiliert, und ob MSIL ausgeführt wird. Insbesondere wenn die statische Variable ohne **/clr** kompiliert wird (oder sich in einem #pragma- `unmanaged` -Block befindet), und der dynamische Initialisierer erforderlich ist, um ihre Ergebnisse der Ausführung der MSIL-Anweisungen zu initialisieren, kann ein Deadlock auftreten. Dies liegt daran, dass bei Modulen, die ohne **/clr**kompiliert werden, die Initialisierung statischer Variablen von DllMain durchgeführt wird. Im Gegensatz dazu werden mit **/clr** kompilierte statische Variablen nach Abschluss der nicht verwalteten Initialisierungsphase, und nachdem die Loadersperre aufgehoben wurde, durch „.cctor“ initialisiert.

Es gibt eine Reihe von Lösungen zu einem Deadlock, das durch die dynamische Initialisierung von statischen Variablen verursacht wird (etwa nach erforderlichem Zeitaufwand zum Beheben des Problems angeordnet):

- Die Quelldatei, die die statische Variable enthält, kann mit **/clr**kompiliert werden.

- Alle von der statischen Variablen aufgerufenen Funktionen können mit der #pragma- `unmanaged` -Richtlinie in nativen Code kompiliert werden.

- Duplizieren Sie manuell den Code, von dem die statische Variable abhängig ist, sodass Sie eine .NET- und eine native Version mit unterschiedlichen Namen bereitstellen. Entwickler können dann die native Version der nativen statischen Initialisierer aufrufen und die .NET-Version an anderer Stelle.

### <a name="user-supplied-functions-affecting-startup"></a>Benutzerdefinierte Funktionen, die den Start beeinflussen

Es gibt mehrere benutzerdefinierte Funktionen, von denen Bibliotheken zur Initialisierung beim Start abhängig sind. Beispielsweise, wenn Global wie Überladen von Operatoren in C++ die `new` und `delete` Operatoren, die vom Benutzer bereitgestellten Versionen überall verwendet, einschließlich der in der C++-Standardbibliothek Initialisierung und Beschädigung. Daher werden C++-Standardbibliothek und die vom Benutzer bereitgestellte statische Initialisierer alle vom Benutzer bereitgestellten Versionen dieser Operatoren aufrufen.

Wenn die vom Benutzer bereitgestellten Versionen in MSIL kompiliert werden, versuchen diese Initialisierer, MSIL-Anweisungen ausführen, während die Loadersperre aktiviert ist. Ein vom Benutzer bereitgestellte `malloc` hat die gleichen folgen. Um dieses Problem zu lösen, müssen alle diese Überladungen oder benutzerdefinierten Definitionen als nativer Code mit der #pragma- `unmanaged` -Richtlinie implementiert werden.

Weitere Informationen zu diesem Szenario finden Sie unter „Diagnosehindernisse“.

### <a name="custom-locales"></a>Benutzerdefinierte Gebietsschemas

Wenn der Benutzer ein benutzerdefiniertes globales Gebietsschema bereitstellt, wird dieses Gebietsschema zum Initialisieren aller zukünftigen E/A-Ströme, einschließlich der statisch initialisierten, verwendet. Wenn dieses globale Gebietsschemaobjekt in MSIL kompiliert wird, können in MSIL kompilierte Gebietsschemaobjekt-Memberfunktionen aufgerufen werden, während die Loadersperre aktiviert ist.

Es gibt drei Optionen zur Lösung dieses Problems:

Die Quelldateien, die alle globalen E/A-Stromdefinitionen enthalten, können mit der Option **/clr** kompiliert werden. Dies verhindert, dass ihre statischen Initialisierer unter der Loadersperre ausgeführt werden.

Die Funktionsdefinitionen des benutzerdefinierten Gebietsschemas können mit der #pragma- `unmanaged` -Richtlinie in nativen Code kompiliert werden.

Legen Sie das benutzerdefinierte Gebietsschema nicht als globales Gebietsschema fest, solange die Loadersperre nicht freigegeben ist. Konfigurieren Sie dann explizit die während der Initialisierung mit dem benutzerdefinierten Gebietsschema erstellten E/A-Ströme.

## <a name="impediments-to-diagnosis"></a>Diagnosehindernisse

In einigen Fällen ist es schwierig, die Quelle von Deadlocks zu erkennen. In den folgenden Unterabschnitten werden diese Szenarien und die Möglichkeiten, diese Probleme zu umgehen, erörtert.

### <a name="implementation-in-headers"></a>Implementierung in Headern

In bestimmten Fällen können Funktionsimplementierungen in Headerdateien die Diagnose erschweren. Inlinefunktionen und Vorlagencode erfordern, dass Funktionen in einer Headerdatei angegeben werden.  Die Programmiersprache C++ gibt die One Definition Rule (Eine-Definition-Regel) an, die erzwingt, dass alle Implementierungen von Funktionen gleichen Namens semantisch gleichwertig sind. In der Folge muss der C++-Linker beim Zusammenführen von Objektdateien, die doppelte Implementierungen einer bestimmten Funktion aufweisen, nichts Spezielles berücksichtigen.

Vor Visual Studio 2005 wählt der Linker einfach die größte dieser semantisch äquivalenten Definitionen, um weiterleitungsdeklarationen und Szenarien anzupassen, wenn für unterschiedliche Quelldateien verschiedene Optimierungsoptionen verwendet werden. Daraus erwächst ein Problem für gemischte native/.NET-DLLs.

Da derselbe Header möglicherweise enthalten sowohl von C++-Dateien mit **"/ CLR"** aktiviert und deaktiviert, oder ein #include können in einem #pragma umschlossen werden `unmanaged` Block, es ist möglich, dass MSIL und native Versionen von Funktionen, die bereitstellen in Headern Implementierungen. Die Semantik von MSIL- und nativen Implementierungen unterscheidet sich in Bezug auf die Initialisierung unter der Loadersperre, was effektiv die One Definition Rule verletzt. Wenn also der Linker die größte Implementierung wählt, könnte er selbst dann die MSIL-Version einer Funktion wählen, wenn sie explizit an anderer Stelle mit der nicht verwalteten #pragma-Direktive in nativen Code kompiliert wäre. Um sicherzustellen, dass eine MSIL-Version einer Vorlage oder Inlinefunktion niemals unter der Loadersperre aufgerufen wird, muss jede Definition einer jeden solchen Funktion, die unter der Loadersperre aufgerufen wird, mit der #pragma- `unmanaged` -Richtlinie geändert werden. Wenn die Headerdatei von einem Drittanbieter stammt, erreichen Sie dies am einfachsten, indem die nicht verwaltete #pragma-Direktive mit „Push and Pop“ die #include-Direktive für die problematische Headerdatei umgeht. (Siehe [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) ein Beispiel.) Allerdings funktioniert diese Strategie nicht bei Headern, die anderen Code enthalten, der direkt .NET-APIs aufrufen muss.

Zur Erleichterung für Benutzer, die sich mit Loadersperren auseinandersetzen müssen, wählt der Linker die native Implementierung über die verwaltete Direktive, wenn er mit beiden konfrontiert wird. So werden die oben genannten Probleme vermieden. Aufgrund ungelöster Probleme mit dem Compiler gibt es jedoch zwei Ausnahmen von dieser Regel in dieser Version:

- Der Aufruf einer Inlinefunktion erfolgt über einen globalen statischen Funktionszeiger. Dieses Szenario ist besonders bemerkenswert, da virtuelle Funktionen über globale Funktionszeiger aufgerufen werden. Ein auf ein Objekt angewendeter
  
```cpp
#include "definesmyObject.h"
#include "definesclassC.h"

typedef void (*function_pointer_t)();

function_pointer_t myObject_p = &myObject;

#pragma unmanaged
void DuringLoaderlock(C & c)
{
    // Either of these calls could resolve to a managed implementation,
    // at link-time, even if a native implementation also exists.
    c.VirtualMember();
    myObject_p();
}
```

### <a name="diagnosing-in-debug-mode"></a>Diagnose im Debugmodus

Alle Diagnosen von Loadersperrenproblemen sollten mit Debugbuilds erfolgen. Releasebuilds bringen vielleicht keine Diagnoseergebnisse, und die im Releasemodus durchgeführten Optimierungen könnten einige der „MSIL unter Loadersperre“-Szenarien verdecken.

## <a name="how-to-debug-loader-lock-issues"></a>Debuggen von Problemen mit Loadersperren

Die Diagnose, die die CLR beim Aufruf einer MSIL-Funktion generiert, bewirkt, dass die CLR die Ausführung unterbricht. Dies führt wiederum dazu, dass der Visual C++-Debugger im gemischten Modus ebenfalls unterbrochen wird, wenn er die zu debuggenden Komponenten ausführt. Beim Anfügen an den Prozess ist das Abrufen einer verwalteten Aufrufliste für die zu debuggende Komponente mit dem gemischten Debugger jedoch nicht möglich.

Um die bestimmte MSIL-Funktion zu identifizieren, die unter der Loadersperre aufgerufen wurde, sollten Entwickler die folgenden Schritte ausführen:

1. Stellen Sie sicher, dass für „mscoree.dll“ und „mscorwks.dll“ Symbole verfügbar sind.

   Dazu gibt es zwei Möglichkeiten. Erstens können die PDBs für „mscoree.dll“ und „mscorwks.dll“ dem Symbolsuchpfad hinzugefügt werden. Öffnen Sie dazu das Dialogfeld für den Symbolsuchpfad. (Aus der **Tools** Menü wählen **Optionen**. Im linken Bereich des der **Optionen** öffnen Sie im Dialogfeld die **Debuggen** Knoten, und wählen Sie **Symbole**.) Fügen Sie den Pfad zu den PDB-Dateien „mscoree.dll“ und „mscorwks.dll“ der Suchliste hinzu. Diese PDB-Dateien werden in den %VSINSTALLDIR%\SDK\v2.0\symbols installiert. Klicken Sie auf **OK**.

   Zweitens können die PDBs für „mscoree.dll“ und „mscorwks.dll“ vom Microsoft-Symbolserver heruntergeladen werden. Öffnen Sie zum Konfigurieren des Symbolservers das Dialogfeld für die Symbolsuchpfad-Optionen. (Aus der **Tools** Menü wählen **Optionen**. Im linken Bereich des der **Optionen** öffnen Sie im Dialogfeld die **Debuggen** Knoten, und wählen Sie **Symbole**.) Fügen Sie den folgenden Suchpfad der Suchliste hinzu: http://msdl.microsoft.com/download/symbols. Fügen Sie dem Symbolservercache-Textfeld ein Symbolcacheverzeichnis hinzu. Klicken Sie auf **OK**.

1. Legen Sie den Debugmodus auf nur nativ fest.

   Öffnen Sie hierzu die **Eigenschaften** Raster für das Startprojekt in der Projektmappe. Wählen Sie **Konfigurationseigenschaften** > **Debuggen**. Legen Sie die **Debuggertyp** auf **nur nativ**.

1. Starten Sie den Debugger (F5).
  
1. Wenn die **"/ CLR"** -Diagnose generiert wurde, wählen Sie **wiederholen** und wählen Sie dann **unterbrechen**.
  
1. Öffnen Sie das Fenster „Aufrufliste“. (Wählen Sie in der Menüleiste **Debuggen** > **Windows** > **Aufrufliste**.) -Verstoßes `DllMain` oder statischer Initialisierer wird mit einem grünen Pfeil gekennzeichnet. Wenn die auslösende Funktion nicht erkannt wird, müssen die folgenden Schritte ausgeführt werden, um sie zu finden.

1. Öffnen der **Direktfenster** Fenster (Wählen Sie in der Menüleiste **Debuggen** > **Windows** > **Direktfenster**.)

1. Geben Sie .load sos.dll in der **Direktfenster** Fenster aus, um den SOS-Debugdienst zu laden.
  
1. Typ! Dumpstack der **Direktfenster** Fenster aus, um eine vollständige Liste des internen abrufen **"/ CLR"** Stapel.

1. Suchen Sie nach der ersten Instanz (nahe dem Ende des Stapels erreicht) von entweder _CorDllMain (Wenn `DllMain` das Problem verursacht) oder _VTableBootstrapThunkInitHelperStub bzw. GetTargetForVTableEntry (wenn ein statischer Initialisierer das Problem verursacht). Der Stapeleintrag direkt unterhalb dieses Aufrufs ist der Aufruf der MSIL-implementierten Funktion, die eine Ausführung unter der Loadersperre versuchte.

1. Wechseln Sie zur Quelldatei und Zeilennummer im vorherigen Schritt identifizierten und korrigieren Sie Sie das Problem mithilfe der Szenarien und Lösungen, die im szenarienabschnitt beschrieben.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgende Beispiel wird gezeigt, wie Sie Loadersperre zu vermeiden, indem das Verschieben von Code aus `DllMain` an den Konstruktor eines globalen Objekts.

In diesem Beispiel besteht ein verwaltetes globales Objekt, dessen Konstruktor das verwaltete Objekt, das ursprünglich enthält in `DllMain`. Der zweite Teil dieses Beispiels verweist auf die Assembly und erstellt eine Instanz des verwalteten Objekts, um den Modulkonstruktor aufzurufen, der die Initialisierung durchführt.

### <a name="code"></a>Code

```cpp
// initializing_mixed_assemblies.cpp
// compile with: /clr /LD
#pragma once
#include <stdio.h>
#include <windows.h>
struct __declspec(dllexport) A {
   A() {
      System::Console::WriteLine("Module ctor initializing based on global instance of class.\n");
   }

   void Test() {
      printf_s("Test called so linker does not throw away unused object.\n");
   }
};

#pragma unmanaged
// Global instance of object
A obj;

extern "C"
BOOL WINAPI DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved) {
   // Remove all managed code from here and put it in constructor of A.
   return true;
}
```

In diesem Beispiel wird veranschaulicht, Probleme bei der Initialisierung gemischter Assemblys:

```cpp
// initializing_mixed_assemblies_2.cpp
// compile with: /clr initializing_mixed_assemblies.lib
#include <windows.h>
using namespace System;
#include <stdio.h>
#using "initializing_mixed_assemblies.dll"
struct __declspec(dllimport) A {
   void Test();
};

int main() {
   A obj;
   obj.Test();
}
```

Dieser Code erzeugt die folgende Ausgabe:

```Output
Module ctor initializing based on global instance of class.

Test called so linker does not throw away unused object.
```

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
