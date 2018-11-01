---
title: Vorkompilierte Headerdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d93486d8df8cdb8bc253a0e71037f4e2ddf9e128
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890478"
---
# <a name="precompiled-header-files"></a>Vorkompilierte Headerdateien

Diese Dateien werden dazu verwendet, die vorkompilierte Headerdatei *Projektname.pch*und die vorkompilierte Typendatei „StdAfx.obj“ zu erstellen.

Diese Dateien befinden sich im Verzeichnis *Projektname* . Im Projektmappen-Explorer befindet sich „Stdafx.h“ im Ordner „Headerdateien“ und „Stdafx.cpp“ im Ordner „Quelldateien“.

|Dateiname|Beschreibung |
|---------------|-----------------|
|stdafx.h|Eine Includedatei für systemspezifische Standardincludedateien und projektspezifische Includedateien, die häufig verwendet, aber nur selten geändert werden.<br /><br /> Sie sollten die _AFX_NO_XXX-Makros in stdafx.h weder definieren noch deren Definition aufheben.|
|stdafx.cpp|Enthält die Präprozessordirektive `#include "stdafx.h"` und fügt Includedateien für vorkompilierte Typen hinzu. Vorkompilierte Dateien eines beliebigen Typs, einschließlich Headerdateien, sorgen für kürzere Kompilierungszeiten, indem sie die Kompilierung auf die Dateien beschränken, die dies erfordern. Sobald Ihr Projekt erstmalig erstellt wurde, werden Sie feststellen, dass die Buildzeiten nachfolgender Builds aufgrund der vorkompilierten Headerdateien sehr viel kürzer sind.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)