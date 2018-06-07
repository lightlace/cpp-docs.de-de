---
title: Fehler LNK1318 der Linkertools | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1318
dev_langs:
- C++
helpviewer_keywords:
- LNK1318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364c819c6ec2bf6e1195011eced6e6ad1699877b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570699"
---
# <a name="linker-tools-error-lnk1318"></a>Linker-Tools Fehler LNK1318

> Unerwarteter Fehler beim PDB; *dazu führen, dass* "*Details*"

Der Linker hat einen unerwarteten Fehler beim Öffnen, lesen oder Schreiben in eine PDB-Datei gefunden.

Diese Fehlermeldung ist ungewöhnlich, dass Probleme in PDB-Dateien erstellt. Die *dazu führen, dass* und *Details* verfügbaren Informationen an den Linker darstellen, wenn der Fehler aufgetreten ist. Dies möglicherweise nicht sehr hilfreich sein, wie häufige Fehler beim Umgang mit PDB-Dateien sind separate, ausführlichere Fehlermeldungen.

Da die Quelle des Fehlers ungewöhnlich ist, wird nur generische Ratschläge zur Behebung dieses Problems:

- Führen Sie einen Bereinigungsvorgang in Ihre Buildverzeichnisse, und führen Sie einen vollständigen Build der Projektmappe.

- Den Computer neu, oder überprüfen verirrte oder nicht reagierende mspdbsrv.exe Prozesse, und im Task-Manager zu beenden.

- Deaktivieren Sie antivirus-Überprüfungen in Ihrem Projekt Verzeichnissen aus.

- Verwenden der [/ZF](../../build/reference/zf.md) Compileroption Wenn [/MP](../../build/reference/mp-build-with-multiple-processes.md) mit MSBuild oder eine andere parallele Buildprozess.

- Versuchen Sie das Erstellen mit dem gehosteten 64-Bit-Toolset.

- Verknüpfen, um parallele Link Probleme zu minimieren, bei Bedarf zu serialisieren. Dieser Fehler kann verursacht werden, wenn mspdbsrv.exe, indem eine Instanz des Links gestartet wird, und heruntergefahren wird, bevor eine andere Instanz von Link erfolgt verwenden. Der Nachteil dieser Korrektur ist, dass Ihr Projekt wird erstellt erheblich länger dauern können.