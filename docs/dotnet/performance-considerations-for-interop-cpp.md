---
title: Überlegungen zur Leistung von Interop (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: c6b4456d9c75061c9a8c93f37f98b58f92adc899
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384750"
---
# <a name="performance-considerations-for-interop-c"></a>Überlegungen zur Leistung von Interop (C++)

Dieses Thema enthält Richtlinien für verwaltete/nicht verwaltete interop-Übergänge auf die Leistung zur Laufzeit zu reduzieren.

Visual C++ unterstützt die gleichen Interoperabilitätsmechanismen wie anderen wie Visual Basic und C# -Code (P/Invoke), aber es bietet auch Interop-Unterstützung, die Visual c++ (C++-Interop) spezifisch sind. Bei leistungskritischen Anwendungen ist es wichtig zu verstehen, die Auswirkungen auf die Leistung jeder Interop-Methode.

Unabhängig von der Interop-Technik, die verwendet wird müssen besondere Übergangs-Sequenzen, die genannte Thunks, jedes Mal eine verwaltete Funktion, eine nicht verwaltete Funktion und umgekehrt ist dies aufruft. Diese Thunks werden vom Visual C++-Compiler automatisch eingefügt, aber es ist wichtig zu beachten, dass kumulativ, diese Übergänge im Hinblick auf Leistung teuer sein können.

## <a name="reducing-transitions"></a>Reduzieren von Übergängen

Eine Möglichkeit zur Vermeidung oder Reduzierung der Kosten für Interop-Thunks werden die Schnittstellen zum Minimieren der Übergänge von verwaltetem/nicht verwaltetem zu gestalten. Durch Angeben von ' geschwätzige ' Schnittstellen, die, die häufige Aufrufe über die verwaltete/nicht verwaltete Grenze beteiligt sind, können erhebliche leistungsverbesserungen vorgenommen werden. Eine verwaltete Funktion, die eine nicht verwaltete Funktion in einer Schleife aufruft ist z. B. ein guter Kandidat für die Umgestaltung. Wenn die Schleife selbst in der nicht verwalteten Seite verschoben wird, oder eine verwaltete Alternative zu der nicht verwaltete Aufruf erstellt (vielleicht Einreihen von Daten in der verwalteten Seite werden angezeigt, und klicken Sie dann auf die nicht verwaltete API Marshalling, alle auf einmal nach der Schleife), kann die Anzahl der Übergänge sein reduziert anmelden Ificantly.

## <a name="pinvoke-vs-c-interop"></a>P/Invoke im Vergleich zu C++ Interop

Für Sprachen wie Visual Basic und c# .NET, ist die vorgesehene Methode für die Interoperation mit nativen Komponenten P/Invoke. Da P/Invoke von .NET Framework unterstützt wird, Visual C++ unterstützt es auch, Visual C++ bietet jedoch auch eigene interoperabilitätsunterstützung, der als C++ Interop bezeichnet wird. C++-Interop wird über P/Invoke bevorzugt, da der P/Invoke nicht typsicher ist. Daher Fehler werden in erster Linie zur Laufzeit gemeldet, aber C++-Interop verfügt auch über die Leistungsvorteile gegenüber der P/Invoke.

Beide Verfahren erfordert mehrere Schritte ausgeführt werden, wenn eine verwaltete Funktion eine nicht verwaltete Funktion aufruft:

- Die Argumente für die Funktion aufrufen, werden von CLR in native Typen gemarshallt.

- Ein Thunk verwaltetem auf wird ausgeführt.

- Die nicht verwaltete Funktion wird aufgerufen (mithilfe der systemeigenen Versionen der Argumente).

- Ein Thunk nicht verwalteten zu verwalteten ausgeführt wird.

- Der Rückgabetyp und die "out" oder "in, out" Argumente von nativem zu CLR-Typen gemarshallt werden.

Die verwaltete/nicht verwaltete-Thunks für Interoperabilität überhaupt funktionieren erforderlich sind, aber das Marshalling von Daten, das erforderlich sind, hängt davon ab, der beteiligten Datentypen, die Funktionssignatur und wie die Daten verwendet werden.

Datenmarshalling von C++-Interop ist die einfachste mögliche Form: die Parameter einfach über die verwaltete/nicht verwaltete Grenze in einer bitweisen Weise; kopiert keine Transformation wird auf allen ausgeführt. Für P/Invoke, dies gilt nur, wenn alle Parameter einfach sind blitfähige Typen. Andernfalls führt P/Invoke sehr robuste Schritte aus, um jede Verwaltete Parameter in einen geeigneten systemeigenen Typ zu konvertieren und umgekehrt verwendet werden, wenn die Argumente als "Out", gekennzeichnet sind oder "in, out".

C++-Interop verwendet also die schnellste Methode des Marshalling von Daten aus, während die P/Invoke die zuverlässigste Methode verwendet. Dies bedeutet, dass C++-Interop (in einer Weise, die typisch für C++) eine optimale Leistung in der Standardeinstellung bietet, und der Programmierer verantwortlich ist für die Adressierung von Fällen, in dem dieses Verhalten nicht sicheren oder geeigneten ist.

C++-Interop erfordert deshalb, dass Daten-Marshalling explizit angegeben werden muss, aber der Vorteil, dass der Programmierer ist kostenlos, um zu entscheiden, was angemessen ist, aufgrund der Art der Daten ist, und es ist, verwendet werden soll. Darüber hinaus auch das Verhalten der P/Invoke Marshalling von Daten zur geändert werden kann zu einem gewissen Grad angepasst, ermöglicht die C++-Interop, Daten-Marshalling, um pro Aufrufe-angepasst werden. Dies ist nicht möglich, mit P/Invoke.

Weitere Informationen zu C++-Interop, finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
