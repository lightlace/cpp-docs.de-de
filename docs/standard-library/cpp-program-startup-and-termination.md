---
title: Starten und Beenden eines C++-Programms
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
ms.openlocfilehash: e59e8852172a998e4bf4f42f9f919dc29c2ded85
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450650"
---
# <a name="c-program-startup-and-termination"></a>Starten und Beenden eines C++-Programms

Ein C++-Programm führt beim Programmstart und bei Beendigung des Programms die gleichen Vorgänge wie ein C-Programm durch und noch einige weitere, die nachfolgend beschrieben werden.

Bevor die Zielumgebung die Funktion `main` aufruft, und nachdem sie alle anfänglichen Konstantenwerte gespeichert hat, die Sie in allen Objekten mit statischer Dauer festgelegt haben, führt das Programm alle übrigen Konstruktoren für solche statischen Objekte aus. Die Reihenfolge der Ausführung wird zwischen den Übersetzungseinheiten nicht angegeben. Sie können dennoch davon ausgeben, dass einige [iostreams](../standard-library/iostreams-conventions.md)-Objekte ordnungsgemäß für die Verwendung durch diese statischen Konstruktoren initialisiert werden. Zu diesen Steuerungtextstreams zählen:

- [cin](../standard-library/iostream.md#cin) – für die Standardeingabe

- [cin](../standard-library/iostream.md#cout) – für die Standardausgabe

- [cerr](../standard-library/iostream.md#cerr) – für die ungepufferte Standardfehlerausgabe

- [clog](../standard-library/iostream.md#clog) – für die gepufferte Standardfehlerausgabe

Sie können diese Objekte auch innerhalb der Destruktoren verwenden, die für statische Objekte während der Beendigung des Programms aufgerufen werden.

Ähnlich wie bei C ruft die Rückgabe von `main` oder der Aufruf von `exit` alle Funktionen auf, die bei `atexit` in umgekehrter Reihenfolge der Registrierung registriert wurden. Eine von einer solchen registrierten Funktion ausgelöste Ausnahme ruft `terminate` auf.

## <a name="see-also"></a>Siehe auch

[Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
