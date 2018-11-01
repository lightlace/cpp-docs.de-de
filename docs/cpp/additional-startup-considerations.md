---
title: Zusätzliche Überlegungen zum Starten
ms.date: 11/04/2016
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
ms.openlocfilehash: 16e48f2e4f7544d28a1bea00e1fdf2d1cff397b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605576"
---
# <a name="additional-startup-considerations"></a>Zusätzliche Überlegungen zum Starten

In C++ können Objektkonstruktion und -zerstörung das Ausführen von Benutzercode beinhalten. Daher ist es wichtig zu verstehen, welche Initialisierungen vor dem Eintritt in auftreten `main` und welche Destruktoren aufgerufen werden, nach dem Verlassen von `main`. (Ausführliche Informationen zur Erstellung und Zerstörung von Objekten finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md) und [Destruktoren](../cpp/destructors-cpp.md).)

Die folgenden Initialisierungen direkt vor dem Eintritt in `main`:

- Standardinitialisierung von statischen Daten auf Null. Alle statischen Daten ohne explizite Initialisierer werden vor dem Ausführen eines beliebigen anderen Codes auf Null gesetzt, einschließlich der Laufzeitinitialisierung. Statische Datenmember müssen noch explizit definiert werden.

- Initialisierung eines globalen statischen Objekts in einer Übersetzungseinheit. Dies kann auftreten, entweder vor dem Eintritt in `main` oder vor der ersten Verwendung einer Funktion oder eines Objekts in der Übersetzungseinheit des Objekts.

**Microsoft-spezifisch**

In Microsoft C++ werden globale statische Objekte vor dem Eintritt in initialisiert `main`.

**Ende Microsoft-spezifisch**

Globale statische Objekte, die wechselseitig voneinander abhängig sind, sich jedoch in unterschiedlichen Übersetzungseinheiten befinden, können möglicherweise ein falsches Verhalten verursachen.

## <a name="see-also"></a>Siehe auch

[Starten und Beenden](../cpp/startup-and-termination-cpp.md)