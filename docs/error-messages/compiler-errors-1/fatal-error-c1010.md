---
title: Schwerwiegender Fehler C1010
ms.date: 11/04/2016
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 6974f0d82653203973be50b5ea709bd9487a215f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363972"
---
# <a name="fatal-error-c1010"></a>Schwerwiegender Fehler C1010

Unerwartetes Dateiende während der Suche nach dem vorkompilierten Header. Haben Sie vergessen, hinzufügen ' #include "Quellcode?

Eine Includedatei mit angegebenen ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) ist in der Quelldatei nicht aufgeführt.  Diese Option ist standardmäßig aktiviert, in den meisten Typen von Visual C++-Projekt, und "stdafx.h" ist der Standardwert dieser Option angegebenen Includedatei.

Verwenden Sie in der Visual Studio-Umgebung eine der folgenden Methoden zum Beheben dieses Fehlers ein:

- Wenn Sie in Ihrem Projekt keine vorkompilierte Header verwenden, legen Sie die **vorkompilierten Header erstellen/verwenden** Eigenschaft Quelldateien **vorkompilierte Header nicht verwenden**. Um diese Compileroption festlegen möchten, gehen Sie folgendermaßen vor:

   1. Klicken Sie im Bereich Projektmappen-Explorer des Projekts mit der rechten Maustaste in des Namens des Projekts, und klicken Sie dann auf **Eigenschaften**.

   1. Klicken Sie im linken Bereich auf die **C/C++-** Ordner.

   1. Klicken Sie auf die **vorkompilierte Header** Knoten.

   1. Klicken Sie im rechten Bereich auf **vorkompilierten Header erstellen/verwenden**, und klicken Sie dann auf **vorkompilierte Header nicht verwenden**.

- Stellen Sie sicher, dass Sie nicht versehentlich gelöscht, umbenannt oder entfernt Header-Datei (standardmäßig "stdafx.h") aus dem aktuellen Projekt. Diese Datei muss vor jedem anderen Code in den Quellcodedateien mit einzuschließenden **#include "stdafx.h"**. (Diese Headerdatei wird angegeben, als **PCH durch Datei erstellen/verwenden** Projekteigenschaft)