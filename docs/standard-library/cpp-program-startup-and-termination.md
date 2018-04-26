---
title: Starten und Beenden eines C++-Programms | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eec5c6d72152f2aaea8d77df7ca65bf5f5f5565b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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

[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
