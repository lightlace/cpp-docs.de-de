---
title: 'Gewusst wie: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil'
ms.date: 03/14/2018
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
ms.openlocfilehash: 04730524fa756b0c6f1e505f3610609bdec6262a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476543"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Gewusst wie: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil

Profilgesteuerte Optimierung (PGO) ist ein hervorragendes Tool zum Erstellen von optimierter Binärdateien, die basierend auf einem Szenario, das ein Profil erstellt wird. Aber was geschieht, wenn eine Anwendung, die mehrere wichtige, doch unterschiedliche Szenarien hat? Wie erstellen Sie ein einzelnes Profil an, dem Profilgesteuerte Optimierung verwenden, können aus verschiedenen Szenarien? In Visual Studio der PGO-Manager [pgomgr.exe](pgomgr.md), übernimmt diese Aufgabe für Sie.

Die Syntax für das Zusammenführen von Profilen lautet:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

wo `num` ist eine optionale Gewichtung, die für die PGC-Dateien hinzugefügt, indem diese Zusammenführung verwendet. Gewichtungen werden häufig verwendet, wenn es gibt einige Szenarien, die wichtiger als andere sind oder es gibt Szenarien, in denen mehrere Male ausgeführt werden sollen.

> [!NOTE]
> Der PGO-Manager funktioniert nicht mit veralteten Profildaten. Um eine PGC-Datei in eine PGD-Datei zu importieren, muss die .pgc-Datei durch eine ausführbare Datei generiert werden, die werden die gleichen Link erstellt wurde, die die PGD-Datei generiert.

## <a name="examples"></a>Beispiele

In diesem Beispiel fügt der PGO-Manager Datei Datei bis zu sechs Mal:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

In diesem Beispiel fügt der PGO-Manager die beiden Dateien Pgcdatei1.pgc und Pgcdatei2.PGC Datei zweimal für jeden PGC-Datei:

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

Wenn es sich bei der PGO-Manager, die ohne Argumente PGC-Datei ausgeführt wird, durchsucht sie das lokale Verzeichnis für alle PGC-Dateien, die den gleichen Basisnamen wie die PGD-Datei gefolgt von einem Ausrufezeichen (!), und klicken Sie dann eine oder mehrere beliebige Zeichen enthalten. Z. B., wenn das lokale Verzeichnis Dateien test.pgd, Test! 1.pgc, test2.pgc und Test! Hello.pgc, und klicken Sie dann der folgende Befehl wird aus dem lokalen Verzeichnis, ausgeführt **"pgomgr"** führt Test! 1.pgc und Test! Hello.pgc in test.pgd.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)
