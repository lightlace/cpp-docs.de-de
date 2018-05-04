---
title: 'Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca8fd6ef94af290d568f3186747c659b918c0fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Gewusst wie: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil

Profilgesteuerte Optimierung (PGO) eignet sich hervorragend zum Erstellen von optimierte Binärdateien, die basierend auf einem Szenario, das ein Profil erstellt wird. Aber was geschieht, wenn Sie eine Anwendung, die mehrere wichtige, noch unterschiedliche Szenarien haben? Erstellen Sie ein einzelnes Profil, das für die profilgesteuerte Optimierung verwenden, können wie in verschiedenen Szenarien? In Visual Studio den Manager für die profilgesteuerte Optimierung [pgomgr.exe](pgomgr.md), übernimmt diese Aufgabe für Sie.

Die Syntax für das Zusammenführen von Profilen lautet:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

wobei `num` ist eine optionale Gewichtung für die PGC-Dateien hinzugefügt werden, indem Sie diese Zusammenführung verwendet. Gewichtungen werden häufig verwendet, wenn es gibt einige Szenarios wichtiger als andere sind oder es gibt Szenarien, die mehrere Male ausgeführt werden sollen.

> [!NOTE]
> PGO-Manager funktioniert nicht mit veralteten Profildaten. Um eine PGC-Datei in einer PGD-Datei zusammenzuführen, muss die PGC-Datei durch eine ausführbare Datei generiert das durch den Aufruf der gleiche Link erstellt wurde, die die PGD-Datei generiert.

## <a name="examples"></a>Beispiele

In diesem Beispiel fügt der PGO-Manager Datei Datei sechs Mal:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

In diesem Beispiel fügt der PGO-Manager die beiden Dateien Pgcdatei1.pgc und Pgcdatei2.PGC Datei zweimal für jeden PGC-Datei:

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

Wenn der PGO-Manager ohne Argumente PGC-Datei ausgeführt wird, durchsucht das lokale Verzeichnis für alle PGC-Dateien, die über den gleichen Basisnamen wie die PGD-Datei gefolgt von einem Ausrufezeichen (!) und dann eine oder mehrere beliebige Zeichen enthalten. Angenommen, wenn das lokale Verzeichnis Dateien test.pgd, Test! 1.pgc test2.pgc und Test! Hello.pgc, und klicken Sie dann den folgenden Befehl wird aus dem lokalen Verzeichnis ausführen **Pgomgr** führt Test! 1.pgc und Test! Hello.pgc in test.pgd.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)
