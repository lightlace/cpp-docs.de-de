---
title: Vorkompilierte Headerdateien
ms.date: 11/04/2016
f1_keywords:
- stdafx.h
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
ms.openlocfilehash: c9df203aac7d43c4c16850dd617639a85234917b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740884"
---
# <a name="precompiled-header-files"></a>Vorkompilierte Headerdateien

Diese Dateien werden dazu verwendet, die vorkompilierte Headerdatei *Projektname.pch*und die vorkompilierte Typendatei „StdAfx.obj“ zu erstellen.

Diese Dateien befinden sich im Verzeichnis *Projektname* . Im Projektmappen-Explorer befindet sich „Stdafx.h“ im Ordner „Headerdateien“ und „Stdafx.cpp“ im Ordner „Quelldateien“.

|Dateiname|Beschreibung|
|---------------|-----------------|
|stdafx.h|Eine Includedatei für systemspezifische Standardincludedateien und projektspezifische Includedateien, die häufig verwendet, aber nur selten geändert werden.<br /><br /> Sie sollten die _AFX_NO_XXX-Makros in stdafx.h weder definieren noch deren Definition aufheben.|
|stdafx.cpp|Enthält die Präprozessordirektive `#include "stdafx.h"` und fügt Includedateien für vorkompilierte Typen hinzu. Vorkompilierte Dateien eines beliebigen Typs, einschließlich Headerdateien, sorgen für kürzere Kompilierungszeiten, indem sie die Kompilierung auf die Dateien beschränken, die dies erfordern. Sobald Ihr Projekt erstmalig erstellt wurde, werden Sie feststellen, dass die Buildzeiten nachfolgender Builds aufgrund der vorkompilierten Headerdateien sehr viel kürzer sind.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)
