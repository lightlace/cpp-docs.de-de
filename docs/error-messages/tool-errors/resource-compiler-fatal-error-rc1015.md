---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1015 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0456845152fb2879d2f58c9c40af2562c7207535
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890243"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Ressourcencompiler: Schwerwiegender Fehler RC1015

Includedatei 'Dateiname' kann nicht geöffnet werden

Die angegebenen Include-Datei ist nicht vorhanden, konnte nicht geöffnet werden oder wurde nicht gefunden.

Stellen Sie sicher, dass die Umgebungseinstellungen gültig sind und der richtige Pfad für die Datei angegeben wurde. Stellen Sie sicher, dass genügend Dateihandles Ressourcencompiler zur Verfügung stehen. Ist die Datei auf einem Netzlaufwerk, stellen Sie sicher, dass Sie über Berechtigungen zum Öffnen der Datei verfügen.

RC1015 kann auch auftreten, wenn die Include-Datei vorhanden, in einem Verzeichnis ist als zusätzliches Includeverzeichnis in den Konfigurationseigenschaften -> Ressourcen angegeben -> Eigenschaftenseite "Allgemein"; Geben Sie den vollständigen Pfad zur Include-Datei.
