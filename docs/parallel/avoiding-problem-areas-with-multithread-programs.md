---
title: Vermeiden von Problembereichen bei Multithreadprogrammen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4da775a8b068db830d161936a1ca93890d54a1f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425403"
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Vermeiden von Problembereichen bei Multithreadprogrammen

Es gibt mehrere Probleme, die auftreten können, erstellen, verknüpfen oder eine C-Multithreadprogramm ausführen. Einige der häufigsten Probleme werden in der folgenden Tabelle beschrieben. (Eine vergleichbare Erläuterung von MFC-Sicht, finden Sie unter [Multithreading: Tipps für die Programmierung](multithreading-programming-tips.md).)

|Problem|Mögliche Ursache|
|-------------|--------------------|
|Sie erhalten ein Meldungsfeld anzeigt, dass das Programm eine Schutz-Verletzung verursacht hat.|Verstöße gegen den Zugriffsschutz zu viele Win32-Programmierung-Fehlern führen. Eine häufige Ursache für den Schutz von Verletzungen ist die indirekte Zuweisung zu null-Zeiger. Da dies in Ihrem Programm auf Speicher zugreift, die nicht zu der er gehört führt, wird ein Schutz gegen ausgegeben.<br /><br /> Eine einfache Möglichkeit, um die Ursache eines Verstoßes Schutz zu erkennen ist, das Programm mit Debuginformationen kompiliert, und führen Sie es über den Debugger in Visual C++-Umgebung. Wenn der Schutzverletzungsfehler auftritt, Windows überträgt die Steuerung an den Debugger, und der Cursor befindet sich in der Zeile, die das Problem verursacht hat.|
|Das Programm generiert zahlreiche Fehler in der Kompilierung und Verknüpfung.|Sie können viele Probleme vermeiden, durch die Warnstufe des Compilers auf die höchsten Werte festlegen und die gewonnenen der Warnmeldungen an. Mit der Ebene 3 oder die Optionen für Warnung der Stufe 4, können Sie unbeabsichtigte datenkonvertierungen, fehlende Funktionsprototypen und Verwendung von nicht-ANSI-Funktionen erkennen.|

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)