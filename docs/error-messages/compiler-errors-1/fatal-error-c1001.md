---
title: Schwerwiegender Fehler C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: beb382b9c6ccf80d01f5a0262832e7fb7e1ea0a4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770927"
---
# <a name="fatal-error-c1001"></a>Schwerwiegender Fehler C1001

> Interner Compilerfehler ERROR(compiler file *file*, line *number*)

Der Compiler kann nicht die korrekten Code für ein Konstrukt, häufig aufgrund der Kombination aus einem bestimmten Ausdruck und eine Optimierungsoption oder ein Problem bei der Analyse generieren. Verfügt die Compilerdatei aufgelisteten eine utc oder der C2-OData-Pfadsegment, ist es wahrscheinlich ein Fehler für die Optimierung. Wenn die Datei ein Pfadsegment Cxxfe oder c1xx hat oder msc1.cpp ist, ist es wahrscheinlich ein Fehler im Parser. Wenn die Datei, die mit dem Namen cl.exe ist, ist keine weiteren Informationen verfügbar.

Sie können häufig eine Optimierungsproblem beheben, durch das Entfernen von ein oder mehrere Optimierungsoptionen. Um zu bestimmen, welche Option fehlerhaft ist, entfernen Sie Optionen eine Neukompilierung und bis die Fehlermeldung angezeigt verschwindet. Die Optionen, die am häufigsten verantwortlich sind [/Og (globale Optimierungen)](../../build/reference/og-global-optimizations.md) und [/Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md). Wenn Sie bestimmen, welche Optimierungsoption verantwortlich ist, können Sie es deaktivieren, um die Funktion, in dem der Fehler tritt auf, mit, der [optimieren](../../preprocessor/optimize.md) Pragma und weiterhin die Option für den Rest des Moduls verwenden. Weitere Informationen zu den Optimierungsoptionen, finden Sie unter [bewährten Methoden zur Datenbankoptimierung](../../build/optimization-best-practices.md).

Wenn Optimierungen nicht für den Fehler verantwortlich sind, versuchen Sie es Umschreiben der Zeile, in dem der Fehler gemeldet wird, oder mehrere Zeilen von Code im Zusammenhang mit dieser Zeile. Den Code die Möglichkeit erhalten nach dem Präprozessorlauf der Compiler erkennt können Sie die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Option.

Weitere Informationen wie die Quelle des Fehlers zu isolieren und einen internen Compilerfehler an Microsoft zu melden, finden Sie unter [wie Melden eines Problems mit dem Visual C++-Toolset](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).