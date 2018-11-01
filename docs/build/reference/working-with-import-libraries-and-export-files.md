---
title: Arbeiten mit Importbibliotheken und Exportdateien
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: 71162d896ee76d99f5d47dfa670b62d456243837
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445681"
---
# <a name="working-with-import-libraries-and-export-files"></a>Arbeiten mit Importbibliotheken und Exportdateien

Sie können mit der Option/DEF LIB verwenden, zum Erstellen einer Importbibliothek und einer Exportdatei. LINK-verwendet, die die Exportdatei auf, um ein Programm erstellen, enthält exportiert (in der Regel eine Dynamic Link Library (DLL)), und die Importbibliothek zum Auflösen von Verweisen auf diese Exporte in anderen Programmen verwendet.

Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL-Datei übergeben werden wie bei der Erstellung der Importbibliothek.

In den meisten Fällen müssen Sie keine LIB verwenden, um die Importbibliothek erstellen. Wenn Sie ein Programm (eine ausführbare Datei oder eine DLL-Datei), das Exporte enthält verknüpfen, erstellt die Verknüpfung automatisch eine Importbibliothek, die die Exporte beschreibt. Später, wenn Sie ein Programm, die diese Exporte verweist verknüpfen, geben Sie die Importbibliothek.

Allerdings, wenn eine DLL-Datei mit einem Programm exportiert werden soll, die es auch importiert, müssen, ob direkt oder indirekt LIB können Sie eine Importbibliotheken erstellen. Wenn LIB eine Importbibliothek erstellt wird, wird es auch eine Exportdatei erstellt. Sie müssen die Exportdatei verwenden, wenn Sie eine DLL verknüpfen.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)