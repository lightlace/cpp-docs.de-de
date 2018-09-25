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
ms.openlocfilehash: 8d2e2bab9da3d19347577f0b1d1e8ab2ed6bb0dc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404019"
---
# <a name="precompiled-header-files"></a>Vorkompilierte Headerdateien

Diese Dateien werden dazu verwendet, die vorkompilierte Headerdatei *Projektname.pch*und die vorkompilierte Typendatei „StdAfx.obj“ zu erstellen.

Diese Dateien befinden sich im Verzeichnis *Projektname* . Im Projektmappen-Explorer befindet sich „Stdafx.h“ im Ordner „Headerdateien“ und „Stdafx.cpp“ im Ordner „Quelldateien“.

|Dateiname|Beschreibung |
|---------------|-----------------|
|stdafx.h|Eine Includedatei für systemspezifische Standardincludedateien und projektspezifische Includedateien, die häufig verwendet, aber nur selten geändert werden.<br /><br /> Sie sollten für keines der _AFX_NO_XXX-Makros in „stdafx.h“ dessen Definition ändern. Weitere Informationen hierzu finden Sie im Knowledge Base-Artikel „PRB: Probleme beim Definieren von _AFX_NO_XXX“. Sie finden Knowledge Base-Artikel in MSDN Library oder unter [http://support.microsoft.com](http://%20support.microsoft.com/).|
|stdafx.cpp|Enthält die Präprozessordirektive `#include "stdafx.h"` und fügt Includedateien für vorkompilierte Typen hinzu. Vorkompilierte Dateien eines beliebigen Typs, einschließlich Headerdateien, sorgen für kürzere Kompilierungszeiten, indem sie die Kompilierung auf die Dateien beschränken, die dies erfordern. Sobald Ihr Projekt erstmalig erstellt wurde, werden Sie feststellen, dass die Buildzeiten nachfolgender Builds aufgrund der vorkompilierten Headerdateien sehr viel kürzer sind.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)