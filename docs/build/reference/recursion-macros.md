---
title: Rekursionsmakros
description: Beschreibt die Makros, die Sie verwenden, um NMAKE in rekursiven Sitzungen aufzurufen.
ms.date: 11/20/2019
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
no-loc:
- MAKE
- MAKEDIR
- MAKEFLAGS
ms.openlocfilehash: f2bda23cb079e4fd7d12cea3598d33b3625c088d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303155"
---
# <a name="recursion-macros"></a>Rekursionsmakros

Verwenden Sie Rekursions Makros, um NMAKE rekursiv aufzurufen. Rekursive Sitzungen erben Befehlszeilen-und Umgebungsvariablen Makros und Tools. ini-Informationen. Sie erben weder Makefile-definierte Rückschluss Regeln noch `.SUFFIXES` und `.PRECIOUS` Spezifikationen. Es gibt drei Möglichkeiten, Makros an eine rekursive NMAKE-Sitzung zu übergeben: Legen Sie eine Umgebungsvariable mit einem :::no-loc text="SET":::-Befehl vor dem rekursiven Aufrufen fest. Definieren Sie ein Makro im Befehl für den rekursiven-Befehl. Oder definieren Sie ein Makro in "Tools. ini".

|Makro|Definition|
|-----------|----------------|
|**MAKE**|Befehl, der ursprünglich zum Aufrufen von NMAKE verwendet wurde.<br /><br /> Das `$(MAKE)`-Makro gibt den vollständigen Pfad zu NMAKE. exe an.|
|**MAKEDIR**|Aktuelles Verzeichnis, wenn NMAKE aufgerufen wurde.|
|**MAKEFLAGS**|Die derzeit gültigen Optionen. Verwenden Sie als `/$(MAKEFLAGS)`. Die **/F** -Option ist nicht enthalten.|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
