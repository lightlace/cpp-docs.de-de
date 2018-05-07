---
title: Schwerwiegender Fehler C1001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1001
dev_langs:
- C++
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f605dd7e4892c4a8b57e544ed857257be72f020d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1001"></a>Schwerwiegender Fehler C1001

> Interner Compilerfehler ERROR(compiler file *file*, line *number*)  
  
Der Compiler kann nicht die korrekten Code für ein Konstrukt, häufig aufgrund der Kombination aus einem bestimmten Ausdruck und eine Optimierungsoption oder ein Problem bei der Analyse generieren. Verfügt der aufgeführten Compilerdatei ein utc oder der C2-OData-Pfadsegment, ist es wahrscheinlich ein Fehler für die Optimierung. Wenn die Datei ein Pfadsegment Cxxfe oder c1xx hat oder msc1.cpp ist, ist es wahrscheinlich ein Fehler im Parser. Wenn die Datei namens cl.exe ist, ist keine weiteren Informationen verfügbar.  

Sie können oft eine Optimierungsproblem beheben, indem Sie eine oder mehrere Optimierungsoptionen entfernen. Um zu bestimmen, welche Option fehlerhaft ist, entfernen Sie diese Optionen eine zu einem Zeitpunkt Recompile, bis die Fehlermeldung beendet wurde. Die Optionen, die am häufigsten sind [/Og (globale Optimierungen)](../../build/reference/og-global-optimizations.md) und [/Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md). Sobald Sie feststellen, welche Optimierungsoption zuständig ist, können Sie es deaktivieren, um die Funktion, in dem der Fehler tritt auf, mit, der [optimieren](../../preprocessor/optimize.md) Pragma, und fahren Sie mit der Option für den Rest des Moduls verwendet werden. Weitere Informationen zu den Optimierungsoptionen, finden Sie unter [bewährte Vorgehensweisen für die Optimierung](../../build/reference/optimization-best-practices.md).

Wenn Optimierungen nicht für den Fehler verantwortlich sind, versuchen Sie die Zeile, in dem der Fehler gemeldet wird, oder mehrere dieser Zeile umgebenden Codezeilen umschreiben. Um den Code wie der Compiler es nach der vorverarbeitung erkennt angezeigt wird, können Sie die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Option.

Weitere Informationen wie die Quelle des Fehlers zu isolieren und wie einen interner Compilerfehler an Microsoft zu melden, finden Sie unter [zum Melden eines Problems mit der Visual C++-Toolsets](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md).