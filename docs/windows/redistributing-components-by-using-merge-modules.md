---
title: Neuverteilen von Komponenten mit Mergemodulen
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: 7a110826e21f33986d68dcd46417ec5cbd5171bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362242"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Neuverteilen von Komponenten mit Mergemodulen

Visual Studio umfasst [Mergemodule](/windows/desktop/Msi/about-merge-modules) für jede Visual C++-Komponente, die dafür lizenziert ist, mit einer Anwendung verteilt zu werden. Wenn ein Mergemodul in einer Windows Installer-Setupdatei kompiliert wird, aktiviert es die Bereitstellung von spezifischen DLLs für Computer, die eine spezifische Plattform haben. Geben Sie in der Setupdatei an, dass die Mergemodule erforderliche Komponenten für Ihre Anwendung sind. Wenn Visual Studio installiert wird, werden die Mergemodule unter \Programme\Gemeinsame Dateien\Mergemodule\\\ installiert. (Debugversionen von Visual C++-DLLs dürfen nicht verteilt werden.) Weitere Informationen und einen Link zu einer Liste von Mergemodulen, die für die Neuverteilung lizenziert sind, finden Sie unter [Redistributing Visual C++ Files (Verteilen von Visual C++-Dateien)](redistributing-visual-cpp-files.md).

Mithilfe der Mergemodule können Sie die Installation von verteilbaren Visual C++-DLLs in den Ordner %SYSTEMROOT%\system32\ aktivieren. (Visual Studio verwendet dieses Verfahren.) Die Installation in diesen Ordner ist jedoch nur erfolgreich, wenn der installierende Benutzer über Administratorrechte verfügt.

Wir empfehlen, dass Sie Mergemodule nicht verwenden, außer wenn Sie Ihre Anwendung nicht bedienen müssen und Sie keine Abhängigkeiten von mehr als einer Version der DLLs haben. Mergemodule für unterschiedliche Versionen derselben DLL können nicht in einen Installer einbezogen werden, und Mergemodule erschweren es, dass DLLs unabhängig von Ihrer Anwendung bedient werden. Stattdessen wird empfohlen, dass Sie ein Visual C++ Redistributable Package installieren.

## <a name="see-also"></a>Siehe auch

[Verteilen von Visual C++-Dateien](redistributing-visual-cpp-files.md)
