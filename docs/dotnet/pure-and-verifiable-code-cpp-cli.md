---
title: "Reiner und überprüfbarer Code (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ec68a6179cd74020638aa895028942bc76e21f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>Reiner und überprüfbarer Code (C++/CLI)
Bei der .NET-Programmierung unterstützt Visual C++ das Erstellen dreier unterschiedlicher Typen von Komponenten und Anwendungen: gemischt, rein und überprüfbar. Alle drei stehen über die [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu überprüfbaren Assemblys finden Sie unter:  
  
-   [Funktionsvergleich zwischen „gemischt“, „rein“ und „überprüfbar“ (C++/CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Vorgehensweise: Migrieren auf/CLR: pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Vorgehensweise: Erstellen überprüfbarer C++-Projekte (C++/CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Vorgehensweise: Migrieren zu/CLR: safe (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [Verwenden überprüfbarer Assemblys mit SQL Server (C++/CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [Empfohlene Vorgehensweisen bezüglich der Sicherheit](../security/security-best-practices-for-cpp.md)  
  
-   [Konvertieren von Projekten im gemischten Modus in reine Intermediate Language](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>Gemischt (/clr)  
 Gemischte Assemblys (kompiliert mit **"/ CLR"**) enthalten sowohl unverwaltete als und verwaltete Teile, sodass es möglich, dass sie .NET-Funktionen verwenden, jedoch weiterhin unverwalteten Code enthalten. Dadurch können Anwendungen und Komponenten für die Verwendung von .NET-Funktionen aktualisiert werden, ohne dass das gesamte Projekt neu geschrieben werden muss. Derartiges Mischen von verwaltetem und nicht verwaltetem Code mit Visual C++ wird als C++ Interop bezeichnet. Weitere Informationen finden Sie unter [gemischte (systemeigene und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [einheitlichen als auch .NET Interoperabilität](../dotnet/native-and-dotnet-interoperability.md).  
  
## <a name="pure-clrpure"></a>Rein (/clr:pure)  
 Reine Assemblys (kompiliert mit **/CLR: pure**) können beide systemeigenen und verwalteten Datentypen enthalten, aber nur verwaltete Funktionen. Ebenso wie bei gemischten Assemblys können reine Assemblys interop mit systemeigenen DLLs über P/Invoke (finden Sie unter [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)), aber der C++-Interop-Funktionen sind nicht verfügbar. Darüber hinaus reine Assemblys können nicht Exportieren von Funktionen, die von systemeigenen Funktionen aufgerufen werden, da in einer reinen Assembly verwendet Einstiegspunkte die [__clrcall](../cpp/clrcall.md) Aufrufkonvention.  
  
### <a name="advantages-of-clrpure"></a>Vorteile von /clr:pure  
  
-   Besseres Leistungsverhalten: Da reine Assemblys ausschließlich MSIL enthalten, gibt es keine systemeigenen Funktionen, sodass keine Übergänge zwischen verwalteten und unverwalteten Funktionen notwendig sind. (Funktionsaufrufe durch P/Invoke sind eine Ausnahme von dieser Regel.)  
  
-   AppDomain-Unterstützung: Verwaltete Funktionen und CLR-Datentypen sind in `Application Domains` vorhanden, was ihre Sichtbarkeit und Verfügbarkeit beeinflusst. Reine Assemblys sind Domäne-fähig (__declspec ([Appdomain](../cpp/appdomain.md)) wird für jeden Typ impliziert), damit der Zugriff auf ihre Typen und Funktionen von anderen Komponenten .NET einfacher und sicherer ist. Folglich arbeiten reine Assemblys einfacher mit anderen .NET-Komponenten zusammen als gemischte Assemblys.  
  
-   Laden von Nichtdatenträgern: Reine Assemblys können speicherintern und sogar als Stream geladen werden. Dies ist entscheidend für die Verwendung von .NET-Assemblys als gespeicherte Prozeduren. Darin unterscheiden sie sich von gemischten Assemblys, die aufgrund ihrer Abhängigkeit von Windows-Lademechanismen auf einem Datenträger vorliegen müssen, um ausgeführt werden zu können.  
  
-   Reflektion: Es ist nicht möglich, eine Reflektion über gemischte ausführbare Dateien durchzuführen, während reine Assemblys die Reflektion in vollem Umfang unterstützen. Weitere Informationen finden Sie unter [Reflektion (C + c++ / CLI)](../dotnet/reflection-cpp-cli.md).  
  
-   Hoststeuerbarkeit: Da reine Assemblys nur MSIL enthalten, verhalten sie sich vorhersagbarer und flexibler als gemischte Assemblys, wenn sie in Anwendungen verwendet werden, die das CLR hosten und sein Standardverhalten modifizieren.  
  
### <a name="limitations-of-clrpure"></a>Einschränkungen von /clr:pure  
 Dieser Abschnitt enthält Funktionen, die derzeit nicht unterstützt, indem **/CLR: pure**.  
  
-   Reine Assemblys können nicht von nicht verwalteten Funktionen aufgerufen werden. Deshalb können reine Assemblys keine COM-Schnittstellen implementieren oder systemeigene Rückrufe verfügbar machen. Reine Assemblys können keine Funktionen über __declspec(dllexport) oder DEF-Dateien exportieren. Darüber hinaus Funktionen deklariert, mit der \__clrcall Konvention kann nicht importiert werden, über \__declspec(dllimport). Funktionen in einem systemeigenen Modul können von einer reinen Assembly aufgerufen werden, aber reine Assemblys können keine von systemeigenen Funktionen aufrufbaren Funktionen verfügbar machen, sodass das Verfügbarmachen von Funktionalität in einer reinen Assembly durch verwaltete Funktionen in einer gemischten Assembly erfolgen muss. Finden Sie unter [Vorgehensweise: Migrieren auf/CLR: pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) für Weitere Informationen.  
  
-   ATL- und MFC-Bibliotheken werden von der Kompilierung im pure-Modus in Visual C++ nicht unterstützt.  
  
-   Reine .netmodules werden als Eingabe für den Visual C++-Linker nicht akzeptiert. Reine OBJ-Dateien werden jedoch vom Linker akzeptiert, und OBJ-Dateien enthalten ein Superset der in netmodules enthaltenen Informationen. Finden Sie unter [NETMODULE-Dateien als Linkereingabe](../build/reference/netmodule-files-as-linker-input.md) für Weitere Informationen.  
  
-   Compiler-COM-Unterstützung (#import) wird nicht unterstützt, da dies nicht verwaltete Anweisungen in die reine Assembly einführen würde.  
  
-   Gleitkommaoptionen für die Ausrichtung und Ausnahmebehandlungen sind für reine Assemblys nicht einstellbar. Daher kann __declspec(align) nicht verwendet werden. Hierdurch werden einige Headerdateien, z. B. fpieee.h, als nicht mit /clr:pure kompatibel gerendert.  
  
-   Die GetLastError-Funktion im PSDK kann zu nicht definiertem Verhalten beim Kompilieren mit **/CLR: pure**.  
  
## <a name="verifiable-clrsafe"></a>Überprüfbar (/clr:safe)  
 Die **/CLR: safe** Compileroption generiert überprüfbare Assemblys, wie in Visual Basic und C#-, nach Anforderungen, die die common Language Runtime (CLR), um sicherzustellen, dass der Code nicht verletzt aktuelle ermöglichen geschriebene Sicherheitseinstellungen. Wenn die Sicherheitseinstellungen beispielsweise einer Komponente verbieten, auf die Festplatte zu schreiben, kann die CLR feststellen, ob eine überprüfbare Komponente dieses Kriterium erfüllt, bevor der Code ausgeführt wird. Es gibt für überprüfbare Assemblys keine CRT-Unterstützung. (CRT-Unterstützung steht reinen Assemblys durch eine Pure-MSIL-Version der C-Laufzeitbibliothek zur Verfügung.)  
  
 Diese Vorteile bieten überprüfbare Assemblys gegenüber reinen und gemischten Assemblys:  
  
-   Erhöhte Sicherheit.  
  
-   Einige Situationen erfordern dies (z. B. SQL-Komponenten).  
  
-   Zukünftige Versionen von Windows werden überprüfbare Komponenten und Anwendungen zunehmend erfordern.  
  
 Ein Nachteil ist, dass C++ Interop-Funktionen nicht verfügbar sind. Überprüfbare Assemblys können keine nicht verwalteten Funktionen oder systemeigenen Datentypen enthalten, selbst wenn der verwaltete Code nicht auf sie verweist.  
  
 Kompilieren Sie trotz der Verwendung des Worts "Safe", Anwendungen mit **/CLR: safe** bedeutet nicht, dass keine Fehler vorhanden sind; es bedeutet lediglich, dass die CLR die Sicherheitseinstellungen zur Laufzeit überprüfen kann.  
  
 Unabhängig vom Assemblytyp werden Aufrufe systemeigener DLLs über P/Invoke durch verwaltete Assemblys kompiliert, können aber aufgrund von Sicherheitseinstellungen zur Laufzeit scheitern.  
  
> [!NOTE]
>  Es gibt eine Codekonstellation, die kompiliert wird, obwohl dies eine unüberprüfbare Assembly zu Folge hat: Aufruf einer virtuellen Funktion durch eine Objektinstanz mit dem Bereichsauflösungsoperator.  Beispiel: `MyObj -> A::VirtualFunction();`.  
  
## <a name="see-also"></a>Siehe auch  
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)