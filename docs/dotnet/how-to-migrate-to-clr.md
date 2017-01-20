---
title: "Gewusst wie: Migrieren zu /clr"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Portieren auf"
  - "Kompilieren von systemeigenem Code [C++]"
  - "Interop [C++], /clr-Compileroption"
  - "Interoperabilität [C++], /clr-Compileroption"
  - "Migration [C++], /clr-Compileroption"
  - "Aktualisieren von Visual C++-Anwendungen, /clr-Compileroption"
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
caps.latest.revision: 37
caps.handback.revision: "37"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Migrieren zu /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden Probleme erläutert, die beim Kompilieren von systemeigenem Code mit **\/clr** auftreten \(weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md)\).  Mit **\/clr** können Visual C\+\+\-Module aufgerufen und von .NET\-Assemblys aus aufgerufen werden, während die Kompatibilität mit nicht verwalteten Modulen erhalten bleibt.  Weitere Informationen zu den Vorteilen der Kompilierung mit **\/clr** finden Sie unter [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md).  
  
## Bekannte Probleme beim Kompilieren von Bibliotheksprojekten mit \/clr  
 Visual Studio enthält einige bekannte Probleme beim Kompilieren von Bibliotheksprojekten mit **\/clr**:  
  
-   Der Code kann zur Laufzeit Typen mit [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md) abfragen.  Befindet sich der Typ allerdings in einer MSIL\-DLL\-Datei \(kompiliert mit **\/clr**\), kann der Aufruf von [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md) durchgeführt werden, wenn er vor der Ausführung der statischen Konstruktoren in der verwalteten DLL erfolgt. \(Dieses Problem tritt nicht auf, wenn der FromName\-Aufruf erst nach dem Ausführen des Codes in der verwalteten DLL stattfindet.\)  Um dieses Problem zu umgehen, können Sie die Konstruktion des verwalteten statischen Konstruktors erzwingen, indem Sie in der verwalteten DLL eine Funktion definieren, sie exportieren und anschließend aus der systemeigenen MFC\-Anwendung aufrufen.  Beispiel:  
  
    ```  
    // Extension DLL Header file:  
    __declspec( dllexport ) void EnsureManagedInitialization () {  
       // managed code that won't be optimized away  
       System::GC::KeepAlive(System::Int32::MaxValue);  
    }  
    ```  
  
## Kompilieren mit Visual C\+\+  
 Kompilieren und verknüpfen Sie ein systemeigenes Projekt mit Visual Studio 2010, bevor Sie auf eines seiner Module **\/clr** anwenden.  
  
 Die folgenden Schritte gewährleisten in der angegebenen Reihenfolge den einfachsten Weg einer Kompilierung mit **\/clr**.  Wichtig ist dabei, das Projekt nach jedem dieser Schritte zu kompilieren und auszuführen.  
  
### Ältere Versionen als Visual C\+\+ 2003  
 Wenn Sie von einer älteren Version als Visual C\+\+ 2003 auf Visual Studio 2010 aktualisieren, werden Ihnen möglicherweise Compilerfehler angezeigt, die sich auf die erweiterte C\+\+\-Standardkonformität in Visual C\+\+ 2003 beziehen.  
  
### Aktualisieren von Visual C\+\+ 2003  
 Projekte, die mit Visual C\+\+ 2003 erstellt wurden, müssen zunächst ohne **\/clr** kompiliert werden, da es in Visual Studio eine verbesserte ANSI\/ISO\-Kompatibilität und einige grundlegende Änderungen gibt.  [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md) ist wahrscheinlich die Änderung, die die meiste Aufmerksamkeit verlangt.  Code, der das CRT verwendet, löst sehr wahrscheinlich Veraltungswarnungen aus.  Diese Warnungen lassen sich zwar unterdrücken, ein Migrieren zu den neuen [CRT\-Funktionsversionen mit erweiterter Sicherheit](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) ist jedoch vorzuziehen, da sie eine höhere Sicherheit gewährleisten und möglicherweise Sicherheitsprobleme in Ihrem Code aufdecken.  
  
### Aktualisieren von Managed Extensions für C\+\+  
 Bei Projekten, die mit Visual C\+\+ .NET oder Visual C\+\+ 2003 unter Verwendung von Managed Extensions für C\+\+ erstellt wurden, ist mindestens eine Änderung in den Projekteinstellungen erforderlich, da diese Erweiterungen veraltet sind.  Folglich lässt sich mit Managed Extentions für C\+\+ geschriebener Code nicht unter **\/clr** kompilieren.  Verwenden Sie stattdessen **\/clr:oldSyntax**.  
  
## Konvertieren von C\-Code in C\+\+  
 Obwohl Visual Studio C\-Dateien kompiliert, ist es notwendig, diese für eine Kompilierung mit **\/clr** in C\+\+ zu konvertieren.  Der eigentliche Dateiname muss nicht geändert werden. Sie können **\/Tp** verwenden \(Informationen dazu finden Sie unter [\/Tc, \/Tp, \/TC, \/TP \(Typ der Quelldatei angeben\)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)\). Beachten Sie, dass zwar C\+\+\-Quellcodedateien für **\/clr** erforderlich sind, der Code jedoch nicht für die Verwendung objektorientierter Paradigmen umgestaltet werden muss.  
  
 Es ist sehr wahrscheinlich, dass C\-Code bei einer Kompilierung als C\+\+\-Datei gewisse Änderungen erfordert.  Da die C\+\+\-Typsicherheitsregeln streng sind, müssen Typkonvertierungen explizit durch Umwandlungen vorgenommen werden.  Beispielsweise gibt malloc einen void\-Zeiger zurück, kann aber durch Umwandlung einem Zeiger zugewiesen werden, der auf einen beliebigen Typ in C zeigt:  
  
```  
int* a = malloc(sizeof(int));   // C code  
int* b = (int*)malloc(sizeof(int));   // C++ equivalent  
```  
  
 Auch Funktionszeiger sind in C\+\+ streng typsicher, deshalb muss der folgende C\-Code geändert werden.  Es ist das Beste, in C\+\+ einen `typedef` zu erstellen, der den Funktionszeigertyp definiert, und diesen Typ zur Umwandlung von Funktionszeigern zu verwenden:  
  
```  
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code  
typedef int(*MYPROC)(int);   // C++ equivalent  
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );  
```  
  
 C\+\+ verlangt außerdem, dass Funktionen entweder einen Prototyp haben oder vollständig definiert sind, bevor auf sie verwiesen wird oder sie aufgerufen werden können.  
  
 In C\-Code verwendete Bezeichner, die in C\+\+ Schlüsselwörter sind, \(wie `virtual`, `new`, `delete`, `bool`, `true`, `false` usw.\) müssen umbenannt werden.  Dies kann im Allgemeinen durch einfache Such\- und Ersetzungsvorgänge erfolgen.  
  
 Schließlich erfordern COM\-Aufrufe im C\-Format die explizite Verwendung von v\-table und dem `this`\-Zeiger. Dies gilt nicht für C\+\+:  
  
```  
COMObj1->lpVtbl->Method(COMObj, args);  // C code  
COMObj2->Method(args);  // C++ equivalent  
```  
  
## Umkonfigurieren von Projekteinstellungen  
 Nachdem das Projekt kompiliert wurde und in Visual Studio 2010 ausgeführt wird, sollten Sie neue Projektkonfigurationen für **\/clr** erstellen, statt die Standardkonfigurationen zu ändern.  **\/clr** ist mit einigen Compileroptionen nicht kompatibel, und durch Erstellen separater Konfigurationen können Sie das Projekt als systemeigen oder verwaltet erstellen.  Wenn **\/clr** im Dialogfeld der Eigenschaftenseiten ausgewählt wird, werden Projekteinstellungen, die nicht mit **\/clr** kompatibel sind, deaktiviert \(deaktivierte Optionen werden nicht automatisch wieder aktiviert, wenn die Auswahl von **\/clr** rückgängig gemacht wird\).  
  
### Erstellen neuer Projektkonfigurationen  
 Sie können im [New Project Configuration Dialog Box](assetId:///cca616dc-05a6-4fe3-bdc1-40c72a66f2be) die Option **Einstellungen kopieren von** zum Erstellen einer Projektkonfiguration auf Grundlage der vorhandenen Projekteinstellungen verwenden.  Führen Sie dies einmal für die Debugkonfiguration und einmal für die Releasekonfiguration durch.  Anschließend können Änderungen an der **\/clr**\-spezifischen Konfiguration vorgenommen werden, ohne dass die ursprünglichen Projektkonfigurationen berührt werden.  
  
 Projekte, die benutzerdefinierte Buildregeln verwenden, erfordern möglicherweise zusätzliche Aufmerksamkeit.  
  
 Dieser Schritt hat auf Projekte, die Makefiles verwenden, unterschiedliche Auswirkungen.  In diesem Fall kann ein separates Buildziel konfiguriert werden, oder es kann eine für **\/clr** kompilierungsspezifische Version aus einer Kopie des Originals erstellt werden.  
  
### Ändern von Projekteinstellungen  
 Um **\/clr** in der Entwicklungsumgebung auszuwählen, folgen Sie den Anweisungen unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md).  Wie bereits erwähnt, werden in diesem Schritt automatisch sich widersprechende Projekteinstellungen deaktiviert.  
  
> [!NOTE]
>  Beim Aktualisieren einer verwalteten Bibliothek oder eines Webdienstprojekts von Visual C\+\+ 2003 wird die **\/Zl**\-Compileroption auf der Eigenschaftenseite für die **Befehlszeile** hinzugefügt.  Dadurch wird LNK2001 verursacht.  Beheben Sie das Problem, indem Sie **\/Zl** auf der Eigenschaftenseite für die **Befehlszeile** entfernen.  Weitere Informationen finden Sie unter [\/Zl \(Kein Standardbibliotheksname\)](../build/reference/zl-omit-default-library-name.md) und [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  Eine andere Möglichkeit besteht darin, der Eigenschaft **Zusätzliche Abhängigkeiten** des Linkers msvcrt.lib und msvcmrt.lib hinzuzufügen.  
  
 Bei mit Makefiles erstellten Projekten müssen nicht kompatible Compileroptionen manuell deaktiviert werden, sobald **\/clr** hinzugefügt wird.  Informationen über Compileroptionen, die nicht kompatibel mit **\/clr** sind, finden Sie unter [Einschränkungen für "\/clr"](../build/reference/clr-restrictions.md).  
  
### Vorkompilierte Header  
 Vorkompilierte Header werden unter **\/clr** unterstützt.  Wenn Sie jedoch nur einige der CPP\-Dateien mit **\/clr** kompilieren \(und den Rest als systemeigenen Code\) sind einige Änderungen erforderlich, da mit **\/clr** vorkompilierte Header nicht kompatibel sind mit solchen, die ohne **\/clr** erzeugt wurden.  Diese Inkompatibilität basiert auf der Tatsache, dass **\/clr** Metadaten generiert und benötigt.  Mit **\/clr** kompilierte Module können folglich keine vorkompilierten Header verwenden, die keine Metadaten enthalten, und umgekehrt können nicht mit **\/clr** kompilierte Module keine vorkompilierten Headerdateien verwenden, die Metadaten enthalten.  
  
 Um ein Projekt zu kompilieren, in dem einige Module mit **\/clr** kompiliert sind, deaktivieren Sie am besten vorkompilierte Header insgesamt. \(Öffnen Sie im Dialogfeld der Eigenschaftenseiten des Projekts den Knoten C\/C\+\+, und wählen Sie Vorkompilierte Header aus.  Ändern Sie dann die Eigenschaft "Erstellen\/Verwenden" vorkompilierter Header in "Vorkompilierte Header nicht verwenden".\)  
  
 Allerdings beschleunigen vorkompilierte Header insbesondere in großen Projekten die Kompilierung, insofern ist eine Deaktivierung dieser Funktion nicht wünschenswert.  In diesem Fall ist es am besten, die **\/clr**\-Dateien und die Nicht\-**\/clr**\-Dateien für die Verwendung separater vorkompilierter Header zu konfigurieren.  Dies kann in einem Schritt getan werden: Markieren Sie im Projektmappen\-Explorer gleichzeitig alle Module, die mit **\/clr** kompiliert werden sollen, klicken Sie dann mit der rechten Maustaste auf die Gruppe, und wählen Sie Eigenschaften aus.  Ändern Sie dann die beiden Eigenschaften "PCH durch Datei erstellen\/verwenden" und "Vorkompilierte Headerdatei" auf einen anderen Headerdateinamen bzw. eine andere PCH\-Datei.  
  
## Beheben von Fehlern  
 Eine Kompilierung mit **\/clr** kann zu Compiler\-, Linker\- oder Laufzeitfehlern führen.  In diesem Abschnitt werden die häufigsten Probleme behandelt.  
  
### Zusammenführen von Metadaten  
 Unterschiedliche Datentypversionen können den Linker scheitern lassen, weil die für die beiden Typen generierten Metadaten nicht übereinstimmen. \(Dies geschieht gewöhnlich, wenn Member eines Typs bedingt definiert sind, die Bedingungen jedoch nicht für alle CPP\-Dateien gleich sind, die diesen Typ verwenden.\) In diesem Fall scheitert der Linker und meldet nur den Symbolnamen sowie den Namen der zweiten OBJ\-Datei, in der der Typ definiert wurde.  Es ist häufig hilfreich, die Reihenfolge zu ändern, in der die OBJ\-Dateien an den Linker gesendet werden, um herauszufinden, wo sich die andere Version des Datentyps befindet.  
  
### Ladeprogrammsperren\-Deadlocks  
 In Visual C\+\+ .NET und Visual C\+\+ 2003 war die Initialisierung unter **\/clr** anfällig für nicht deterministische Deadlocks.  Dieses Problem wird als "Ladeprogrammsperren\-Deadlock" bezeichnet.  In Visual Studio 2010 ist dieses Deadlock einfacher zu vermeiden. Es wird während der Laufzeit entdeckt und gemeldet und ist nicht mehr nicht deterministisch.  Das Problem mit der Ladeprogrammsperre kann immer noch auftreten, kann aber jetzt viel leichter vermieden und gelöst werden.  Ausführliche Hintergrundinformationen sowie eine Anweisung und Lösungen finden Sie unter [Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md).  
  
### Datenexporte  
 Das Exportieren von DLL\-Daten ist fehleranfällig und daher nicht empfehlenswert.  Das liegt daran, dass die Initialisierung des Datenabschnitts einer DLL nicht gewährleistet ist, solange kein verwalteter Teil der DLL ausgeführt wurde.  Verweisen Sie mit [\#using\-Direktive](../preprocessor/hash-using-directive-cpp.md) auf Metadaten.  
  
### Typsichtbarkeit  
 Systemeigene Typen sind jetzt standardmäßig privat.  In Visual C\+\+ .NET 2002 und Visual C\+\+ 2003 waren systemeigene Typen standardmäßig öffentlich.  Das kann dazu führen, dass ein systemeigener Typ außerhalb der DLL nicht sichtbar ist.  Beheben Sie diesen Fehler, indem Sie zu diesen Typen `public` hinzufügen.  Weitere Informationen finden Sie unter [Typ\- und Membersichtbarkeit](../misc/type-and-member-visibility.md).  
  
### Gleitkomma\- und Ausrichtungsprobleme  
 `__controlfp` wird von der Common Language Runtime nicht unterstützt \(weitere Informationen finden Sie unter [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)\).  Auch [align](../cpp/align-cpp.md) wird von der CLR nicht berücksichtigt.  
  
### COM\-Initialisierung  
 Die Common Language Runtime initialisiert COM automatisch beim Initialisieren eines Moduls. Bei automatischer Initialisierung wird COM als MTA initialisiert.  Folglich führt explizites Initialisieren von COM zu Rückgabecodes, die angeben, dass COM bereits initialisiert ist.  Wenn Sie versuchen, COM mit einem bestimmten Threadingmodell zu initialisieren, obwohl die CLR COM bereits mit einem anderen Threadingmodell initialisiert hat, kann die Anwendung möglicherweise nicht ausgeführt werden.  
  
 Die Common Language Runtime startet COM standardmäßig als MTA; verwenden Sie [\/CLRTHREADATTRIBUTE \(Festlegen des CLR\-Threadattributs\)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md), um dies zu ändern.  
  
### Leistungsaspekte  
 Möglicherweise stellen Sie eine Verschlechterung der Leistung fest, wenn systemeigene für MSIL generierte C\+\+\-Methoden indirekt aufgerufen werden \(durch virtuelle Funktionsaufrufe oder die Verwendung von Funktionszeigern\).  Weitere Informationen dazu finden Sie unter [Doppeltes Thunking](../dotnet/double-thunking-cpp.md).  
  
 Wenn Sie von systemeigenem Code zu MSIL wechseln, werden Sie feststellen, dass das Workingset größer wird.  Das liegt daran, dass die Common Language Runtime viele Funktionen enthält, die sicherstellen, dass Programme ordnungsgemäß ausgeführt werden.  Falls die **\/clr**\-Anwendung nicht ordnungsgemäß funktioniert, können Sie C4793 aktivieren \(standardmäßig deaktiviert\). Weitere Informationen hierzu finden Sie unter [Compilerwarnung \(Stufe 1 und 3\) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md).  
  
### Programmabstürze beim Herunterfahren  
 In manchen Fällen wird die CLR heruntergefahren, bevor die Ausführung des verwalteten Codes abgeschlossen ist.  Die Ursache kann in der Verwendung von `std::set_terminate` und `SIGTERM` liegen.  Weitere Informationen finden Sie unter [Signalkonstanten](../c-runtime-library/signal-constants.md) und [set\_terminate](../Topic/set_terminate%20\(%3Cexception%3E\).md).  
  
## Verwenden neuer Visual C\+\+\-Funktionen  
 Sobald die Anwendung kompiliert, verknüpft und ausgeführt werden kann, können Sie .NET\-Funktionen in jedem mit **\/clr** kompilierten Modul verwenden.  Weitere Informationen finden Sie unter [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
 Wenn Sie Managed Extensions für C\+\+ verwendet haben, können Sie den Code für die Verwendung der neuen Syntax konvertieren.  Eine Zusammenfassung der syntaktischen Unterschiede finden Sie unter [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](assetId:///edbded88-7ef3-4757-bd9d-b8f48ac2aada).  Ausführliche Informationen zum Konvertieren von Managed Extensions für C\+\+ finden Sie unter [Einführung in die C\+\+\/CLI\-Migration](../dotnet/cpp-cli-migration-primer.md)  
  
 Informationen zur .NET\-Programmierung in Visual C\+\+ finden Sie unter:  
  
-   [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
  
-   [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)  
  
-   [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)