---
title: Schwerwiegender Fehler C1010
ms.date: 08/19/2019
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 35b0f60f7eb3be887598e7ffaf3e3eae74aefcff
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630786"
---
# <a name="fatal-error-c1010"></a>Schwerwiegender Fehler C1010

Unerwartetes Dateiende während der Suche nach dem vorkompilierten Header. Haben Sie vergessen, der Quelle "#include Name" hinzuzufügen?

Eine Includedatei, die mit [/Yu](../../build/reference/yu-use-precompiled-header-file.md) angegeben wird, ist nicht in der Quelldatei aufgeführt.  Diese Option ist in den meisten Visual Studio C++ -Projekttypen standardmäßig aktiviert, und *PCH. h* (*stdafx. h* in Visual Studio 2017 und früher) ist die standardmäßige Include-Datei, die von dieser Option angegeben wird.

Verwenden Sie in der Visual Studio-Umgebung eine der folgenden Methoden, um diesen Fehler zu beheben:

- Wenn Sie im Projekt keine vorkompilierten Header verwenden, legen Sie die Eigenschaft **vorkompilierten Header erstellen/verwenden** von Quelldateien auf **keine Verwendung vorkompilierter Header**fest. Führen Sie die folgenden Schritte aus, um diese Compileroption festzulegen:

   1. Klicken Sie im Projektmappen-Explorer Bereich des Projekts mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.

   1. Klicken Sie im linken Bereich auf den Ordner **CC++ /** .

   1. Klicken Sie auf den Knoten **Vorkompilierte Header** .

   1. Klicken Sie im rechten Bereich auf **vorkompilierten Header erstellen/verwenden**, und klicken Sie dann auf **Vorkompilierte Header nicht verwenden**.

- Stellen Sie sicher, dass Sie die Header Datei (standardmäßig "stdafx. h") aus dem aktuellen Projekt nicht versehentlich gelöscht, umbenannt oder entfernt haben. Diese Datei muss auch vor jedem anderen Code in ihren Quelldateien mit **#include "stdafx. h"** eingeschlossen werden. (Diese Header Datei wird als Eigenschaft " **PCH über Datei Projekt erstellen/verwenden** " angegeben)