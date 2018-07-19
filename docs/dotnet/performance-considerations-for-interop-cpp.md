---
title: Überlegungen zur Leistung für Interop (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9223c52e4ef831a9a1ff657db1a0d7859dd6ce6c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164049"
---
# <a name="performance-considerations-for-interop-c"></a>Überlegungen zur Leistung von Interop (C++)
Dieses Thema enthält Richtlinien für verwaltete/nicht verwaltete Interop-Übergänge auf die Leistung zur Laufzeit zu reduzieren.  
  
 Visual C++ unterstützt die gleichen Interoperabilitätsmechanismen wie andere z. B. Visual Basic und c# (P/Invoke), bietet jedoch darüber hinaus Interop-Unterstützung, die für Visual C++ (C++-Interop) spezifisch sind. Für leistungskritische Anwendungen ist es wichtig zu verstehen, die Auswirkungen auf die Leistung der einzelnen Interop-Verfahren.  
  
 Unabhängig von der Interop-Technik, die verwendet wird müssen spezielle Übergang Sequenzen genannte Thunks, jedes Mal eine verwaltete Funktion aufruft, eine nicht verwaltete Funktion und umgekehrt zu. Diese Thunks werden von der Visual C++-Compiler automatisch eingefügt, aber es ist wichtig zu bedenken, dass kumulativ, diese Übergänge im Hinblick auf Leistung teuer sein können.  
  
## <a name="reducing-transitions"></a>Reduzieren von Übergängen  
 Eine Möglichkeit, um zu vermeiden oder reduzieren Sie die Kosten der Interop-Thunks ist umgestaltet werden die Beteiligten minimieren, Übergänge verwalteten und unverwalteten Schnittstellen. Erhebliche Leistungssteigerungen können vorgenommen werden, indem Sie als Ziel ' geschwätzige ' Schnittstellen, die die Apartmentgrenze verwalteten und unverwalteten häufige Aufrufe beteiligt sind. Eine verwaltete Funktion, die eine nicht verwaltete Funktion, in einer Schleife aufruft ist z. B. ein guter Kandidat für die Umgestaltung. Wenn die Schleife selbst wird in der nicht verwalteten Seite verschoben, oder der nicht verwaltete Aufruf wird erstellt, wenn eine verwaltete Alternative zu (vielleicht queuing Daten auf der verwalteten Seite und klicken Sie dann auf die nicht verwaltete API alle auf einmal nach der Schleife Marshalling) kann die Anzahl der Übergänge reduziert anmelden Ificantly.  
  
## <a name="pinvoke-vs-c-interop"></a>Im Vergleich mit P/Invoke. C++ Interop  
 Für .NET-Sprachen wie z. B. Visual Basic und C#-ist die vorgeschriebene Methode für die Interoperation mit systemeigenen Komponenten P/Invoke. Da P/Invoke durch .NET Framework unterstützt wird, Visual C++ ebenfalls unterstützt, aber Visual C++ bietet auch eine eigene interoperabilitätsunterstützung, der als C++ Interop bezeichnet wird. C++-Interop wird über P/Invoke bevorzugt, da P/Invoke nicht typsicher ist. Folglich wird Fehler werden in erster Linie zur Laufzeit gemeldet, aber C++-Interop verfügt auch über die Leistungsvorteile gegenüber P/Invoke.  
  
 Beide Verfahren erfordert mehrere Schritte ausgeführt werden, wenn eine verwaltete Funktion eine nicht verwaltete Funktion aufruft:  
  
-   Funktionsargumente Aufruf werden aus der CLR in systemeigenen Typen gemarshallt.  
  
-   Ein Thunk verwaltet, nicht verwaltete ausgeführt wird.  
  
-   Die nicht verwaltete Funktion wird aufgerufen (unter Verwendung der systemeigenen Versionen der Argumente).  
  
-   Ein Thunk nicht verwalteten zum verwalteten ausgeführt wird.  
  
-   Der Rückgabetyp und "out" oder "in, out" Argumente von systemeigenen CLR-Typen gemarshallt werden.  
  
 Die verwalteten und unverwalteten Thunks für Interop überhaupt Arbeit erforderlich sind, aber das Marshalling von Daten, das erforderlich ist, hängt davon ab, die Datentypen, die Funktionssignatur und wie die Daten verwendet werden soll.  
  
 Die einfachste mögliche Form der Daten-Marshalling von C++-Interop durchgeführt wird: die Parameter einfach über die verwalteten und unverwalteten Grenze in einer bitweisen Weise; kopiert werden überhaupt wird keine Transformation ausgeführt. Für P/Invoke, dies ist nur "true", wenn alle Parameter einfache, blitfähige Typen. Andernfalls führt P/Invoke sehr robuste Schritte aus, um jeden verwalteten Parameter in einen geeigneten systemeigenen Typ zu konvertieren und umgekehrt, wenn die Argumente als "Out", markiert sind oder "in, out".  
  
 Das heißt, verwendet die C++-Interop die schnellste Methode des Daten-Marshalling, während P/Invoke die zuverlässigste Methode verwendet. Dies bedeutet, dass die C++-Interop (in einer Weise, die typisch für C++) bietet eine optimale Leistung standardmäßig, und der Programmierer ist verantwortlich für die Adressierung von Fällen, in denen dieses Verhalten nicht sicheren oder geeigneten ist.  
  
 C++-Interop erfordert daher Daten-Marshalling muss explizit angegeben werden, jedoch den Vorteil besteht darin, dass der Programmierer kostenlos ist, um zu entscheiden, was die Art der Daten geeignet ist, und wie sie verwendet wird. Darüber hinaus, obwohl das Verhalten von P/Invoke Marshalling von Daten zur geändert werden kann bis zu einem gewissen Grad angepasst, können die C++-Interop, Daten-Marshalling, um auf Basis von Aufrufen angepasst werden. Dies ist nicht möglich mit P/Invoke.  
  
 Weitere Informationen zu C++-Interop finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)