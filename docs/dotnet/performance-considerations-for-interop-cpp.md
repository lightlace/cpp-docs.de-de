---
title: "&#220;berlegungen zur Leistung von Interop (C++)"
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
  - "/clr-Compileroption [C++], Interop-Leistungsaspekte"
  - "Interop [C++], Überlegungen zur Leistung"
  - "Interoperabilität [C++], Überlegungen zur Leistung"
  - "Gemischte Assemblys [C++], Überlegungen zur Leistung"
  - "Plattformaufruf [C++], Interoperabilität"
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berlegungen zur Leistung von Interop (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält Richtlinien zum Reduzieren der Auswirkungen von Interop\-Übergängen zwischen verwalteten und nicht verwalteten Funktionen auf die Laufzeitleistung.  
  
 Visual C\+\+ unterstützt dieselben Interoperabilitätsmechanismen wie andere .NET\-Sprachen, etwa Visual Basic oder C\# \(P\/Invoke\), bietet jedoch auch eine spezifische Interoperabilitätsunterstützung für Visual C\+\+ \(C\+\+\-Interop\).  Bei leistungskritischen Anwendungen ist es wichtig, die Leistungsauswirkungen der einzelnen Interop\-Techniken zu kennen.  
  
 Unabhängig von der verwendeten Interop\-Technik sind bei jedem Aufruf einer nicht verwalteten Funktion durch eine verwaltete Funktion und umgekehrt spezielle Übergangssequenzen, so genannte Thunks, erforderlich.  Diese Thunks werden automatisch vom Visual C\+\+\-Compiler eingefügt, wobei jedoch beachtet werden muss, dass diese Übergänge zusammengenommen die Leistung beeinträchtigen können.  
  
## Reduzieren von Übergängen  
 Eine Möglichkeit zur Vermeidung oder Reduzierung der Kosten solcher Interop\-Thunks besteht darin, die beteiligten Schnittstellen umzugestalten, um Übergänge zwischen verwalteten und unverwalteten Funktionen zu minimieren.  Beträchtliche Leistungsverbesserungen können durch eine genaue Prüfung solcher Schnittstellen erreicht werden, bei denen häufig Aufrufe über Grenzen verwalteter und nicht verwalteter Funktionen hinweg auftreten.  Beispielsweise wäre eine verwaltete Funktion, die eine nicht verwaltete Funktion in einer kurzen Schleife aufruft, ein guter Kandidat für die Umgestaltung.  Wenn die Schleife selbst auf die nicht verwaltete Seite verschoben oder eine verwaltete Alternative zu den nicht verwalteten Aufrufen gewählt wird \(möglicherweise durch Einreihen der Daten auf der verwalteten Seite in eine Warteschlange und dem gemeinsamen Marshalling all dieser Daten auf eine nicht verwaltete API, wenn die Schleife beendet ist\), kann die Anzahl der Übergänge bedeutend reduziert werden.  
  
## P\/Invoke und C\+\+\-Interop  
 In .NET\-Sprachen wie Visual Basic und C\# ist die empfohlene Methode für die Interoperation mit systemeigenen Komponenten P\/Invoke.  Da P\/Invoke durch .NET Framework unterstützt wird, wird es auch von Visual C\+\+ unterstützt. Visual C\+\+ verfügt jedoch auch über eine eigene Interoperabilitätsunterstützung, die als C\+\+\-Interop bezeichnet wird.  C\+\+\-Interop wird gegenüber P\/Invoke bevorzugt, da P\/Invoke nicht typsicher ist.  In der Konsequenz werden Fehler hauptsächlich zur Laufzeit gemeldet, jedoch besitzt C\+\+\-Interop auch Leistungsvorteile gegenüber P\/Invoke.  
  
 Bei beiden Techniken müssen bei Aufrufen einer nicht verwalteten durch eine verwaltete Funktion mehrere Schritte ausgeführt werden:  
  
-   Die Funktionsaufrufargumente werden von CLR zu systemeigenen Typen gemarshallt.  
  
-   Ein Thunk für den Übergang von verwalteten auf nicht verwalteten Code wird ausgeführt.  
  
-   Die nicht verwaltete Funktion wird aufgerufen \(unter Verwendung der systemeigenen Versionen der Argumente\).  
  
-   Ein Thunk für den Übergang von nicht verwalteten auf verwalteten Code wird ausgeführt.  
  
-   Der Rückgabetyp und alle "out" oder "in, out"\-Argumente werden von systemeigenen zu CLR\-Typen gemarshallt.  
  
 Die Thunks für den Übergang von verwaltetem auf nicht verwalteten Code sind für Interop grundsätzlich erforderlich, doch das erforderliche Datenmarshalling hängt von den beteiligten Datentypen, der Funktionssignatur und der Art der Verwendung der Daten ab.  
  
 C\+\+\-Interop führt ein Datenmarshalling in der einfachsten möglichen Form durch: Die Parameter werden einfach bitweise über die Grenze zwischen verwaltetem und nicht verwaltetem Code hinweg kopiert, ohne dass eine Transformation erfolgt.  Bei P\/Invoke ist dies nur der Fall, wenn alle Parameter einfache, blitfähige Typen sind.  Andernfalls führt P\/Invoke sehr stabile Schritte zur Konvertierung jedes verwalteten Parameters in einen geeigneten systemeigenen Typ und umgekehrt aus, wenn die Argumente als "out" oder "in,out" gekennzeichnet sind.  
  
 Anders ausgedrückt verwendet C\+\+\-Interop die schnellstmögliche Methode des Datenmarshalling, P\/Invoke die stabilste.  Das bedeutet, dass C\+\+\-Interop \(auf eine für C\+\+ typische Weise\) standardmäßig optimale Leistung bietet und der Programmierer die Aufgabe hat, sich um Fälle zu kümmern, in denen dieses Verhalten nicht sicher oder ungeeignet ist.  
  
 C\+\+\-Interop erfordert daher eine explizite Bereitstellung des Datenmarshalling, doch für den Programmierer liegt der Vorteil darin, dass er frei entscheiden kann, welche Form je nach Daten geeignet ist und wie das Marshalling verwendet werden soll.  Das Verhalten des P\/Invoke\-Datenmarshalling kann zwar geändert und zu einem gewissen Grad angepasst werden, jedoch erlaubt C\+\+\-Interop darüber hinaus eine Anpassung auf Basis einzelner Aufrufe.  Mit P\/Invoke ist das nicht möglich.  
  
 Weitere Informationen über C\+\+\-Interop finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)