---
title: Verteilen von Komponenten mithilfe von Mergemodulen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f4dda75533b2c16405485f8bb2f3ab9982033ce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425560"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Neuverteilen von Komponenten mit Mergemodulen

Visual Studio umfasst [Mergemodule](/windows/desktop/Msi/about-merge-modules) für jede Visual C++-Komponente, die dafür lizenziert ist, mit einer Anwendung verteilt zu werden. Wenn ein Mergemodul in einer Windows Installer-Setupdatei kompiliert wird, aktiviert es die Bereitstellung von spezifischen DLLs für Computer, die eine spezifische Plattform haben. Geben Sie in der Setupdatei an, dass die Mergemodule erforderliche Komponenten für Ihre Anwendung sind. Wenn Visual Studio installiert wird, werden die Mergemodule unter \Programme\Gemeinsame Dateien\Mergemodule\\\ installiert. (Debugversionen von Visual C++-DLLs dürfen nicht verteilt werden.) Weitere Informationen und einen Link zu einer Liste von Mergemodulen, die für die Neuverteilung lizenziert sind, finden Sie unter [Redistributing Visual C++ Files (Verteilen von Visual C++-Dateien)](../ide/redistributing-visual-cpp-files.md).

Mithilfe der Mergemodule können Sie die Installation von verteilbaren Visual C++-DLLs in den Ordner %SYSTEMROOT%\system32\ aktivieren. (Visual Studio verwendet dieses Verfahren.) Die Installation in diesen Ordner ist jedoch nur erfolgreich, wenn der installierende Benutzer über Administratorrechte verfügt.

Wir empfehlen, dass Sie Mergemodule nicht verwenden, außer wenn Sie Ihre Anwendung nicht bedienen müssen und Sie keine Abhängigkeiten von mehr als einer Version der DLLs haben. Mergemodule für unterschiedliche Versionen derselben DLL können nicht in einen Installer einbezogen werden, und Mergemodule erschweren es, dass DLLs unabhängig von Ihrer Anwendung bedient werden. Stattdessen wird empfohlen, dass Sie ein Visual C++ Redistributable Package installieren.

## <a name="see-also"></a>Siehe auch

[Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)