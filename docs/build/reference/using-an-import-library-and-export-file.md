---
title: Verwenden einer Importbibliothek und einer Exportdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77157ae9404e1d64aec34c897af7564511f275f8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717239"
---
# <a name="using-an-import-library-and-export-file"></a>Verwenden einer Importbibliothek und einer Exportdatei

Wenn ein Programm (eine ausführbare Datei oder eine DLL-Datei) exportiert, in ein anderes Programm, dem es auch importiert, oder wenn mehr als zwei Programme Exporte und voneinander zu importieren, müssen die Befehle zum Verknüpfen dieser Programme zirkuläre Exporte berücksichtigen.

Wenn von einem anderen Programm, verknüpfen ein Programm, das verwendet exportiert werden, müssen Sie in einer Situation ohne zirkuläre Exporte die Importbibliothek für das ausführende Programm angeben. Die Importbibliothek für das ausführende Programm wird erstellt, wenn Sie das ausführende Programm verknüpfen. Aus diesem Grund müssen Sie das ausführende Programm vor dem Importieren von Programm verknüpfen. Z. B. wenn TWO.dll aus ONE.dll importiert werden soll, müssen Sie zunächst ONE.dll verknüpfen und die Importbibliothek ONE.lib abrufen. Anschließend geben Sie beim Verknüpfen von TWO.dll ONE.lib. Wenn der Linker TWO.dll erstellt wird, wird auch die Importbibliothek TWO.lib erstellt. Verwenden Sie TWO.lib, beim Verknüpfen von Programmen, die aus TWO.dll importieren.

In einer Exportsituation zirkuläre ist es jedoch nicht möglich, alle voneinander abhängigen Programme mit Importbibliotheken andere Programme zu verknüpfen. Im Beispiel besprochene TWO.dll exportiert ebenfalls um ONE.dll, die Importbibliothek für TWO.dll nicht vorhanden, aber wenn ONE.dll verknüpft ist. Wenn zirkuläre Exporte vorhanden sind, müssen Sie den LIB verwenden, erstellen eine Importbibliothek und exportieren die Datei für eines der Programme.

Wählen Sie zunächst eines der Programme zum Ausführen von LIB. Klicken Sie in der LIB-Befehl aus, alle Objekte und Bibliotheken für das Programm, und geben Sie Sie/DEF an Wenn das Programm eine DEF-Datei "oder" / Export-Spezifikationen verwendet, geben Sie diese ebenfalls.

Nachdem Sie die Importbibliothek (.lib) und die Exportdatei (.exp) für das Programm erstellen, verwenden Sie die Importbibliothek das andere Programm oder Programme verknüpfen. LINK erstellt eine Importbibliothek für jedes ausführende Programm aus, den sie erstellt. Wenn das Ausführen von LIB für die Objekte und Exporte für ONE.dll erstellen Sie z. B. ONE.lib und ONE.exp. Sie können jetzt ONE.lib verwenden, beim Verknüpfen von TWO.dll. Dieser Schritt wird auch die Importbibliothek TWO.lib erstellt.

Verknüpfen Sie schließlich die Anwendung, die, der Sie bereits mitgebracht haben. Geben Sie im LINK-Befehl die Objekte und Bibliotheken für die Anwendung, die EXP-Datei, die von LIB für das Programm, und die Importbibliothek erstellt oder Bibliotheken für die Exporte, die von der Anwendung verwendet. Zum Fortsetzen des Vorgangs des Beispiels enthält die LINK-Befehl für ONE.dll ONE.exp und TWO.lib als auch die Objekte und Bibliotheken, die in One.dll enthalten sind. Geben Sie nicht die DEF-Datei oder der/Export-Spezifikationen im LINK-Befehl; Diese sind nicht erforderlich, da die Exportdefinitionen in die EXP-Datei enthalten sind. Wenn Sie eine Verknüpfung über eine .exp-Datei, wird LINK erstellt eine Importbibliothek nicht, da angenommen wird, dass eine beim Erstellen die EXP-Datei erstellt wurde.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)