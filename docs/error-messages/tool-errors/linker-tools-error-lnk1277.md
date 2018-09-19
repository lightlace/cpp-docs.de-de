---
title: Linkertoolfehler Lnk1277 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 542c48bd23b3f84ab301404987c77d964f51823e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082518"
---
# <a name="linker-tools-error-lnk1277"></a>Linkertoolfehler LNK1277

Objektdatensatz wurde in Pgd (Dateiname) nicht gefunden.

Bei Verwendung [PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), der Pfad einer Eingabe lib, Def oder OBJ-Dateien aus dem Pfad, auf denen sie während der/LTCG: PGINSTRUMENT gefunden wurden, verschiedene wurde. Dies kann durch eine Änderung in der LIB-Umgebungsvariablen nach/LTCG: PGINSTRUMENT erläutert werden. Der vollständige Pfad zu den Eingabedateien ist in die PGD-Datei gespeichert.

/ LTCG: PGOPTIMIZE erfordert, dass die Eingaben identisch mit der/LTCG: PGINSTRUMENT-Phase.

Führen Sie eine der folgenden Schritte aus, um diese Warnung zu beheben:

- Führen Sie/LTCG: PGINSTRUMENT, wiederholen Sie alle Testläufe und führen Sie/LTCG: PGOPTIMIZE.

- Ändern Sie die LIB-Umgebungsvariablen, wenn Sie/LTCG: PGINSTRUMENT ausgeführt haben.

Es wird nicht empfohlen, dass Sie mithilfe von/LTCG: PGUPDATE LNK1277 arbeiten.