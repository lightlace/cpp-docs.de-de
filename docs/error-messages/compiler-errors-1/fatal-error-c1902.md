---
title: Schwerwiegender Fehler C1902 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5a443b5f80eabe9691cf8ff5220bb9b66da51e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052561"
---
# <a name="fatal-error-c1902"></a>Schwerwiegender Fehler C1902

Programm Datenbank-Manager-Konflikt; Überprüfen Sie die installation

Erstellt eine Programmdatenbankdatei (.pdb) wurde mit einer neueren Version von Mspdb*XXX*DLL-Datei als die der Compiler auf Ihrem System gefunden. Dieser Fehler in der Regel gibt an, dass mspdbsrv.exe mspdbcore.dll fehlen oder weisen verschiedene Versionen als Mspdb*XXX*DLL-Datei. (Die *XXX* Platzhalter in der Mspdb*XXX*DLL-Datei ändert sich mit jeder Produktversion. Beispielsweise wird in Visual Studio 2015 ist der Dateiname mspdb140.dll.)

Stellen Sie sicher übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und Mspdb*XXX*DLL-Datei auf Ihrem System installiert sind. Stellen Sie sicher, dass nicht übereinstimmende Versionen nicht in das Verzeichnis kopiert wurden, die der Compiler und Link-Tools für Ihre Zielplattform enthält. Z. B. Sie möglicherweise haben die Dateien kopiert, damit Sie das Tool Compiler oder einem Link, über die Eingabeaufforderung festlegen, ohne aufgerufen werden konnte die **Pfad** Umgebungsvariable entsprechend.