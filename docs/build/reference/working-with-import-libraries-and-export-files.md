---
title: Arbeiten mit Importbibliotheken und Exportdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28b4b94025c813ea526964ed6395a2e6af1ac0b9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721239"
---
# <a name="working-with-import-libraries-and-export-files"></a>Arbeiten mit Importbibliotheken und Exportdateien

Sie können mit der Option/DEF LIB verwenden, zum Erstellen einer Importbibliothek und einer Exportdatei. LINK-verwendet, die die Exportdatei auf, um ein Programm erstellen, enthält exportiert (in der Regel eine Dynamic Link Library (DLL)), und die Importbibliothek zum Auflösen von Verweisen auf diese Exporte in anderen Programmen verwendet.

Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL-Datei übergeben werden wie bei der Erstellung der Importbibliothek.

In den meisten Fällen müssen Sie keine LIB verwenden, um die Importbibliothek erstellen. Wenn Sie ein Programm (eine ausführbare Datei oder eine DLL-Datei), das Exporte enthält verknüpfen, erstellt die Verknüpfung automatisch eine Importbibliothek, die die Exporte beschreibt. Später, wenn Sie ein Programm, die diese Exporte verweist verknüpfen, geben Sie die Importbibliothek.

Allerdings, wenn eine DLL-Datei mit einem Programm exportiert werden soll, die es auch importiert, müssen, ob direkt oder indirekt LIB können Sie eine Importbibliotheken erstellen. Wenn LIB eine Importbibliothek erstellt wird, wird es auch eine Exportdatei erstellt. Sie müssen die Exportdatei verwenden, wenn Sie eine DLL verknüpfen.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)