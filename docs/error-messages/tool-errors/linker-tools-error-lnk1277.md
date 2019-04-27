---
title: Linkertoolfehler LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 137aa15dd9dad4b08d52af55da60a9cdf8b58055
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160548"
---
# <a name="linker-tools-error-lnk1277"></a>Linkertoolfehler LNK1277

Objektdatensatz wurde in Pgd (Dateiname) nicht gefunden.

Bei Verwendung [PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), der Pfad einer Eingabe lib, Def oder OBJ-Dateien aus dem Pfad, auf denen sie während der/LTCG: PGINSTRUMENT gefunden wurden, verschiedene wurde. Dies kann durch eine Änderung in der LIB-Umgebungsvariablen nach/LTCG: PGINSTRUMENT erläutert werden. Der vollständige Pfad zu den Eingabedateien ist in die PGD-Datei gespeichert.

/ LTCG: PGOPTIMIZE erfordert, dass die Eingaben identisch mit der/LTCG: PGINSTRUMENT-Phase.

Führen Sie eine der folgenden Schritte aus, um diese Warnung zu beheben:

- Führen Sie/LTCG: PGINSTRUMENT, wiederholen Sie alle Testläufe und führen Sie/LTCG: PGOPTIMIZE.

- Ändern Sie die LIB-Umgebungsvariablen, wenn Sie/LTCG: PGINSTRUMENT ausgeführt haben.

Es wird nicht empfohlen, dass Sie mithilfe von/LTCG: PGUPDATE LNK1277 arbeiten.