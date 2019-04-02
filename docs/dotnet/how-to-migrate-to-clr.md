---
title: 'Vorgehensweise: Migrieren auf - clr'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 6ac470b85a14bfe32c7f3fe47168180687669ec6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781314"
---
# <a name="how-to-migrate-to-clr"></a>Vorgehensweise: Migrieren auf/CLR

Dieses Thema behandelt Probleme, die beim Kompilieren mit auftreten **"/ CLR"** (finden Sie unter [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) Informationen). **"/ CLR"** systemeigenen C++-Code aufrufen und von .NET-Assemblys zusätzlich zu anderen systemeigenen C++-Code aus aufgerufen werden können. Finden Sie unter [gemischte (Native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [Native und .NET Interoperabilität](../dotnet/native-and-dotnet-interoperability.md) für Weitere Informationen zu den Vorteilen der Kompilierung mit **"/ CLR"**.

## <a name="known-issues-compiling-library-projects-with-clr"></a>Bekannte Probleme beim Kompilieren von Bibliotheksprojekten mit /clr

Visual Studio enthält einige bekannte Probleme beim Kompilieren von Bibliotheksprojekten mit **"/ CLR"**:

- Der Code kann zur Laufzeit Typen mit Abfragen [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md#fromname). Jedoch ist ein Typ in einer MSIL-DLL-Datei (kompiliert mit **"/ CLR"**), den Aufruf von `FromName` kann fehlschlagen, wenn er vor der Ausführung der statischen Konstruktoren in der verwalteten DLL (wird nicht angezeigt, dieses Problem Wenn der FromName-Aufruf erfolgt, nach dem Code verfügt über erfolgt ausgeführt, in der verwalteten DLL). Um dieses Problem zu umgehen, können Sie die Konstruktion des verwalteten statischen Konstruktors erzwingen, indem Sie in der verwalteten DLL eine Funktion definieren, sie exportieren und anschließend aus der nativen MFC-Anwendung aufrufen. Zum Beispiel:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Kompilieren mit Visual C++

Vor der Verwendung von **"/ CLR"** für jedes Modul in Ihrem Projekt, kompilieren und verknüpfen Sie ein systemeigene Projekt mit Visual Studio 2010.

Geben Sie die folgenden Schritte aus, in der angegebenen Reihenfolge den einfachsten Weg einer **"/ CLR"** Kompilierung. Wichtig ist dabei, das Projekt nach jedem dieser Schritte zu kompilieren und auszuführen.

### <a name="versions-prior-to-visual-c-2003"></a>Ältere Versionen als Visual C++ 2003

Wenn Sie von einer älteren Version als Visual C++ 2003 auf Visual Studio 2010 aktualisieren, werden Ihnen möglicherweise Compilerfehler angezeigt, die sich auf die erweiterte C++-Standardkonformität in Visual C++ 2003 beziehen.

### <a name="upgrading-from-visual-c-2003"></a>Aktualisieren von Visual C++ 2003

Projekte, die mit Visual C++ 2003 erstellten sollten zunächst kompiliert werden, ohne **"/ CLR"** wie Visual Studio jetzt ANSI/ISO-Kompatibilität und einige grundlegende Änderungen erhöht hat. Die Änderung, die meiste Aufmerksamkeit erfordert wahrscheinlich ist, ist [Sicherheitsfunktionen in CRT](../c-runtime-library/security-features-in-the-crt.md). Code, der das CRT verwendet, löst sehr wahrscheinlich Veraltungswarnungen aus. Diese Warnungen können unterdrückt werden, aber Migrieren zu den neuen werden [Versionen der CRT-Funktionen über](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) wird empfohlen, da sie eine höhere Sicherheit gewährleisten und möglicherweise Sicherheitsprobleme in Ihrem Code anzuzeigen.

### <a name="upgrading-from-managed-extensions-for-c"></a>Aktualisieren von Managed Extensions für C++

Visual Studio 2005 ab, mit der Managed Extensions for C++ geschriebener Code nicht kompiliert unter **"/ CLR"**.

## <a name="convert-c-code-to-c"></a>Konvertieren von C-Code in C++

Obwohl Visual Studio C-Dateien kompiliert, ist es erforderlich, um sie in C++ zu konvertieren eine **"/ CLR"** Kompilierung. Der eigentliche Dateiname muss keine geändert werden; Sie können **/TP** (finden Sie unter [/TC, / TP, / TC, / TP (Typ der Quelldatei angeben)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) Beachten Sie, dass zwar C++-Quellcodedateien für **"/ CLR"**, es ist nicht erforderlich, um Ihren Code, um die Verwendung objektorientierter Paradigmen umgestaltet.

Es ist sehr wahrscheinlich, dass C-Code bei einer Kompilierung als C++-Datei gewisse Änderungen erfordert. Da die C++-Typsicherheitsregeln streng sind, müssen Typkonvertierungen explizit durch Umwandlungen vorgenommen werden. Beispielsweise gibt malloc einen void-Zeiger zurück, kann aber durch Umwandlung einem Zeiger zugewiesen werden, der auf einen beliebigen Typ in C zeigt:

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

Auch Funktionszeiger sind in C++ streng typsicher, deshalb muss der folgende C-Code geändert werden. Es ist das Beste, in C++ einen `typedef` zu erstellen, der den Funktionszeigertyp definiert, und diesen Typ zur Umwandlung von Funktionszeigern zu verwenden:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

C++ verlangt außerdem, dass Funktionen entweder einen Prototyp haben oder vollständig definiert sind, bevor auf sie verwiesen wird oder sie aufgerufen werden können.

In C-Code verwendete Bezeichner, die in C++ Schlüsselwörter sind (z. B. **virtuellen**, **neue**, **löschen**, **"bool"**, **"true"** , **"false"** usw.) müssen umbenannt werden. Dies kann im Allgemeinen durch einfache Such- und Ersetzungsvorgänge erfolgen.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>Umkonfigurieren von Projekteinstellungen

Nachdem das Projekt kompiliert und ausgeführt, in Visual Studio 2010 wird sollten Sie für neue Projektkonfigurationen erstellen **"/ CLR"** statt die Standardkonfigurationen zu ändern. **"/ CLR"** ist mit einigen Compileroptionen nicht kompatibel, und Erstellen separater Konfigurationen können Sie das Projekt als systemeigen oder verwaltet erstellen. Wenn **"/ CLR"** ausgewählt ist, in der Eigenschaft Seiten (Dialogfeld), projekteinstellungen nicht kompatibel mit **"/ CLR"** sind deaktiviert (und deaktivierte Optionen werden nicht automatisch wiederhergestellt, wenn **"/ CLR"** Auswahl).

### <a name="create-new-project-configurations"></a>Erstellen neuer Projektkonfigurationen

Können Sie **Einstellungen Kopieren von** option die **neue im Dialogfeld Projektkonfiguration** (**erstellen** > **Configuration Manager**  >  **Aktive Projektmappenkonfiguration** > **neu**) zum Erstellen einer Projektkonfiguration, die basierend auf der vorhandenen projekteinstellungen. Führen Sie dies einmal für die Debugkonfiguration und einmal für die Releasekonfiguration durch. Nachfolgende Änderungen klicken Sie dann auf angewendet werden können die **"/ CLR"** -spezifischen Konfigurationen, die ursprünglichen Projektkonfigurationen erhalten bleibt.

Projekte, die benutzerdefinierte Buildregeln verwenden, erfordern möglicherweise zusätzliche Aufmerksamkeit.

Dieser Schritt hat auf Projekte, die Makefiles verwenden, unterschiedliche Auswirkungen. In diesem Fall kann ein separates Buildziel konfiguriert werden und für Version **"/ CLR"** Kompilierung kann von einer Kopie des Originals erstellt werden.

### <a name="change-project-settings"></a>Ändern von Projekteinstellungen

**"/ CLR"** in der Entwicklungsumgebung ausgewählt werden kann, um mithilfe der Anweisungen in [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md). Wie bereits erwähnt, werden in diesem Schritt automatisch sich widersprechende Projekteinstellungen deaktiviert.

> [!NOTE]
>  Beim Upgrade von einer verwalteten Bibliothek oder eines Webdienstprojekts von Visual C++ 2003 die **/Zl** Compiler-Option wird hinzugefügt, die **Befehlszeile** Eigenschaftenseite. Dadurch wird LNK2001 verursacht. Entfernen Sie **/Zl** aus der **Befehlszeile** Eigenschaftenseite, um Sie zu beheben. Finden Sie unter [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md) und [Compiler festgelegt und Buildeigenschaften](../build/working-with-project-properties.md) für Weitere Informationen. Oder, um des Linkers msvcrt.lib und msvcmrt.lib hinzuzufügen **zusätzliche Abhängigkeiten** Eigenschaft.

Bei mit Makefiles erstellten Projekten, nicht kompatible Compileroptionen müssen deaktiviert werden einmal manuell **"/ CLR"** hinzugefügt wird. Finden Sie unter /[/CLR Einschränkungen](../build/reference/clr-restrictions.md) für Informationen über Compileroptionen, die nicht kompatibel mit **"/ CLR"**.

### <a name="precompiled-headers"></a>Vorkompilierte Header

Vorkompilierte Header werden unter unterstützt **"/ CLR"**. Jedoch wenn Sie nur einige der CPP-Dateien mit Kompilieren **"/ CLR"** (den Rest als nativen Code kompilieren) einige Änderungen werden möglicherweise erforderlich vorkompilierte Header mit generiert **"/ CLR"** sind nicht kompatibel mit den ohne generiert **"/ CLR"**. Diese Inkompatibilität beruht auf der Tatsache, dass **"/ CLR"** Metadaten generiert und benötigt. Kompilierte Module **"/ CLR"** vorkompilierter Header, die Metadaten enthalten keine kann daher nicht verwendet und nicht **"/ CLR"** Module keine vorkompilierten Headerdateien, die Metadaten enthalten, verwenden.

Die einfachste Möglichkeit, ein Projekt zu kompilieren, in dem einige Module werden kompiliert **"/ CLR"** besteht darin, vorkompilierte Header vollständig zu deaktivieren. (Öffnen Sie im Dialogfeld der Eigenschaftenseiten des Projekts den Knoten C/C++, und wählen Sie Vorkompilierte Header aus. Ändern Sie dann die Eigenschaft „Erstellen/Verwenden“ vorkompilierter Header in „Vorkompilierte Header nicht verwenden“.)

Allerdings beschleunigen vorkompilierte Header insbesondere in großen Projekten die Kompilierung, insofern ist eine Deaktivierung dieser Funktion nicht wünschenswert. In diesem Fall empfiehlt sich, konfigurieren Sie die **"/ CLR"** und nicht **"/ CLR"** Dateien in die Verwendung separater vorkompilierter Header. Dies kann erfolgen in einem Schritt Auswahl mehrerer Module zu kompilierenden **"/ CLR"** mit **Projektmappen-Explorer**, mit der rechten Maustaste auf die Gruppe, und wählen Sie Eigenschaften. Ändern Sie dann die beiden Eigenschaften „PCH durch Datei erstellen/verwenden“ und „Vorkompilierte Headerdatei“ auf einen anderen Headerdateinamen bzw. eine andere PCH-Datei.

## <a name="fixing-errors"></a>Beheben von Fehlern

Beim Kompilieren mit **"/ CLR"** Compiler-, Linker- oder Fehler verursachen. In diesem Abschnitt werden die häufigsten Probleme behandelt.

### <a name="metadata-merge"></a>Zusammenführen von Metadaten

Unterschiedliche Datentypversionen können den Linker scheitern lassen, weil die für die beiden Typen generierten Metadaten nicht übereinstimmen. (Dies geschieht gewöhnlich, wenn Member eines Typs bedingt definiert sind, die Bedingungen jedoch nicht für alle CPP-Dateien gleich sind, die diesen Typ verwenden.) In diesem Fall scheitert der Linker und meldet nur den Symbolnamen sowie den Namen der zweiten OBJ-Datei, in der der Typ definiert wurde. Es ist häufig hilfreich, die Reihenfolge zu ändern, in der die OBJ-Dateien an den Linker gesendet werden, um herauszufinden, wo sich die andere Version des Datentyps befindet.

### <a name="loader-lock-deadlock"></a>Ladeprogrammsperren-Deadlocks

Der "Ladeprogrammsperren-Deadlock" können auftreten, jedoch ist deterministisch erkannt und zur Laufzeit gemeldet. Finden Sie unter [Initialization of Mixed Assemblies](../dotnet/initialization-of-mixed-assemblies.md) für Ausführliche Hintergrundinformationen, Anleitungen und Lösungen.

### <a name="data-exports"></a>Datenexporte

Das Exportieren von DLL-Daten ist fehleranfällig und daher nicht empfehlenswert. Das liegt daran, dass die Initialisierung des Datenabschnitts einer DLL nicht gewährleistet ist, solange kein verwalteter Teil der DLL ausgeführt wurde. Die Verweismetadaten mit [#using-Direktive](../preprocessor/hash-using-directive-cpp.md).

### <a name="type-visibility"></a>Typsichtbarkeit

Systemeigene Typen sind standardmäßig privat. Das kann dazu führen, dass ein systemeigener Typ außerhalb der DLL nicht sichtbar ist. Beheben Sie diesen Fehler, indem Sie zu diesen Typen `public` hinzufügen.

### <a name="floating-point-and-alignment-issues"></a>Gleitkomma- und Ausrichtungsprobleme

`__controlfp` wird für die common Language Runtime nicht unterstützt (siehe [_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) für Weitere Informationen). Der CLR wird auch nicht berücksichtigt. [ausrichten](../cpp/align-cpp.md).

### <a name="com-initialization"></a>COM-Initialisierung

Die Common Language Runtime initialisiert COM automatisch beim Initialisieren eines Moduls. Bei automatischer Initialisierung wird COM als MTA initialisiert. Folglich führt explizites Initialisieren von COM zu Rückgabecodes, die angeben, dass COM bereits initialisiert ist. Wenn Sie versuchen, COM mit einem bestimmten Threadingmodell zu initialisieren, obwohl die CLR COM bereits mit einem anderen Threadingmodell initialisiert hat, kann die Anwendung möglicherweise nicht ausgeführt werden.

Die common Language Runtime startet COM als MTA standardmäßig; Verwenden Sie [/CLRTHREADATTRIBUTE (festlegen CLR-Threadattributs)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) ändern.

### <a name="performance-issues"></a>Leistungsaspekte

Möglicherweise stellen Sie eine Verschlechterung der Leistung fest, wenn systemeigene für MSIL generierte C++-Methoden indirekt aufgerufen werden (durch virtuelle Funktionsaufrufe oder die Verwendung von Funktionszeigern). Weitere Informationen hierzu finden Sie unter [doppeltes Thunking](../dotnet/double-thunking-cpp.md).

Wenn Sie von systemeigenem Code zu MSIL wechseln, werden Sie feststellen, dass das Workingset größer wird. Das liegt daran, dass die Common Language Runtime viele Funktionen enthält, die sicherstellen, dass Programme ordnungsgemäß ausgeführt werden. Wenn Ihre **"/ CLR"** Anwendung wird nicht ordnungsgemäß ausgeführt, Sie möchten möglicherweise C4793 aktivieren (standardmäßig deaktiviert), finden Sie unter [Compilerwarnung (Stufe 1 und 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) für Weitere Informationen.

### <a name="program-crashes-on-shutdown"></a>Programmabstürze beim Herunterfahren

In manchen Fällen wird die CLR heruntergefahren, bevor die Ausführung des verwalteten Codes abgeschlossen ist. Die Ursache kann in der Verwendung von `std::set_terminate` und `SIGTERM` liegen. Finden Sie unter [signalkonstanten](../c-runtime-library/signal-constants.md) und [Set_terminate](../c-runtime-library/abnormal-termination.md) für Weitere Informationen.

## <a name="using-new-visual-c-features"></a>Verwenden neuer Visual C++-Funktionen

Nachdem Ihre Anwendung kompiliert, Links und ausgeführt wird, können Sie beginnen, mithilfe der Features von .NET in einem Modul mit kompiliert **"/ CLR"**. Weitere Informationen finden Sie unter [Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md).

Wenn Sie Managed Extensions für C++ verwendet haben, können Sie den Code für die Verwendung der neuen Syntax konvertieren. Weitere Informationen zum Konvertieren von Managed Extensions for C++ finden Sie unter [C++ / CLI Migration Primer](../dotnet/cpp-cli-migration-primer.md).

Informationen zur .NET-Programmierung in Visual C++ finden Sie unter:

- [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)

- [Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
