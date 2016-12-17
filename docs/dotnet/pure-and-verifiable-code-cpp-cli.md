---
title: "Reiner und &#252;berpr&#252;fbarer Code (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
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
  - ".NET Framework [C++], Reiner und überprüfbarer Code"
  - "/clr-Compileroption [C++], Gemischte Assemblys"
  - "/clr-Compileroption [C++], Reine Assemblys"
  - "/clr-Compileroption [C++], Überprüfbare Assemblys"
  - "Assemblys [C++], Gemischter Code"
  - "Assemblys [C++], Reiner Code"
  - "Assemblys [C++], Überprüfbarer Code"
  - "Gemischte Assemblys [C++]"
  - "Gemischte Assemblys [C++], Informationen zu gemischten Assemblys"
  - "Reine MSIL [C++]"
  - "Reine MSIL [C++], Informationen zu reinem Code"
  - "Überprüfbare Assemblys [C++]"
  - "Überprüfbare Assemblys [C++], Informationen zu überprüfbaren Assemblys"
  - "Überprüfbar typsicherer Code [C++]"
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: 31
caps.handback.revision: "31"
ms.author: "mblome"
manager: "ghogen"
---
# Reiner und &#252;berpr&#252;fbarer Code (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der .NET\-Programmierung unterstützt Visual C\+\+ das Erstellen dreier unterschiedlicher Typen von Komponenten und Anwendungen: gemischt, rein und überprüfbar.  Alle drei sind über die Compileroption [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) verfügbar.  
  
## Hinweise  
 Weitere Informationen zu überprüfbaren Assemblys finden Sie unter:  
  
-   [Featurevergleich zwischen "gemischt", "rein" und "überprüfbar"](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Gewusst wie: Migrieren auf \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Gewusst wie: Erstellen überprüfbarer C\+\+\-Projekte](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Gewusst wie: Migrieren auf \/clr:safe](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [Verwenden überprüfbarer Assemblys mit SQL Server](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [Empfohlene Vorgehensweisen bezüglich der Sicherheit](../top/security-best-practices-for-cpp.md)  
  
-   [Konvertieren von Projekten im gemischten Modus in reine Intermediate Language](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## Gemischt \(\/clr\)  
 Gemischte Assemblys \(kompiliert mit **\/clr**\) enthalten sowohl unverwaltete als auch verwaltete Teile, sodass sie .NET\-Funktionen verwenden, jedoch weiterhin unverwalteten Code enthalten können.  Dadurch können Anwendungen und Komponenten für die Verwendung von .NET\-Funktionen aktualisiert werden, ohne dass das gesamte Projekt neu geschrieben werden muss.  Derartiges Mischen von verwaltetem und nicht verwaltetem Code mit Visual C\+\+ wird als C\+\+ Interop bezeichnet.  Weitere Informationen finden Sie unter [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md).  
  
## Rein \(\/clr:pure\)  
 Reine Assemblys \(kompiliert mit **\/clr:pure**\) können sowohl systemeigene als auch verwaltete Datentypen enthalten, aber nur verwaltete Funktionen.  Ebenso wie bei gemischten Assemblys ist Interop mit systemeigenen DLLs durch P\/Invoke \(siehe [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)\) auch bei reinen Assemblys möglich, allerdings sind die C\+\+ Interop\-Funktionen nicht verfügbar.  Darüber hinaus können reine Assemblys keine Funktionen exportieren, die von systemeigenen Funktionen aufrufbar sind, weil die Einstiegspunkte in einer reinen Assembly die [\_\_clrcall](../cpp/clrcall.md)\-Aufrufkonvention verwenden.  
  
### Vorteile von \/clr:pure  
  
-   Besseres Leistungsverhalten: Da reine Assemblys ausschließlich MSIL enthalten, gibt es keine systemeigenen Funktionen, sodass keine Übergänge zwischen verwalteten und unverwalteten Funktionen notwendig sind. \(Funktionsaufrufe durch P\/Invoke sind eine Ausnahme von dieser Regel.\)  
  
-   AppDomain\-Unterstützung: Verwaltete Funktionen und CLR\-Datentypen sind in `Application Domains` vorhanden, was ihre Sichtbarkeit und Verfügbarkeit beeinflusst.  Reine Assemblys sind domainfähig \(\_\_declspec\([appdomain](../cpp/appdomain.md)\) ist für jeden einzelnen Typ vorhanden\), sodass ein Zugreifen auf ihre Typen und Funktionen seitens anderer .NET\-Komponenten einfacher und sicherer ist.  Folglich arbeiten reine Assemblys einfacher mit anderen .NET\-Komponenten zusammen als gemischte Assemblys.  
  
-   Laden von Nichtdatenträgern: Reine Assemblys können speicherintern und sogar als Stream geladen werden.  Dies ist entscheidend für die Verwendung von .NET\-Assemblys als gespeicherte Prozeduren.  Darin unterscheiden sie sich von gemischten Assemblys, die aufgrund ihrer Abhängigkeit von Windows\-Lademechanismen auf einem Datenträger vorliegen müssen, um ausgeführt werden zu können.  
  
-   Reflektion: Es ist nicht möglich, eine Reflektion über gemischte ausführbare Dateien durchzuführen, während reine Assemblys die Reflektion in vollem Umfang unterstützen.  Weitere Informationen finden Sie unter [Reflektion](../dotnet/reflection-cpp-cli.md).  
  
-   Hoststeuerbarkeit: Da reine Assemblys nur MSIL enthalten, verhalten sie sich vorhersagbarer und flexibler als gemischte Assemblys, wenn sie in Anwendungen verwendet werden, die das CLR hosten und sein Standardverhalten modifizieren.  
  
### Einschränkungen von \/clr:pure  
 In diesem Abschnitt werden derzeit von **\/clr:pure** nicht unterstützte Funktionen behandelt.  
  
-   Reine Assemblys können nicht von nicht verwalteten Funktionen aufgerufen werden.  Deshalb können reine Assemblys keine COM\-Schnittstellen implementieren oder systemeigene Rückrufe verfügbar machen.  Reine Assemblys können keine Funktionen über \_\_declspec\(dllexport\) oder DEF\-Dateien exportieren.  Ebenso können mit der \_\_clrcall\-Konvention deklarierte Funktionen nicht über \_\_declspec\(dllimport\) importiert werden.  Funktionen in einem systemeigenen Modul können von einer reinen Assembly aufgerufen werden, aber reine Assemblys können keine von systemeigenen Funktionen aufrufbaren Funktionen verfügbar machen, sodass das Verfügbarmachen von Funktionalität in einer reinen Assembly durch verwaltete Funktionen in einer gemischten Assembly erfolgen muss.  Weitere Informationen finden Sie unter [Gewusst wie: Migrieren auf \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
-   ATL\- und MFC\-Bibliotheken werden von der Kompilierung im pure\-Modus in Visual C\+\+ nicht unterstützt.  
  
-   Reine .netmodules werden als Eingabe für den Visual C\+\+\-Linker nicht akzeptiert.  Reine OBJ\-Dateien werden jedoch vom Linker akzeptiert, und OBJ\-Dateien enthalten ein Superset der in netmodules enthaltenen Informationen.  Weitere Informationen finden Sie unter [.NETMODULE\-Dateien als Eingabe für den Linker](../build/reference/netmodule-files-as-linker-input.md).  
  
-   Compiler\-COM\-Unterstützung \(\#import\) wird nicht unterstützt, da dies nicht verwaltete Anweisungen in die reine Assembly einführen würde.  
  
-   Gleitkommaoptionen für die Ausrichtung und Ausnahmebehandlungen sind für reine Assemblys nicht einstellbar.  Daher kann \_\_declspec\(align\) nicht verwendet werden.  Hierdurch werden einige Headerdateien, z. B. fpieee.h, als nicht mit \/clr:pure kompatibel gerendert.  
  
-   Die GetLastError\-Funktion im PSDK \(Platform Software Development Kit\) kann bei Kompilierung mit **\/clr:pure** zu nicht definiertem Verhalten führen.  
  
## Überprüfbar \(\/clr:safe\)  
 Die Compileroption **\/clr:safe** generiert überprüfbare Assemblys, die wie in Visual Basic und C\# geschriebene Assemblys die Anforderungen erfüllen, anhand derer die CLR \(Common Language Runtime\) gewährleisten kann, dass der Code die aktuellen Sicherheitseinstellungen nicht verletzt.  Wenn die Sicherheitseinstellungen beispielsweise einer Komponente verbieten, auf die Festplatte zu schreiben, kann die CLR feststellen, ob eine überprüfbare Komponente dieses Kriterium erfüllt, bevor der Code ausgeführt wird.  Es gibt für überprüfbare Assemblys keine CRT\-Unterstützung. \(CRT\-Unterstützung steht reinen Assemblys durch eine Pure\-MSIL\-Version der C\-Laufzeitbibliothek zur Verfügung.\)  
  
 Diese Vorteile bieten überprüfbare Assemblys gegenüber reinen und gemischten Assemblys:  
  
-   Erhöhte Sicherheit.  
  
-   Einige Situationen erfordern dies \(z. B. SQL\-Komponenten\).  
  
-   Zukünftige Versionen von Windows werden überprüfbare Komponenten und Anwendungen zunehmend erfordern.  
  
 Ein Nachteil ist, dass C\+\+ Interop\-Funktionen nicht verfügbar sind.  Überprüfbare Assemblys können keine nicht verwalteten Funktionen oder systemeigenen Datentypen enthalten, selbst wenn der verwaltete Code nicht auf sie verweist.  
  
 Bei der Kompilierung von Anwendungen mit **\/clr:safe** bedeutet "safe" nicht, dass es keine Fehler gibt. Es bedeutet lediglich, dass die CLR die Sicherheitseinstellungen zur Laufzeit überprüfen kann.  
  
 Unabhängig vom Assemblytyp werden Aufrufe systemeigener DLLs über P\/Invoke durch verwaltete Assemblys kompiliert, können aber aufgrund von Sicherheitseinstellungen zur Laufzeit scheitern.  
  
> [!NOTE]
>  Es gibt eine Codekonstellation, die kompiliert wird, obwohl dies eine unüberprüfbare Assembly zu Folge hat: Aufruf einer virtuellen Funktion durch eine Objektinstanz mit dem Bereichsauflösungsoperator.  Beispiel: `MyObj -> A::VirtualFunction();`.  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)